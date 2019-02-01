# 2. HTML 태그
## 6) 리스트 요소
- `dl` 태그 : dl(definition/description list) 태그는 용어와 그에 대한 **정의**를 표현할 때 사용
    - `dt` 태그 : **용어**를 작성한다. 
    - `dd` 태그 : **용어에 대한 설명**을 작성한다.
    - 위 두 태그가 하나의 세트를 이룬다.

```HTML
<dl>
    <dt>리플리 증후군</dt>
    <dd>허구의 세계를 진실이라 믿고 거짓된 말과 행동을 상습적으로 반복하는 반사회적 성격장애를 뜻하는 용어</dd>
    <dt>피그말리온 효과</dt>
    <dd>타인의 기대나 관심으로 인하여 능률이 오르거나 결과가 좋아지는 현상</dd>
    <dt>언더독 효과</dt>
    <dd>사람들이 약자라고 믿는 주체를 응원하게 되는 현상</dd>
</dl>
```
---
## 7) 이미지 요소
- `img`
- `alt`
- `src`

```HTML
<img src="./images/pizza.png" alt="피자">
```
### alt
- **이미지의 대체 텍스트**를 나타내는 속성.
- **웹 접근성** 측면에서 중요한 속성입니다.

### width/height
- 선택적인 속성이지만 **크기가 고정적이라면** width/height 속성을 **선언하는 것이 성능적인 측면에서 좋다**.
- 둘 중 하나만 선언하면 나머지 한 속성은 선언한 속성의 크기에 맞춰 자동으로 비율을 조정
<br>
### 상대경로와 절대경로
- 상대경로: 현재 웹 페이지를 기준으로 상대적으로 이미지의 위치를 나타내는 경로

- 절대경로: 실제 그 이미지가 위치한 곳의 전체 경로
```HTML
<!-- 상대경로 -->
<img src="./images/pizza.png" alt="피자">

<!-- 절대경로 -->
<img src="C:/users/document/images/pizza.png" alt="피자">
<img src="http://www.naver.com/pizza.png" alt="피자">
```
---
## 8) 테이블 요소 1
- `table` 태그 : 표를 나타내는 태그
- `th` 태그: 제목 셀을 나타내는 태그
- `tr` 태그: 행을 나타내는 태그
- `td` 태그: 셀을 나타내는 태그

### 표의 구조와 관련된 태그
표가 복잡해지면 표를 해석해서 음성으로 전달해야 하는 스크린 리더기와 같은 보조기기가 코드를 해석하기 어려워진다. 이러한 **웹 접근성에 생기는 문제를 해결하는데 도움**을 주는 **태그**가 존재한다.

- `caption` 태그 : 표의 제목을 나타내는 태그
- `thead` 태그 : 제목 행을 그룹화하는 태그
- `tfoot` 태그 : 바닥 행을 그룹화하는 태그
- `tbody` 태그 : 본문 행을 그룹화하는 태그

```html
<table>
    <caption>Monthly Savings</caption>
    <thead>
        <tr><th>Month</th><th>Savings</th></tr>
    </thead>
    <tfoot> <!--tfoot 태그 위치를 주의하자-->
        <tr><td>Sum</td><td>$180</td></tr>
    </tfoot>
    <tbody>
        <tr><td>January</td><td>$100</td></tr>
        <tr><td>February</td><td>$80</td></tr>
    </tbody>
</table>
```
- `tfoot`은 `thead` 다음에 있지만, 실제 화면에서는 표의 맨 아래에 위치하게 된다는 점을 주의하자.

---
## 10) 폼 요소 1
### `input` 태그
- type='text'
- placeholder
- type='radio'
    - 중복선택 불가
- type='checkbox'
    - 중복선택 가능 
- type='password'
- name 속성
- checked 속성

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input
    
---
## 11) 폼 요소 2
### `input` 태그
- type='file'
- type='submit'
- type='image'
- type='button'
```html
<form action="./test.html">
    메시지: <input type="text" name="message"><br>
    <input type="submit">
    <input type="reset">
    <input type="image" src="http://placehold.it/50x50?text=click" alt="click" width="50" height="50">
    <input type="button" value="버튼">
</form>
```
https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Forms

---
## 12) 폼 요소 3
### `select` 태그
- 선택목록상자, 콤보박스라고 불린다.
```html
<select>
    <option>서울</option>
    <option selected>경기</option>
    <option>강원</option>
    ...
</select>
```
- `select` 태그
    - `option` 태그
- `selected` 속성 존재
<br><br>
### `textarea` 태그
- rows, cols 속성

### `button` 태그
- type='submit'
- type='reset'
- type='button'
- `input`태그때의 타입과 동일
---
## 13) 폼 요소 4
### `label` 태그
`form` 이름과 `form` 요소를 명시적으로 연결시켜준다. **웹접근성 향상**에 도움이 되므로 **필수적**으로 작성한다.
```html
<label for="name">이름</label>: <input type="text" id="name"><br>

<label for="nickname">닉네임</label>: <input type="text" id="nickname"><br>

<label for="address">주소</label>: <input type="text" id="address"><br>
```
- `form` 요소의 **id 속성값**과 `label`의 **for 속성값**을 같게 적어주어야 한다.
- examples 폴더 확인 - [form4.html](./examples/form4.html)
<br><br>

### `fieldset`, `legend` 태그
`form` 요소를 **구조화** 하는데 쓰이는 태그이다.
- `fieldset` 태그 : 폼 요소를 그룹화 한다.
    - `legend` 태그 : `fieldset` 태그로 묶인 그룹의 이름을 지정한다.
```html
<fieldset>
    <legend>기본 정보</legend>
    ... 폼 요소들 ...
</fieldset>
<fieldset>
    <legend>부가 정보</legend>
    ... 폼 요소들 ...
</fieldset>
``` 
- `legend` 태그는 반드시 `fieldset` 태그의 **첫번째 자식**으로 작성되어야 한다.
- 폼 작성 성향에 따라 구조화 한다. ex) 필수작성-선택작성, 이벤트 응모부분-개인정보 작성부분
<br><br>
## `form` 태그
- action
- method
    - get
    - post
- `fieldset` 구조로 그룹화된 부분까지 다 감싼다.