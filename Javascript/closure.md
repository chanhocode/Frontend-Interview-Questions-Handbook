# 클로저 (Closure)

`A closure is the combination of a function and the lexical envirnment within which that function was declared`

`💡 클로저는 함수와 그 함수가 선언됐을 때의 렉시컬 환경과의 조합이다.`

❓ 렉시컬 환경: 내부함수가 선언 됐을 때의 스코프

> 클로저는 `반환된 내부함수`가 자신이 선언된 환경인 `렉시컬 스코프를 기억`하여 `스코프 밖에서 호출`되어도 `그 스코프에 접근`할 수 있는 함수이다.

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

⚙️ 추가

- 렉시컬 환경(Lexical Environment)란?

1. 환경 레코드 <br>
   : 모든 지역 변수를 프로퍼티로 저장하고 있는 객체이다. this 값과 같은 기타 정보도 여기에 저장된다.
2. 외부 렉시컬 환경에 대한 참조<br>
   : 환경 레코드는 변수나 함수에 대한 정보를 갖고 있으며, 변수가 변경되면 환경 레코드의 프로퍼티가 변걍된다. 외부 렉시컬 환경에 대한 참조는 스코프 체인에 활용 된다. 내부 렉시컬 환경에서 원하는 변수를 찾지 못한다면 내부 렉시컬 환경이 참조하는 외부 렉시컬 환경으로 검색범위를 확장하며 전역 렉시컬 환경까지 반복 될 수 있다.

- 스코프 체인이란?<br>
  : 자바스크립트 엔진은 식별자를 찾을 때, 자신이 속한 스코프에서 찾고 없을경우 상위 스코프에서 다시 찾아 나아가는대 이런 현상을 스코프 체인이라고 한다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./copy.md)

</div>
