# 5.단위, 배경, 박스모델
## 2) 속성-단위
- px ★
- pt 
- % ★
- em ★
- rem
- vw

단위도 브라우저마다 지원률이 다르다.

https://www.w3schools.com/cssref/css_units.asp

---
## 3) 속성-색상

- 컬러 키워드 
* 참고 : transparent는 투명을 나타내는 키워드 *

- 16 진법    ex.  #RRGGBB

- 16 진법 축약형   ex.  #RGB, 같은 문자가 2번 연속 반복되면 하나로 축약 할 수 있다.

- RGB( )

- RGBA( )

    - RGBA 값은 기존 RGB에서 A값이 추가된 형태.
    - rgb(R, G, B, A)의 형태로 각 변수는(R 적색, G 녹색, B - 청색, A 투명도)의 강도를 정의.
    - A 값은 0 ~ 1 사이의 값을 지정할 수 있으며, 0.5와 같이 소수점으로 표기.
    - 0 → 1은 불투명 → 투명으로 값이 변화한다.

---
## 4) 속성-background
- background-color
    - 기본 값 : transparent
- background-image
    - 기본 값 :  none
- background-repeat
   - repeat: x, y축 으로 모두 반복.
   - repeat-x: x 축 방향으로만 반복.
   - repeat-y: y 축 방향으로만 반복.
   - no-repeat: 이미지를 반복하지 안흔다.

- background-position
    - %
    - px
    - 키워드 :top, left, right, bottom, center 키워드를 사용할 수 있다.
- background-attachment : 화면 스크롤에 따른 배경 이미지의 움직임 여부를 지정하는 속성 (성능상의 이유로 잘 사용되지 않는다.)
    - 기본 값 : scroll
    - scroll
    - local
    - fixed

 - 뷰포트 : 사용자가 시각적으로 볼 수 있는 웹페이지 영역                ex) 컴퓨터나 휴대폰과 같은 장치에 Display 요소가 표현되는 영역

