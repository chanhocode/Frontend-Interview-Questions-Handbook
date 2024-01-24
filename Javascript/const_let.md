# Const 와 let의 호이스팅(Hoisting)

: `호이스팅은 스코프 내의 최상단으로 가는 것`이며, const와 let도 var와 같이 호이스팅이 있다.

let 과 const는 블록 스코프를 가진다.

> 선언 -> TDZ -> 초기화 -> 할당

? TDZ
: 'Temporal Dead Zone' 은 스코프의 시작지점 부터 초기화 지점 까지의 구간

```javascript
let a = 1;
if (true) {
  console.log(a); // error
  let a = 2; // 호이스팅
}
```

> Reference Error(참조에러) 발생, if 스코프 내의 a가 호이스팅 되어 스코프 상단에서 a는 선언만 되고 초기화가 되지 않았다.

[처음으로](../README.md)
