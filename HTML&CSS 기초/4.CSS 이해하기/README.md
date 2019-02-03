# 4.CSS 이해하기
## 2) CSS 문법과 적용
### CSS 구문
```CSS
h1 { color: yellow; font-size:2em; }
```
- 선택자(selector) - "h1"
- 속성(property) - "color"
- 값(value) - "yellow"
- 선언(declaration) - "color: yellow", "font-size: 2em"
- 선언부(declaration block) - "{ color: yellow; font-size:2em; }"
- 규칙(rule set) - "h1 { color: yellow; font-size:2em; }"
<br><br>
### CSS의 속성(Property)과 HTML의 속성(Attribute)
HTML에도 속성이 있고, CSS에도 속성이 있다. 두 가지는 **전혀 다른 것**입니다.

**HTML의 속성은 영어로 attribute**이고, **CSS의 속성은 property**이다. 

둘 다 **한국어로 번역할 때** "속성"이라고 부르기 때문에 잘 구분해야한다.

---
## 5) 선택자 3
### 선택자의 조합
```css
/* 요소와 class의 조합 */
p.bar { ... } 

/* 다중 class */
.foo.bar { ... }

/* id와 class의 조합 */
#foo.bar { ... }
```
- `p.bar` : `p` 태그 이면서 class 속성에 `bar`가 존재
- `.foo.bar` : class 속성에 `foo`와 `bar`가 있는 경우
- `#foo.bar` : id 속성이 `foo`이면서 class 속성이 `bar`인 경우 
<br><br>
### 속성 선택자
#### 단순 속성으로 선택
- 단순 속성이름으로 선택한다.
- 속성 값은 상관이 없다.
```css
p[class] { color: silver; } /* p태그 이면서 class 속성이 있는 것*/
p[class][id] { text-decoration: underline; } /* p 태그 이면서 class와 id 속성이 있는 것*/
```
```html
<p class="foo">Hello</p>
<p class="bar">CSS</p>
<p class="baz" id="title">HTML</p>
```
<br><br>

#### 부분 속성값으로 선택
속성 이름과 속성값 사이에 사용되는 기호에 따라 선택을 달리한다.
- [class~="bar"] : class 속성의 값이 공백으로 구분한 "bar" 단어가 포함되는 요소 선택
- [class^="bar"] : class 속성의 값이 "bar"로 시작하는 요소 선택
- [class$="bar"] : class 속성의 값이 "bar"로 끝나는 요소 선택
- [class*="bar"] : class 속성의 값이 "bar" 문자가 포함되는 요소 선택

```css
p[class~="color"] { font-style: italic; } /* 1 , 2 */
p[class^="color"] { font-style: italic; } /* 1 */
p[class$="color"] { font-style: italic; } /* 2 */
p[class*="color"] { font-style: italic; } /* 1, 2, 3 */
```
```html
<p class="color hot">1. red</p>  
<p class="cool color">2. blue</p>
<p class="colorful nature">3. rainbow</p>
```
---
## 6) 문서 구조 관련 선택자
### 문서 구조 관련 선택자

#### 자손 선택자
```css
div span { color: red; }
```
- 아무 기호 없기 공백으로 구분
- `div` 의 자손인 `span`을 선택

#### 자식 선택자
```css
div > h1 { color: red; }
```
- 선택자 사이에 닫는 꺽쇠 기호(>)를 넣는다.
- `div`의 자식 요소인 `h1`를 선택

#### 인접 형제 선택자
```css
div + p { color: red; }
```
- 선택자 사이에 + 기호를 넣는다.
- 형제 관계이면서 바로 뒤에 인접해 있는 요소를 선택하는 선택자


#### 응용
```css
body > div h1 + span { ... }
```
유의할 점은 요소들이 많이 나열되어 있더라고 제일 우측에 있는 요소가 실제 선택되는 요소이다.

---

## 7) 가상 선택자 1
- **미리 정의해놓은 상황에 적용**되도록 **약속된** 보이지 않는 class 이다.
- 우리가 직접 class를 선언하는 것이 아닌, 약속된 상황에 브라우저가 스스로 class를 선언한다.
    ex) 마우스 올렸을 때 텍스트 색 변경, 링크 클릭 했을 때 등..
- 자바스크립트 없이 동적인 효과를 낼 수 있어 자주 사용된다.

```css
:pseudo-class {
    property: value;
}
```
- `:(콜론)` 기호를 써서 나타낸다.
- 가상 클래스의 종류는 다양하다. 
https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes

### 문서 구조와 관련된 가상 클래스
- :first-child
- :last-child

### 앵커 요소와 관련된 가상 클래스
- :link
- :visited

### 사용자 동작과 관련된 가상 클래스
- :focus
- :hover
- :active

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<title>css</title>
	<style>
		a:focus { background-color: yellow }
		a:hover { font-weight: bold }
		a:active { color: red }
	</style>
