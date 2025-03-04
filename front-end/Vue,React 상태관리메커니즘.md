### React와 Vue 상태관리 메커니즘의 차이

#### React

<strong>React는 state를 불변적으로 취급한다.</strong>즉, 새로운 상태와 이전 상태를 비교해 값이 다르다면 재렌더링시킨다.<br/>
원시 타입(string, number 등)은 값을 비교해버리고, 객체는 참조값(reference)를 그냥 비교한다.

그래서 destructing을 통해 새로운 array로 바꿔줬을 때는 새로운 참조값이 전달되어 렌더링이 일어나고, push를 해서 이전 참조값을 그대로 사용했을 때는 렌더링이 일어나지 않는다.

#### Vue

<strong>Vue는 상태 비교에 Proxy를 사용한다.</strong><br />
<strong>Proxy는 특정 객체를 감싸 프로퍼티 읽기, 쓰기와 같은 객체에 가해지는 작업을 중간에 가로채는 객체다.</strong><br/>
즉, Vue의 reactive 함수는 Proxy 객체를 반환해, setter가 발생하는 것을 추적해 재렌더링을 시킨다.

그래서 destructing을 통해 새로운 array를 선언해버리면 기존의 Proxy를 덮어써서 렌더링이 일어나지 않고, push를 통해 기존 array를 변경했을 때는 기존 Proxy로 이 변화를 감지해 재렌더링이 일어난다.

\*React는 새로운 bind를 만들고 싶어하고, Vue는 기존 bind를 유지하고 싶어한다.

#### destructing

ex) React
useState로 빈 배열 상태 선언후 setState로 destructing을 활용해 값을 추가해 array 변형

```
import { useState } from "react";

export default function App() {
  const [list, setList] = useState([]);

  const onClick = () => setList([...list, "a"]);
  // result click 시마다 a 추가

  return (
    <div className="App">
      <h1>List: {list.join(", ")}</h1>
      <button type="button" onClick={onClick}>
        add
      </button>
    </div>
  );
}
```

ex) Vue
reactive 활용해서 array 상태 선언한 뒤 destructing으로 'a' 추가

```
<script setup>
import { reactive } from 'vue'

const list = reactive([])
const onClick = () => {
  list = [...list , 'a']
}
// 버튼 클릭해도 UI 상 a가 추가되지 않음음
</script>

<template>
  <h1> List: {{ list.join(', ')  }} </h1>
  <button @click='onClick'>
    add
  </button>
</template>
```

#### push

ex) React

```
import { useState } from "react";

export default function App() {
  const [list, setList] = useState([]);

  const onClick = () => {
    list.push("a");
    setList(list);
  };
  // result UI 상 a가 추가되지 않음

  return (
    <div className="App">
      <h1>List: {list.join(", ")}</h1>
      <button type="button" onClick={onClick}>
        add
      </button>
    </div>
  );
}
```

ex) Vue

```
<script setup>
import { reactive } from 'vue'

const list = reactive([])
const onClick = () => {
  list.push('a')
}
// a가 추가됨

</script>

<template>
  <h1> List: {{ list.join(', ')  }} </h1>
  <button @click='onClick'>
    add
  </button>
</template>
```
