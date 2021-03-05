# CSS 우선순위
* CSS가 중복 적용될 때 어떤 속성이 우선할 것인지 결정하는 기준
  1. 속성값 뒤에 !important 여부
  2. 태그에 inline style로 속성을 지정한 것이 style 태그 내에서 style을 적용한 것보다 우선함
  3. #id 선택자로 지정된 속성
  4. style 태그 내에서 더 뒤에 작성된 속성이 앞에 작성된 속성보다 우선함
  5. .class 또는 :pseudo-class로 지정된 속성
  6. 태그 선택자로 지정된 속성
  7. 상속된 속성
* 우선순위가 같다면 CSS 명시도(specificity) 계산을 통해 명시도가 높은 속성이 우선함
  * inline style 방식이면 +1000
  * #id 선택자 1개당 +100
  * .class와 :pseudo-class 선택자 1개당 +10
  * 태그 선택자 1개당 +1
  * ::pseudo-element는 무시