</head>
<body>
	<a href="http://www.naver.com">네이버</a>
	<a href="http://www.google.com">구글</a>
	<a href="http://www.daum.net">다음</a>
</body>
</html>
```
---
## 8) 가상 선택자 2
### 가상 요소
- 가상 요소도 가상 클래스처럼 문서 내에 보이지 않지만, 미리 정의한 위치에 삽입되도록 약속이 되어있다.
- 가상 클래스와 가상 요소를 구분하기 위해 가상 요소에는 `::(더블 콜론)` 기호를 사용한다.
- 가상 요소도 여러 종류가 있다.
https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-elements

```css
::pseudo-element {
    property: value;
}
```
- :before : 가장 앞에 요소를 삽입(선택된 태그의 첫 번째 자식요소로)
- :after : 가장 뒤에 요소를 삽입(선택된 태그의 맨 마지막 자식요소로)
- :first-line : 요소의 첫 번째 줄(화면에 보이는 기준으로 한줄)에 있는 텍스트를 감싸는 요소가 생긴다.
- :first-letter : 블록 레벨 요소의 첫 번째 문자를 감싸는 요소가 생긴다

`before`와 `after` 가상 요소는 애초에 내용이 없는 상태로 생성되기 때문에 내용을 넣기 위해 
**`content` 속성을 이용해야** 합니다.

```html
<style>    
    p::before { content: "###" }
    p::after { content: "!!!" }
    p::first-line { ... }
    p::first-letter { ... }
</style>

<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
```
〓
```html
<p>
    <before>###</before>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    <after>!!!</after>
</p>
```
```html
<p>
    <first-letter>L</first-letter>orem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>
<p>
    <first-line>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiu ..(..어딘가쯤..) </first-line>... unt ut labore et dolore magna aliqua.
</p>
```
---
## 9) 구체성
### 구체성
서로 다른 선택자가 같은 요소를 선택 했을 때 구체성 값에 따라 적용 우선순위가 정해진다. 구체성은 4개의 숫자 값으로 이루어져 있다.

#### 구체성 규칙
 - 0, 1, 0, 0 : 선택자에 있는 모든 id 속성값
 - 0, 0, 1, 0 : 선택자에 있는 모든 class 속성값, 기타 속성, 가상 클래스
 - 0, 0, 0, 1 : 선택자에 있는 모든 요소, 가상 요소
 - 전체 선택자는 0, 0, 0, 0을 가진다.
 - 조합자는 구체성에 영향을 주지 않는다. (>, + 등)

```css
h1 { ... }  /* 0,0,0,1 */
body h1 { ... }  /* 0,0,0,2 적용! */

.grape { ... }  /* 0,0,1,0 */

*.bright { ... }  /* 0,0,1,0 */
p.bright em.dark { ...}  /* 0,0,2,2  적용! */

#page { ... }  /* 0,1,0,0 */
div#page { ... }  /* 0,1,0,1 적용! */
```
- 구체성 값을 잘 파악해 규칙을 정의해야 한다.
<br><br>

### 인라인 스타일
```css
p#page { color: red; } /* 0,1,0,1 */
```
```html
<p id="page" style="color:blue">Lorem impusm dolor sit.</p>
```
- blue가 적용된다.
- 인라인 스타일의 구체성 값은 1, 0, 0, 0이며 규칙들 중 가장 큰 구체성을 가진다.
<br><br>
### important
- 모든 구체성을 무시하고 우선권을 갖는다.

```css
p#page { color: red !important; }
```
```html
<p id="page" style="color:blue">Lorem impusm dolor sit.</p>
```
- red가 적용된다
---
## 10) 상속
- 박스모델 속성은 상속되지 않는다. ex) margin, padding, background, border 등

### 상속되는 속성의 구체성
```css
* { color: red; }
h1#page { color: gray; }
```
```html
<h1 id="page">Hello, <em>CSS</em></h1>
```
- `em`에 red가 적용된다.
- 상속된 속성은 아무런 구체성을 가지지 못했기 때문이다.

---
## 11) 캐스케이딩
cascading에는 다음과 같이 3가지 규칙이 있다.

- 중요도(!important)와 출처
    - 제작자와 사용자, 그리고 사용자 에이전트(user agent) 경우로 구분
- 구체성
- 선언 순서
    - 나중에 선언된 규칙일수록 우선순위 ↑
---

## 생각해보기
### 7) 가상선택자 1
```css
p ~ ul { ... }
```
~(틸트) 선택자 : `p` 뒤에있는 형제요소 중 `ul`인 모든 태그를 선택한다. 

https://www.w3schools.com/cssref/sel_gen_sibling.asp

---

### 8) 가상선택자 2
꼭 기억해야할 css 선택자 30가지 : 
https://code.tutsplus.com/ko/tutorials/the-30-css-selectors-you-must-memorize--net-16048


### 12) CSS 선택자 정리
https://www.w3schools.com/cssref/css_selectors.asp