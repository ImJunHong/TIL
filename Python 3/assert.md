# assert condition[, message]
* assert 뒤의 조건이 True가 아니라면 AssertionError를 발생시킴
* 오류를 찾는 것이 아닌, 값이 오류가 아님을 보증하는 일종의 디버깅 보조 도구
* 실수가 있을 것을 가정하고 가정 설정문을 통해 이를 방지하는 방어적 프로그래밍(defensive programming) 구현

```python
a = 50
assert a > 100, "100보다 크지 않음" # AssertionError: 100보다 크지 않음
```

# raise문과의 차이점
* raise문은 이미 오류를 발견한 상황에서 지정한 exception을 항상 발생시킴
* assert문은 상태를 검증하기 위한 명령으로, 검증식이 거짓일 때만 AssertionError를 발생시킴
