## Dynamic Route에서 Params는 왜 Promise로 바뀌었나?

ex) string => Promise

```
//app/blog/[slug]/page.tsx

export default async function Page({params,}: {
  params: Promise<{ slug: string }>
}) {
  const slug = (await params).slug

  return <div>My Post: {slug}</div>
}
```

### Dynamic Route 정의

매 요청 시마다 바뀌는 <br/>
route가 바뀌는 시점<br/>

1. request time
2. build time(generate static paths)

### 기존 Dynamic Route에 접근하는 컴포넌트 렌더링 방식

1. Static Rendering 가정
2. 컴포넌트 트리 생성
3. Dynamic Route 접근 컴포넌트를 만나면
4. Static Rendering을 중지(interrupt)시킨다.
5. Dynamic Rendering을 다시 진행시킴

### 변화된 렌더링 방식

PPR 렌더링 방식 - 컴포넌트 단위로 렌더링

1. static Rendering 가정
2. 컴포넌트 트리 생성
3. Dynamic Route 접근 컴포넌트를 만나면
4. 해당 컴포넌트를 Postpone 처리하고
5. 나머지를 static 렌더링을 진행
6. Postpone 처리했던 컴포넌트를 Dynamic 렌더링으로 재진행

\*Dynamic Route 접근 컴포넌트를 Postpone 시키기 위해서 해당 params를 비동기 처리(promise)해서 Postpone 시킴
