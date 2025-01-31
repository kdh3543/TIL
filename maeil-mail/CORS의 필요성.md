![image](https://github.com/user-attachments/assets/cb982e2f-f07c-4106-9c5e-804e670dbcca)<strong>CORS는 서로 다른 출처(Origin)에서 제공되는 리소스에 접근할 수 있도록 허용하는 정책이다.</strong>
기본적으로 브라우저에는 보안 상의 이유로 <strong>동일 출처 정책(Same-Origin Policy)</strong>이 적용되어 있다. 해당 리소스가 같은 출처에서 제공되는 것이 아니라면 브라우저가 이를 차단하도록 되어 있다.
다른 출처의 서버에 요청을 보낼 경우, 해당 요청에 대한 응답에 접근할 수 없도록 막는다. 이러한 정책은 보안을 강화하지만, 이로 인해 <strong>합법적인 요청까지 차단될 수 있다.</strong> 그런 상황을 해결하기 위해 CORS가 개발되었다.

<strong>CORS를 적용하는 법</strong>은 서버 측에서 <strong>Access-Control-Allow-Origin</strong> 헤더를 설정하면, 특정 출처세어싀 접근을 허용할 수 있다. 
```
Access-Control-Allow-Origin: *
```
로 모든 출처에 대해 허용하거나 특정 출처만 선택적으로 허용할 수 있다. 추가로 <strong>Access-Control-Allow-Methods</strong>와 <strong>Access-Control-Allow-Headers</strong> 헤더를 통해 HTTP 메소드나 특정 헤더를 허용할 수도 있다. 이는 서버에서 수행되는 동작이므로, 프론트엔드 개발자는 일반적으로 서버 개발자에게 클라이언트 도메인을 허용하도록 요청해야 한다.

* <strong>동일 출처 정책(Same-Origin Policy)은 어떤 공격을 막기 위해 존재하는지?</strong>
<strong>동일 출처 정책</strong>은 주로 <strong>크로스사이트 요청 위조(CSRF)</strong> 공격의 위력을 낮추기 위해 존재한다.

<strong>CSRF공격</strong>은 악성 웹사이트가 사용자의 요청을 도용하여, 의도치 않은 요청을 서버에 보내게 만드는 공격이다. 예를 들어, 피해자가 공격자의 웹 사이트에 들어왔을 때 해당 사용자의 요청인 것처럼 타 사이트에 GET 요청을 보내 사용자의 개인정보를 탈취할 수 있다.
SOP는 악성 사이트에서 임의로 다른 출처의 서버로 요청을 보내거나, 응답에 접근하는 것을 막아, CSRF 공격의 효과를 줄여준다.
