# 3. 콘텐츠모델, 시멘틱마크업, 블록 & 인라인
## 콘텐츠 모델
- Flow
- Sectioning
- Heading
- Phrasing
- Embedded
- Interactive

https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories

---
## 2) 시멘틱 마크업
시멘틱은 기계(컴퓨터, 브라우저)가 잘 이해할 수 있도록 하는 것을 뜻한다.

```HTML
<b>굵은</b> vs <strong>중요한</strong>
<i>기울어진</i> vs <em>강조하는</em>
<u>밑줄친</u> vs <ins>새롭게 추가된</ins>
<s>중간선이 있는</s> vs <del>삭제된</del>
```
- 서로 **결과**는 같지만 **의미**는 전혀 다르다.
- `b` 태그는 **의미 없이 단순히 텍스트를 굵게** 표현하는 태그지만, `strong` 태그는 중요하다는 의미를 지닙니다. 즉, `strong`은 **중요하다는 의미에 맞춘 굵은 스타일 표현**이다.
- 즉, 중요하다는 의미가 포함될 때에는 `b` 태그가 아닌 `strong` 태그를 사용해야 한다.

시멘틱 관련 정말 좋은 내용 : https://nuli.navercorp.com/sharing/seminar/2014/08

---
## 3) HTML5 시멘틱 요소
- `article`
- `aside`
- `figcaption`
- `figure`
- `footer`
- `header`
- `main`
- `mark`
- `nav`
- `section`
- `time`

https://developer.mozilla.org/en-US/docs/Glossary/Semantics

---

## 4) 블록&인라인
- 블록 레벨 요소 ⊂ 인라인 레벨 요소를 허용하지 않는다.
- 단, 예외적으로 `a` 태그는 자식요소로 블록 레벨 요소를 넣을 수 있다.  

---