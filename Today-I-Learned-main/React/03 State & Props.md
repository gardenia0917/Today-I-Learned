# React State & Props

## Achievement Goals
- state, props 개념 이해
- React함수 컴포넌트(React Function Component)에서 state hook 이용 state 정의 및 변경
- React Component에 props전달 가능
- 이벤트 핸들러 함수 React 에 이용가능
- 실제 웹 앱을 보고 state props 판단
- 실제 웹 앱을 보고 state props 위치 정하기
- React 단방향 데이터 흐름(One-way data flow) 설명 가능

## Props

### Props 특징
#### 컴포넌트의 속성 의미
=> 성별이나 이름처럼 `변하지 않는` 외부로 부터 전달 받은 값
#### 부모(상위) 컴포넌트 로부터 전달 받은 값
=> 컴포넌트가 최초 렌더링 될때 출력되는 `초기 값`으로 사용 가능
#### 객체 형태
#### 읽기 전용
=> 외부로 전달 받아 변하지 않는 값이므로 함부로 변경 될 수 없는 `읽기 전용 객체`

### How to use props

🔻 하위 컴포넌트에 전달 하고자 하는 속성과 값 정의
🔻 props 이용 정의된 값과 속성 전달
🔻 전달 받은 props 렌더링

2개의 컴포넌트 선언

~~~
function a() {
  return (
    <div className="a">
      <h1>a</h1>
      <b /> // a 컴포넌트에 b 컴포넌트 작성
    </div>
  );
};

function b() {
  return (
    <div className="b"></div>
  );
};
~~~
---
### 💪 Hands-on❗❗

#### 1️⃣ 전달하고자 하는 속성 정의 하기

HTML에서의 정의하기
`<a href="www.naver.com">Click me to visit Naver</a>`

React에서는 전달하고 자 하는 값을 중괄호 {} 로 감싸주기 
`<컴포넌트 attribute={value} />`

⬆️ 방법 대로 하면
`<b text={"I'm b!"} />`
이걸
#### 2️⃣ b 컴포넌트에 넣어준다.
~~~
function b(props) { // 이렇게 넣어주기!!
  return (
    <div className="b"></div>
  );
};
~~~
#### 3️⃣ props 렌더링 하기
JSX안에 직접 불러서 사용.
props 는 `객체`이므로 {key : value} 형태로
`dot notation` 사용 가능!

~~~
function b(props) {
  return (
    <div className="b">
      <p>{props.text}</p> // 짠!
    </div>
  );
};
~~~

완성!
~~~
function a() {
  return (
    <div className="a">
      <h1>a</h1>
      <b text={"I'm b"} />
    </div>
  );
}

function b(props) {
  return (
    <div className="b">
      <p>{props.text}</p>
    </div>
  );
}
~~~
---
### 또 다른 방법이 있을까 ❓

`<컴포넌트>입력내용</컴포넌트>`
~~~
function a() {
  return (
    <div className="a">
        <h1>a</h1>
        <Child>I'm b</Child> // text 안쓰고
    </div>
  );
};

function b(props) {
  return (
    <div className="b">
        <p>{props.children}</p> //여기서 바로 밸류값 접근
    </div>
  );
};
~~~
## State
### State 특징
=> 애플리케이션의 `상태`
=> 컴포넌트 내에서 변할 수 있는 값

### State hook, useState

#### How to use useState ❓
1️⃣ `useState`를 이용하려면 React로 부터 불러와야함
`import { useState } from "react";`

