# 문제1 - 삼항연산자

다음 조건을 if문으로 작성 해 주시고, 삼항연산자로도 작성 해 주세요.
사전 조건 : condition, name이라는 변수가 있습니다.
조건 1. condition이 true일 때 name은 “트루”
조건 2. condition이 false일 때 name은 “팔스”

```js
// answer
let confition = false;
let name;
// if문
if (confition === true) {
  name = "트루";
} else {
  name = "팔스";
}
// 삼항연산자
confition === true ? (name = "트루") : (name = "팔스");

console.log(name);
```

---

# 문제 2 - 삼항연산자

다음 조건을 if문으로 작성 해 주시고, 삼항연산자로도 작성 해 주세요.

- 사전 조건 : condition, name, param이라는 변수가 있습니다.
  condition은 함수이고, 파라미터로는 숫자를 받습니다.
  함수 안의 내용은 홀수인지 짝수인지 구분을 하는 것 입니다.
  return true, false로 해도 되고, “홀수” “짝수”로 해도 됩니다. (삼항연산자만 되면 됩니다)

- 조건 1. condition에 파라미터를 넣고 결과가 짝수 일 때 name은 “짝수”

- 조건 2. condition에 파라미터를 넣고 결과가 홀수 일 때 name은 “홀수”

```js
// answer
const param = 2;
let confition = (param) => param % 2;
let name;
// if문
if (confition(param) === 0) {
  name = "짝수";
} else {
  name = "홀수";
}
// 삼항연산자
confition(param) === 0 ? (name = "짝수") : (name = "홀수");

console.log(name);
```

---

# 문제 3- 삼항연산자 중첩

다음 조건을 if문으로 작성 해 주시고, 삼항연산자로도 작성 해 주세요.

- 사전 조건 : condition, name, param이라는 변수가 있습니다.
  condition은 함수이고, 파라미터로는 숫자를 받습니다.
  함수 안의 내용은 홀수인지 짝수인지 구분을 하는 것 입니다.
  return true, false로 해도 되고, “홀수” “짝수”로 해도 됩니다. (삼항연산자만 되면 됩니다)

- 조건 1. condition에 파라미터를 넣고 결과가 짝수 일 때

  - 조건 1-1. 파라미터가 10보다 같거나 크면 “10보다 큰 짝수”

  - 조건 1-2. 파라미터가 10보다 작으면 “10보다 작은 짝수”

  - 조건 2. condition에 파라미터를 넣고 결과가 홀수 일 때 name은 “홀수”

  ```js
  // answer
  const param = 11;
  let confition = (param) => param % 2;
  let name;
  // if문
  if (confition(param) === 0) {
    if (param >= 10) {
      name = "10보다 큰 짝수";
    } else {
      name = "10보다 작은 짝수";
    }
  } else {
    name = "홀수";
  }
  console.log(name);
  // 삼항연산자
  confition(param) === 0 ? (param >= 10 ? (name = "10보다 큰 짝수") : (name = "10보다 작은 짝수")) : (name = "홀수");
  console.log(name);
  ```

---

# 문제 4 - 삼항연산자로 바꾸기

```js
router.get("/follower/:uid"),
  (req, res) => {
    let { page, count } = req.query;
    if (!page) page = 0;
    if (!count) count = 10;
  };
// answer
const req = {
  body: {
    page: 0,
    count: 5,
  },
};
let page = req.body.page === undefined ? 0 : req.body.page;
let count = req.body.count === undefined ? 0 : req.body.count;
```

---

# 문제 5 - JSX

다음 HTML을 JSX로 바꾸어 주세요.

```jsx
<div id="profile" class="wrap-left-profile">
  <span>PROFILE</span>
</div>;

// answer
const Span = () => <span>PROFILE</span>;

function App() {
  return (
    <div id="profile" className="wrap-left-profile">
      <span />
    </div>
  );
}

export default App;
```

---

# 문제 6 - JSX

다음 HTML을 JSX로 바꾸어 주세요

```jsx
<div id="following">
  <span class="count" id="following-count"></span>
  <span>팔로잉</span>
</div>;

// answer
const Span1 = () => <span className="count" id="following-count"></span>;
const Span2 = () => <span>팔로잉</span>;

function App() {
  return (
    <div id="following">
      <Span1 />
      <Span2 />
    </div>
  );
}

export default App;
```

---

# 문제 7 - JSX

다음 HTML을 JSX로 바꾸어 주세요.

```jsx
<div class="wrap-left-search">
  <img src="./images/search.png" />
  <input type="text" id="search" placeholder="Search" />
</div>;

// answer
const Img = () => <img src={"./images/search.png"} alt="img" />;
const Input = () => <input type="text" id="serch" placeHolder="Search" />;

function App() {
  return (
    <div className="wrap-left-search">
      <Img />
      <Input />
    </div>
  );
}

export default App;
```
