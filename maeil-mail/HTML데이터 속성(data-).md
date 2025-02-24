<strong>데이터 속성은 사용자 정의 데이터를 HTML 요소에 저장하기 위해 사용되는 속성</strong>이다. 선언 방법은 data-로 시작하는 속성을 HTML 태그에 추가하면 된다.
예를 들어, <div data-user-id='12345' data-role='admin'></div>와 같이 사용할 수 있다. 여기서 data-user-id와 data-role이 데이터 속성에 해당한다.

자바스크립트를 통해 데이터 속성에 접근하려면 dataset 객체를 활용한다. HTML의 데이터 속성 이름이 JS의 camelCase 형식으로 매핑된다.
예를 들어, data-user-id는 dataset.userId로, data-role은 dataset.role로 접근할 수 있다. 예를 들어 앞선 예제에서 해당요소.dataset.userId를 호출하면 '12345'라는 값이 반환된다.

또한, CSS에서도 데이터 속성을 활용할 수 있다. attr() 함수나 속성 선택자를 통해 데이터 속성의 값을 기반으로 스타일을 적용할 수 있따.

```
/* attr() 함수를 사용해 접근 */
article::before {
  content: attr(data-parent)
}

/* 속성 선택자를 사용해 접근 */
article[data-columns = '3'] {
  width: 400px;
}
```

### 데이터 속성 활용

<strong>DOM 요소에 특정 데이터를 바인딩하고, 자바스크립트 로직에서 해당 데이터를 활용하기 위해 사용된다.</strong>
예를 들어, 버튼 클릭 이벤트에서 특정 데이터를 전달하거나, 데이터를 기반으로 UI를 동적으로 변경해야 할 때 유용하다. 이렇게 하면 HTML과 자바스크립트 간 데이터 상호작용을 간단하게 구현할 수 있다.
