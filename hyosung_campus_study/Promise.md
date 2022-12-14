# 문제 1 - Promise 만들기

아래의 Callback 함수를 Promise로 바꾸어 주세요.

```js
// question
function call(v1, callback) {
  callback(v1[0] + v1[1]);
}

call([1, 2], (value) => {
  console.log(value);
});

// answer
function call(v1) {
  return new Promise((resolve, reject) => {
    resolve(v1[0] + v1[1]);
  });
}

call([1, 2]).then((res) => {
  console.log(res);
});
```

---

# 문제 2 - Resolve, Reject 이용 해 보기

아래의 Callback 함수를 promise로 바꾸어 주세요.

```js
// question
const error = true; // true이면 에러가 있음 , false이면 에러가 없음
function promise(callback) {
  if (error === true) {
    callback("success");
  } else {
    callback("fail");
  }
}

promise((result) => {
  console.log(result);
});

// answer
const error = true; // true이면 에러가 없음 , false이면 에러가 있음

function promise(v1, v2) {
  return new Promise((resolve, reject) => {
    resolve(v1 + v2);
    reject(error === true ? console.log("성공") : console.log("실패"));
  });
}

promise(1, 2)
  .then((res) => {
    console.log(res);
  })
  .catch((err) => {
    console.log(err);
  });
```

---

# 문제 3 - 여러 함수 Promise로 묶기

아래의 함수들을 이용해서 `((((3+1) - 2) * 4) / 2)`

```js
// answer
function add(v1, v2) {
  return new Promise((resolve) => {
    resolve(v1 + v2);
  });
}

function min(v1, v2) {
  return new Promise((resolve) => {
    resolve(v1 - v2);
  });
}

function mul(v1, v2) {
  return new Promise((resolve) => {
    resolve(v1 * v2);
  });
}

function div(v1, v2) {
  return new Promise((resolve) => {
    resolve(v1 / v2);
  });
}

add(3, 1)
  .then((v1) => min(v1, 2))
  .then((v2) => mul(v2, 4))
  .then((v3) => div(v3, 2))
  .then((res) => {
    console.log(res);
  });
```

---

# 문제 4 - 중앙값 구하기

### 문제 설명

중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미합니다. 예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다. 정수 배열 `array`가 매개변수로 주어질 때, 중앙값을 return 하도록 solution 함수를 완성해보세요.

```js
// answer
function solution(array) {
  let answer = 0;
  let value = Math.floor(array.sort((a, b) => a - b).length / 2);
  answer = array[value];
  return answer;
}

console.log(solution([1, 2, 7, 10, 11]));
```

---

# 문제 5 - 숨어있는 숫자의 덧셈 (1)

### 문제 설명

문자열 `my_string`이 매개변수로 주어집니다. `my_string`안의 모든 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

```js
// answer
const solution = (my_string) => {
  array = my_string
    .replace(/[^0-9]/g, "")
    .split("")
    .map(Number);
  let answer = array.reduce((a, b) => a + b);
  return answer;
};
console.log(solution("1a2b3c4d123"));
```
