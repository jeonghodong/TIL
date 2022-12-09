## 문제 1 - Map And Key

다음 빈칸에 알맞은 JSX 코드를 넣어 주세요.

- 조건 1 → key값은 index로 넣어 주세요.

```js
//question
const root = ReactDOM.createRoot(document.getElementById("root"));
const array = [1, 2, 3, 4, 5];
const array2 = array.map((value, index) => {
  return <li /* "JSX" 코드를 넣어 주세요 */>{value}</li>;
});
function ClientList(props) {
  return <ul>{props.clientList}</ul>;
}
root.render(<ClientList /* props를 전달하는 코드를 넣어 주세요 */ />);

//answer
const root = ReactDOM.createRoot(document.getElementById("root"));
const array = [1, 2, 3, 4, 5];
const array2 = array.map((value, index) => {
  return <li key={index}>{value}</li>;
});
function ClientList(props) {
  return <ul>{props.clientList}</ul>;
}
root.render(<ClientList clientList={array2} />);
```

---

## 문제 2 - State

List의 숫자를 클릭하면 해당 값이 2배가 되는 페이지를 만들어 주세요.

```js
//question
const root = ReactDOM.createRoot(document.getElementById("root"));

function ListItem(props) {
  return <li /* 여기를 채워 주세요 */>{props.value}</li>;
}

function TextLists(props) {
  const items = props.items;
  return (
    <ul>
      {items.map((value, index) => {
        return (
          <ListItem
            key={index}
            value={value}
            /* 여기를 채워 주세요 */
          />
        );
      })}
    </ul>
  );
}

class ListControl extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      list: [1, 2, 3],
      value: "",
    };
  }

  handleClick = (index) => {
    this.setState({
      /* 여기를 채워 주세요*/
    });
  };

  render() {
    return (
      <React.Fragment>
        <TextLists
          items={this.state.list}
          /* 여기를 채워 주세요 */
        />
      </React.Fragment>
    );
  }
}

root.render(<ListControl />);

//answer
const root = ReactDOM.createRoot(document.getElementById("root"));

function ListItem(props) {
  return (
    <li
      onClick={() => {
        props.onClick(props.index);
      }}
    >
      {props.value}
    </li>
  );
}

function TextLists(props) {
  const items = props.items;
  return (
    <ul>
      {items.map((value, index) => {
        return <ListItem key={index} value={value} onClick={props.onClick} index={index} />;
      })}
    </ul>
  );
}

class ListControl extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      list: [1, 2, 3],
      value: "",
    };
  }

  handleClick = (index) => {
    const array = [...this.state.list];
    array[index] = array[index] * 2;
    this.setState({
      list: array,
    });
  };

  render() {
    return (
      <React.Fragment>
        <TextLists items={this.state.list} onClick={this.handleClick} />
      </React.Fragment>
    );
  }
}

root.render(<ListControl />);
```

---

## 문제 3 - 피자 나눠 먹기 (1)

### 문제 설명

머쓱이네 피자가게는 피자를 일곱 조각으로 잘라 줍니다. 피자를 나눠먹을 사람의 수 `n`이 주어질 때, 모든 사람이 피자를 한 조각 이상 먹기 위해 필요한 피자의 수를 return 하는 solution 함수를 완성해보세요.

```js
//answer
const solution = (n) => Math.ceil(n / 7);

console.log(solution(15)); //3
```

---

## 문제 4 - 피자 나눠 먹기 (2)

### 문제 설명

머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다. 피자 조각 수 `slice`와 피자를 먹는 사람의 수 `n`이 매개변수로 주어질 때, `n`명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

```js
//answer
const solution = (slice, n) => Math.ceil(n / slice);

console.log(solution(4, 12)); //3
```
