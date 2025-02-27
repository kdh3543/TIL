### 특징

Layout 컴포넌트와 다르게 <strong>re-rendering이 가능</strong>

\*리액트 렌더링 => Fiber 확장을 통해 VDOM node로 mount되고 DOM으로 업데이트<br/>
Fiber가 가지고 있는 정보(state, Lifecycle method 등)

리렌더링 <br />
=> Fiber를 새롭게 만듦<br/>
=> 새로운 메모리를 할당함<br/>
=> state가 리셋되고, Lifecycle method(ex. useEffect)를 통해 함수가 재호출(resynchronize)

리렌더링이 일어나는 경우 - route, navigation, Link component, route push/back

### 활용예시

re-rendering이 필요한 모든 곳에 활용 가능

- page 초기화 로직
  - data를 서버로부터 가져와서 fetch
  - metadata(S.E.O)가 고정값이 아닌 동적으로 바껴야할 때
  - page 전환 애니메이션 적용 시
