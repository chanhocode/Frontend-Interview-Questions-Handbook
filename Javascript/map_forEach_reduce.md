# map & forEach & reduce

## map 함수

> `map`함수는 배열의 모든 요소에 대해 주어진 함수를 호출하고, 그 결과를 모아 새로운 배열을 반환합니다. 각 요소에 대해 주어진 함수를 실행하고, 그 결과를 새로운 배열에 담아 반환합니다.

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map((x) => x * 2);
console.log(doubled); // [2, 4, 6, 8]
```

## forEach 함수

> `forEach`함수는 배열의 각 요소에 대해 주어진 함수를 실행하지만, 새로운 배열을 반환하지 않습니다. 주로 배열의 각 요소에 대한 부수 효과(side effect)를 일으키는 용도로 사용

```javascript
const numbers = [1, 2, 3, 4];
numbers.forEach((x) => console.log(x)); // 1, 2, 3, 4 출력
```

## reduce 함수

> `reduce` 함수는 배열의 각 요소에 대해 주어진 리듀서(reducer)함수를 실행하고, 하나의 결과값을 반환합니다. 누적 계산의 결과를 반환하는 데 주로 사용합니다.

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0
);
console.log(sum); // 10
```

[처음으로](../README.md)
