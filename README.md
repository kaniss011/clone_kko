# 카드리스트 만들기

## 1. 주의 사항

```
a 태그는 너비와 높이를 줄 수 없다.
이유는 초기값이 display: inline 이라서.
```

```
a 태그에 너비, 높이, 마진, 패딩 주려면
display: block 을 손으로 적어준다.
팁! display: flex 를 준다.
```

```
span 태그는 너비와 높이를 줄 수 없다.
이유는 초기값이 display: inline 이라서.
```

```
span 태그에 너비, 높이, 마진, 패딩 주려면
display: block 을 손으로 적어준다.
팁! display: flex 를 준다.
```

## 2. 정말 중요한 내용

### 2.1. position 을 필수로 이해하셔야 해요.

#### 2.1.2. postion:fixed

```
웹 브라우저 기준으로 위치 고정
스크롤 되어도
화면이 넓어도
화면이 좁아도
화면이 짧아도
위치고정
```

- 주의사항

```
postion: fixed 하면 웹브라우저 기준이라서
화면에 보이는 내용의 레이아웃에서 높이가 반영이 안된다.
```

```
postion: fixed 하면 너비를 주셔야 합니다.
배경색도 주셔야 합니다.
웹브라우저 기준으로 left, top, bottom, right 도 설정
```

```
position:fixed 하시면
우선 전체너비를 기준으로
내용과 구분해서 div 구성하시기를 추천합니다.
```

```
화면 즉, z-index 값을 많이 줍니다.
z-index: 999999999999999
```

#### 2.1.3. postion:absolute

- fixed 와 똑 같다.
- 차이점은 body를 기준으로 한다.
- 반드시 원하는 css 에 relative 가 있으면 기준이 바뀐다.

#### 2.1.4. postion:relative

- absolute 의 기준을 세운다.

# 참고사항

## 1. 아이콘 폰트

- https://fontawesome.com
- https://xpressengine.github.io/XEIcon
  : index.html <link> 태그 확인

### 1.1. 본프로젝트 활용 아이콘 폰트

- https://react-icons.github.io/react-icons

## 2. css 초기화

- reset.css
  : https://meyerweb.com/eric/tools/css/reset/reset.css
  : 간략한 정리

- normalize.css
  : https://necolas.github.io/normalize.css/8.0.1/normalize.css
  : 상세한 정리

- 우리가 만든 common.css 파일

```css
@charset "utf-8";
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Inter&display=swap");

* {
  margin: 0px;
  padding: 0;
  box-sizing: border-box;
  /* outline-style: none; */
}
a {
  color: #1e1e1e;
  text-decoration: none;
}
ul,
ol,
li {
  list-style: none;
}
html {
  font-size: 14px;
  overflow-x: hidden;
}

body {
  font-family: "Inter", "Noto Sans KR", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-optical-sizing: auto;
  color: #1e1e1e;
  font-size: 14px;
}
```

- 필수 주의 사항

```
반드시 reset 또는 normalize 를 먼저배치하고
본인의 css 를 배치해야합니다.
그렇지 않으면 우리 css 가 덮어써 져서 정상적 구성 불가능

```

```html
<link
  rel="stylesheet"
  href="https://meyerweb.com/eric/tools/css/reset/reset.css"
/>
<link
  rel="stylesheet"
  href="https://necolas.github.io/normalize.css/8.0.1/normalize.css"
/>
<link
  rel="stylesheet"
  href="//cdn.jsdelivr.net/npm/xeicon@2.3.3/xeicon.min.css"
/>
<link rel="stylesheet" href="./css/common.css" />
<link rel="stylesheet" href="./css/header.css" />
<link rel="stylesheet" href="./css/main.css" />
<link rel="stylesheet" href="./css/card-list.css" />
<link rel="stylesheet" href="./css/footer.css" />
```

## 3. inline, block, inline-block 정리

### 3.1. display:inline

```
 <span>, <b>, <strong>, <a>, <img> ...
```

- 가로로 배치된다.
- 너비, 높이 비활성
- 패딩, 마진 일부 미지원
- 글자처럼 옆으로 계속 배치된다.

### 3.2. display: block

```
<div>, <header>, <main>, <footer>
<ul>, <li>, <h1>, <h2> ....
```

- 자동으로 너비가 100% 기본값
- 너비, 높이, 마진, 패딩... 모두 가능

### 3.3. display: inline-block

- inline 이면서 너비, 높이등을 셋팅, 즉 block 도 같이 부영
- display:inline-block
- 기본너비는 지정하지 않으면 내용물 만큼 소비
- 가로로 연속 배치가 가능하다.
