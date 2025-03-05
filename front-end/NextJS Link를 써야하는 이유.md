### Routing & Navigation 과정(배경지식)

Routing => URL을 구성하고 조직화함(url segments)
Navigation => 이동 ex) home => example page 이동

### code split -> prefetech

1. code split(server)
   route segments 기준으로 서버에서 코드를 split 해놓고 해당 페이지에 접근하면 그 코드들을 불러옴

2. prefetch
   dev 환경이 아닌 production 환경에서 페이지 코드를 미리 가져옴(rsc) ==> Link 컴포넌트를 사용했을 때

### Link component를 써야하는 이유 + 대안

route segments에 해당하는 페이지의 rsc(관련된 파일)을 prefetch 함 => 렌더링 최적화

- 대안
  router를 이용해서 useEffect를 이용해서 router.prefetch를 사용하면 미리 가져옴