backgroud 축약형
```css
background: [-color] [-image] [-repeat] [-attachment] [-position];
```
실습
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>background</title>
  <style>
    div {
      height: 500px;
      background-color: yellow;
      background-image: url(https://www.w3schools.com/CSSref/img_tree.gif);
      background-repeat: no-repeat;
      background-position: center top;
      /* 축약형 */
      background: yellow url(https://www.w3schools.com/CSSref/img_tree.gif) no-repeat center top;
    }
  </style>
</head>
<body>
    <div> css background 속성 실습 </div>
</body>
</html>
```
https://www.w3schools.com/css/css_background.asp

---
## 6) 속성-border
```css
border: [-width] [-style] [-color];
```
https://www.w3schools.com/css/css_border.asp

---
## 7) 속성-padding
```CSS
padding: [-top] [-right] [-bottom] [-left];
                   0      10px     20px      30px   /* 상, 우, 하, 좌 다름 */
                   0      10px     20px                 /* 좌, 우 같음 */
                   0      10px                              /* 상, 하 같음 & 좌, 우 같음 */
                   0                                            /* 상, 우, 하, 좌 모두 같음 */
```
- `padding : 20px 30px 40px 30px` 일 때, 좌우의 패딩 값이 같을 때 `padding : 20px 30px 40px` 와 같이 함축하여 사용할 수 있습니다.

- `padding : 20px 30px 20px` 일 때, 좌우 패딩과 마찬가지로 상하의 패딩 값이 같을 때 `padding : 20px 30px` 와 같이 함축하여 사용 할 수 있습니다.
- `padding : 20px 20px ( = 20px, 20px, 20px, 20px )`일 때, 상하좌우 패딩 값이 모두 같을 때 `padding : 20px` 와 같이 하나의 값으로 함축하여 사용할 수 있습니다.
* 참고 : CSS에서 0 값에 대해서는 단위를 따로 적지 않습니다.

     0px = 0% = 0em = 0pt...  =>   "  0 "

```css
<style>
    div {
      padding-top: 10px;
      padding-right: 20px;
      padding-bottom: 40px;
      padding-left: 20px;


      /* 축약형 */
      padding: 10px 20px 40px;
    }
</style>
<div> css padding 속성 실습 </div>
```
---
## 8) 속성-margin
### margin: auto
수평 정렬할 때 많이 사용된다.

```css
margin-left: auto;
margin-right: auto;
margin: 0 auto; /*width 값을 필수로 요구한다.*/
```
좌우의 margin이 모두 auto로 적용 되었다면, 브라우저는 요소가 가질수 있는 가로 영역에서 자신의 width를 제외한 나머지 여백에 크기에 대해 균등 분할 하여 적용한다.

### margin collapse(마진 병합)
- 요소의 아래쪽 여백이 다른 요소의 위쪽 여백과 만나는 경우 마진 병합(합쳐지는) 현상
- 여백이 서로 더해지는 것이 아니라 더 큰 margin 값을 가진 여백이 적용된다.
- 좌우 여백은 적용되지 않는다.

마진 병합을 활용하여 첫 번째와 두 번째 컴포넌트의 조합이 다양한 경우 여백을 다르게 사용 할 수 있다.

---
### 9) 속성-margin&padding
|  | + | - | auto | 단위 |
|:-------:|:--:|---|------|----------|
| margin | O  | O | O | px, %.. |
| padding | O | X | X | px, %.. |

### %값의 사용과 기준점
- %는 상하좌우의 방향에 관계없이 모두 요소의 width 값을 기준으로 값이 결정된다.

---
##10) 속성-width

- auto: 브라우저에 의해 자동으로 계산하여 적용합니다. 
    * 요소의 레벨 기본 특성에 따라 다르게 동작합니다.
- length: ex. px, em ...
- percent:  **부모 요소**의 width에 상대적인 크기를 지정. ex) 부모: 300px, 자식: 50% => 자식 : 150px

auto가 아닌 특정한 값을 지정하여 사용하면, 그 크기는 box model 영역에서 margin 영역을 제외한 모든 영역에 대해 영향을 받는다.    

---
## 11) 속성-height

- auto: 브라우저 자동으로 계산하여 적용합니다. 
    * 기본적으로 컨텐츠 영역의 내용만큼 높이를 가집니다.
- length: 고정값으로 지정합니다. (ex. px, em ....)
- percent: 부모 요소의 height에 상대적인 크기를 지정합니다.
     * 단, 부모 요소가 명시적으로 height 값이 있어야 합니다.

부모가 명시적인 높이 값을 가지고 있지 않으면
자식의 높이를 %값으로 지정해줘도 적용되지 않는다.

---

## 생각해보기

### 3) 속성 - 색상
- 강의에서 다룬 종류 외에도 HSL, HWB 등 다양한 방식이 존재.

### 4) 속성 - background
- background-size, background-origin, background-clip, background-blend-mode 등 다른 다양한 속성들도 확인

### 8) 속성 - margin 
- margin은 padding과 달리 음수 값 지정 가능
- margin collapse는 절대 위치나 상대 위치가 주어진 요소들에서는 발생하지 않는다.

### 10) 속성-width
- width는 기본적으로 content 영역의 너비를 지정합니다. box-sizing이라는 속성을 이용하여 padding, border 영역을 기준으로 크기를 가질 수 있도록 변경할 수 있습니다. 
- 부모가 인라인 레벨 요소일 때, 자식(블록 요소)이 width 값에 %를 가지면, 가장 가까운 블록 레벨인 조상의 width를 기준으로 계산됩니다. 만일 최상단까지 블록 레벨 요소가 없으면 body를 기준으로 계산됩니다. 

### 11) 속성-height
- height 또한 box-sizing 속성을 이용하여 기준값을 padding 영역, border 영역으로 바꿀 수 있습니다.