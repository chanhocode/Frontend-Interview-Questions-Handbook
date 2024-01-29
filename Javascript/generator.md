# 제너레이터 (Generator)

> 자바스크립트 ES6에서 도입된 특별한 종류의 함수로 `이터레이터를 반환하는 함수이다.`, 이 함수들은 호출될 때 함수 내의 모든 코드를 한 번에 실행하는 대신, `yield` 표현식을 `만날 때까지만 실행`하고 해당 상태에서 함수의 실행을 중지할 수 있습니다. 이후 `다시 함수를 호출`하면, 중단된 부분부터 `실행을 재개`합니다.

```javascript
function* numberGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = numberGenerator(); // 제너레이터 객체 생성

console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3
```

## 사용 사례

- 제너레이터는 데이터 스트림을 처리하거나, 특정 조건에 따라 다른 값을 순차적으로 생성할 때 유용합니다.
- 비동기 프로그래밍에서 복잡한 흐름을 간결하게 표현할 때도 사용될 수 있습니다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./iterable_iterator.md)

</div>
