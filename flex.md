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
