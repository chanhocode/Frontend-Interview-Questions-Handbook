# CallStack

: Javascript는 단일 콜스택 기반이다.

```javascript
function A() {
  B();
}
function B() {
  console.log('B!!');
}
A();
```
> 실행 컨텍스트 단위로 쌓인다.

![Alt text](image.png)

[처음으로](../README.md)