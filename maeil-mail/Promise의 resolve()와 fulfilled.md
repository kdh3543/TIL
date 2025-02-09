resolve()는 Promise를 완료시키는 함수이고, fulfilled는 해당 Promise가 완료된 상태를 뜻한다.

resolve는 Promise가 성공적으로 끝났을 때 결과 값을 넘겨주는 함수이다.
ex) 어떤 비동기 작어비 끝났을 때, resolve를 호출해서 '이 작업이 끝났고 결과는 이거다'라고 전달하게 된다. 

resolve가 호출되면, Promise 상태는 '이행됨'으로 바뀌는데, 이를 fulfilled라고 부른다.
ex) new Promise((resolve, reject) => { resolve('완료'); })처럼 resolve를 호출하면, 이 Promise의 상태는 fulfilled로 변경된다. resolve는 fulfilled 상태로 전환시키는 역할을 한다.

*resolve는 Promise를 성공적으로 <strong>마무리 짓는 행위</strong>라고 할 수 있고, fulfilled는 그 결과로 발생되는 <strong>완료된 상태</strong>를 의미한다.

*** resolve에서 작업이 실패하는 경우
resolve가 실패하는 상황은 발생하지 않는다. resolve는 Promise를 이행(fulfilled)로 만드는 함수이기 때문에, 성공적인 결과를 전달할 때 사용되며 실패와는 관련이 없다. 만약 Promise가 실패한다면, resolve가 호출되지 않고 reject()가 호출된다.

비동기 작업이 성공적으로 완료되면 resolve가 호출되어 fulfilled 상태가 되고, 오류나 실패가 발생하면 reject가 호출되어 rejected 상태가 된다.

추가로, then()은 resolve된 값을 처리하고, catch()는 reject된 오류를 처리하는 식으로 Promise의 결과를 다루게 된다.
