# numpy.array(lst)
입력받은 리스트를 ndarray(다차원 배열) 형태로 바꾸어 반환

```python
lst = [1, 2, 3, 4, 5]
arr = numpy.array(lst)

print(arr)
```
```bash
[1 2 3 4 5]
```

# numpy.arange([start,] stop [,step])
* start부터 stop바로 앞까지 step만큼 일정하게 떨어져 있는 숫자들을 배열로 반환
* start가 없으면 0을 기본값으로, step이 없으면 1을 기본값으로 갖음

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

# numpy.zeros(shape)/ones(shape)
* shape(정수 또는 정수로 구성된 튜플) 모양의 ndarray 반환
* zeros()는 모든 값이 0인 배열 생성, ones()는 모든 값이 1인 배열 반환

```python
print(numpy.zeros((2,3)))
print(numpy.ones((2,3)))
print(numpy.zeros(3))
print(numpy.ones((3,)))
print(numpy.zeros((2, 3, 4)))
```
```bash
[[0. 0. 0.] 
 [0. 0. 0.]]
[[1. 1. 1.] 
 [1. 1. 1.]]
[0. 0. 0.]
[1. 1. 1.]
[[[0. 0. 0. 0.]
  [0. 0. 0. 0.]
  [0. 0. 0. 0.]]

 [[0. 0. 0. 0.]
  [0. 0. 0. 0.]
  [0. 0. 0. 0.]]]
```

# numpy.empty(shape)
초기화되지 않은 값으로 shape 모양의 ndarray 반환

```python
print(numpy.empty((2,3)))
```
```bash
[[ 4.64583300e-308  4.66664552e-308 -2.57703408e+010]
 [-4.70231646e-064  2.26262303e-319  0.00000000e+000]] # 가비지 값으로 채워진 배열 반환
```

# numpy.zeros_like(arr)/ones_like(arr)/empty_like(arr)
arr의 shape 크기만큼 지정된 값으로 채운 배열 반환

```python
arr = numpy.array([[2, 3], [4, 5]])

print(numpy.zeros_like(arr))
print(numpy.ones_like(arr))
print(numpy.empty_like(arr))
```
```bash
[[0 0]
 [0 0]]
[[1 1]
 [1 1]]
[[0 0]
 [0 0]]
```

# numpy.argmax(arr[,axis])/argmin(arr[,axis])
* 최댓값과 최솟값의 index를 반환
* axis가 0이면 열, 1이면 행을 기준으로 최댓값과 최솟값의 index값으로 된 배열 반환

```python
arr = numpy.array([[1, 2, 3], [9, 8, 7], [4, 6, 5]])

print(arr)
print(numpy.argmax(arr))
print(numpy.argmin(arr))
print(numpy.argmax(arr,axis=0))
print(numpy.argmax(arr,axis=1))
print(numpy.argmin(arr,axis=0))
print(numpy.argmin(arr,axis=1))
```
```bash
[[1 2 3]
 [9 8 7]
 [4 6 5]]
3
0
[1 1 1]
[2 0 1]
[0 0 0]
[0 2 0]
```

# numpy.where(condition [,x,y])
* 배열의 각 요소를 condition과 비교하여 True면 x로, False면 y로 바꾼 배열을 반환
* condition만 인자로 받으면 condition을 만족하는 값의 index를 반환

```python
arr = numpy.array([[1, 2, 3], [4, 5, 6]])

print(numpy.where(arr > 2, 0, 1))
print(numpy.where(arr > 2))
```
```bash
[[1 1 0]
 [0 0 0]]
(array([0, 1, 1, 1], dtype=int64), array([2, 0, 1, 2], dtype=int64))
```
