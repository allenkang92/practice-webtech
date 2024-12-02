# HTML 기초

**버전**: 1.0.0  
**최종 수정일**: 2024-01-20

## 목차
- [1. HTML 이해하기](#1-html-이해하기)
  - [HTML 소개](#html-소개)
  - [HTML 문법 - 태그](#html-문법---태그)
  - [HTML 문법 - 속성](#html-문법---속성)
  - [HTML 문법 - 태그 중첩](#html-문법---태그-중첩)
- [2. HTML 태그](#2-html-태그)
  - [제목과 단락 요소](#제목과-단락-요소)
  - [텍스트를 꾸며주는 요소](#텍스트를-꾸며주는-요소)
  - [앵커 요소](#앵커-요소)
  - [의미가 없는 컨테이너 요소](#의미가-없는-컨테이너-요소)
  - [리스트 요소](#리스트-요소)
  - [이미지 요소](#이미지-요소)
  - [테이블 요소](#테이블-요소)
  - [폼 요소](#폼-요소)
- [3. 콘텐츠 모델, 시맨틱 마크업, 블록 & 인라인](#3-콘텐츠-모델-시맨틱-마크업-블록--인라인)
  - [콘텐츠 모델](#콘텐츠-모델)
  - [시맨틱 마크업](#시맨틱-마크업)
  - [블록 & 인라인 요소](#블록--인라인-요소)

## 1. HTML 이해하기

### HTML 소개

HTML(Hyper Text Markup Language)은 웹 페이지를 만드는 데 사용되는 기본적인 마크업 언어.

- **목적**: 웹에서 정보를 구조화하고 표현
- **특징**: 태그를 사용하여 문서 구조 정의
- **역사**: 1990년대 팀 버너스리가 개발

### HTML 문법 - 태그

HTML의 기본 구성 요소는 태그입니다.

```html
<태그명>내용</태그명>
```

- **시작 태그**: `<태그명>`
- **종료 태그**: `</태그명>`
- **내용**: 태그 사이에 위치
- **요소**: 시작 태그, 내용, 종료 태그를 모두 포함한 전체

예시:
```html
<h1>Hello, HTML</h1>
```

### HTML 문법 - 속성

태그에 추가 정보를 제공하거나 동작을 제어하는 데 사용.

```html
<태그명 속성명="속성값">내용</태그명>
```

- 여러 속성 사용 가능 (공백으로 구분)
- 글로벌 속성과 특정 태그 전용 속성 존재

예시:
```html
<h1 id="title" class="main">Hello, HTML</h1>
```

### HTML 문법 - 태그 중첩

태그 안에 다른 태그를 포함 가능.

- 올바른 중첩: 부모 태그 내에서 자식 태그가 완전히 열리고 닫혀야 함

```html
<h1>Hello, <i>HTML</i></h1>
```

### HTML 문법 - 빈 태그

내용이 없는 태그를 빈 태그.

- 종료 태그가 없음
- 주로 브라우저가 직접 내용을 그리는 경우 사용

예시:
```html
<br>
<img src="image.jpg">
<input type="text">
```

### HTML 문법 - 공백

HTML에서 두 칸 이상의 공백과 줄바꿈은 하나의 공백으로 처리.

### HTML 문법 - 주석

주석은 코드에 설명을 추가하거나 일시적으로 코드를 비활성화하는 데 사용.

```html
<!-- 이것은 주석쓰 -->
```

### HTML 문서의 기본 구조

```html
<!DOCTYPE html>
<html lang="ko">
    <head>
        <meta charset="UTF-8">
        <title>문서 제목</title>
    </head>
    <body>
        <h1>Hello, HTML</h1>
    </body>
</html>
```

- `<!DOCTYPE html>`: 문서 타입 선언
- `<html>`: 루트 요소
- `<head>`: 문서 메타데이터
- `<body>`: 문서 본문 내용

## 2. HTML 태그

### 제목과 단락 요소

- `<h1>` ~ `<h6>`: 제목 태그
- `<p>`: 단락 태그
- `<br>`: 줄바꿈 태그

### 텍스트를 꾸며주는 요소

- `<b>`: 굵은 글씨
- `<i>`: 기울임 글씨
- `<u>`: 밑줄
- `<s>`: 취소선

### 앵커 요소

- `<a href="URL">`: 링크 생성
  - `target="_blank"`: 새 창에서 열기

### 의미가 없는 컨테이너 요소

- `<div>`: 블록 레벨 컨테이너
- `<span>`: 인라인 레벨 컨테이너

### 리스트 요소

- `<ul>`: 순서 없는 목록
- `<ol>`: 순서 있는 목록
- `<li>`: 목록 항목
- `<dl>`, `<dt>`, `<dd>`: 정의 목록

### 이미지 요소

- `<img src="이미지URL" alt="대체텍스트">`: 이미지 삽입

### 테이블 요소

- `<table>`: 표 생성
- `<tr>`: 행
- `<th>`: 제목 셀
- `<td>`: 데이터 셀
- `<caption>`: 표 제목
- `<thead>`, `<tbody>`, `<tfoot>`: 표 구조화

### 폼 요소

- `<form>`: 폼 생성
  - `action`: 데이터를 보낼 서버 주소
  - `method`: 데이터 전송 방식 (get/post)

- `<input>`: 다양한 입력 필드
  - `type="text"`: 텍스트 입력
  - `type="password"`: 비밀번호 입력
  - `type="radio"`: 라디오 버튼
  - `type="checkbox"`: 체크박스
  - `type="file"`: 파일 업로드
  - `type="submit"`: 제출 버튼
  - `type="reset"`: 초기화 버튼
  - `type="button"`: 일반 버튼

- `<select>`, `<option>`: 선택 목록
- `<textarea>`: 여러 줄 텍스트 입력
- `<button>`: 버튼 생성
- `<label>`: 폼 요소에 레이블 지정
- `<fieldset>`, `<legend>`: 폼 요소 그룹화

### 예시 코드

```html
<form action="">
  <fieldset>
    <legend>기본 정보</legend>
    <label for="userid">아이디: </label>
    <input type="text" id="userid" placeholder="영문으로만 써주세요"><br>
    <label for="userpw">비밀번호: </label>
    <input type="password" id="userpw"><br>
    성별: 
    <label for="male">남자</label>
    <input type="radio" name="gender" id="male" checked>
    <label for="female">여자</label>
    <input type="radio" name="gender" id="female">
  </fieldset>
  
  <fieldset>
    <legend>부가 정보</legend>
    취미: 
    <input type="checkbox" name="hobby" checked> 영화 감상
    <input type="checkbox" name="hobby"> 음악 감상
    <input type="checkbox" name="hobby"> 독서<br>
    프로필 사진: <input type="file"><br>
    사는 지역: 
    <select>
      <option>서울</option>
      <option>경기</option>
      <option>강원</option>
      <option selected>제주</option>
    </select><br>
    자기소개: 
    <textarea cols="30" rows="5" placeholder="자기소개는 짧게 해주세요."></textarea><br>
    <button type="submit">전송</button>
    <button type="reset">취소</button>
  </fieldset>
</form>
```

## 3. 콘텐츠 모델, 시맨틱 마크업, 블록 & 인라인

### 1) 콘텐츠 모델

HTML5에서는 요소들의 성격에 따라 7가지 카테고리로 분류:

1. **Metadata Content**: 문서의 메타데이터를 정의 (예: `base`, `link`, `meta`, `noscript`, `script`, `style`, `title`)
2. **Flow Content**: 문서의 자연스러운 흐름에 따라 배치되는 대부분의 요소
3. **Sectioning Content**: 문서의 구조를 정의 (예: `article`, `aside`, `nav`, `section`)
4. **Heading Content**: 섹션의 헤더를 정의 (예: `h1`, `h2`, `h3`, `h4`, `h5`, `h6`)
5. **Phrasing Content**: 텍스트와 텍스트를 꾸미는 요소
6. **Embedded Content**: 외부 콘텐츠를 표현 (예: `audio`, `canvas`, `embed`, `iframe`, `img`, `math`, `object`, `svg`, `video`)
7. **Interactive Content**: 사용자와 상호작용하는 요소 (예: 폼 요소들)

### 2) 시맨틱 마크업

시맨틱 마크업은 의미에 맞는 태그를 사용하여 문서를 구조화하는 방식.

- 예시:
  ```html
  <strong>중요한</strong> vs <b>굵은</b>
  <em>강조하는</em> vs <i>기울어진</i>
  <ins>새롭게 추가된</ins> vs <u>밑줄친</u>
  <del>삭제된</del> vs <s>중간선이 있는</s>
  ```

- 시맨틱 마크업의 이점:
  - 검색 엔진 최적화 (SEO)
  - 접근성 향상
  - 코드의 가독성과 유지보수성 향상

### 3) HTML5 시맨틱 요소

HTML5에서 새로 추가된 주요 시맨틱 요소들:

- `<article>`, `<aside>`, `<figcaption>`, `<figure>`, `<footer>`, `<header>`, `<main>`, `<mark>`, `<nav>`, `<section>`, `<time>`

### 4) 블록 & 인라인 요소

#### 블록 레벨 요소
- 특징:
  - 부모 요소의 전체 가로 영역을 차지
  - 새로운 줄에서 시작하고 끝남
  - 다른 블록 레벨 및 인라인 요소를 포함 가능
- 예: `<div>`, `<h1>-<h6>`, `<p>`, `<ul>`, `<li>`, `<table>`

#### 인라인 레벨 요소
- 특징:
  - 콘텐츠의 흐름을 방해하지 않음
  - 줄 바꿈 없이 한 줄에 표시
  - 일반적으로 블록 레벨 요소를 포함할 수 없음 (예외: `<a>` 태그)
- 예: `<span>`, `<a>`, `<img>`, `<em>`, `<strong>`

이러한 구분은 요소의 기본적인 표시 방식을 결정하지만, CSS를 통해 변경 가능.

### 더 알아보기
- [HTML Living Standard](https://html.spec.whatwg.org/)
- [MDN HTML 가이드](https://developer.mozilla.org/ko/docs/Web/HTML)
- [HTML Best Practices](https://github.com/hail2u/html-best-practices)

### 실습하기
예제 코드는 [examples/index.html](examples/index.html)에서 확인할 수 있습니다.
