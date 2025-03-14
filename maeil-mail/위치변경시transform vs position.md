애니메이션이나 동적인 위치 변경이 필요한 경우 transform을 선호한다.

transform을 선호하는 이유는 성능 때문이다. transform은 브라우저의 composite 단계에서 실행된다. 따라서 reflow나 repaint를 유발하지 않아 성능 상 이점이 있다.

반면, position 관련 속성을 이용한 위치 변경은 reflow, repaint를 유발한다. 예를 들어 top, left 등의 속성을 변경하면 브라우저는 주변 요소들의 위치를 다시 계산하는 과정부터 다시 수행하며, 이는 성능 부하를 높인다.

두 방식을 사용하여 버튼 호버 시 위로 올라가는 효과를 구현하면 다음과 같다.

```
.button: hover {
  transform: translateY(-5px)
}
.button {
  position: relative
}
.button:hover {
  top: -5px;
}
```

### position 관련 속성 사용 경우

레이아웃 구조를 잡거나, 부모를 기준으로 위치를 조정할 때에는 position을 사용한다. transform은 시각적인 위치만 변경할 뿐 실제 문서 흐름과 무관하게 동작하기 때문에, 문서 흐름에 따라 조정되는 경우에는 사용할 수 없기 때문이다.
