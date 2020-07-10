# Animation

`Animation`을 적용할 때는 **CSS를 이용하는 방법**과 **JS를 이용하는 방법**이 있다. 여기서는 CSS를 이용하는 방법에 대해서 정리한다.



## 2D Transforms

특정 Element를 회전시키고, 크기를 늘렸다 줄이고 하는 등 변형하는 방법이 있다.



`translate()`

```css
transform: translate([X-asix], [Y-axis]);
```

- X, Y 만큼 이동



`rotate()`

```css
transform: rotate(20deg);
```

- 시계방향으로 deg만큼 회전



`scaleX()`

```css
transform: scaleX(N);
```

- width의 N배만큼 확장



`scaleY()`

```css
transform: scaleY(N);
```

- height의 N배만큼 확장



`scale()`

```css
transforM: scale(X, Y);
```

- width의 X배, height의 Y배만큼 확장



`skewX()`

```css
transform: skewX(20deg);
```

- 가로방향으로 20 degree만큼 비스듬히 변형



`skewY()`

```css
transform: skewY(20deg);
```

- 세로방향으로 20 degree만큼 비스듬히 변형



`skew()`

```css
transform: skew(20deg, 10deg);
```

- 가로방향 20 degree, 세로방향 10 degree 만큼 비스듬히 변형



`matrix()`

```css
transform: matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY());
```



## 3D Transforms

<img src="./img/animation-axis.png" />

`rotateX()`

```css
transform: rotateX(150deg);
```



`rotateY()`

```css
transform: rotateY(130deg);
```



`rotateZ()`

```css
transform: rotateZ(90deg);
```



## Transitions

CSS Property에 대해서 duration을 주고 부드럽게 변하게 하는 방법이다.



### :heavy_check_mark: Transition 적용

- 효과를 적용할 property를 지정
- 효과의 지속 시간(duration) 지정



#### Example

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

div:hover {
  width: 300px;
}
```

<img src="./img/transition.gif" />



### 다양한 transition 종류

- `ease` : 느리게 시작하고, 빨랐다가 다시 느리게 끝남
- `linear` : 시작부터 끝까지 동일한 속도
- `ease-in` : 느리게 시작
- `ease-out` : 느리게 끝남
- `ease-in-out` : 느리게 시작, 느리게 끝남
- `cubic-bezier(n,n,n,n)` : 커스터마이징할 수 있는 함수

```css
#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}
```



## Animation 적용

CSS Animation을 적용하려면 `animation` 속성과 `하위 속성`을 이용한다.

