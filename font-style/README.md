# 폰트 스타일

## 글자 크기

```css
test {
    font-size: small;
}
```

- xx-small, x-small, small, medium, large, x-large, xx-large
    - 실제로 많이 쓰이지 않음
    - why? 단위로 크기를 지정함

- 단위 : px, %, em, rem, vw, vh
    - 참고 : http://pxtoem.com/
    - vw, vh : 모바일, 테블릿 위주 사용

## 글자 두께

```css
test {
    font-weight: 400;
}
```

- 숫자 방식을 사용 가능
- normal, bold 사용 권장
    - thin, medium 은 적용안될 수 있음

## 글자 장식
```css
test {
    text-decoration: 선위치, 선형태, 색깔;
}
```
- 선 위치
    - none
    - underline
    - overline
    - line-through
- 선 형태
    - dotted
    - dashed
    - wavy
    - solid

## 글자 스타일