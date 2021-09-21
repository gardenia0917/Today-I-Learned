# React




# intro
## Achievement Goals

- React의 3가지 특징 이해
 - 선언형 (Declarative)
 - 컴포넌트 기반
   - 하나의 기능 구현을 위해 여러 종류의 코드를 묶어둠
 - 범용성
- JSX 가 어째서 명시적인가?
  - 한 페이지를 보여 주기 위해 하나의 파일에 명시적으로 작성하기 위해 jsx 를 활용
- React Component (리액트 컴포넌트)의 필요성 이해
- `create-react-app` 으로 간단한 리액트 앱 실행

## JSX
### React에서 UI를 구성할 때 사용하는 문법 // JavaSvript를 확장한 문법
=> 브라우저가 바로 실행 X 
=> 이해할 수 있는 자바스크립트 코드로 변환해줄 때 필요한 것 `Babel`

- React에서는 DOM과 다르게 CSS,JSX 문법으로 웹 애플리케이션 개발 가능

=> `컴포넌트` 구조와 동작에 대한 코드를 한 뭉치로 적은 코드셋

JSX 없이도 React 요소를 만들 수 있지만 코드 복잡, 가독성 떨어짐

### JSX 활용

#### 규칙 1️⃣
=> 하나의 엘리먼트 안에 모든 엘리먼트 포함
-> 여러 엘리먼트 작성 하는 경우, opening tag 와 closing tag로 감싸야함

#### 규칙 2️⃣
=> 엘리먼트 클래스 사용시, className 으로 표기(class 대신)

#### 규칙 3️⃣
=> JSX에서 JacaScript 사용시 중괄호 이용`{}`

#### 규칙 4️⃣
=> React 엘리먼트가 JSX로 작성되면 `대문자` 로 시작해야함
-> 소문자일 경우 HTML로 인식
-> 대문자로 작성된 JSX 컴포넌트를 사용자 정의 컴포넌트라고 부름

#### 규칙 5️⃣
=> 조건부 렌더링에는 삼항연산자 사용
-> if (X) -> ? : (O)

#### 규칙 6️⃣
=> 여러개의 HTML 엘리먼트 표시시 ,map() 함수 이용

### Map() 메소드 활용
 [추가공부](https://ko.reactjs.org/docs/lists-and-keys.html#keys)
- `key 속성` `map`메소드 사용시 key 속성을 넣어야함
  - `map` 메소드 내부에 있는 첫 엘리먼트에 넣기

## Component
#### => 하나의 기능 구현을 위한 여러 종류의 코드 묶음
#### => UI를 구성하는 필수 요소
#### => 리액트의 심장

모든 리액트 애플리케이션은 최소 한 개의 컴포넌트를 가지고 있음
// 이 컴포넌트는 앱 내부로 근원의 역학을 함
// 최상위 컴포넌트는 자식 컴포넌트 가질 수 있음
=> 트리 구조 형상화


# Create React App
- `Create React App` 가 무엇인가
- `npx create-react-app` 으로 새로운 리액트 프로젝트 시작
-  리액트 랜덤 명언 앱을 따라 만들기
- `Create React App`  으로 만들어진 구성 이해


## Create React App ?
=> SPA를 쉽고 빠르게 개발 할 수 있도록 만들어진 툴 체인

#### 터미널 실습

파일 만든 후 (디렉토리 만든 후)
npx create-react-app '리액트 파일 입력'





