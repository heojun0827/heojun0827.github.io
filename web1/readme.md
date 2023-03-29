# CSS 속성

## CSS 웹 폰트
```css
웹 폰트 : 구글 웹폰트 또는 눈누, 응용 프로그램용 폰트 : 다폰트
    font-family:"1차폰트명",2차폰트명,3차폰트명;}
- 3차 폰트는 기본 폰트를 적용함
- 기본 폰트 : 브라우저에서 기본적으로 제공하는 폰트
    sans-serif(고딕), serif(명조), cursive(궁서), monospace(가로세로비율1:1폰트), fantasy(심볼기호나 디자인폰트)
```

## CSS 크기 관련 속성

### CSS 크기 지정
width : 너비 - 주로 px단위 또는 %단위, auto 등으로 기입 
height : 높이 - 주로 px단위 또는 %단위, auto 등으로 기입 
max-width : 최대너비(이하)
min-width : 최소너비(이상)
max-height : 최대높이
min-height : 최소높이
```css
선택자 { width:100%; height:200px; min-width:200px; max-width:500px; }
선택자2 { width:100vw; height:100vh; }
```

### CSS 여백 지정
margin : 테두리의 바깥여백
```css
선택자 {
    margin:10px;    /* 상/우/하/좌 모두 10px */
    margin:10px 20px;   /* 상/하는 10px 좌우 20px */
    margin:10px 20px 30px 40px; /* 상:10px 우:20px 하:30px 좌:40px */
    /* - 크기가 400px 박스를 좌/우 가운데로 배치 */
    width:400px;    margin:10px auto;
    /*
    - 세부속성 : margin-top, margin-bottom, margin-left, margin-right
        상하좌우를 각 각 개별적으로 지정하는 속성
    - 반드시 통합속성과 세부속성을 같이 쓴다면, 통합속성부터 지정하고, 세부속성을 나중에 지정해야함
    */
}
padding : 테두리의 안쪽여백
```css
선택자 {
    padding:10px;
    padding:10px 20px;
    padding:10px 20px 30px 40px;
}
```
/*
    세부속성 padding-top, padding-bottom, padding-left, padding-right   
*/

### CSS 테두리
- 통합속성
border : 상/우/하/좌의 테두리의 두께, 선모양, 선색 등을 지정
    - border:선두께 선모양 선색;
- 세부속성
border-left : 왼쪽 테두리의 두께, 선모양, 선색 등을 지정
    - border-left:선두께 선모양 선색;
border-right : 오른쪽 테두리의 두께, 선모양, 선색 등을 지정
    - border-right:선두께 선모양 선색;    
border-top : 위쪽 테두리의 두께, 선모양, 선색 등을 지정
    - border-top:선두께 선모양 선색;    
border-bottom : 오른쪽 테두리의 두께, 선모양, 선색 등을 지정
    - border-bottom:선두께 선모양 선색;    
border-width : 상/우/하/좌의 선두께
    - border-width:선두께
    - border-width:상하선두께 좌우선두께
    - border-width:상/우/하/좌의 선두께
border-style : solid, hidden, dashed, dotted, double 등의 선모양 지정
    - border-style:선모양
    - border-style:상하선모양 좌우선모양
    - border-style:상/우/하/좌의 선모양
border-color : 색상16진코드, 컬러명, rgb(), hsl()
- 세세속성
border-[left|right|top|bottom]-[width|style|color]
- 주의사항 : 기입시에는 통합속성 > 세부속성 > 세세속성 순으로 설정해야함

```css
선택자 {
    border:1px solid black;
    border-left:2px dashed red;
    border-style:double;
    border-left-color:green;
}
```

### CSS 박스 크기 계산 방법
box-sizing : content-box | padding-box | border-box
설정하지 않은 경우 content-box이며, 그 밖에 border-box를 사용함
content-box 크기 : 크기+패딩+보더+마진
border-box 크기 : 크기+마진

```css
선택자 { width:200px; height:300px; padding:10px; border:20px solid black; box-sizing:border-box; }
/* 위 박스는 적용크기 기준이 content-box(기본 설정)
    실제폭 : 200+20+40=260
    실제높이 : 300+20+40=360
적용크기 기준이 border-box 기준
    실제폭 : 200=200
    실제높이 : 300=300
*/ 
```

## 배치 속성
### 위치 속성
position : static | relative | absolute | fixed
- 모든 요소는 static이 기본적으로 지정되어 있으며, 위에서 아래로 좌에서 우로 가면서 배치가 된다.
- static : 정적. 기본값으로 별도의 position 속성을 지정하지 않아도 static으로 됨
- relative : 상대적인 위치로 설정시에 필요하며, 위치 좌표를 부모 기준으로 정할 경우 활용
- absolute : 절대적인 위치로 설정시에 필요하며, x좌표 위치와 y좌표 위치를 지정해야 함
    위치값은 auto 또는 px단위와 %단위 등으로 지정함  
    left : 왼쪽 기준으로 부터의 위치
    right : 오른쪽 기준으로 부터의 위치
    top : 위쪽 기준으로 부터의 위치
    bottom : 아래쪽 기준으로 부터의 위치
    ※ x좌표 위치는 left나 right 중에서 하나만 기술하고, y좌표 위치는 top이나 bottom 중에서 하나만 기술해야한다.
- fixed : 화면에 고정된 위치를 설정할 때 필요하며, 스크롤시 fixed된 요소는 스크롤 되지 않고, 화면에 고정되어 있음.
    absolute과 마찬가지로 left/right, top/bottom의 위치를 설정해야 함
- static이나 relative일 경우는 margin으로 떨어진 거리를 지정하고, absolute이나 fixed일 경우는 left/right, top/bottom으로 위치를 설정

### 레이어 속성 
z-index : position이 absolute이거나 fixed일 경우 여러 콘텐츠 박스를 겹칠 경우
어떤 콘텐츠 박스를 앞에 배치할지 층(레이어)를 설정하는 것으로 숫자 정수만으로 지정하며, 숫자 값이 큰 것이 위(앞)에 배치됨.

### 흐름 속성
float : left | right | none
- position이 static이거나 relative일 경우 활용하는 배치 흐름 속성

### 흐름 해제 속성
clear : left | right | both | none
- float 설정된 박스의 흐름을 해제시 사용하며, float이 left로 설정되면, clear도 left로 하면 흐름이 해제되며, left나 right 모두 해제시에는 both를 사용하여 흐름을 해제함

## CSS 가시 속성

### 출력 속성
display : inline | block | inline-block | none
- 모든 태그 요소는 inline 또는 block 이거나 inline-block 요소이다.
- inline : 위/아래 마진이나 패딩 설정이 불가능하고, img나 video 등을 제외한 input, a, span, strong, em 등은 크기지정이 불가능한 인라인 요소이다.
    만약, 블록요소를 인라인 요소로 변경시에 활용
- block : h, p, ul, ol, dl, li, dt, dd, div, section,.. 등은 대부분 크기지정이 가능한 블록요소이다.
    만약, 인라인요소를 블록요소로 변경시에 활용
- inline-block : 한 줄 안에 배치도 가능하고, 위/아래 마진/패딩 적용 가능, 크기 지정한 가시 속성    
- none : 출력을 하지 않을 경우 활용

### 불투명도 속성
opacity :  0~1 의 정수 또는 실수를 사용하여 지정(0:투명, 1:불투명)

### 가시 속성
visibility : visible | hidden
- visible : 보이기
- hidden : 숨기기
- display:none과 달리 hidden을 하면, 안보이는 것 뿐이지 그 자리를 차지하고 있음.

### 넘침 속성
overflow : hidden | scroll | auto | visible
hidden : 흘러 넘치는 부분을 숨김
scroll : 흘러 넘치든 안 넘치든 무조건 스크롤바로 표시
auto : 흘러 넘칠 경우만 스크롤바 표시
visible : 기본값으로 흘러 넘쳐도 그냥 콘텐츠를 모두 표시

