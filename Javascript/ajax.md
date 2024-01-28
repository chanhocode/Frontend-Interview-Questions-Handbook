# AJAX에 대해서

> AJAX는 `Asynchronous Javascript and XML`의 약자로, `자바스크립트를 사용하여 서버와 비동기적으로 통신하고, 데이터를 교환하여 웹 페이지를 동적으로 업데이트하는 기술`입니다. AJAX를 사용하면 웹 페이지의 일부만을 갱신할 수 있기 떄문에, 전체 페이지를 새로고침하지 않고도 서버로부터 데이터를 가져와 웹페이지에 표시할 수 있습니다. 'onreadystatechange'를 이용하여 서버 응답에 따른 로직을 작성할 수 있고, open(), send()를 이용하여 서버로 요청을 보낼 수 있습니다.

- 장점

  - `페이지 전체를 다시 로드할 필요 없이 데이터만 갱신`할 수 있습니다.
  - 사용자 경험이 향상되며, 웹 애플리케이션의 `반응 속도가 개선`됩니다.

```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === XMLHttpRequest.DONE && xhr.status === 200) {
    console.log(xhr.responseText);
  }
};
xhr.send();
```

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./generator.mds)

</div>