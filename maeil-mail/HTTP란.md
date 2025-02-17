<strong>HTTP(Hypertext Transfer Protocol)는 웹 상에서 클라이언트와 서버 간 데이터를 주고받는 데 사용되는 통신 규약</strong>이다. 클라이언트가 서버에 요청을 보내고, 서버가 이에 대한 응답을 반환하는 방식으로 동작한다.
HTTP는 <strong>비연결성(stateless)</strong>을 특징으로 하여 한 번의 요청-응답이 끝나면 연결이 종료된다. 또한, 통신이 안전하게 연결될 수 있도록 TCP 연결을 사용한다.

HTTP는 HTML, JSON 등 <strong>다양한 데이터 포맷</strong>을 전달할 수 있다. 요청과 응답에는 <strong>URL 경로, 각종 메서드, 상태 코드와 헤더</strong> 등 정해진 몇 가지 정보를 포함한다.

HTTP의 보안을 강화한 버전인 HTTP(Hypertext Transfer Protocol Secure)는 HTTP에 TLS/SSL 프로토콜에 따라 데이터를 암호화하여 전송한다. 이를 통해 보안 상 중요한 정보들을 안전하게 보호하여 통신을 주고 받는다.

### HTTP와 함께 자주 언급되는 RESTful API는?
<strong>RESTful API는 REST(Representational State Transfer) 스타일을 준수하여 설계된 API</strong>를 의미한다. 여기서 <strong>REST는 웹의 리소스를 클라이언트와 서버가 일관된 방식으로 처리할 수 있도록 하는 설계 원칙</strong>이다.

기본적으로 REST에서는 리소스를 고유한 URI로 표현하고, HTTP 메서드(GET, POST, PUT, DELETE 등)를 사용해 행위를 표현한다.
ex) /users URI에 GET 요청을 보내면 사용자 목록을 가져오는 API로 동작할 수 있다.

REST의 핵심 규칙들

* <strong>클라이언트-서버 분리:</strong> 클라이언트와 서버 간 역할을 명확히 분리한다.
* <strong>무상태성(Stateless):</strong> 서버는 클라이언트의 상태를 저장하지 않으며, 각 요청은 독립적으로 처리한다.
* <strong>일관된 인터페이스(Uniform Interface):</strong> 고유한 URI로 리소스를 식별하고 일관된 인터페이스를 통해 클라이언트와 서버가 간단하고 예측 가능하게 통신할 수 있게 한다.
* <strong>캐시 가능성:</strong> 가능하다면, 서버의 응답 시간을 개선하기 위해 리소스 캐싱을 지원한다.
