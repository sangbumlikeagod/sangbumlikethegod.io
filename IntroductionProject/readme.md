# 오늘의 방점

내가 이 프로젝트를 통해 지원하고 싶은 아이디어는 다음과 같다 
1. 요구사항이었던 반응형 웹을 위해 웹페이지 크기에 따라 화면을 바꾸는 기능 적용
2. 페이지 왼쪽에 사이드바를 만들고 스크롤에 상관없이 유지되게 한다
3. 사이드바를 클릭하면 해당 챕터로 이동하게하는 방식을 만든다.


기능 2, 3에 대한 구현 
```html

<div class="row align-items-start">
          <div class="col left">
            <div class="sidebar">
                <ul id = "left_sidebar">
                    <!-- <a href="#Python" class="inside">안녕</a> -->
                    <li class="inside"><a href="#Intro" class="inside">🐯안녕</a></li>
                    <li class="inside"><a href="#Python" class="inside">🐉Python</a></li>
                    <li class="inside"><a href="#Web" class="inside">🌐Web</a></li>
                    <!-- <a href="#Python" class="inside">안녕</a>
                    <a href="#Python" class="inside">안녕</a>
                    <a href="#Python" class="inside">안녕</a> -->
                    <!-- <li>안녕</li>
                    <li>안녕</li>
                    <li>안녕</li> -->
                </ul>
            </div>
          </div>

```
html에선 bootstrap을 이용해 2개의 열로 페이지를 나누고 3가지의 챕터로 나누었다. css에서는 다음과 같다.

```css
.container{
    /* display: flex; */
    /* margin-top: 10; */
    /* margin-top: auto; */
    position: fixed;
    margin-right: auto;
    max-width: 100%;
    position: relative;
    margin-left: 0;
    margin-right: 0;
    height: inherit;
    /* overflow: hidden;  */
    z-index: 0;
}
.sidebar{
    justify-content: center;
    margin-right: auto;
    display: flex;
    position: sticky;
    /* height: 100vh; */
    top: 50%;
    transform: translateY(-50%);
    right: 300px;
    z-index: 3;

}
.inside{
    padding-left: 0%;
    color: black;
    text-decoration: none;
    height: 10lvh;
    text-align: center;
    display: flex;
    font-size: 3vh;
    justify-content: center; /* 수평 가운데 정렬 */
    align-items: center; /* 수직 가운데 정렬 */
    text-align: center; /* 텍스트 가운데 정렬 */
}
.inside:hover{
    color: white;
}
.inside:active{
    font-size: larger;
}
.inside:visited{
    font-size: large;
}


```

기능 1의 구현

```css
.not-provided {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }


  
@media (max-width: 800px) {

    .left{
        display: none;
    }

}


@media (max-width: 600px) {
    .container{
        display: none;
    }
    .sidebar{
        display: none;
    }
    .not-provided {
        display: block;
    }
}


```
css에서 다음과 같은 코드를 추가해 너비마다 서로다른  화면을 만들게했다 