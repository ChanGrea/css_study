# Media Query



`Media Query`는 Device(PC, Mobile) 타입 별로 스타일을 다르게 하고 싶을 경우 유용하다.



## Syntax

```
@media [Media Types | Media Features | Logical Operators] {
	...
}
```

3가지 구성 요소로 이루어져 있다.

- Media Types
- Media Features
- Logical Operators



### :white_check_mark: Media Types

일반적인 Device의 카테고리를 정의한다.

`all`

- 모든 Device



`print`

- 프린트 장치에 해당



`screen`

- 컴퓨터의 스크린, 태블릿, 스마트폰에 해당
- :star: 가장 많이 쓰이는 타입 :star:



`speech`

- 페이지를 읽어주는 장치에 해당



### :white_check_mark: Media Features

사용자의 화면에 대한 특성을 정의, 예를 들어 화면의 너비, 가로세로 비율 등

여러가지 속성이 있지만, 자주 쓰이는 것 위주로 나열하자면

`aspect-ratio`

- 뷰포트의 너비와 높이에 대한 비율. ‘너비/높이’ 순으로 조건을 작성

```css
@media all and (aspect-ratio:5/4) { … } // 뷰포트 너비가 5, 높이가 4 비율이면 실행
@media all and (min-aspect-ratio:5/4) { … } // 뷰포트 너비가 5/4 비율 이상이면 실행
@media all and (max-aspect-ratio:5/4) { … } // 뷰포트 너비가 5/4 비율 이하면 실행
```



`height`

- 뷰포트의 높이



`orientation`

- 뷰포트의 너비와 높이의 비율을 이용해서 **가로 모드인지 세로 모드인지** 판별

```css
@media all and (orientation:portrait) { … } // 세로 모드. 뷰포트의 높이가 너비에 비해 상대적으로 크면 실행
@media all and (orientation:landscape) { … } // 가로 모드. 뷰포트의 너비가 높이에 비해 상대적으로 크면 실행
```



`width`

- 뷰포트의 너비



`max-width / max-height`

- 뷰포트의 최대 너비와 최대 높이



`min-width / min-height`

- 뷰포트의 최소 너비와 최소 높이



### :white_check_mark: Logical Operators

`Media Type`과 `Media Feature`를 같이 사용하고자 할 때 쓰이는 연산자



`and`

- single media query들을 연결해서 쓰기 위해 사용



`not`

- media query를 부정하기 위해 사용



`only`

- 조건에 해당하는 media query를 실행하기 위해 사용
- 보통 **오래된 브라우저**에 대해서 실행을 막기 위해 사용
- 예를 들어 `screen and (max-width: 500px)`의 경우 오래된 브라우저는 `screen`에 대해서만 실행하고 `max-width`는 인식하지 못하므로 계속 해석하려고 할 것이다.



`,`(comma)

- `or`의 역할



## Example

```css
@media (min-width: 30em) and (orientation: landscape) { ... }
```

- 최소 너비가 **30em**이고(and) **가로모드**인 경우



```css
@media screen and (min-width: 30em) and (orientation: landscape) { ... }
```

- **스크린**이고(and) 최소 너비가 **30em**이고(and) **가로모드**인 경우



```css
@media (min-height: 680px), screen and (orientation: portrait) { ... }
```

- 최소 높이가 **680px**이거나(,) **스크린**이고(and) **세로모드**인 경우



## 일반적인 Device Breakpoints

```css
/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {...}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {...}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {...}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {...}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {...}
```

