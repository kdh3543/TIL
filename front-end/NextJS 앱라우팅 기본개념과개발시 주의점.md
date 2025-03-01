## 앱 라우팅

### 기본개념

트리구조

1. Tree: 최상단에 있는 app
2. Subtree: 하위에 있는 폴더 구조를 묶어서 Subtree라 함
3. Root: Tree나 Subtree의 최상단에 있는 폴더를 Root라 함
4. Leaf: 최끝단에 있는 폴더

5. URL Path: 폴더 단위로 되어있는 path로 접근해서 나오는 도메인 ex) localhost:3000/dashboard/settings
6. URL Segment: 폴더 이름, URL Path를 슬래시(/) 단위로 나뉘어져 있는 단위

### 주의점

1. pages router, app router 혼용 시

- 둘 다 같이 사용 가능하지만 같은 pathname(url path)이 겹칠 때 build time error가 발생할 수 있음

2. Colocation

- ex) app 하위에 example/components/button.tsx URL과 무관함 => Next JS 자체에서 최하위에 page.tsx로 정의하지 않으면 URL path로 인식하지 않음
