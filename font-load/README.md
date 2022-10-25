# 폰트 로드

* 폰트 정의 구조
```html
<style>
    body {
        font-family: '궁서체', dotum, helvetica, sans-serif; /* 우선 순위 */
    }
</style>
```

* 폰트 로드
    1. font-face
    ```css
    font-face { 
        font-family: 폰트명;
        src:url('경로');
    }
    ```
    2. CDN
        - link 방식
        - import 방식
        - 참조 : https://fonts.google.com

* 웹에 최적화된 폰트
    * if 시스템 폰트 then 웹 폰트 변환
    * webfont generator