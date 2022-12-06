## 문제 1 - for문

다음 배열을 콘솔에 맞게 출력하는 for문을 작성 해 주세요.

```js
// const array = [1, 2, 3, 4, 5]
// for(정답을 입력 해 주세요.) {
// 	console.log(정답을 입력 해 주세요.)
// }

// 출력
// 1
// 2
// 3
// 4
// 5

// answer
const array = [1, 2, 3, 4, 5];

for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```

---

## 문제 2 - for문 역순

다음 배열을 콘솔에 맞게 출력하는 for문을 작성 해 주세요.

```js
// const array = [1, 2, 3, 4, 5]
// for(정답을 입력 해 주세요.) {
// 	console.log(정답을 입력 해 주세요.)
// }

// 출력
// 5
// 4
// 3
// 2
// 1

// answer
const array = [1, 2, 3, 4, 5];
for (let i = 5; i >= 0; i--) {
  console.log(array[i]);
}
```

---

## 문제 3 - 이중 for문

다음 배열을 콘솔에 맞게 출력하는 for문을 작성 해 주세요.

```js
// const array = [1, 2, 3, 4, 5]
// for(정답을 입력 해 주세요.) {
// 	for(정답을 입력 해 주세요.) {
// 		console.log(정답을 입력 해 주세요.)
// 	}
// }

// 출력
// 1 2
// 1 3
// 1 4
// 1 5
// 2 3
// 2 4
// 2 5
// 3 4
// 3 5
// 4 5

// answer
const array = [1, 2, 3, 4, 5];

for (let i = 0; i < array.length; i++) {
  for (let j = i + 1; j < array.length; j++) {
    console.log(array[i], array[j]);
  }
}
```

---

## 문제 4 - 이중 for문

다음 배열을 콘솔에 맞게 출력하는 for문을 작성 해 주세요.

```js
// const array = [1, 2, 3, 4, 5]
// for(정답을 입력 해 주세요.) {
// 	for(정답을 입력 해 주세요.) {
// 		console.log(정답을 입력 해 주세요.)
// 	}
// }

// 출력
// 1 1
// 1 2
// 1 3
// 1 4
// 1 5
// 3 1
// 3 2
// 3 3
// 3 4
// 3 5
// 5 1
// 5 2
// 5 3
// 5 4
// 5 5

// answer
const array = [1, 2, 3, 4, 5];
for (let i = 0; i < array.length; i = i + 2) {
  for (let j = 0; j < array.length; j++) {
    console.log(array[i], array[j]);
  }
}
```

---

## 문제 5 - 삼항연산자

다음 IF문을 삼항연산자로 바꾸어 주세요.

```js
// let isTrue = false;
// let name;
// if(isTrue === flase) {
// 	name = "거짓"
// } else {
//   name = "진실"
// }

// // 아래에 빈칸을 채워 주세요.
// name =      ?        :

// answer
let isTrue = false;
let name;
name = isTrue === false ? "거짓" : "진실";
console.log(name);
```

---

## 문제 6 - Props

다음 React 코드에서 Props가 제대로 전달 되도록 정답을 채워 주세요.

```js
// const root = ReactDOM.createRoot(document.getElementById("root"));

// const obj = {
// 	lastLogin: "2022-12-06",
// 	name: "hun",
// 	phon: "010-1234-1234"
// }

// function Userinfo(props) {
//   return (
//     <div className="UserInfo">
//       <h1 className="name">{정답을 채워 주세요}</h1>
//       <h2 className="phon">{정답을 채워 주세요}</h2>
//       <h2 className="lastLogin">{정답을 채워 주세요}</h2>
//     </div>
//   );
// }

// root.render(
//   정답을 채워 주세요
// );

// answer
const root = ReactDOM.createRoot(document.getElementById("root"));

const obj = {
  lastLogin: "2022-12-06",
  name: "hun",
  phon: "010-1234-1234",
};

function Userinfo(props) {
  return (
    <div className="UserInfo">
      <h1 className="name">{props.name}</h1>
      <h2 className="phon">{props.phon}</h2>
      <h2 className="lastLogin">{props.lastLogin}</h2>
    </div>
  );
}

root.render(<Userinfo name={obj.name} phon={obj.phon} lastLogin={obj.lastLogin} />);
```

