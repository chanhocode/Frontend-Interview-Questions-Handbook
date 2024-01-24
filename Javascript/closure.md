# 클로저 (Closure)

`A closure is the combination of a function and the lexical envirnment within which that function was declared`

`💡 클로저는 함수와 그 함수가 선언됐을 때의 렉시컬 환경과의 조합이다.`

❓ 렉시컬 환경: 내부함수가 선언 됐을 때의 스코프

> 클로저는 반환된 내부함수가 자신이 선언된 환경인 렉시컬 스코프를 기억하여 스코프 밖에서 호출되어도 그 스코프에 접근할 수 있는 함수이다.

- 용도: 데이터 캡슐화 및 정보은닉, 고차함수에서 콜백함수를 사용시, private method를 모방

```javascript
// private method 모방

function createCount() {
  int count; // 비공개 변수

  // 내부 함수를 통한 접근
  function increment() {
    count++;
    console.log(count);
  }

  function decrement() {
    count--;
    console.log(count);
  }

  // 외부에 공개할 메서드를 객체로 반환
  return {
    increment,
    decrement
  }
}

```

- 클로저의 단점
  클로저가 외부함수의 변수에 대한 참조를 유지하기 때문에, 이 변수들은 가비지컬렉션의 대상이 되지 않을 수 있다.
  즉, `메모리 누수가 발생할 수 있다.`

[처음으로](../README.md)
