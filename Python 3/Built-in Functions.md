# zip(*iterables)
* iterable들의 같은 인덱스에 있는 각 요소를 튜플로 묶어 반환
* iterable들의 길이가 서로 다르다면, 가장 짧은 iterable의 길이만큼만 반환

```python
a = [1, 2, 3]
b = [4, 5, 6]
c = [7, 8]

for i in zip(a, b):
    print(i)
print()

for i in zip(a, c):
    print(i)
print()

print(dict(zip(a, b)))
```
```bash
(1, 4)
(2, 5)
(3, 6)

(1, 7)
(2, 8)

{1: 4, 2: 5, 3: 6}
```
