###1. Intro

깃헙에서 기본 프로젝트 파일들을 볼 수 있다. [github.com/stephengrider](github.com/stephengrider)
 

---
###3. The Purpose of Boilerplate Projects

우리의 프로젝트는 여러 js파일(컴포넌트, 리액트, 리덕스) 파일을 
webpack + babel 툴을 통해 Transpile한다(JSX + ES6 to ES5)

---
###4. Environment Setup

이제 본격적으로 React 실습에 들어간다.
 - `$ git clone https://github.com/StephenGrider/ReduxSimpleStarter.git` 기본 뼈대가 되는 파일들을 클론받는다.
 - `$ npm install` 명령어로 package.json에 있는 라이브러리들을 다운받아야 원할한 진행이 가능하다.

---
###5. Project Setup
####Component??
기본적으로 리액트는 js 라이브러리이고, 브라우저에서 html 뷰를 보여주기 위해 사용한다. 그리고 우리는 component를 개별 뷰 단위로 사용할 것이다.
(component가 html을 생성한다고 보면 된다.) 컴포넌트를 통해 복잡한 어플리케이션을 비교적 간단하게 구성할 수 있다.

```{.javascript}
const App = function() {
	return <div>Hi!</div>;
}
```
 - `$ npm start` 명령어로 컴파일과 로컬 서버를 띄운다. 아직 브라우저에 아무것도 보이지 않는다. 차후 알아보도록 한다.

---
###6. A Taste of JSX
JSX는 React에서 권장하는 문법이다. 필수 사항은 아니지만 몇가지 장점들로 인해 React 프로젝트들은 기본적으로 JSX를 사용한다.

 - `const` ES6에서 추가된 예악어이다. var와 달리 오직 사용된 블럭 스코프 내에서만 사용될 수 있으며 재할당, 재선언으로 바꿀 수 없다. 
 - `let` 또한 추가된 예약어 인데, 재할당이 가능하다. const와 똑같이 블럭 스코프를 가진다.

---
###7. More on JSX
이전 섹션에서 App을 선언하고 div를 생성했다. 하지만 브라우저에선 아무것도 보이지 않았고
개발자 도구를 키고 콘솔을 보면 React가 정의 되지 않았다고 에러 메시지가 뜬다.
이전 섹션의 코드가 Babel로 컴파일되면
```{.javascript}
var _temporalUndefined = {};
var App = _temporalUndefined;

App = function App(){
	return React.createElement("ol", null);
}
```
이렇게 바뀐다.
React를 어디선가 가지고 와야한다.

 ---
###8. ES6 Import Statements
 - `import React from 'react';` 
 위코드를 파일 상단에 추가한다.

---
###9. ReactDOM vs React
 - 이제 컴포넌트를 DOM에 그려볼 차례이다. 몇몇 legacy 코드를 보면 `React.render()`가 있다. 하지만 이는 deprecate 됐다.
 - 대신 ReactDOM.render() 사용해야 한다.
 - `import ReactDOM from 'react-dom';`을 추가한다.

---
###10. Differences Between Component Instances and Component Classes
App을 컴포넌트를 정의했다. 문맥상 App은 클래스를 나타낸다. 그리고 그 클래스의 인스턴스는 <[클래스 이름] />으로 나타낼 수 있다.
ReactDOM에는 클래스가 아닌 인스턴스 객체를 전달해 주어야 렌더링이 된다.
 - `ReactDOM.render( [인스턴스] )`를 넣으면 렌더링이 된다

 ```{.javascript}
 ReactDOM.render(<App />);
 ```
 하지만 아직도 렌더링이 되지않고 콘솔에 오류가 떠있다.
 `"Target container is not a DOM element"`

---
###11. Render Target
 - 두번째 인자로 렌더링 될 DOM 엘리먼트를 지정해주어야 한다. ReactDOM.render([컴포넌트 인스턴스], [ 렌더링할 타겟 DOM 엘리먼트 ] )
 ```{.javascript}
 ReactDOM.render(<App />, document.querySelector('.container'));
 ```
이제 브라우저를 보면 'Hi!'가 뜰 것이다.

####ES6 신규 문법 Arrow function
커피스크립트에서 볼 수 있던 모습이다. 위 아래 똑같은 동작을 하는 함수다.
 - `( [arguments] ) => { do something... }`
 - `function something([arguments]){ do something... }`

---
###12. Component Structure
 - View를 컴포넌트 단위로 쪼갠다. 기능 덩어리 별로.
 - 소스파일 또한 컴포넌트 별로 모듈화 한다.

---
###13. Youtube Search API Signup

