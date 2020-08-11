# numpy.array(lst)
입력받은 리스트를 ndarray(다차원 배열) 형태로 바꿈

```python
lst = [1, 2, 3, 4, 5]
arr = numpy.array(lst)
print(arr)
```
```bash
[1 2 3 4 5]
```

# numpy.arange([start,] stop, [step,] dtype=None)
* start부터 stop바로 앞까지 step만큼 일정하게 떨어져 있는 숫자들을 배열로 반환
* start가 없으면 0을 기본값으로, step이 없으면 1을 기본값으로 갖음
* dtype은 배열의 자료형을 명시적으로 지정할 때 사용

```python
print(numpy.arange(1, 6, 2))
print(numpy.arange(1, 6))
print(numpy.arange(6))
```
```bash
[1 3 5]
[1 2 3 4 5]
[0 1 2 3 4 5]
```
