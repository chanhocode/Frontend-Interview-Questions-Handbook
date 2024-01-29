# Callback & Promise

## 콜백 함수 (Callback)

> 콜백 함수는 다른 함수의 인자로 넘겨지는 함수 이다. 비동기 프로그래밍에 사용되며 콜백함수가 연쇄적으로 이어지면 `콜백지옥`이 발생한다.

```javascript
function requestData(callback) {
  // 데이터 요청 로직 (예: AJAX)
  setTimeout(() => {
    console.log('데이터 요청');
    callback();
  }, 1000);
}

// 콜백 지옥
requestData(function () {
  requestData(function () {
    requestData(function () {
      console.log('데이터 처리 완료');
    });
  });
});
```

- 콜백 지옥 (Callback Hell) <br>
  콜백 지옥은 자바스크립트에서 중첩된 콜백함수들이 여러겹 겹쳐져 코드의 가독성과 유지보수성을 떨어뜨리는 현상을 말합니다.

- 콜백 지옥의 해결방법 <br>
  콜백 지옥을 해결하는 방법에는 `Promise`나 `Async`가 있습니다. 프로미스 사용시 콜백 기반의 비동기 코드를 체인 형태로 표현할 수 있게 해줍니다. 이를 통해 코드의 가독성을 향상합니다. 'async/await'사용시 프로미스 기반의 비동기 코드를 동기적인 형태로 작성할 수 있게 해줍니다. 이를 사용하면 코드의 구조를 명확하게 유지할 수 있습니다.

```javascript
// Promise
function requestData() {
  return new Promise((resolve, reject) => {
    // 데이터 요청 로직
    setTimeout(() => {
      console.log('데이터 요청');
      resolve();
    }, 1000);
  });
}

requestData()
  .then(() => requestData())
  .then(() => requestData())
  .then(() => console.log('데이터 처리 완료'))
  .catch((error) => console.log(error));
// async/await
async function processData() {
  await requestData();
  await requestData();
  await requestData();
  console.log('데이터 처리 완료');
}

processData().catch((error) => console.log(error));
```

## 프로미스 (Promise)

> 프로미스는 자바스크립트 비동기 처리에 사용되는 객체입니다. 비동기 작업의 최종 성공 또는 실패를 나타내며, 세가지 상태를 가집니다. `Pending(대기)`, `Fulfiled(이행)`, `Rejected(거부)`. 프로미스는 `then`, `catch`, `finally` 메서드를 사용해 비동기 작업의 결과를 처리합니다.

- pending: 초기 상태, 이행 또는 거부되지 않음
- fulfilled: 작업이 성공적으로 완료됨
- rejected: 작업이 실패함

```javascript
const promise = new Promise((resolve, reject) => {
    // 비동기 작업 수행
    if (/* 성공 조건 */) {
        resolve(value); // 이행
    } else {
        reject(error); // 거부
    }
});

promise
    .then(value => {
        // 이행 시 처리
    })
    .catch(error => {
        // 거부 시 처리
    })
    .finally(() => {
        // 마무리 작업
    });
```

### 프로미스 관련 메서드

- `Promise.all()` <br>
  여러 프로미스를 병렬로 처리할 때 사용되는 메서드이다. 이 메서드는 프로미스 배열을 인자로 받으며, 모든 프로미스가 이행될 때까지 기다립니다. 모든 프로미스가 이행되면, 그 결과를 배열로 반환합니다. 하나라도 거부되면 'promise.all()'은 즉시 거부되며, 거부된 이유를 반환합니다.
- `Promise.allSettled()` <br>
  모든 프로미스가 이행되거나 거부될 때까지 기다립니다. 각 프로미스의 결과(이행, 거부)를 배열로 반환합니다.
- `Promise.race()` <br>
  주어진 프로미스 중 하나가 이행되거나 거부되는 즉시, 그 결과와 함께 프로미스를 반환합니다.
- `Promise.any()` <br>
  ES2021에서 도입된 메서드로, 주어진 프로미스 중 하나라도 이행되면 그 결과를 반환합니다. 모든 프로미스가 거부될 경우에만 거부합니다.

⚙️ 추가

- Promise와 Callback 비교 <br>
  콜백함수를 사용하면 비동기 코드의 결과 값을 처리하기 위해 콜백 안에서만 처리할 수 있고, 밖에서는 그 결과값을 알 수 없습니다. 하지만 프로미스를 사용하면 비동기 로직의 결과 값이 Promise 객체에 저장되기 때문에 코드 작성이 용이합니다.

- Promise와 Async/await 의 차이 <br>
  프로미스는 '.catch()'를 통해 에러 핸들링이 가능하지만, async/await는 try-catch()문을 사용하여 에러를 핸들링 한다. 또한 프로미스도 .then 지옥이 발생할 수 있기에 async/await을 활용한 코드가 코드 흐름을 이해하기 쉽다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./ajax.md)

</div>
