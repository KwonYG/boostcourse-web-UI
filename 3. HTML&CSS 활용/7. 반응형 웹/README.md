# 7. 반응형 웹
## 반응형 웹 - PC용(기본) 제작
- 일반적으로 mobile-first 개념으로 제작을 시작하지만, 여기서는 이해를 위해 desktop-first 기준으로 시작한다.

### index.html
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <link rel="stylesheet" href="./reset.css">
</head>

<body>
    <div class="wrap">
        <header>
            <a href="#" class="logo">
                <h1>LOGO</h1>
            </a>
            <nav>
                <a href="#">MENU1</a>
                <a href="#">MENU2</a>
                <a href="#">MENU3</a>
                <a href="#">MENU4</a>
                <a href="#">MENU5</a>
                <a href="#">MENU6</a>
                <a href="#">MENU7</a>
                <a href="#">MENU8</a>
            </nav>
        </header>
        <section>
            <ul class="list">
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀을 길게 써보도록 하겠습니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>

            </ul>
        </section>

        <footer>
            Copyright @ Naver Corp. All Rights Reserved.
        </footer>
    </div>
</body>

</html>
```

### css
```css
a{
    text-decoration: none;
}
header{
    overflow:hidden;
    background-color: pink;
    padding:20px;

}

.logo{
    float:left;
    font-size: 20px;
    color:#fff;
}

nav{
    float:right;
}

nav a{
    padding: 0 5px;
    font-size: 20px;
    color:#fff; 
}

footer{
    height: 50px;
    line-height: 50px;
    text-align: center;
    background-color: #ccc;
    font-size: 14px;
    color:#000;
}

section{
    max-width: 900px; /* 중요, 최대 900px 컨텐츠 내용*/
    margin: 50px auto;
}

.list{
    margin: -5px;
    overflow:hidden;
}

.list li{
    float:left;
    width:20%; /*너비를 100%로 따졌을 때, 각 컨텐츠가 5개씩 나올려면 20%씩 차지해야한다.*/
}

.inner {
    display:block;
    margin: 5px;
    border: 1px solid #000;
}

.thumb img {
    width: 100%;
    height: auto; 
}

/*말 줄임*/
.title{
    overflow: hidden;
    text-align: center;
    font-size:14px;
    color: #555;
    white-space: nowrap;
    text-overflow: ellipsis; 
}
```
---
## 4) 반응형 웹 - TABLET 제작
- css의 우선순위(캐스캐이딩)를 염두해두고 작성해야한다.
    - 모바일 CSS는  태블릿의 CSS 밑에 작성이 되어야 하고, 태블릿의 CSS는 PC의 CSS 밑에 작성
- 태블릿 미디어쿼리 작성
```css
@media screen and (max-width: 768px), screen and (max-height: 768px) and (orientation: landscape)  {
    /* TABLET CODE.. */
}
```
- 스크린 환경이면서 최대가로길이가 768px을 넘지 않거나, 스크린 환경이면서 최대 높이가 768px을 넘기지 않고 비율이 가로가 더 긴경우에 해당 코드를 적
### css
```css
/* tablet */
@media screen and (max-width: 768px), screen and (max-height: 768px) and (orientation: landscape)  {
    header{
        background-color:lightseagreen;
    }

    .logo{
        width:100px;
        float:none;
        display:block; /* float이 없어지면서 블록속성이 사라짐, 그래서 다시 선언*/
        margin: 0 auto;
        font-size:40px;
        text-align: center;
    }

    nav{
        overflow-x:auto; /* 메뉴 넘치면 옆쪽으로 스크롤이 생긴다.*/
        overflow-y:hidden; /* 아예 세로로는 스크롤이 생기지 않게 억제*/
        margin-top:20px;
        float:none;
        white-space: nowrap; /* 개행 억제*/
    }
    nav a{
        font-size:25px;
    }

    footer{
        background-color:lightcoral;
        color:#fff;
    }

    .list {
        margin: -4px;/* 데탑에서 -5px로 되어있어 콘텐츠 border부분이 짤린다. 이를 해결하기 위한 코드*/
    }
    .list li{
        width: 25%;
    }
    .inner{
        position: relative;
        margin: 4px; 
    }
    .title{
        position : absolute;
        left:0; right:0; bottom:0;
        padding: 10px 0;
        background-color:rgba(0,0,0,0.2);
    }
}
```
---
## 5) 반응형 웹 - MOBILE 제작

### index.html
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <link rel="stylesheet" href="./reset.css">
</head>

<body>
    <div class="wrap">
        <header>
            <a href="#" class="logo">
                <h1>LOGO</h1>
            </a>
            <nav>
                <a href="#">MENU1</a>
                <a href="#">MENU2</a>
                <a href="#">MENU3</a>
                <a href="#">MENU4</a>
                <a href="#">MENU5</a>
                <a href="#">MENU6</a>
                <a href="#">MENU7</a>
                <a href="#">MENU8</a>
            </nav>
        </header>
        <section>
            <ul class="list">
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀을 길게 써보도록 하겠습니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>
                <li>
                    <a href="#" class="inner">
                        <div class="thumb">
                            <img src="thumb.png" alt="썸네일이미지">
                        </div>
                        <div class="title">
                            타이틀입니다.
                        </div>
                    </a>
                </li>

            </ul>
        </section>

        <footer>
            Copyright @ Naver Corp. All Rights Reserved.
        </footer>
    </div>
</body>

</html>
```
- 햄버거 버튼을 만들기 위해 `<header>`영역 안에 아래의 코드를 추가한다.
```html
<a href="#" class="gnb_menu">gnb menu</a>
```

### css
```css
/* mobile */
@media screen and (max-width: 375px), screen and (max-height: 375px) and (orientation: landscape) {
    header{
        padding: 10px 0;
    }

    nav {
        display: none; /* 보이게 할려면 js를 사용해야한다.*/
        position:absolute;
        top:60px;
        left:0;
        bottom:0;
        z-index: 10;
        width: 200px;
        margin: 0;
        background-color: lightslategray;
    }

    nav a{
        display: block;
        padding: 20px 10px;
        font-size: 20px;
        border-bottom: 1px solid #fff;
    }

    .gnb_menu {
        position: absolute;
        top: 12px; left: 12px; 
        display: block;
        width:40px;
        height:35px;
        font-size: 1px;
        color: transparent;
        background:linear-gradient(#fff 50%, transparent 50%);
        background-size: 100% 10px;
    }

    section{
        margin:0;
    }

    .list li {
        width: 100%;
    }

    .inner{
        display:table;
        table-layout: fixed;
        width:100%;
        margin:0;
        border:none;
        border-top: 1px solid #000;

    }

    .thumb{
        display:table-cell;
        width:100px;
    }

    .title{
        display:table-cell;
        position: relative;
        right:auto;
        left:auto;
        bottom:auto;
        vertical-align: middle;
        background-color:#fff;
        padding: 8px;
        color:#000;
        text-overflow: inherit; /* 말줄임 해제*/
        white-space: inherit;
        text-align: left;
    }
}
```