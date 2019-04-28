# 미디어쿼리
## 실습
### 실습 1. 디스플레이 크기에 따른 body요소의 background-color 변경
#### index.html
```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <title>Media Queries</title>
    <style>

    </style>
</head>

<body>
    <p>W3C는 <a href="https://www.w3.org/TR/css3-mediaqueries/">CSS3 미디어쿼리 문서</a>를 2012년 6월에 표준 권고안으로 제정하였습니다.</p>
    <p>또한, 기존의 미디어쿼리 개선 작업을 진행 중이며, 2017년 9월에 <a href="https://www.w3.org/TR/mediaqueries-4/">미디어쿼리 레벨4</a>를 발표했습니다. 이
        문서는 현재 유력 표준 권고안입니다.</p>
</body>

</html>
```
#### 세부 조건
- 0~767px 이면 : gold
- 768px~1024px 이면 : lightblue
- 1025px~ 이면 : lightpink

```css
@media (max-width: 767px) {
	body { background-color: gold; }
}
@media (min-width: 768px) and (max-width: 1024px) {
	body { background-color: lightblue; }
}
@media (min-width: 1025px) {
	body { background-color: lightpink; }
}
```

미디어 쿼리는 최대한 줄일 수 있으면 좋다. 현재 미디어 쿼리가 3개 쓰여있는데, 이를 2개까지 줄여보자.

먼저 데스크탑인제 모바일인지 기준을 세운 뒤 작성한다.

#### mobile-first
```css
/* mobile first*/
body { background-color: gold; }
@media (min-width: 768px) and (max-width: 1024px) {
	body { background-color: lightblue; }
}
@media (min-width: 1025px) {
	body { background-color: lightpink; }
}
```
#### desktop-first
```css
/* desktop first*/
body { background-color: lightpink; }
@media (min-width: 768px) and (max-width: 1024px) {
	body { background-color: lightblue; }
}
@media (max-width: 767px) {
	body { background-color: gold; }
}
```