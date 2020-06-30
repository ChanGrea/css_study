# Flex(Flexible box)

## 참고

[https://heropy.blog/2018/11/24/css-flexible-box/](https://heropy.blog/2018/11/24/css-flexible-box/)

## 개요

대부분 사이트는 위에서 아래로 수직 구성이 되어 있는데, **수평 구성**을 좀 더 쉽게 하기 위해서 flex가 쓰인다고 한다.

> Flex는 수직 구성도 쉽다. 사실 Header, Contnets, Footer를 구성하기 위한 방법으로 찾다가 flex에 대해서 정리하게 되었음.

## 기본적인 개념, 속성

Flex는 2개의 개념으로 나뉜다.

1. Container (부모)
2. Items (자식)

Container에는 `display`, `flex-flow`, `justify-contents`, `align-items`, `align-content`

Items에는 `order`, `flex`, `flex-grow`, `flex-shrink`, `flex-basis`, `align-self` 속성을 사용한다.

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

- 교차 축(cross-axis)의 정렬 방법 지정

:exclamation: `flex-wrap`을 통해 **items가 여러 줄(2줄 이상)**일 경우 많이 사용

`stretch`(default), `flex-start`, `flex-end`, `center`, `space-between`, `space-around`

- :thinking: `justify-content` 의 수직 버전이라고 생각하면 된다



### :banana: align-items

교차 축(cross-axis)의 정렬 방법 지정

:exclamation: **items가 1줄**일 경우 많이 사용

> `align-content` 속성을 기본 값(`stretch`)으로 설정해야 한다.



## Flex Items

| 속성        | 의미                                                 | 기본값 |
| ----------- | ---------------------------------------------------- | ------ |
| order       | Flex Item의 순서를 결정                              |        |
| flex        | `flex-grow`, `flex-shrink`, `flex-basis`의 단축 속성 |        |
| flex-grow   | Flex Item의 **증가 너비 비율**을 설정                | 0      |
| flex-shrink | Flex Item의 **감소 너비 비율**을 설정                | 1      |
| flex-basis  | Flex Item의 (공간 배분 전) 기본 너비 설정            | auto   |
| align-self  | 교차 축(cross-axis)에서 Item의 정렬 방법을 설정      |        |

### :banana: order

- Flex Item의 **순서**를 결정

#### Example

```html
<header>...</header>
<main>
  <article>Article</article>
  <nav>Nav</nav>
  <aside>Aside</aside>
</main>
<footer>...</footer>
```

```css
main { display: flex;  text-align:center; }
main > article { flex:1;        order: 2; }
main > nav     { width: 200px;  order: 1; }
main > aside   { width: 200px;  order: 3; }
```

- 이 예제에서는 order를 `nav >> article >> aside` 순으로 1, 2, 3 값으로 지정
- HTML에서  article >> nav >> aside 순으로 작성하더라도 실제 출력은 nav >> article >> aside 순으로 출력



### :banana: flex

- Flex Container에서 Item들의 크기의 증가/감소 비율을 결정
- `flex-grow`, `flex-shrink`, `flex-basis` 세 가지 속성을 표현

#### flex-grow

- Flex Item의 **증가 너비 비율**을 설정
- 기본 값은 0으로 Flex Container의 크기가 증가해도 Item은 크기가 증가하지 않는다.
- 양수 값 지정 가능 :arrow_right: 지정한 값의 비율만큼 크기가 증가

#### flex-shrink

- Flex Item의 **감소 너비 비율**을 설정
- 기본 값은 1

> :exclamation: flex-shrink는 flex-basis나 기본 width, height 크기의 영향을 받기 때문에 계산이 까다롭다.
>
> 실제 item A와 item B의 flex-shrink가 2, 1이라고 해도 감소 비율이 2:1이라고 생각하면 안된다.
>
> 이것은 **A와 B의 크기가 같을 때(1:1**)의 이야기고, **A와 B의 크기 비율이 2:3이라면 감소 비율의 곱 (2x2 : 3x1 = 4: 3)** 이라고 생각하면 쉬울 것 같다.

#### flex-basis

- Flex Item의 (공간 배분 전) 기본 너비 설정
- 기본 값은 auto :arrow_right: width나 height로 너비 설정
- 0으로 설정 시 absolute flex item이 되어 flex container를 기준으로 크기가 결정 (**0으로 설정시에는 단위도 함께 명시해야 한다.**)
- 그 외에는 단위를 붙여서 값을 지정하면 고정 크기가 지정된다.



### :banana: align-self

- 교차 축(cross-axis)에서 Item의 정렬 방법을 설정
- align-items는 Flex Container 내의 items의 정렬 방법을 설정, align-self는 align-items보다 우선순위가 높아 개별적인 item들의 정렬 방법을 설정할 때 이용한다.
- `auto`, `stretch`, `flex-start`, `flex-end`, `center`, `baseline`
  - auto : 기본값으로 align-items의 값을 따른다.
  - stretch : items를 늘려서 꽉 채운다.
  - flex-start : 시작점부터 정렬
  - flex-end :  끝점부터 정렬
  - center : item들을 가운데 정렬
  - baseline : 문자 기준선에 정렬

