## 2.2 First React Element

### React JS

- application이 interactive하게 만들어주는 library. ( =engine)

### Vanilla JS와 React JS의 차이점

코드의 시작점이 다르다.

- Vanilla JS: `Html -> JS`
- React JS: `JS -> Html`
    - `모든 것이 JS로써 시작한다. 그 후에 Html이 된다.`
    - JS를 통해 element를 만들고 제어한다.
    - 필요한 element만 업데이트 한다.
    - 유저에게 보여질 내용을 컨트롤 할 수 있다.

### React JS 문법으로 element 만들기

```javascript
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
ReactDOM.render(container, root); // Htmlbody에 elements를 보여준다.
```
**ReactDOM**: React element를 Html body에 두는 역할을 한다

  
## 2.5 JSX

Html과 흡사한 문법으로 React element를 만든다.

- JSX 문법으로 element 만들기
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
  - [Babel test link][https://babeljs.io/repl]
- Babel 사용 방법
```javascript
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<script type="text/babel">
  //
  //
</script>
```