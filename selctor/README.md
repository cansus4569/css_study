# 선택자

- 전체 ('*')
```html
<style>
    *{
        font-size: 12px;
    }
</style>
```
- tag (태그명)
```html
<style>
    h1{
        font-size: 12px;
    }
</style>
```
- id : unique ('#')
```html
<style>
    #test{
        font-size: 12px;
    }
</style>
<h1 id="test">Test</h1>
```
- class ('.')
```html
<style>
    .small{
        font-size: 12px;
    }
    .hilight-color{
        color: yellow;
    }
    .bold{
        font-weight: bold;
    }
</style>
<p class="small"> Number 1</p>
<p class="small hilight-color"> Number 2</p>
<p class="small hilight-color bold"> Number 3</p>
```
- 자손 (' ')
```html
<style>
    header h1{
        font-size: 12px;
    }
    section .class {
        background-color: lightgray;
    }
</style>

<header>
    <h1 class="title">header title</h1>
</header>
<section>
    <h1 class="title">section title</h1>
</section>
```
- 자식 ('>')
```html
<style>
    /* nav ul li a{
        background: lightgray;
        text-decoration: underline;
    } */
    nav > ul > li > a{
        background: lightgray;
        text-decoration: underline;
    }
</style>

<header>
    <h1 class="title">header title</h1>
    <nav>
        <ul>
            <li><a href="#">menu</a>
                <ul>
                    <li><a href="">sub menu 1</a></li>
                    <li><a href="">sub menu 2</a></li>
                </ul>
            </li>
            <li><a href="">menu</a></li>
            <li><a href="">menu</a></li>
        </ul>
    </nav>
</header>
```
- 형제
```html
<style>
    h1 + ul{ /* h1 뒤에 따라오는 ul만 */
        font-size: 12px;
    }
    h2 ~ ul{ /* h2 다음에 따라오는 모든 ul */
        background: lightgray;
    }
</style>
<h1>형제 선택자</h1>
<ul>
    <li>menu1</li>
    <li>menu2</li>
    <li>menu3</li>
</ul>
<h2>main</h2>
<ul>
    <li>menu1</li>
    <li>menu2</li>
    <li>menu3</li>
</ul>
<h3>sub</h3>
<ul>
    <li>menu1</li>
    <li>menu2</li>
    <li>menu3</li>
</ul>
```
- 속성
```html
<style>
    [target]{
        text-decoration: none;
    }
    [target="_blank"]{
        background: lightgray;
    }
    a[class^="inner"]{
        font-weight: bold;
    }
</style>
<p>
    <a href="" class="inner_sm">link</a>
    <a href="" target="_blank">naver</a>
    <a href="" target="_blank">daum</a>
    <a href="" target="_self" class="inner_big">google</a>
</p>
```
- 의사 클래스 (":")
```html
<style>
    h1:hover{ /* mouseover */
        background: lightgray;
    }
    :link{
        font-size: 20px;
        text-decoration: none;
        font-weight: bold;
    }
    :visited { /* 이미 클릭한 링크 */
        color: red;
    }
    a:focus {
        background: yellow;
    }
    a:active{ /* 누르는 순간 */
        background: black;
        color: yellow;
    }
    input, button{
        outline: none;
    }
    input:focus, button:focus{
        background: green;
        color: #fff;
    }
    form:focus-within{ /* 자식요소에 포커스가 걸리면 부모요소도 선택됨 */
        background: silver;
    }
</style>
<h1>Pseudo-class Selector</h1>
<p>
    <a href="">link</a>
</p>
<form action="">
    <input type="text">
    <button>send</button>
</form>
```
- 의사 요소
```html
<style>
    h1:before{
        content:'- ';
        color:blue;
    }
    h1:after{
        content:' -';
        color:blue;
    }
    h2:before{
        content: '\2c2'; /* Unicode HEX */
    }
</style>
<h1>Pseudo-element</h1>
<h2>body</h2>
```
- 구조
```html
<style>
    /* li:first-child,
    li:last-child,
    li:nth-child(3) {
        text-decoration: underline;
    } */
    li:nth-child(2n) { /* n 값은 0부터 시작함 */
        background:silver
    }
    li:nth-child(even) { /* 짝수 */
        background: silver;
    }
    li:nth-child(odd) { /* 홀수 */
        background: silver;
    }
</style>
<ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
    <li>item 4</li>
    <li>item 5</li>
</ul>
```
- 형태구조
```html
<style>
    h2:first-of-type { /* 같은 타입중에서 첫째 */
        background: lightgray;
    }
    h2:nth-of-type(2) { /* 같은 타입중에서 둘째 */
        background: lightgray;
    }
</style>
<h1>nth-of-type</h1>
<h2>h2</h2>
<h1>h1</h1>
<h2>h2</h2>
<h2>h2</h2>
```
- 상태
```html
<style>
    #policy:target{
        background: green;
        color: #fff;
    }
    input:checked + label{
        background: lightgray;
    }
    button:disabled{
        background: #999;
        color: #ebebeb;
    }
</style>
<a href="#description">설명보기</a>
<form action="">
    <input type="radio" name="newsletter" id="yes">
    <label for="yes">YES</label>
    <input type="radio" name="newsletter" id="no">
    <label for="no">NO</label>
    <hr>
    <input type="checkbox" id="agree">
    <label for="agree">동의</label>
    <hr>
    <button disabled>전송</button>
</form>
<div id="policy">
    <h2>안내문</h2>
</div>
```
- 부정선택자 (':(선택자)')
```html
<style>
    header *:not(h1) { /* header 안에 모든것 중에 h1 제외하고 */
        color: green;
    }
    li:not(:last-child){ /* li 중에 막내 제외하고... */
        background-color: silver;
    }
</style>
<h1>부정 선택자</h1>
<header>
    <h1>logo</h1>
    <h2>main title</h2>
    <p>Tip</p>
    <a href="">read more</a>
</header>
<ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
    <li>item 4</li>
</ul>
```

# 선택자 우선순위
- [예제](./index.html)

- 우선순위 (왼쪽이 높음)
```
!important > inline style > id > class > tag > *
```