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
- `button`요소는 `ul`로 묶었기에 `ul` 요소에 `flex`를 주어 배치함

<br>

```css
.white-black-button {
  width: 100px;
  height: 40px;
  border: 1px solid var(--black);
  padding: var(--x-small-spacing) var(--small-spacing);
  font-size: var(--xx-small-text);
  border-radius: 25px;
  background-color: transparent;
  color: var(--black);
}

.white-black-button:hover {
  background-color: var(--black);
  color: var(--white);
}
```

- 버튼 요소는 배경색-글자색 순서로 이름을 작성해 만들었고 각각의 요소에 맞도록 작성하였고 hover를 주어 마우스를 올리면 색이 변하도록 설정함

<br>

```css
.airpods-pro-bg {
  background-image: image-set(
    url(./../products/airpods_pro.jpeg) 1x,
    url(./../products/airpods_pro_2x.jpeg) 2x
  );
  background-repeat: no-repeat;
  background-position: 50% 50%;
  background-size: cover;
}
```

- 각각의 이미지에 맞도록 이미지 사진을 image-set을 이용해 작성하였고 cover를 사용하여 크기가 변함에 따라 그에 맞도록 함

<br>

```css
/* 카드 레이아웃 */
.apple-item-container {
  display: grid;
  grid-template-columns: 1fr;
  grid-auto-rows: auto;
  gap: var(--base-spacing);
}

@media (min-width: 1024px) {
  .apple-item-container {
    grid-template-columns: repeat(2, 1fr);
    .ipad-pro-bg,
    .ipad-air-bg,
    .iphone15-pro-bg {
      grid-column: span 2;
    }
  }
  .ipad-pro-bg {
    background-image: image-set(
      url(./../products/ipad_pro_wide.jpeg) 1x,
      url(./../products/ipad_pro_wide_2x.jpeg) 2x
    );
  }
}
```

- 처음에는 grid를 주고 column에 1fr을 주어 배치하도록 함
- 1024px이 넘어가면 column을 2fr로 변경하고 가장 위에 3요소는 2fr을 주어 사이즈를 다 차지하도록 함 그리고 변경된 요소에 맞게 클래스 요소들을 다 변경시켜줌

## 느낀점

- 이번에는 스타일 요소에만 신경을 쓰다보니 아무래도 접근성 요소에 신경을 많이 쓰지 못한것이 아쉬웠다.
- cover를 쓰고 aspect-ratio를 쓰니 뭔가 작동을 하지 않았던거 같은데 내가 잘못써서 그런지 확신할 수 없어서 나중에 한번 확인해봐야 될 것 같다.
- grid를 대충 사용해서 정확히 이해하지 못했는데 그래도 이번 과제를 통해 어느정도 배운 것 같다.

### 이미지 업로드를 못해서 죄송합니다ㅠㅠ