---

## 문제 7 - defaultProps

문제 6번의 코드를 실수로 obj를 빼고 전달 해 버렸습니다!
obj의 내용을 바탕으로 defaultProps를 작성 해 주세요.

```js
// const root = ReactDOM.createRoot(document.getElementById("root"));

// //const obj = {
// //	lastLogin: "2022-12-06",
// //	name: "hun",
// //	phon: "010-1234-1234"
// //}

// function Userinfo(props) {
//   return (
//     <div className="UserInfo">
//       <h1 className="name">{정답을 채워 주세요}</h1>
//       <h2 className="phon">{정답을 채워 주세요}</h2>
//       <h2 className="lastLogin">{정답을 채워 주세요}</h2>
//     </div>
//   );
// }

// // 여기에 defaultProps를 넣어주세요

// root.render(
//   정답을 채워 주세요
// );

//answer
const root = ReactDOM.createRoot(document.getElementById("root"));

//const obj = {
//	lastLogin: "2022-12-06",
//	name: "hun",
//	phon: "010-1234-1234"
//}

function Userinfo(props) {
  return (
    <div className="UserInfo">
      <h1 className="name">{props.name}</h1>
      <h2 className="phon">{props.phon}</h2>
      <h2 className="lastLogin">{props.lastLogin}</h2>
    </div>
  );
}

Userinfo.defaultProps = {
  name: "hun",
  phon: "010-1234-1234",
  lastLogin: "2022-12-06",
};

root.render(<Userinfo />);
```

---

## 문제 8 - PropTypes

다음 React 코드에서 Props가 제대로 타입을 검사 할 수 있도록 정답을 채워 주세요.

```js
// const root = ReactDOM.createRoot(document.getElementById("root"));

// function Userinfo(props) {
//   return (
//     <div className="UserInfo">
//       <h1 className="work">{props.author.work}</h1>
//       <h2 className="UserInfo-name">{props.author.name}</h2>
//     </div>
//   );
// }

// Userinfo.propTypes = {
//   // 정답을 채워 주세요
// };

// function Comment(props) {
//   return (
//     <div className="Comment">
//       <Userinfo author={props.author} />
//       <div className="Comment-text">{props.text}</div>
//       <div className="Comment-date">{props.date}</div>
//     </div>
//   );
// }

// Comment.propTypes = {
//   // 정답을 채워 주세요
// };

// const comment = {
//   author: {
//     name: "hun",
//     work: "효성직업전문학원",
//   },
//   text: 5,
//   date: new Date().toLocaleDateString(),
// };

// root.render(<Comment author={comment.author} text={comment.text} date={comment.date} />);

// answer
const root = ReactDOM.createRoot(document.getElementById("root"));

function Userinfo(props) {
  return (
    <div className="UserInfo">
      <h1 className="work">{props.author.work}</h1>
      <h2 className="UserInfo-name">{props.author.name}</h2>
    </div>
  );
}

Userinfo.propTypes = {
  author: propTypes.objectOf(propTypes.stirng),
};

function Comment(props) {
  return (
    <div className="Comment">
      <Userinfo author={props.author} />
      <div className="Comment-text">{props.text}</div>
      <div className="Comment-date">{props.date}</div>
    </div>
  );
}

Comment.propTypes = {
  author: PropTypes.object,
  text: PropTypes.number,
  date: PropTypes.string,
};

const comment = {
  author: {
    name: "hun",
    work: "효성직업전문학원",
  },
  text: 5,
  date: new Date().toLocaleDateString(),
};

root.render(<Comment author={comment.author} text={comment.text} date={comment.date} />);
```

---

## 문제 9 - 배열의 평균값

### 문제 설명

정수 배열 `numbers`가 매개변수로 주어집니다. `numbers`의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

```js
// answer
const solution = (numbers) => {
  let num = 0;
  for (let i = 0; i < numbers.length; i++) {
    num = numbers[i] + num;
  }
  return (answer = num / numbers.length);
};

console.log(solution([89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99]));
// 94
```
