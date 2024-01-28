# Const 와 let의 호이스팅(Hoisting)

: `호이스팅이란 인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당`하는 것으로 `즉, 호이스팅은 스코프 내의 최상단으로 가는 것`이다. const와 let도 var와 같이 호이스팅이 있다.

let 과 const는 블록 스코프를 가진다.

> 선언 -> TDZ -> 초기화 -> 할당

? TDZ
: `'Temporal Dead Zone' 은 스코프의 시작지점 부터 초기화 지점 까지의 구간`

> 변수가 선언되기 전에 블록 안에서 사용할 수 없는데, 이 위치를 시간상 사각지대라고 표현한다.

```javascript
let a = 1;
if (true) {
  console.log(a); // error
  let a = 2; // 호이스팅
}
```

> Reference Error(참조에러) 발생, if 스코프 내의 a가 호이스팅 되어 스코프 상단에서 a는 선언만 되고 초기화가 되지 않았다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./let_var.md)

</div>