2️⃣ `useState`를 컴포넌트 안에서 호출
=> 변수 `state`를 선언하는 것과 같음
-> 변수 이름은 상관 없음
=> 일반적이라면 함수가 끝날 때 변수도 사라지지만, React에 의해 끝까지 살아남아있음
~~~
function CheckboxExample() {
// 새로운 state 변수를 선언, 여기서는 이것을 isChecked 라 명명함
const [isChecked, setIsChecked] = useState(false);
~~~

풀어쓰면

~~~
 const stateHookArray = useState(false); // 2번
 const isChecked = stateHookArray[0];
 const setIsChecked = stateHookArray[1];
~~~

=>`useState`를 호출하면 배열 반환
->여기서 배열의 0번째 요소는 `현재 state변수` 
  1번째 요소는 `이 변수를 갱신할 수 있는 함수`
  
`useState` 수도 코드
> `const [state 저장 변수, state 갱신 함수] = useState(상태 초기 값);`


3️⃣ 실제 코드 작성하기

~~~
   function CheckboxExample() {
   const [isChecked, setIsChecked] = useState(false);
// const [state 저장 변수, state 갱신 함수] = useState(state 초기 값);
~~~

- `isChecked` : state 저장 변수
- `setIsChecked` : 갱신 함수
- `useState` : hook
- `false` : 초기화 값

4️⃣ state 변수 값 사용 하려면 JSX 엘리먼트 안에 불러 사용.
->`isChecked` 가 `boolean` 값 쓰므로 삼항 연산자 사용 (조건?참일때 :거짓일 때)

`<span>{isChecked ? "Checked!!" : "Unchecked"}</span>`


### ⭕ state 갱신 // 이해가 안된다....

1️⃣ state 변수를 갱신 할 수 있는 함수 `setIsChecked` 호출

2️⃣ `input[type=checkbox]` 이게 변경 되면 그에 따라 `Ischecked`가 변경 되야함

3️⃣ ` input[type=checkbox]` 변경시 `onChange` 이벤트 발생

4️⃣  `onChange` 이벤트가 이 이벤트 핸들러 함수인 `handleChecked`호출 하고 이 함수가 `setIsChecked` 함수 호출하게됨

5️⃣ 이 결과에 따라 `isChecked` 함수 갱신. React는 새로운 `isChecked` 변수를 `CheckboxExample` 컴포넌트에 넘겨 해당 컴포넌트 다시 랜더링
예시
~~~
function CheckboxExample() {
  const [isChecked, setIsChecked] = useState(false);

  const handleChecked = (event) => {
    setIsChecked(event.target.checked);
  };

  return (
    <div className="App">
      <input type="checkbox" checked={isChecked} onChange={handleChecked} />
      <span>{isChecked ? "Checked!!" : "Unchecked"}</span>
    </div>
  );
}
~~~

### ❌ 주의 사항 ❌
- React 컴포넌트는 state가 변경 되면 새롭게 호출, 리렌더링 됨
- React state는 상태 변경 함수 호출로 변경 되야함
=> 강제 변경 안됨
=> 상태 변경 함수 사용은 지켜야 합니다.
-> 강제로 하면 오류 행김

## Hands-on 1️⃣
### => React의 Event handling 방식은 DOM의 방식과 유사
- React에서 이벤트는 소문자 대신 camelCase(카멜 케이스) 사용
- JSX를 사용 문자열이 아닌 함수로 Event handler를 전달

HTML 이벤트 처리 방식
~~~
<button onclick="handleEvent()">Event</button>
~~~

React 이벤트 처리 방식 
~~~
<button onClick={handleEvent}>Event</button>
~~~

### onChange
=> 이벤트 발생시 `e.target.value`를 통해 이벤트 객체에 담겨 있는 `input` 값 불러올 수 있음
~~~
function NameForm() {
  const [name, setName] = useState("");

  const handleChange = (e) => {
    setName(e.target.value);
  }

  return (
    <div>
      <input type="text" value={name} onChange={handleChange}></input>
      <h1>{name}</h1>
    </div>
  )
};

~~~
### onClick
=> 사용자가 클릭이라는 행동을 했을 때 발동하는 이벤트
~~~
function NameForm() {
  const [name, setName] = useState("");

  const handleChange = (e) => {
    setName(e.target.value);
  }

  return (
    <div>
      <input type="text" value={name} onChange={handleChange}></input>
      <button onClick={alert(name)}>Button</button>
      <h1>{name}</h1>
    </div>
  );
};
~~~
종합하면
~~~
// 함수 정의하기

return (
  <div>
	...
    <button onClick={() => alert(name)}>Button</button>
	...
  </div>
  );
};

// 함수 자체를 전달하기

const handleClick = () => {
  alert(name);
};

return (
  <div>
      ...
    <button onClick={handleClick}>Button</button>
      ...
  </div>
  );
};
~~~
## React 데이터 흐름

- React 개발 방식의 큰 특징은
  페이지 단위가 아닌 컴포넌트 단위로 시작하는 것
  
- 페이지를 만들기 전 컴포넌트 먼저 만들고 조립하기
=> 상향식(bottom-up)으로 만들기
=> 장점은 테스트 쉽고 확장성 좋음

- 하나의 컴포넌트는 하나의 일만 한다.

- 컴포넌트는 컴포넌트 바깥에서 props를 이용, 데이터를 인자나 속성 처럼 받을수 있음

- 데이터 전달 주체는 부모컴포넌트(부모-> 자식 이동) 
=> 데이터 흐름이 하향식임(top-down)

### 어떤 데이터를 상태(state)로 두어야 하나❓
- 부모로 부터 props를 통해 전달 되니?
- 시간이 지나도 변하지 않지?
- 컴포넌트안의 다른 state나 props를 가지고 계산하니?

=> 그렇다면 state가 아니다.

### 상태 위치 정하기


