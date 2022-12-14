# 문제 1 - Class

아래의 빈칸에 올바른 답을 넣어 주세요.

```js
// question
class Study {
  constructor(name) {
    |빈칸에 올바른 답을 넣어 주세요.|
  }

  speak() {
    console.log(`${this.name}을 공부하고 있습니다.`);
  }
}

class Coding |빈칸에 올바른 답을 넣어 주세요.| {
  constructor(name, today) {
    |빈칸에 올바른 답을 넣어 주세요.|
    |빈칸에 올바른 답을 넣어 주세요.|
  }

  speak() {
    console.log(`${this.today}은 ${this.name}를 공부 하고 있습니다.`);
  }
}

const coding = new Coding("React", "오늘");
coding.speak();

|출력 결과를 입력 해 주세요|

// answer
class Study {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name}을 공부하고 있습니다.`);
  }
}

class Coding extends Study {
  constructor(name, today) {
    super(name);
    this.today = today;
  }
  speak() {
    console.log(`${this.today}은 ${this.name}를 공부 하고 있습니다.`);
  }
}

const coding = new Coding("React", "오늘");
coding.speak();

// 오늘은 React를 공부 하고 있습니다.
```

---

# 문제 2 - Props(Class)

다음 이미지를 보고 해당 뷰를 만들기 위한 빈칸을 채워 주세요.
![](./img/예제1.png)

```js
// question
const root = document.getElementById("root");

class H1 |빈칸에 올바른 답을 넣어 주세요.| {
  constructor(props) {
    |빈칸에 올바른 답을 넣어 주세요.|
  }

  render() {
    return <h1>여기는 |빈칸에 올바른 답을 넣어 주세요.|!!!</h1>;
  }
}

const Container = () => {
  return (
    <React.Fragment>
      <H1 |빈칸에 올바른 답을 넣어 주세요.| />
    </React.Fragment>
  );
};

ReactDOM.render(<Container />, root);

// answer
const root = document.getElementById("root");

class H1 extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h1>여기는 {this.props.name}!!!</h1>;
  }
}

const Container = () => {
  return (
    <React.Fragment>
      <H1 name="대한민국" />
    </React.Fragment>
  );
};

ReactDOM.render(<Container />, root);
```

---

# 문제 3 - Props(function)

다음 이미지를 보고 해당 뷰를 만들기 위한 빈칸을 채워 주세요.
![](./img/예제1.png)

```js
// question
const root = document.getElementById("root");

function H1(|빈칸에 올바른 답을 넣어 주세요.|) {
  return <h1>여기는 {|빈칸에 올바른 답을 넣어 주세요.|}!!!</h1>;
}

const Container = () => {
  return (
    <React.Fragment>
      <H1 |빈칸에 올바른 답을 넣어 주세요.| />
    </React.Fragment>
  );
};
ReactDOM.render(<Container />, root);

// answer
const root = document.getElementById("root");

function H1(props) {
  return <h1>여기는 {props.name}!!!</h1>;
}

const Container = () => {
  return (
    <React.Fragment>
      <H1 name="대한민국" />
    </React.Fragment>
  );
};

ReactDOM.render(<Container />, root);
```

---

# 문제 4 - State

다음 자바스크립트 코드를 보고 조건에 충족 하도록 빈칸을 채워 주세요.

- 조건 1 - state안에 counter를 넣어주시고, 초기 값은 0입니다.
- 조건 2 - 클릭을 했을 때 state의 counter는 1씩 증가가 됩니다.
- 조건 3 - counter는 span의 클릭에 표현이 됩니다.

```js
// question
const root = document.getElementById("root");

class App extends React.Component {
  constructor(props) {
    super(props);
		|빈칸에 올바른 답을 넣어 주세요.|
  }

  add = () => {
		|빈칸에 올바른 답을 넣어 주세요.|
  };

  render() {
    return (
      <div>
        <span>클릭: {|빈칸에 올바른 답을 넣어 주세요.|}</span>
        <button style={{ color: "red" }} onClick={|빈칸에 올바른 답을 넣어 주세요.|}>
          클릭
        </button>
      </div>
    );
  }
}

ReactDOM.render(<App />, root);

// answer
// class component 방식
const root = document.getElementById("root");

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0,
    };
  }

  add = () => {
    this.setState((v1) => ({
      counter: v1.counter + 1,
    }));
  };

  render() {
    return (
      <div>
        <span>클릭: {this.state.counter}</span>
        <button style={{ color: "red" }} onClick={this.add}>
          클릭
        </button>
      </div>
    );
  }
}

ReactDOM.render(<App />, root);

// function component 방식
const root = document.getElementById("root");

function App() {
  const [counter, setCounter] = React.useState(0);

  function add() {
    setCounter(counter + 1);
  }

  return (
    <div>
      <span>클릭: {counter} </span>
      <button style={{ color: "red" }} onClick={add}>
        클릭
      </button>
    </div>
  );
}

ReactDOM.render(<App />, root);
```

---

# 문제 5 - 생명주기 (LifeCycle)

4번 문제의 답이 렌더링이 되었을 때 `"페이지 로딩이 완료되었습니다"` 라는 console.log를 찍어 주세요.

```js
// answer
const root = document.getElementById("root");

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0,
    };
  }

  componentDidMount() {
    console.log("페이지 로딩이 완료되었습니다.");
  }

  add = () => {
    this.setState({ counter: this.state.counter + 1 });
  };

  render() {
    return (
      <div>
        <span>클릭: {this.state.counter}</span>
        <button style={{ color: "red" }} onClick={this.add}>
          클릭
        </button>
      </div>
    );
  }
}

ReactDOM.render(<App />, root);
```

---

# 문제 6 - 순서쌍의 개수

### 문제 설명

순서쌍이란 두 개의 숫자를 순서를 정하여 짝지어 나타낸 쌍으로 (a, b)로 표기합니다. 자연수 `n`이 매개변수로 주어질 때 두 숫자의 곱이 `n`인 자연수 순서쌍의 개수를 return하도록 solution 함수를 완성해주세요.

```js
// answer
const solution = (n) => {
  answer = 0;
  for (i = 1; i <= n; i++) {
    for (j = 1; j <= n; j++) {
      i * j === n ? answer++ : null;
    }
  }
  return answer; //6
};

console.log(solution(20));

// answer2;
const solution2 = (n) => {
  value = [];
  for (i = 1; i <= n; i++) {
    for (j = 1; j <= n; j++) {
      i * j === n ? (value = [true, ...value]) : null;
    }
  }
  return (answer = value.length); //6
};

console.log(solution2(20));
```
