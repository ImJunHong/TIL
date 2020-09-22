# copy.copy(x)
x의 얕은 사본을 반환

# copy.deepcopy(x)
x의 깊은 사본을 반환

```python
a = [1, 2, 3, [4, 5]]
b = copy.copy(a)

b[0] = 0 # b[0]은 immutable한 요소(int)
print(a) # [1, 2, 3, [4, 5]]
print(b) # [0, 2, 3, [4, 5]]

b[3][1] = 6 # b[3]은 mutable한 요소(list)
print(a) # [1, 2, 3, [4, 6]]
print(b) # [0, 2, 3, [4, 6]]
```
```python
a = [1, 2, 3, [4, 5]]
b = copy.deepcopy(a)

b[0] = 0
print(a) # [1, 2, 3, [4, 5]]
print(b) # [0, 2, 3, [4, 5]]

b[3][1] = 6
print(a)# [1, 2, 3, [4, 5]]
print(b)# [0, 2, 3, [4, 6]]
```

# 얕은 복사와 깊은 복사
## 얕은 복사(Shallow Copy)
* 객체를 복사하여 별도로 생성하나, 객체 내의 요소는 원본 객체의 요소와 같은 참조를 가리킴
* 객체 내에 mutable한 요소가 있을 때 해당 요소를 수정하면, 원본 객체의 요소도 수정됨

## 깊은 복사(Deep Copy)
* 객체를 복사하여 별도로 생성하고, 객체 내의 요소도 새롭게 생성함
* Deep Copy된 객체는 원본과의 참조가 완전히 끊어진 객체
