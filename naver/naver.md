# 네이버 로그인 과제 수행과정 설명(5월 3일 과제)

## HTML 마크업

HTML 구조는 다음과 같이 마크업을 진행하였습니다<br>

- 각각의 영역을 크게 `header`와 `section` 영역으로 나누었고 `header` 영역에는 네이버 로고를 배치하였습니다.
- 로그인 영역은 크게 `section`을 사용하여 그 안에 폼 요소를 작성하였고 섹션 태그는 제목 요소가 반드시 들어간다는 피드백을 받아 `h2`태그를 사용해 제목을 넣어줬습니다.
- `form` 태그를 사용하여 `input`과 같은 폼 요소들을 사용하고자 하였고 그 안에 `fieldset`과 `legend`를 사용하여 로그인 내용 요소과 로그인 세부 정보 요소를 `WAI-ARIA`를 최대한 사용하지 않고 나타내고자 하였습니다.
- 로그인 아이디와 비밀번호 그리고 버튼 부분을 `div`로 하나로 묶었고 그 밑에 세부사항들은 `ul`과 `li`태그를 사용해 리스트를 만들어 묶어줬습니다.
- 로그인 상태 유지 부분은 `input`요소 중 `checkbox`를 사용하였고 ip보안 부분은 `a`와 `span`부분으로 구성하였습니다.(span 부분은 후에 수정 예정입니다.)
- `a`태그 부분은 새로운 창을 만들기 위해 `target = _blank`를 사용하였으나 이전에 설명해주시기를 위 방식은 보안 문제가 생겨 `rel="noopener noreferrer"`를 작성해야 한다 하여 작성하였습니다.

<br>

## CSS 스타일링

```css
.sr-only {
  /* 숨김 요소 */
  background-color: red;
  position: absolute;
  inline-size: 1px;
  block-size: 1px;
  clip-path: polygon(0 0, 0 0, 0 0);

  /* 기본 요소*/
  body,
  html {
    margin: 0;
    font-size: 1rem;
    color: #181818;
  }
}
```

- 이번 과제에서는 `h2`태그나 `label`요소와 같이 숨겨야 할 요소들이 많으므로 clip-path를 활용한 숨김 속성을 사용하였습니다.
- 또한 `font-size`나 `color`와 같은 공통 요소는 body와 html에 위 코드와 같이 지정하였습니다.
- 네이버 로그인 폼에 경우 대부분 flex로 구성하였고 반응형으로 만들기 위해 `input`요소에 `flex-grow = 1`로 설정하였습니다.

## 과제 수행 후 느낀점