---
###14. Export Statements
 - functional component에서 React를 import 해야하는 이유: JSX -> JS { React.createElement }로 컴파일 될때 React가 스코프에 없다. Section 7을 보면 자세히 알 수 있다.
 - export해줘야 우리의 work space 어디에서든 컴포넌트를 import 할 수 있다.
 - 라이브러리는 경로를 신경쓰지 않아도 되지만, 우리가 선언한 컴포넌트를 import 하기 위해 상대경로로 찾아야한다.(.js는 안써도 됨)
 - `export default`의 경우 해당 모듈이 기본적으로 export 하는 것으로 부르는 쪽에서 아무 이름을 붙여서 사용할 수 있다. 
 - import 경로는 상대경로를 적어줘야 한다.

 ```{.javascript}
 import SearchBar from './component/search_bar';
 ```

---
###15. Class-Based Components
컴포넌트를 만드는 방법은 두가지이다. Functional-Based-Component 와 Class-Based-Component이다.
조금더 복잡한 컴포넌트를 만들 때 Class-Based-Component를 써야한다 그 이유와 사용법은 다음과 같다.
 - 내부적 자료를 가지고 있을 때 사용한다.
 - 다른 컴포넌트와 상호작용할 때 용이하다.
 - React 내의 Component객체를 확장해서 사용한다.
 - render 메서드는 반드시 jsx를 리턴해주어야 한다. 컴포넌트를 화면에 나타낼 때 render메서드를 실행하기 때문이다.

```{.javascript}
 class SearchBar extends React.Component {
 	render(){
 		return <input />;
 	}
 }
```

---
###16. Handling User Events
이벤트를 등록하여 동적인 뷰를 구성할 수 있다.
```{.javascript}
 class SearchBar extends React.Component {
 	render(){
 		// 모든 input 엘리먼트는 onChange 이벤트를 가지고 있다.
 		// 사용자가 정의한 함수를 등록한다.
 		return <input onChange={this.onInputChange} />;
 	}

	// 사용자 정의 함수
	// 모든 이벤트는 인자를 하나 받는데 통상적으로 event, evt, e로 표기한다
 	onInputChange(event) {
		console.log(event.target.value)
 	}
 }
```
arrow function을 사용할 수도 있다.
```{.javascript}
 class SearchBar extends React.Component {
 	render(){
 		return <input onChange={(event) => {console.log(event.target.value)} } />;
 	}
 }
```
 - { } 대괄호를 통해 JSX문 안에서 JS문을 사용할 수 있다.

---
###17. Introduction of State
 - state는 순수 JS 객체이다. 초기 state값을 지정해서 사용할 수 있다.
 - key : value 형태를 가진다.
 - functional component는 state를 가질 수 없다. 오직 class base component만 가질 수 있다.
 - state값이 변경되면 해당 컴포넌트는 즉시 rerender 된다. 하위 컴포넌트도 강제적으로 rerender 된다.
 - constructor 함수는 클래스의 객체가 생성될때 마다 자동으로 실행

```{.javascript}
class SearchBar extends React.Component {
	constructor(props) {
		// super 메서드로 부모 컴포넌트의 props를 받을 수 있다.
		super(props)

		this.state = { term: '' } // state 초기값 설정
	}
}
```

---
###18. More on State
 - 컴포넌트의 state는 내부에서만 변경할 수 있다.(부모로부터 변경 불가)
 - setState를 통해 state값을 바꿀 수 있다. state값을 직접 변경하는 것은 좋지 않다.
 - setState -> 컴포넌트가 Rerender 된다.
```{.javascript}
 class SearchBar extends React.Component {
 	render(){
 		// BAD example of set state -> this.state.term = event.target.value
 		return (
 			<div>
	 			<input onChange={(event) => {this.setState({ term: event.target.value }); } />;
	 			Value of the input: {this.state.term}
	 		</div>
 		)
 	}
 }
```

---
###19. Controlled Components
React에서 데이터의 흐름을 이애하는 것이 가장 중요하다.

```{.javascript}
 class SearchBar extends React.Component {
 	render(){
 		return (
 			<div>
	 			<input onChange={(event) => {this.setState({ term: event.target.value }); } />;
	 			Value of the input: {this.state.term}
	 		</div>
 		)
 	}
 }
```
 1. input 은 등록된 이벤트로인해 변화가 생겼을 때 state의 변경을 알린다.
 2. setState 로 인해 term의 값이 바뀐다.
 3. state값이 바뀌었음으로 컴포넌트가 다시 렌더링 된다.

---
###20. Breather and Review
 - 목적: Youtube Search Application 만들기