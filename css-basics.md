# CSS 기초

**버전**: 1.0.0  
**최종 수정일**: 2024-01-20

## 목차
- [1. CSS 이해하기](#1-css-이해하기)
  - [CSS 소개](#css-소개)
  - [CSS 문법과 적용](#css-문법과-적용)
- [2. CSS 선택자](#2-css-선택자)
  - [기본 선택자](#기본-선택자)
  - [결합자](#결합자)
  - [의사 클래스와 의사 요소](#의사-클래스와-의사-요소)
- [3. 박스 모델](#3-박스-모델)
  - [박스 모델 구성 요소](#박스-모델-구성-요소)
  - [박스 사이징](#박스-사이징)
- [4. 레이아웃](#4-레이아웃)
  - [디스플레이](#디스플레이)
  - [포지션](#포지션)
  - [플렉스박스](#플렉스박스)
  - [그리드](#그리드)

# 4. CSS 이해하기

## 1) CSS 소개

CSS(Cascading Style Sheets)는 HTML을 시각적으로 꾸며줄 수 있는 언어.

- **목적**: 웹 페이지의 레이아웃과 스타일 정의
- **특징**: HTML과 분리되어 스타일 정보만을 담당
- **비유**: HTML이 건물의 구조라면, CSS는 인테리어와 같은 역할

### CSS의 중요성
- HTML 문서의 시각적 표현 담당
- 다양하고 독창적인 디자인 가능
- 하나의 CSS로 여러 HTML 페이지 스타일 지정 가능

## 2) CSS 문법과 적용

### CSS 기본 구문

```css
선택자 { 속성: 값; }
```

- **선택자(selector)**: 스타일을 적용할 HTML 요소 지정
- **속성(property)**: 변경할 스타일 속성
- **값(value)**: 속성에 적용할 값

### CSS 적용 방식

1. **인라인(Inline) 스타일**
   - HTML 요소의 style 속성에 직접 CSS 작성
   ```html
   <p style="color: blue;">This is a blue text.</p>
   ```

2. **내부(Internal) 스타일 시트**
   - HTML 문서의 `<head>` 섹션 내 `<style>` 태그에 CSS 작성
   ```html
   <head>
     <style>
       p { color: blue; }
     </style>
   </head>
   ```

3. **외부(External) 스타일 시트**
   - 별도의 .css 파일에 스타일 정의 후 HTML에 연결
   ```html
   <head>
     <link rel="stylesheet" href="styles.css">
   </head>
   ```

4. **@import 방식**
   - 다른 CSS 파일 내에서 또 다른 CSS 파일 불러오기
   ```css
   @import url("another-stylesheet.css");
   ```

### 주의사항
- 인라인 스타일은 유지보수가 어려워 권장되지 않음
- 외부 스타일 시트가 가장 효율적이고 널리 사용됨

## 3) CSS 선택자

### 기본 선택자

1. **요소 선택자**
   - HTML 태그 이름으로 선택
   ```css
   p { color: blue; }
   ```

2. **클래스 선택자**
   - 특정 클래스를 가진 요소 선택
   ```css
   .highlight { background-color: yellow; }
   ```

3. **ID 선택자**
   - 특정 ID를 가진 요소 선택
   ```css
   #header { font-size: 24px; }
   ```

4. **전체 선택자**
   - 모든 요소 선택
   ```css
   * { margin: 0; padding: 0; }
   ```

### 결합자(Combinators)

1. **자손 선택자**
   - 특정 요소의 자손 요소 선택
   ```css
   div p { font-style: italic; }
   ```

2. **자식 선택자**
   - 특정 요소의 직계 자식 요소 선택
   ```css
   ul > li { list-style-type: square; }
   ```

3. **인접 형제 선택자**
   - 특정 요소의 바로 다음 형제 요소 선택
   ```css
   h1 + p { font-weight: bold; }
   ```

### 속성 선택자

- 특정 속성을 가진 요소 선택
```css
[type="text"] { border: 1px solid gray; }
```

### 가상 클래스 선택자

- 요소의 특정 상태를 선택
```css
a:hover { text-decoration: underline; }
```

### 가상 요소 선택자

- 요소의 특정 부분 선택
```css
p::first-line { font-weight: bold; }
```

## 4) 선택자의 우선순위

1. **중요도(!important)**
   - 가장 높은 우선순위, 사용 주의 필요
   ```css
   p { color: red !important; }
   ```

2. **구체성**
   - 인라인 스타일 > ID > 클래스/속성/가상 클래스 > 요소/가상 요소
   ```css
   #header .nav { color: blue; }  /* 더 구체적이므로 우선 적용 */
   nav { color: green; }
   ```

3. **선언 순서**
   - 나중에 선언된 스타일이 우선 적용

### 상속

- 부모 요소의 일부 스타일 속성이 자식 요소에 상속
- 모든 속성이 상속되는 것은 아님 (예: 박스 모델 속성은 상속되지 않음)

```css
body {
  font-family: Arial, sans-serif;  /* 이 속성은 자식 요소들에 상속됨 */
}
```

CSS 선택자를 잘 이해하고 활용하면 HTML 구조를 변경하지 않고도 원하는 요소에 스타일을 효과적으로 적용할 수 있음.

# 5. 단위, 배경, 박스모델

## 1) 단위

CSS에서는 다양한 단위를 사용하여 요소의 크기와 위치를 지정 가능.

### 절대 길이 단위
- **px**: 픽셀 (1px = 1/96th of 1 inch)
- **pt**: 포인트 (1pt = 1/72 of 1 inch)

### 상대 길이 단위
- **%**: 부모 요소에 대한 백분율
- **em**: 요소의 font-size를 기준으로 계산
- **rem**: 루트 요소의 font-size를 기준으로 계산
- **vw**: 뷰포트 너비의 1%

## 2) 배경 (background)

`background` 속성은 요소의 배경을 설정하는 데 사용.

### 주요 background 속성
- **background-color**: 배경 색상 지정
- **background-image**: 배경 이미지 지정
- **background-repeat**: 배경 이미지 반복 설정
- **background-position**: 배경 이미지 위치 설정
- **background-attachment**: 배경 이미지의 스크롤 여부 설정

### 축약형 사용
```css
background: [color] [image] [repeat] [attachment] [position];
```

## 3) 박스모델

HTML의 모든 요소는 박스 형태로 구성됨 -> 박스모델이라 함.

### 박스모델의 구성
1. **Content**: 실제 내용이 들어가는 영역
2. **Padding**: 내용과 테두리 사이의 여백
3. **Border**: 패딩 주변의 테두리
4. **Margin**: 요소 외부의 여백

### width와 height
- `width`와 `height`는 기본적으로 content 영역의 크기 지정.
- 전체 요소의 크기 = width/height + padding + border + margin

### padding
- 내용과 테두리 사이의 여백 지정.
- 음수 값을 사용할 수 없음.

### border
- 요소의 테두리 지정.
- `border-width`, `border-style`, `border-color`로 구성.

### margin
- 요소 외부의 여백 지정.
- 음수 값을 사용할 수 있음.
- 인접한 요소 간 margin collapse(마진 병합) 현상이 발생할 수 있음.

### box-sizing 속성
- `box-sizing: content-box;` (기본값): width/height가 content 영역만의 크기를 지정
- `box-sizing: border-box;`: width/height가 padding과 border를 포함한 크기를 지정

### 주의사항
- `width`와 `height`에 퍼센트(%) 값을 사용할 때, 부모 요소의 크기를 기준으로 계산.
- `height`의 퍼센트 값은 부모 요소에 명시적인 높이가 지정되어 있어야 제대로 동작.

이런 식으로 CSS를 사용하여 웹 페이지의 레이아웃과 디자인을 효과적으로 제어할 수 있음.

# 6. 폰트, 텍스트

## 1) 타이포그래피 (Typography)

타이포그래피의 구조를 이해하는 것은 폰트 스타일링의 기초.

- **em**: 폰트의 전체 높이
- **ex (x-height)**: 소문자 'x'의 높이
- **baseline**: 소문자 'x'를 기준으로 한 하단 라인
- **descender**: baseline 아래로 내려가는 영역 (g, j, p, q, y)
- **ascender**: x-height 위로 올라가는 영역 (b, d, h, l)

## 2) font-family

글꼴을 지정하는 속성.

```css
font-family: family-name | generic-family ( | initial | inherit );
```

- **family-name**: 사용할 폰트의 이름 (쉼표로 구분하여 여러 개 선언 가능)
- **generic-family**: 대체 폰트 그룹 (serif, sans-serif 등)

예시:
```css
font-family: Helvetica, Dotum, '돋움', Apple SD Gothic Neo, sans-serif;
```

## 3) line-height

줄 높이를 지정하는 속성.

```css
line-height: normal | number | length | percentage | initial | inherit;
```

- **normal**: 브라우저의 기본 값 (보통 1.2)
- **number**: font-size를 기준으로 한 배수
- **length**: px, em 등의 고정 수치
- **percentage**: font-size를 기준으로 한 백분율

## 4) font-size

글꼴의 크기를 지정하는 속성.

```css
font-size: keyword | length | percentage | initial | inherit;
```

- **keyword**: xx-small, x-small, small, medium, large, x-large, xx-large
- **length**: px, em, rem 등의 단위
- **percentage**: 부모 요소의 font-size를 기준으로 한 백분율

## 5) font-weight

글꼴의 굵기를 지정하는 속성.

```css
font-weight: normal | bold | bolder | lighter | number | initial | inherit;
```

- **normal**: 기본 값 (400)
- **bold**: 굵게 (700)
- **number**: 100부터 900까지의 100 단위 숫자

## 6) font-style

글꼴의 스타일을 지정하는 속성.

```css
font-style: normal | italic | oblique | initial | inherit;
```

## 7) font-variant

소문자를 작은 대문자로 변환하는 속성.

```css
font-variant: normal | small-caps | initial | inherit;
```

## 8) font (축약형)

font 관련 속성들을 한 번에 선언할 수 있는 축약형 속성.

```css
font: font-style font-variant font-weight font-size/line-height font-family;
```

## 9) @font-face (웹 폰트)

웹 폰트를 정의하고 사용하는 방법.

```css
@font-face {
    font-family: 'WebFontName';
    src: url('font-file-path.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}
```

## 10) vertical-align

인라인 요소나 테이블 셀 요소의 수직 정렬을 지정하는 속성.

```css
vertical-align: baseline | sub | super | text-top | text-bottom | middle | top | bottom | length | percentage;
```

## 11) text-align

텍스트의 수평 정렬을 지정하는 속성.

```css
text-align: left | right | center | justify | initial | inherit;
```

## 12) text-indent

텍스트 블록의 첫 줄 들여쓰기를 지정하는 속성.

```css
text-indent: length | percentage | initial | inherit;
```

## 13) text-decoration

텍스트의 장식(밑줄, 취소선 등)을 지정하는 속성.

```css
text-decoration: text-decoration-line text-decoration-color text-decoration-style | initial | inherit;
```

## 14) 단어 관련 속성

- **white-space**: 요소 내의 공백 처리 방법을 지정
- **letter-spacing**: 글자 간 간격(자간) 지정
- **word-spacing**: 단어 간 간격 지정
- **word-break**: 단어의 분리 방법 지정
- **word-wrap**: 긴 단어의 줄바꿈 처리 방법 지정

-> 웹 페이지의 텍스트를 효과적으로 스타일링하고 가독성을 향상시킬 수 있음.

# 미디어 쿼리

## 1. 디스플레이 크기에 따른 배경색 변경

### 조건
- 0~767px: gold
- 768px~1024px: lightblue
- 1025px 이상: lightpink

### 기본 코드

```css
@media (max-width: 767px) {
    body { background-color: gold; }
}
@media (min-width: 768px) and (max-width: 1024px) {
    body { background-color: lightblue; }
}
@media (min-width: 1025px) {
    body { background-color: lightpink; }
}
```

### Mobile First 접근

```css
body { background-color: gold; }
@media (min-width: 768px) and (max-width: 1024px) {
    body { background-color: lightblue; }
}
@media (min-width: 1025px) {
    body { background-color: lightpink; }
}
```

### Desktop First 접근

```css
body { background-color: lightpink; }
@media (min-width: 768px) and (max-width: 1024px) {
    body { background-color: lightblue; }
}
@media (max-width: 767px) {
    body { background-color: gold; }
}
```

## 2. 인쇄 시 스타일 적용

### 조건
- 앵커 요소의 URL 출력
- 앵커 요소의 밑줄 제거

### 코드

```css
@media print {
    a { text-decoration: none; }
    a:after { display: inline; content: '(' attr(href) ')'; }
}
```

## Viewport의 이해

모바일 웹 개발에서 중요한 viewport 설정:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- `width=device-width`: 뷰포트의 너비를 기기의 스크린 너비로 설정
- `initial-scale=1.0`: 초기 화면 배율을 1.0(100%)으로 설정

반응형 웹 디자인의 기본, 모바일 기기에서 웹 페이지가 적절하게 표시되도록 함.

### 더 알아보기
- [CSS Tricks](https://css-tricks.com/)
- [MDN CSS 가이드](https://developer.mozilla.org/ko/docs/Web/CSS)
- [CSS 레이아웃](https://ko.learnlayout.com/)

### 실습하기
예제 코드는 [examples/styles.css](examples/styles.css)에서 확인할 수 있습니다.

### 유용한 도구
- [CSS Grid Generator](https://cssgrid-generator.netlify.app/)
- [Flexbox Froggy](https://flexboxfroggy.com/#ko)
- [CSS Diner](https://flukeout.github.io/)