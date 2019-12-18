# Flex(Flexible box)

## 참고

[https://heropy.blog/2018/11/24/css-flexible-box/](https://heropy.blog/2018/11/24/css-flexible-box/)

## 개요

대부분 사이트는 위에서 아래로 수직 구성이 되어 있는데, **수평 구성**을 좀 더 쉽게 하기 위해서 flex가 쓰인다고 한다.

> Flex는 수직 구성도 쉽다. 사실 Header, Contnets, Footer를 구성하기 위한 방법으로 찾다가 flex에 대해서 정리하게 되었음.

## 기본적인 개념, 속성

Flex는 2개의 개념으로 나뉜다.

1. Container
2. Items

Container에는 `display`, `flex-flow`, `justify-contents`

Items에는 `order`, `flex`, `align-self` 속성을 사용한다.

## Flex Container

### :banana: display

| 값            | 의미                                | 기본값 |
| ------------- | ----------------------------------- | ------ |
| `flex`        | Block 특성의 Flex Container를 정의  |        |
| `inline-flex` | Inline 특성의 Flex Container를 정의 |        |

`display: flex`는 Block 요소와 같은 **수직 쌓임**, `display: inline-flex`는 inline(inline-block)과 같은 **수평 쌓임**의 차이가 있다.

### :banana: flex-flow

**주 축**과 **wrap(묶음)** 속성을 지정

```css
flex-flow: flex-direction flex-wrap;
```

#### flex-direction

`row`(default), `row-reverse`, `column`, `column-reverse` 네 가지가 있으며, row는 수평, column은 수직, reverse가 붙은 것은 반대라고 생각하면 된다.

```css
flex-direction: row;
```

#### flex-wrap

줄 묶음(줄 바꿈)을 결정

`nowrap`(default), `wrap`, `wrap-reverse` 세 가지가 있으며, 각각의 속성은 아래 그림을 참고

<img src="img/스크린샷 2019-12-18 오후 10.44.49.png" />

### :banana: justify-content

`flex-start`, `flex-end`, `center`, `space-between`, `space-around`

<img src="img/스크린샷 2019-12-18 오후 11.06.37.png" />

### :banana: align-content

교차 축(cross-axis)의 정렬 방법 지정

:exclamation: `flex-wrap`을 통해 **items가 여러 줄(2줄 이상)**일 경우 많이 사용
