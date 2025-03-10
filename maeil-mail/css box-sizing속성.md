box-sizing은 <strong>CSS에서 요소의 크기를 어떻게 계산할지 결정하는 속성이다.</strong>
레이아웃을 스타일링할 때 예상치 못한 크기(너비, 높이) 변화가 발생하는데, box-sizing 속성이 도움이 될 수 있다.

box-sizing 옵션

1. box-sizing: content-box(기본값)
   content-box는 box-sizing 속성의 기본값으로, 적용 시 요소의 width와 height값이 내용 영역만을 나타낸다. 즉, width와 height는 요소의 실제 콘텐츠 크기만을 정의하고, 그 안에 추가되는 padding과 border는 크기에 포함되지 않는다.

ex) width:200px로 설정된 요소에 padding 20px과 border:2px solid black이 있으면 요소의 실제 너비는 200px + 20px _ 2(padding) + 2px _ 2로 총 244px이 된다. padding과 border가 요소의 총 크기에 영향을 미친다는 점에서 때때로 예측하기 어려운 결과를 초래하기도 한다.

2. box-sizing: border-box
   border-box를 적용하면 width와 height값이 내용 영역, padding, border를 모두 포함하는 크기를 나타낸다. 즉, width와 height는 실제 콘텐츠의 크기뿐만 아니라 패딩과 테두리까지 포함된 크기로 설정된다. 예를 들어, width: 200px로 설정된 요소에 padding: 20px과 border: 2px solid black이 있으면, 자동으로 200px - 20px _ 2 - 2px _ 2 로 계산되어, 실제 콘텐츠 영역의 크기는 156px이 된다. 이 방식은 직관적으로 레이아웃의 크기를 예측하기 용이하다.
