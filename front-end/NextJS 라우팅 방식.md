### Routing 정의

Selecting process => path
CSR에서는 HTML 하나만 내려주기 때문에 path가 하나로 정해져있음
하지만 SSR에서는 여러 개의 path를 받을 수 있기 때문에 path를 selecting하는 process가 필요함 -> Next.js에서 Routing이 중요한 이유

### 다양한 Routing 방식

1. 명시적 라우팅 -> React-router(CSR)<br/>
   ex)

```
<Route path='/' components={`<Home/>`} />
```

2. 코드기반 라우팅 -> express<br/>
   ex)

```
app.get('/', (req, res) => {
  res.send('Homepage contents')
})
```

3. 데코레이터 기반 라우팅(Nest JS)<br/>
   ex)

```
@controller('user')
export class UsersController {
  @get()
  findAll() :string{
    return '~~'
  }
}
```

### Next JS Routing 배경, 방식, 장점

파일구조 기반 Routing
pages/app

- pages 기반 routing
  pages/about.jsx => localhost:3000/about 접근 시 pages에 있는 about.tsx 호출<br/>

- app 기반 routing
  app/about/pages.tsx

pages -> app 라우터로 바뀐 이유()
about 폴더 안에 pages.tsx 외에도 layout.tsx, error.tsx, loading.tsx, template.tsx 이 필요
=> 자주 사용하는 파일을 쉽게 사용할 수 있도록 추상화시킴
=> app router의 File Convention
=> pages에 비해 기능의 추가적인 장점

파일구조 기반 Routing 장점

- 직관적
- 자동 코드 스플리팅(path가 다 나뉘어져 있기 때문에 쪼개서 응답하면 응답 속도가 더 빠름)
- Colocation(명확한 프로젝트 구조) => 유지 보수 용이
