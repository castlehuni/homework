# apple 제품 카드

##구현동영상

## HTML 마크업

```html
<section class="product-container ipad-pro-bg">
  <h2 class="product-name-w">iPad Pro</h2>
  <p class="product-intro-w">
    놀라우치 만큼 얇다. <br />
    엄청나게 강력하다
  </p>
  <p class="open-date">출시일 추후 공개</p>
  <ul class="button-wrapper">
    <li><button class="blue-white-button">더 알아보기</button></li>
    <li><button class="black-blue-button">가격 보기</button></li>
  </ul>
</section>
```

- 위 코드와 같이 카드를 각각 section으로 묶고 그 안에 상품 이름을 `h2` 태그로 소개와 출시일과 같은 요소는 `p`태그로 그리고 버튼 요소들은 `ul`와 `li`를 사용해 리스트 형태로 만들었고 그 안에 버튼을 넣어 각각의 기능을 하도록 하였음
- `section`을`product-container`, `h2`를 `product-name-w/product-name-b` 그리고 제품 소개를 `product-intro-w/product-intro-b` 그리고 리스트 요소를 `버튼 wrapper`로 설정하여 그 안에 버튼을 각각의 색깔에 맞는 클래스를 부여하여 각각 컴포넌트 요소로 분리시킴

<br>

```html
<div class="apple-item-container"></div>
```

그 바깥쪽으로 apple item을 담을 수 있는 `div` 태그를 이용하여 후에 `grid`를 사용하여 묶을 수 있도록 함

<br>

## CSS 스타일링

```css
.product-container {
  display: flex;
  flex-flow: column nowrap;
  flex-grow: 1;
  gap: var(--small-spacing);
  height: var(--size);
  align-items: center;
  text-align: center;

  .product-name-b {
    font-size: var(--large-text);
    font-weight: 700;
    color: var(--black);
    margin-top: var(--large-spacing);
  }

  .product-intro-b {
    font-size: var(--base-text);
    font-weight: 700;
    color: var(--black);
    line-height: var(--line-normal);
  }

  .button-wrapper {
    display: flex;
    flex-flow: row nowrap;
    margin: 0 auto;
    gap: var(--base-spacing);
  }
}
```

- 우선 `section` 태그에 있는 요소들을 `flex`를 사용하여 배치하였고 그 안에 있는 각각의 요소들을 제목이면 `product-name`으로 설명이면 `.product-intro`로 설정하여 각각의 요소에 맞게 작성하였고 색깔이 검정이면 `b`, 하양이면 `w`로 구분하였음
