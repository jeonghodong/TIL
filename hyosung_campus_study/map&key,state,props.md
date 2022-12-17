# 문제 1 - Map And Key

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

# 문제 2 - State

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
