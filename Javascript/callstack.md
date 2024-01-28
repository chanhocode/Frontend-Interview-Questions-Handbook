# CallStack

: Javascript는 `단일 콜스택 기반`이다.

```javascript
function A() {
  B();
}
function B() {
  console.log('B!!');
}
A();
```

> `실행 컨텍스트 단위로 쌓인다.`

![Alt text](image.png)

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./stack_queue_eventloop.md)

</div>
