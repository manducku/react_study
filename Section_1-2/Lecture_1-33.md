###1. Intro
 - 깃헙 : github.com/stephengrider - ReduxSimpleStarter

---
###3. The Purpose of Boilerplate Projects
 - 여러 js파일(컴포넌트, 리액트, 리덕스) 파일을 webpack + babel로 Transpile한다(JSX + ES6 to ES5)

---
###4. Environment Setup
 - git clone https://github.com/StephenGrider/ReduxSimpleStarter.git
 - npm install로 package.json에 있는 라이브러리들을 다운

---
###5. Project Setup
 - npm start로 컴파일과 로컬 서버를 띄운다.

---
###6. A Taste of JSX
 - 깔끔하게 코드를 짤 수 있다.
 - 컴포넌트(js 함수)는 궁극적으로 html뷰를 만들기 위함이다.

---
###7. More on JSX
 - 컴포넌트를 만들고, html페이지에 렌더하기 위해 사용

 ---
###8. ES6 Import Statements
 - 라이브러리 로드법 : import ... from '...';

---
###9. ReactDOM vs React
 - React에서 render메서드는 deprecated됨. 대신 ReactDOM.render() 사용

---
###10. Differences Between Component Instances and Component Classes
 - ReactDOM.render( [클래스] )를 넣으면 렌더링 할때 클래스의 인스턴스가 만들어져 렌더된다

---
###11. Render Target
 - ReactDOM.render(<App />, [ 렌더링할 타겟 DOM 엘리먼트 ] )
 - arrow function ( ) => { }

---
###12. Component Structure
 - View를 컴포넌트 단위로 쪼갠다. 기능 덩어리 별로.
 - 소스파일 또한 컴포넌트 별로 모듈화 한다.

---
###13. Youtube Search API Signup

---
###14. Export Statements
 - functional component에서 React를 import 해야하는 이유: JSX -> JS { React.createElement }로 컴파일 될때 React가 스코프에 없다.
 - export해줘야 우리의 어플리케이션 work space 어디에서든 컴포넌트를 import 할 수 있다.
 - 라이브러리는 경로를 신경쓰지 않아도 되지만, 우리가 선언한 컴포넌트를 import 하기 위해 상대경로로 찾아야한다.(.js는 안써도 됨)

---
###15. Class-Based Components
 - 내부적 자료를 가지고 있을 때 사용한다.
 - 다른 컴포넌트와 상호작용할 때 용이하다.
 - render 메서드는 반드시 jsx를 리턴해주어야 한다. 컴포넌트를 화면에 나타낼 때 render메서드를 실행하기 때문에

---
###16. Handling User Events
 - 이벤트 : 'on' + click, change 같은 이벤트 이름
 - { } 대괄호를 통해 JSX문 안에서 JS문을 사용할 수 있다.
 - 이벤트 핸들러는 기본적으로 event객체를 인자로 받는다(이름은 e, evt, event 아무것이나 상관없음)

---
###17. Introduction of State
 - state는 순수 JS 객체이다. 초기 state값을 지정해서 사용할 수 있다.
 - key : value 형태를 가진다.
 - functional component는 state를 가질 수 없다. 오직 class base component만 가질 수 있다.
 - constructor 함수는 클래스의 객체가 생성될때 마다 자동으로 실행

---
###18. More on State
 - 컴포넌트의 state는 내부에서만 변경할 수 있다.(부모로부터 변경 불가)
 - setState를 통해 state값을 바꿀 수 있다. state값을 직접 변경하는 것은 좋지 않다.
 - setState -> 컴포넌트가 Rerender 된다.

---
###19. Controlled Components
 - Dataflow : 상위 컴포넌트에서 하위 컴포넌트로 흐른다.

---
###20. Breather and Review
 - 목적: Youtube Search Application 만들기

---
###21. Youtube Search Response

---
###22. Refactoring Functional Components to Class Components
 - html엘리먼트의 class ->  className 으로 정의
 - FBC 에서 CBC로 리팩토링때 props가 인자에서 프로퍼티로 바뀌기때문에 앞에  “this.”를 붙여준다.

---
###23. Props
 - 상위에서 하위 컴포넌트로 보내주는 데이터

---
###24. Building List with Map
 - 배열객체의 메서드. 각요소를 인자로 받은 콜백함수에 대입해 새로운 배열을 만든다.

---
###25. List Item Keys
 - React 규칙 : 이터레이터 요소에 유니크한 키 지정
 - 빠른 접근을 위해 지정해주어야 한다.

---
###26. Video List Items
 - FBC 에서 props를 인자로 전달할 때 -> { ..., ... }

---
###27. Detail Component and Template Strings
 - ES6의 문자열 템플릿 문법: ` …${…}`

---
###28. Handling Null Props
 - 컴포넌트가 처음 렌더링 될 때 빈자료형에 따른 문제는 분기처리를 해준다.

---
###29. Video Selection
 - 부모 자식 간 이벤트 흐름이해. 이벤트가 발생된 곳에서 선언된 곳으로

---
###30. Styling with CSS

---
###31. Searching for Videos

---
###32. Throttling Search Term Input
 - lodash(js 유틸리티 플러그인)
 - debounce method: 내부 함수를 지정한 시간동안 지연시켜서 마지막에 호출된 함수를 허용한다.
 
---
###33. React Wrapup