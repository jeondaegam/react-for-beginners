## 2.2 First React Element

### React JS

- 어플리케이션을 interactive하게 만들어주는 library. ( =engine)
  
  
### Vanilla JS와 React JS의 차이점

코드의 시작점이 다르다.

- Vanilla JS: `Html -> JS`
- React JS: `JS -> Html`
    - `모든 것이 JS로써 시작한다. 그 후에 Html이 된다.`
    - JS를 통해 element를 만들고 제어한다.
    - 필요한 element만 업데이트 한다.
    - 유저에게 보여질 내용을 컨트롤 할 수 있다.
  
  
### React JS 문법으로 element 만들기

```html
<script>
  /*
  argument 1: tag type
  argument 2: property(id, class name, event, style...)
  argument 3: content(text, elements array)
  */

  const span = React.createElement("span",
  {
    id : "sexy-span",
    style: {color: "tomato"}
  },
  "I'm a span");

</script>
``` 
  
## 2.3 Events in React

- React JS 문법으로 event 등록하기.

```javascript
const btn = React.createElement("button",
    {
      onClick: () => console.log("im clicked"),
    },
    "Click me");

const container = React.createElement("div", null, [h3, btn]);
ReactDOM.render(co ntainer, root); // Htmlbody에 elements를 보여준다.
```
**ReactDOM**: React element를 Html body에 두는 역할을 한다 
  
  
## 2.5 JSX

Html과 흡사한 형식으로 React element를 만든다.  
createElement를 대체하는 편리한 방법을 제공한다.

- JSX 문법으로 element 만들기
  - event를 property처럼 작성한다.
```javascript
  const button = (
      <button
          style={{
            backgroundColor: "tomato"
          }}
          onClick={() => console.log("Im clicked")}
      >
        Click me
      </button>
  );
```

**Babel**
- JSX 문법으로 작성한 코드를 브라우저가 이해하는 React JS 형식으로 변환해준다.
  - [Babel test link](https://babeljs.io/repl)
- Babel 사용 방법
```javascript
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<script type="text/babel">
  //
  //
</script>
```


## 3.1 setState part 1
React가 data를 저장하고 업데이트 하는 방법

#### React.useStart() 를 사용한다.
- 초기값을 설정할 수 있다.
- 배열이 리턴된다.
  - 첫째요소: 초기값
  - 둘째요소: 값을 바꿀 때 사용할 함수
```javascript
const data = React.useState(4); // 초기값 4
console.log(data);
```

#### Array의 element에 이름 붙이기
```javascript
const food = ["tomato", "potato"];
const [myFavFood, mySecondFav] = food;

// 특정 element 하나만 이름붙이기
const x = [1,2,3]
const num = x[1];
```

## 3.2 setState part 2
React 컴포넌트 안에서 데이터를 바꾸는 방법
#### modifier
- 값을 업데이트하고 리렌더링을 일으킨다.
```javascript
function App() {
    const [counter, setCounter] = React.useState(0); // return받을 두 값의 이름을 counter와 setCounter로 지정한다.
    const onClick = () => {
      setCounter(counter+1); // counter+1을 한 후 리렌더링한다.
    }
    return ( // return의 내용은 사용자가 보게 될 컴포넌트.
        <div>
          <h3>Total clicks: {counter} </h3>
          <button onClick={onClick}>Click me</button> // 버튼 클릭시 onClick을 실행
        </div>
    );
  }
```

## 3.3 Recap
###`key point -> state가 바뀌면 React가 컴포넌트를 refresh 해준다.`

## 3.4 State Functions
#### state를 바꾸는 방법
1. 값을 직접 할당
2. 함수를 할당
```javascript
setState(state + 1); // 1
setState((state) => state + 1); // 2
```
- 현재 state와 관련 없이 새로운 state를 할당하고 싶은 경우에는 (1)
- 현재 state를 바탕으로 새로운 state를 주고 싶은 경우에는 (2)