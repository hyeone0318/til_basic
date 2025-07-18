# 1. 퍼블리싱 환경 설정

- 회사에서 당황하지 않고 업무환경 설정이 가능해야 합니다.
- 아래 순서대로 퍼블리싱 세팅하면 문제없이 진행됩니다.
- 추천 프로그램
  - Byeond Compare 코드 비교 도구(상용버전)
    - https://www.scootersoftware.com/

## 1.1. Node.js 설치

- [node.js](https://nodejs.org/ko)
- Node.js는 로컬PC 및 서버PC에서 JS를 실행하는 환경 구성.
  - 서버는 대표적으로 웹서버(PC), 데이터베이스 서버(PC) 등이 있음.
  - 서버는 고객들이 인터넷으로 접속해서 자료를 사용하는 PC
- 추후 React에서 `NVM(Node Version Manage)`을 통한 관리 예정

## 1.2. VSCode 설치

- [VSCode](https://code.visualstudio.com/)

## 1.3. VSCode Extenstion 설치

- 아래 목록을 위주로 설치한다.

```
- PostCSS Sorting : 추후 설정(css 코드 순서정렬 도구 - 설정 필요)
- Auto Colse Tag
- Auto Rename Tag
- Bracket Pari Clor DLW
- CSS Peak
- HTML CSS Support
- HTML to CSS autocompletion
- Image preview
- indent-rainbow
- Korean Language Pack for... (VSCode 재실행 후 확인)
- Live Server
- Marketdown Preview Enhanced
- Material Icon Theme
- Night Owl (테마)
- Prettier-Code formatter (별도 참조)
```

## 1.4. Prettier 셋팅

- 줄맞춤, 들여쓰기, 따옴표, 세미콜론 등에 대한 문서의 포맷(컨벤션)을 맞추어줌
- 설정 버튼(VSCode의 모서리 왼쪽 아이콘⚙) 선택 > Settings 메뉴 선택
  ![Image](https://github.com/user-attachments/assets/bcdf5326-6705-4f31-81ec-9ae5ed27c24f)
- 검색내용으로 `format`으로 작성
- `Editor:Default Formatter` 설정
- `Editor:Format On Save` 설정
  ![Image](https://github.com/user-attachments/assets/e0375555-80a4-420a-9c5e-2e845eaed43d)
- VSCode 재실행 추천합니다.

# 2. 웹퍼블리싱 개발 구조 설정

- 반드시 프로젝트명은 `영어 소문자`, `단어_단어` 등의 특수기호 추천
- git 셋팅 먼저 진행 필요 : GitHub 포함해서

## 2.1. 추천 폴더 구조

- images 폴더 : 파일명.jpg, 파일명.png, 파일명.gif, 파일명.svg
  - jpg : 사진
  - gif : 그림(애니메이션 그림 가능, 배경 투명 가능)
  - png : 사진 + 배경 투명
  - svg : 디지털 숫자(벡터)로 계산해서 그림을 만듦(아이콘, 반응형 등에 적극 활용)
- css 폴더 : `모듈별.css` 파일들
- js 폴더 : `모듈별.js` 파일들
- assets 폴더 : 기타 파일들(영상, 음악, 계약서, 연락처 ... 포함)
- apis 폴더 : `백엔드 데이터 연동` 관련 파일들(파일명.json, 데이터 요청 등)
  - json : JavaScript Object Notation(자바스크립트 객체 문법 적용된 파일)

## 2.2. 기본 파일

- `index.html` 약속 됨.(파일명 변경 불가 : 엔트리포인트)
- 부가적으로 index만 작업하는 이유가 가장 어렵고 복잡하고 비주얼 합니다.
- 단축키 : `! + tab` 키로 기본형을 생성하자.(반드시 파일 저장 후)

# 3. HTML 태그의 이해

- 웹브라우저가 알아볼 수 있는 문법 구조
- DOM 구조로 해석 : Document Object Model
- https://velog.io/@clydehan/HTML-DOCTYPE%EC%9D%B4%EB%9E%80
- `<!DOCTYPE html>`

  - html 해석할 때 최신 html5 규칙으로 해석하라.
  - 수정은 주의해서 해야 합니다.
  - 유지 보수를 하는 경우에는 html의 첫 줄을 반드시 문의하고 수정해야 함.

- `head 태그`

  - 문서의 필요로한 정보를 작성하는 곳
  - 추후 icon 및 sns 연동 부분에서 주로 활용(`meta 태그`)
  - `SEO` (검색엔진최적화 내용)
  - js 파일, css 파일을 연결 배치 활용
  - 반드시 `title 태그` 내용 작성 필요
  - `GA4` 설정 내용을 작성하는 곳(Google Analytics)

- `body 태그`

  - 실제 화면에 보여질 내용을 배치함.

- <태그>내용</태그>
- 반드시 소문자로 모두 구성합니다.

## 3.1. `div 태그`

- <div>내용</div>
- 내용 배치의 레이아웃을 담당함.
- 기본적으로 `<div class="wrap"> </div>`를 배치하고 내용 작성함.
- 최초 구성 필수(경험-경력이 필요함.)
- 내용을 충분히 분석(`Figma, PRD` 분석)하고 난 이후에 `주석을 명시` 후 div 사용
- div 태그 역할에 맞는 이름을 `class로 지정`함.

## 3.2. `시멘틱 태그`

- 시멘틱 태그는 태그 단어 자체가 내용을 유추하도록 안내함.
- div로 내용을 구분 후 아래 영역은 태그를 변경하기를 추천합니다.
- `header 태그` : 검색엔진에서 내용을 기대함.(로고, 타이틀, 주메뉴, 검색, 회원기능 ...)
- `main 태그` : 컨텐츠 모음
- `footer 태그` : 검색엔진에서 내용을 기대함.(카피라이터, 주소, 연락처, 사이트 맵 ...)

## 3.3. 필수 태그

### 3.3.1. a 태그 : anchor

- 현재 웹브라우저 내용 갱신(페이지 이동) : `<a href="주소">글자/그림</a>`
- 웹브라우저 탭 생성(새탭 페이지) : `<a href="주소" target="_blank">글자/그림</a>`

### 3.3.2. form 태그 : 사용자 입력 양식

- 추천 UI 라이브러리
  - shadCN : https://ui.shadcn.com/docs/components
  - AntDesign : https://ant.design/components/overview
  - Mui : https://mui.com/material-ui/all-components
- action과 method 이해
  - `<form action="백엔드주소"></form>`
  - `<form action="백엔드주소" method="get"></form>`
    - 데이터 공개 : `http://127.0.0.1:5500/good.html?id=iu&pass=1234`
  - `<form action="백엔드주소" method="post"></form>`
    - 데이터 비공개 : `http://127.0.0.1:5500/good.html`
- input 태그 예제

```html
<form action="good.html" method="post">
  <!-- 기본정보 -->
  <fieldset>
    <legend>기본정보</legend>
    <label for="userid">아이디(4자~12자)</label> <br />
    <input
      type="text"
      id="userid"
      name="id"
      minlength="4"
      maxlength="12"
      required
      placeholder="아이디를 입력하세요."
    />
    <button>아이디 중복확인</button>
    <br />
    <br />
    <label for="useremail">이메일</label> <br />
    <input
      type="email"
      id="useremail"
      neme="email"
      required
      placeholder="example@example.com"
    />
    <br />
    <br />
    <label for="userpass">비밀번호(6자~16자)</label> <br />
    <input
      type="password"
      id="userpass"
      name="pwd"
      minlength="6"
      maxlength="16"
      required
      placeholder="비밀번호를 입력해주세요."
      autocomplete="off"
    />
  </fieldset>
  <!-- 상세정보 -->
  <fieldset>
    <legend>상세정보</legend>
    <label>국가 선택:</label>
    <select id="country" name="country">
      <option value="kr">한국</option>
      <option value="us">미국</option>
      <option value="cn">중국</option>
      <option value="jp">일본</option>
    </select>
    <br />
    <br />
    <label>성별</label> <br />
    <input type="radio" id="male" name="gender" value="male" checked />
    <label for="male">남성</label>
    <input type="radio" id="female" name="gender" value="female" />
    <label for="female">여성</label>
    <br />
    <br />
    <label>취미(다중선택가능)</label> <br />
    <input type="checkbox" id="coding" name="hobby" value="coding" checked />
    <label for="coding">코딩</label>

    <input type="checkbox" id="tour" name="hobby" value="tour" checked />
    <label for="tour">여행</label>

    <input type="checkbox" id="music" name="hobby" value="music" checked />
    <label for="music">음악</label>
    <br />
    <br />
    <label for="birthday">생년월일</label> <br />
    <input type="date" id="birthday" name="birthday" />
    <br />
    <br />
    <label for="file">첨부파일</label> <br />
    <input type="file" id="file" name="file" />
    <br />
    <br />
    <label for="intro">자기소개 : </label> <br />
    <textarea
      id="intro"
      name="intro"
      rows="5"
      cols="40"
      placeholder="자기소개를 입력하세요."
    ></textarea>
  </fieldset>
  <!-- 정보입력 -->
  <fieldset>
    <legend>정보입력</legend>
    <input type="reset" value="재작성" />
    <input type="submit" value="등록" />
  </fieldset>
</form>
```

### 3.3.3. ul 태그 : unOrderList(목록태그)

- 동일한 형태의 레이아웃이 반복된다면 묶어서 활용
- 동일한 기능이 반복된다면 묶어서 활용

### 3.3.4. image 태그

- 아이콘은 https://react-icons.github.io/react-icons/ 활용
- `<img src="이미지경로/파일명.확장자" alt="대체글" />`

# 4. CSS의 이해

- css 선택자

```css
태그 {
}
.클래스 {
}
#아이디 {
}
태그 태그 태그 {
}
.클래스 태그 태그 {
}
```

## 4.1. CSS 코딩 자리 3가지

- 인라인 css (추후 React에서는 인라인 방식을 많이 활용함 : css 우선순위 적용)

```html
  <태그 style=""> </태그>
```

- style 태그 css (추후 React에서는 object 방식으로 많이 활용함)

```html
<style></style>
<태그></태그>
```

- style 파일 link 방식 (추후 React에서는 많이 활용함 : 파일명.module.css)

```html
<link rel="stylesheet" href="경로/파일명.css" />
```

## 4.2. header css 실습

- `css/header.css` 파일

```html
<link rel="stylesheet" href="css/header.css" />
```

## 4.3. display의 이해

- block, inline, inline-block, none, flex ...

## 4.3.1. bolck

- 하나의 `침범할 수 없는 가로 영역`
- div, ul, li, h1~h6, p 등등
- 기본적으로 width: 100%
- css의 모든 값을 활용할 수 있다.(width, height, margin, padding 등)

### 4.3.2. inline

- 한개의 글자처럼 처리됩니다.
- width, height, margin, padding을 적용 못함
- a, img, span, b, strong 등등

### 4.3.3. inline-block

- inline과 block을 조합한다.
- 가로로 배치되면서 width, height 등을 자유롭게 활용함
- 엔터키에 의한 공백 한칸이 작성됨. (원하지 않는 공백이 영역에 들어감)

### 4.3.4. flex

- block이면서 inline이면서 가로 정렬, 세로 정렬, 여백조절 가능
- 가로로 레이아웃 배치 시 최적화
- https://studiomeal.com/archives/197
- justify-content, align-items, gap, flex: 숫자 등등

### 4.3.5. grid(추후 파악)

- block이면서 inline이면서 가로 정렬, 세로 정렬, 여백조절 가능
- `표`처럼 레이아웃 배치 시 최적화
- https://studiomeal.com/archives/533

### 4.3.6. none

- 화면에 html 태그가 없는 것처럼 처리
- js에서도 없다고 판단하여 초기 처리 코드 불가

## 4.4. 반응형의 이해

- 넓은 화면부터 html, css 작업
- 좁은 화면으로 html, css 마무리 진행 권장

### 4.4.1. 반응형 체크 사항

- html에 반드시 아래 코드가 있어야 합니다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### 4.4.2. 미디어 쿼리

- 큰 사이즈부터 작은 사이즈로 max-width를 추천합니다.
- 공백을 주의해야 합니다.
- 반드시 {} 안쪽에 원하는 css 코드 하셔야 합니다.

```css
@media and (max-width: 1280px) {
  원하는 css 작성
}
@media and (max-width: 1024px) {
  원하는 css 작성
}
@media and (max-width: 960px) {
  원하는 css 작성
}
@media and (max-width: 540px) {
  원하는 css 작성
}
```

## 4.5. 글꼴 셋팅하기

- 모든 css 및 html 작업 전에 결정하여야 합니다
- 디자이너 및 기획자에게 문의해야 합니다
- css의 body에 기본 글꼴 배치 권장함
- 절대 유료폰트 확인하고 활용

### 4.5.1. 구글 웹폰트 활용하기

- https://fonts.google.com/

### 4.5.2. 눈누 웹폰트 활용하기

- https://noonnu.cc/

## 4.6. position의 이해

- relative, absolute, fixed 등

### 4.6.1. absolute 주의사항

- 픽셀로 정확한 위치를 지정하는 경우 사용
- 반드시 상위 태그에 position이 명시되어야 함

```css
.엄마 {
  position: relative;
}

.자식 {
  position: absolute;
}
```

### 4.6.2. fixed란

- 무조건 웹브라우저를 기준으로 위치 설정

```css
.대상 {
  position: fixed;
  left: 0;
  top: 0;

  width: 100%;
  height: 50px;
  z-index: 999;
}
```

## 4.7. before, after의 이해

- 대표적으로 아이콘 출력하는 경우 많이 활용

```html
<대상> before 내용 after </대상>
```

```css
대상::after {
  content: "";
}
대상::before {
  content: "";
}
```

## 4.8. CSS 우선순위 (아주 중요합니다.)

- 어느 css가 마지막에 적용되는가?
- 기본 : 태그(작성순서 비교) ===> 클래스(작성순서 비교) ===> 아이디
- 범위(`공백`) 선택자 CSS로 다시 적용된다.
- 경로(`>`) 선택자 CSS로 다시 적용된다.
- css 문제해결 : F12 개발자 도구에서 확인(아래에서 윗방향으로 해결)
- 도저히 해결이 안된다면 `!important` 옵션을 사용합니다.

## 4.9. PostCSS Sorting 설치 및 설정

- css 속성 정렬하기
- 단축키 생성 : `shift + alt + p` 등록
- [참고](https://velog.io/@leejpsd/NHN-%EC%BD%94%EB%94%A9-%EC%BB%A8%EB%B2%A4%EC%85%98%EC%97%90-%EB%94%B0%EB%A5%B8-CSS-%EC%84%A0%EC%96%B8%EC%88%9C%EC%84%9C-PostCSS-Sorting-%EC%9D%B4%EC%9A%A9%ED%95%98%EA%B8%B0)

```json
"postcssSorting.config": {
   "properties-order": [
      /* Layout */
      "display",
      "grid",
      "grid-column-gap",
      "grid-row-gap",
      "grid-auto-flow",
      "grid-auto-rows",
      "grid-auto-columns",
      "justify-items",
      "align-content",
      "place-items",
      "gap",
      "align-items",
      "justify-content",
      "flex-wrap",
      "flex-basis",
      "flex-grow",
      "flex-shrink",
      "flex",
      "align-self",
      "flex-direction",

      /* Box */
      "margin",
      "margin-top",
      "margin-right",
      "margin-bottom",
      "margin-left",
      "padding",
      "padding-top",
      "padding-right",
      "padding-bottom",
      "padding-left",
      "border",
      "border-top",
      "border-bottom",
      "border-right",
      "border-left",
      "border-style",
      "border-color",
      "border-top-width",
      "border-right-width",
      "border-bottom-width",
      "border-left-width",
      "border-top-style",
      "border-right-style",
      "border-bottom-style",
      "border-left-style",
      "border-top-color",
      "border-right-color",
      "border-bottom-color",
      "border-left-color",
      "border-top-left-radius",
      "border-top-right-radius",
      "border-bottom-right-radius",
      "border-bottom-left-radius",
      "outline",
      "outline-width",
      "outline-style",
      "outline-color",
      "outline-offset",
      "box-shadow",
      "overflow",
      "overflow-x",
      "overflow-y",
      "clip",
      "position",
      "top",
      "right",
      "bottom",
      "left",
      "z-index",
      "width",
      "min-width",
      "max-width",
      "height",
      "min-height",
      "max-height",
      "float",
      "clear",
      "visibility",
      "vertical-align",

      /* Background */
      "background",
      "background-color",
      "background-image",
      "background-repeat",
      "background-attachment",
      "background-position",
      "background-clip",
      "background-origin",
      "background-size",

      /* Font */
      "font-family",
      "font-size",
      "font-style",
      "font-weight",
      "line-height",
      "color",
      "text-align",
      "text-decoration",
      "text-transform",
      "letter-spacing",
      "text-shadow",
      "white-space",
      "word-spacing",
      "word-break",
      "word-wrap",
      "text-indent",
      "direction",
      "unicode-bidi",
      "hyphens",

      /* Animation and Transition */
      "animation",
      "animation-name",
      "animation-duration",
      "animation-timing-function",
      "animation-delay",
      "animation-iteration-count",
      "animation-direction",
      "animation-fill-mode",
      "animation-play-state",
      "transition",
      "transition-property",
      "transition-duration",
      "transition-timing-function",
      "transition-delay",

      /* Other */
      "content",
      "counter-reset",
      "counter-increment",
      "quotes",
      "list-style",
      "list-style-position",
      "list-style-type",
      "caption-side",
      "empty-cells",
      "table-layout",
      "pointer-events",
      "cursor",
      "resize",
      "overflow-wrap",
      "scroll-snap-type",
      "scroll-padding",
      "scroll-padding-top",
      "scroll-padding-right",
      "scroll-padding-bottom",
      "scroll-padding-left",
      "scroll-behavior",
      "scroll-snap-align",
      "scroll-snap-margin",
      "scroll-snap-stop",
      "scrollbar-width",
      "scrollbar-color"
    ]
  }
```

# 5. javaScript의 이해

- Java는 객체지향 프로그래밍, javaScript는 스크립트 프로그래밍
- 웹브라우저용 js가 원본인데 V8 엔진만 추출해서 Node.js 만듦
- PC용 즉, 로컬용 js가 Node.js 입니다.
  (DB 제어, 네트워크, 소프트웨어, 앱 개발 등)

## 5.1. 기본적인 js의 역할(개인 주관)

- html, css 제어 js
- 데이터 연동 js

## 5.2. js 코딩 자리

- 가장 아랫 줄이 제일 좋은 코드 자리 입니다.

### 5.2.1. 인라인 방식

```html
<태그 onload="" onclick=""> </태그>
```

### 5.2.2. 태그 방식

```html
<script></script>
<태그></태그>
```

### 5.2.3. 파일 방식

```html
<script src="경로/파일명.확장자"></script>
<태그></태그>
```

## 5.3. js가 실행되는 시점 유의사항(htmlm, css 제어 시)

- html과 js가 모두 준비가 되면 실행되길 원함.

```js
window.addEventListener("DOMContentLoaded", function () {
  // 할일
});
```

- 이미지 등의 용량이 큰 리소스가 모두 준비되면 실행되길 원함.

```js
window.addEventListener("load", function () {
  // 할일
});
```

## 5.4. js를 이용한 태그 선택하기

```js
const tag = document.querySelector("태그")
const class = document.querySelector(".클래스")
const id = document.querySelector("#아이디")
const tags = document.querySelectorAll("태그 태그 태그")
const tags2 = document.querySelectorAll(".클래스 태그 태그")
```

## 5.5. 백틱을 이용한 변수값 출력

```js
const age = 20;
const tag = `<div>나이는 ${age}</div>`;
```

## 5.6. 문자를 html로 출력하기

```js
const tag = `<div>안녕</div>`;
const pos = document.querySelector(".hi");
pos.innerHTML = tag;
```

## 5.7. 원시(Primitive) 데이터 종류의 이해

- js에서 이해할 수 있는 자료의 종류를 `데이터 타입` 또는 `데이터 형`이라고 합니다.
- 영어로는 Data Type이라고 합니다.

### 5.7.1. 문자열

- 문자와 문자열은 다릅니다.

```js
const 변수명 = 변수값;
const nickname1 = "홍길동";
const nickname2 = "홍길동";
const nickname3 = `홍길동`;
```

### 5.7.2. 숫자

- 정수(양수, 음수), 실수(양소수, 음소수)

```js
const 변수명 = 변수값;
const age = 10;
const height = 180.5;
```

### 5.7.3. 불리언(참, 거짓)

- true, false

```js
const isLogin = true;
const isMember = false;
```

### 5.7.4. undefined

- 모든 변수의 초기값;
- 변수값이 정의가 안되었어요.

```js
let nickName;
```

### 5.7.5. null

- 개발자가 정말 값이 없다고 명시함.

```js
const = isLogin = null;
```

### 5.7.6. symbol

- 절대로 js 코드에서 절대로 중복이 안되는 내용 만드는 경우

## 5.8. 원시데이터를 모아서 만드는 데이터 종류의 이해

- 복합데이터 또는 참조형 데이터(Reference Data Type)

### 5.8.1. 배열(Array)

- 기호로는 `[]` 사용합니다.
- 배열은 순서(index)가 중요하므로 순서값 즉, 인덱싱을 관리합니다.
- 인덱스는 자동으로 0번부터 `,`마다 증가합니다.
- `변수명[인덱스 번호]`를 통해서 원하는 값 추출함.
- 배열은 `변수명.length`가 주어집니다.

```js
const arr = [1, 3, "안녕", true, false, null, undefined, symbol];
arr[3]; // true 추출
arr.length; // 8 출력
```

### 5.8.2. 객체

```js
const obj = {
  속성명1: 1,
  속성명2: "과학",
  속성명3: false,
};
obj.속성명1; // 1
obj.속성명2; // "과학"
obj.속성명3; // false
```

## 5.9. 반복문

- for문, while문, do while문
- 우선 for문이 활용율 90% 이상일 듯 합니다.
- for문의 특징은 몇 번 박복해야 할지 횟수를 아는 경우 활용

```js
for ( 초기값; 조건식; 증감식;) {
  // 할일
}

for(let i = 0; i < 10; i ++) {
  console.log(i);
}

```

## 5.10. 조건문

- if, switch
- 웹퍼블리싱에서는 if문이 코드에 90% 이상일 듯

```js
if(true 냐 false 냐 조건 판단) {
  // true 면 실행
}else{
  // false 면 실행
}
```
