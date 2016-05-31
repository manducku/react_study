***1강
깃헙 : github.com/stephengrider - ReduxSimpleStarter

***3강
여러 js파일(컴포넌트, 리액트, 리덕스) 파일을 webpack + babel로 Transpile한다(JSX + ES6 to ES5)

***4강
git clone
npm install로 package.json에 있는 라이브러리들을 다운

***5강
npm start로 컴파일과 로컬 서버를 띄운다.

***6강
jsx
컴포넌트 = 궁극적으로 html뷰를 만든다. js 함수

***7강
jsx
컴포넌트를 만들고, html페이지에 렌더하기 위해
깔끔하게 코드를 짤 수 있다.

***8강
js파일 모듈화
라이브러리 로드법

***9강
ReactDOM vs React
React에서 render메서드는 deprecated,

***10강
컴포넌트 인스턴스와 컴포넌트 클래스의 차이
ReactDOM.render( [클래스] )를 넣으면 렌더링 할때 인스턴스로 만들어져 렌더된다

***11강
ReactDOM.render(<App />, [ 렌더링할 타겟 DOM 엘리먼트 ] )
arrow function ( ) => { }

***12강
1. View를 컴포넌트 단위로 쪼갠다. 기능 덩어리 별로.
2. 소스파일 또한 컴포넌트 별로 모듈화 한다.

***13강
1. youtube-api-search

***14강
1.  functional component에서 React를 import 해야하는 이유: JSX -> JS { React.createElement }로 컴파일 될때 React가 스코프에 없다.
2. export해줘야 우리의 어플리케이션 work space 어디에서든 컴포넌트를 import 할 수 있다.
3. 라이브러리는 경로를 신경쓰지 않아도 되지만, 우리가 선언한 컴포넌트를 import 하기 위해 상대경로로 찾아야한다.(.js는 안써도 됨)

***15강
1. 클래스 베이스 컴포넌트
2. render 메서드는 반드시 jsx를 리턴해주어야 한다. 컴포넌트를 화면에 나타낼 때 render메서드를 실행하기 때문에.

***16강
1. 이벤트 : click, change 같은 기본 이벤트 + on

***17강
1. init state(plain javascript object)
2. functional component는 state를 가질 수 없다. 오직 class base component만 가질 수 있다.
3. constructor 함수는 클래스의 객체가 생성될때 마다 자동으로 실행

***18강
1. 컴포넌트의 state는 내부에서만 변경할 수 있다.(부모로부터 변경 불가)
2. setState -> rerender

***19.강
1. dataflow

***20강
총정리

***21강

***23강
html class ->  className
state value를 자작에게
FBC 에서 CBC로 리팩토링때 props가 인자에서 프로퍼티로 바뀌기때문에 앞에  “this.”를 붙여준다.

***24강
map()

***25강
이터레이터  데이터에 유니크 키 지정(어떤 값이든)

***26강
FBC : props -> { … }

***27강
es6 문자열 템플릿 ` …${…}`

***28강
null props handling

***29강
부모 자식 간 이벤트 흐름
이벤트가 발생된 곳에서 선언된 곳으로

***30강
스타일링

***31강
29강 동

***32강
_(lodash)왜 안돼?

***33강