# CORS에 대해서

> CORS(Cross-Origin Resource Sharing)는 웹페이지에서 다른 도메인의 리소스를 안전하게 요청하는 방법을 정의하는 메커니즘이다. CORS는 웹 보안의 중요한 부분으로, 웹 애플리케이션의 출처(도메인, 스킴, 포트)가 서로 다를 때 리소스를 공유할 수 있는 규칙을 제공한다.

- CORS는 도메인 혹은 포트가 다른 서버의 자원을 요청할 때 생긴다. (브라우저에서 CSRF나 XSS 공격을 막는 보안목적으로 차단한다)

- 해당 문제를 해결하려면 response헤더에 "Access-Control-Allow-Origin"를 추가하거나, 서버 쪽에서 처리를 해줘야 한다.

<div style="weight: 100%; display: flex; justify-content: space-between;">

[< 처음으로 >](../README.md)

[< 다음 >](./oop.md)

</div>
