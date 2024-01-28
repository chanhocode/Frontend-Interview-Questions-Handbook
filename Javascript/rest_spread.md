# Rest & Spread

> 두 연산자는 문법적으로 동일한 '...' 기호를 사용하지만 사용 목적과 방식에 차이가 있다.

## Rest 연산자

- Rest연산자는 함수의 `매개변수를 배열로 결합`하는 데 사용된다. 이 연산자를 사용하면 함수에 전달된 인자들을 배열로 그룹화할 수 있다.
- 주로 함수 정의에서 사용되며, `전달된 인자의 개수가 가변적`일 때 유용하다.

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, current) => acc + current, 0);
}

console.log(sum(1, 2, 3, 4)); // 출력: 10
```

## Spread 연산자

- `배열이나 객체를 개별 요소로 확장`하는 데 사용된다. 이 연산자를 사용하면 배열의 요소나 객체의 속성을 개별적으로 분리할 수 있다.
- 배열이나 객체를 복사하거나 합치는 데 주로 사용된다.

```javascript
const numbers = [1, 2, 3];
const moreNumbers = [4, 5, 6];
const combined = [...numbers, ...moreNumbers]; // 배열 결합
console.log(combined); // 출력: [1, 2, 3, 4, 5, 6]

const obj = { name: '홍길동', age: 30 };
const updatedObj = { ...obj, age: 31 }; // 객체 복사 및 속성 업데이트
console.log(updatedObj); // 출력: { name: '홍길동', age: 31 }
```

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./esm_cjs.md)

</div>
