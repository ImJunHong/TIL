# collections.Counter([iterable-or-mapping])
* Counter는 해시 가능한 객체를 세기 위한 딕셔너리의 서브클래스
* 생성자의 매개변수로 iterable, mapping, keyword args가 올 수 있음
* 딕셔너리 인터페이스를 갖고 있어 Counter 인스턴스[키]로 값(키의 개수)에 접근할 수 있고, del로 삭제할 수 있음
* 딕셔너리와는 다르게 존재하지 않는 키에 접근하면 KeyError 대신 0을 반환함

## elements()
* Counter의 요소들을 저장된 순서대로, 저장된 개수만큼 반복하는 iterator를 반환함
```python
counter = Counter("HelloWorld")
for i in counter.elements():
    print(i)
```
```
H
e
l
l
l
o
o
W
r
d
```

## most_common([n])
* 개수가 가장 많은 요소부터 가장 적은 요소 순서대로 n개 나열한 리스트 반환
```python
counter = Counter(a=3, b=2, c=1, d=0) # 0은 물론 음수까지도 입력이 가능함
print(counter.most_common()) # [('a', 3), ('b', 2), ('c', 1), ('d', 0)]
print(counter.most_common(2)) # [('a', 3), ('b', 2)]
```

## update([iterable-or-mapping])
* 인자로 받은 iterable이나 mapping의 요소들을 추가함
* 원래 없는 요소는 추가되고, 원래 있던 요소는 개수를 더함
```python
counter = Counter({"a":3, "b":2, "c":1})
counter.update(a=1, b=-1, c=0, d=4)
print(counter) # Counter({'a': 4, 'd': 4, 'b': 1, 'c': 1})
```

# collections.defaultdict([default_factory[, key=value, ...]])
* 기본적으로 dictionary와 같은 기능을 함
* 존재하지 않는 key에 접근할 때, KeyError가 발생하지 않고 미리 지정한 디폴트 값을 반환함
* default_factory에 메소드를 인자로 받으며, 존재하지 않는 key에 접근할 때 해당 메소드의 반환값을 반환함
* default_factory를 생략하면 dictionary와 마찬가지로 KeyError가 발생함

```python
def function():
    return "default"

dictionary = {"a":1, "b":2, "c":3}
defaultdict1 = collections.defaultdict(function, a=1, b=2, c=3)
defaultdict2 = collections.defaultdict(a=1, b=2, c=3)
defaultdict3 = collections.defaultdict(int, a=1, b=2, c=3)
defaultdict4 = collections.defaultdict(list, a=1, b=2, c=3)
defaultdict5 = collections.defaultdict(dict, a=1, b=2, c=3)

print(dictionary["d"]) # KeyError: 'd'
print(defaultdict1["d"]) # default
print(defaultdict2["d"]) # KeyError: 'd'
print(defaultdict3["d"]) # 0
print(defaultdict4["d"]) # []
print(defaultdict5["d"]) # {}
```
