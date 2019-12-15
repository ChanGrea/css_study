## Relative Position

**상대적**인 위치 즉, <u>**해당 태그 안**에서의 위치</u>를 지정한다.

> :exclamation: 다른 태그들의 배열에는 영향을 주지 않는다.

```html
<style>
  h2 {
    position: relative;
    top: 15px;
  }
</style>
<body>
  <h1>On Being Well-Positioned</h1>
  <h2>Move me!</h2>
  <p>I still think the h2 is where it normally sits.</p>
</body>
```

<img src="img/스크린샷 2019-12-15 오후 3.53.23.png" style="width: 300px;"/>

## Absolute Position

**절대적**인 위치 즉, <u>default로 body태그에서의 위치</u>를 지정한다.

> :exclamation: default로 body태그에서의 위치를 지정하므로, 아래 코드에서처럼 상위태그(section)에서 position을 relative를 지정해줘야 해당 태그를 감싸고 있는 상위 태그에서의 절대 위치를 쓸 수 있다.

```html
<style>
  #searchbar {
    position: absolute;
    top: 50px;
    right: 50px;
  }
  section {
    position: relative;
  }
</style>
<body>
  <h1>Welcome!</h1>
  <section>
    <form id="searchbar">
      <label for="search">Search:</label>
      <input type="search" id="search" name="search">
      <input type="submit" name="submit" value="Go!">
    </form>
  </section>
</body>
```

<img src="img/스크린샷 2019-12-15 오후 3.57.23.png" style="width: 300px;" />

## Fixed Position

**고정 위치**라고 이해하면 된다. `absolute`와의 차이점은 <u>스크롤을 내렸을때도 계속 붙어있다는 점</u>이다.

```html
<style>
  #navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: #767676;
  }
  nav ul {
    margin: 0px;
    padding: 5px 0px 5px 30px;
  }
  nav li {
    display: inline;
    margin-right: 20px;
  }
  a {
    text-decoration: none;
  }
</style>
<body>
  <header>
    <h1>Welcome!</h1>
    <nav id="navbar">
      <ul>
        <li><a href="">Home</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </nav>
  </header>
  <p>I shift up when the #navbar is fixed to the browser window.</p>
</body>
```

<img src="img/스크린샷 2019-12-15 오후 3.58.46.png" style="width: 300px;" />