# CSS (Cascading Style Sheets)

- CSS는 HTML 문서에 스타일을 더해준다.
- 계단식으로 스타일을 정의하는 문서

- CSS 문법 구조
```
선택자 { 속성명1: 속성값1; 속성명2: 속성값2; }
```
```css
h2 {
    color: gray;
    font-size: 16px;
}
```

- CSS 방식
1. 인라인 스타일
    - 비추천
    ```html
    <html>
        <body>
            <h1 style="color:gray;font-size:12px;">title</h1>
        </body>
    </html>
    ```
2. `<head>` 태그 내에 `<style>` 내의 정의
```html
<head>
    <style>
        h2 {
            color: gray;
            font-size: 16px;
        }
    </style>
</head>
```
3. CSS 파일 외부 정의
    - <link> 태그로 추가
    ```html
    <html>
        <head>
            <link rel="stylesheet" href="test.css">
        </head>
    </html>
    ```
    