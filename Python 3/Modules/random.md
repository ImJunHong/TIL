# random.random()
0.0과 1.0 사이의 랜덤한 실수(float) x 반환(0.0 <= x < 1.0)

```python
random.random()
```
```bash
0.38472789375250527
```

# random.uniform(a, b)
a와 b 사이의 랜덤한 실수(float) x 반환(a <= x <= b)

```python
random.uniform(3, 9)
```
```bash
5.531850848384932
```

# random.randint(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x <= b)

```python
random.randint(3, 9)
```
```bash
3
```

# random.randrange(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x < b)  
만약 b 없이 a만 인자로 받았다면 0과 a 사이의 랜덤한 정수(int) x 반환 (0 <= x < a)

```python
random.randrange(3, 9)
```
```bash
4
```
```python
random.randrange(3)
```
```bash
1
```

# random.choice(seq)
seq(문자열, 튜플, 리스트, range)에서 무작위로 하나의 원소를 반환

```python
random.choice([1, 2, 3, 4, 5])
```
```bash
2
```

# random.shuffle(seq)
seq(리스트) 내 데이터의 순서를 무작위로 바꿈

```python
x = [1, 2, 3, 4, 5]
random.shuffle(x)
print(x)
```
```bash
[1, 3, 2, 5, 4]
```

# random.sample(seq or set, k)
seq(문자열, 튜플, 리스트, range) 또는 set에서 k개의 unique한 element를 뽑아 리스트를 만들어 반환

```python
random.sample([1, 2, 3, 4, 5], 3)
```
```bash
[3, 5, 4]
```

# random.seed(a=None)
난수 발생을 위한 시드를 설정  
시드가 같다면 동일한 난수를 생성함

```python
random.seed(5)
random.random()
```
```bash
0.6229016948897019
```
```python
random.random()
```
```bash
0.7417869892607294
```
```python
random.seed(5)
```
```bash
0.6229016948897019
```
```python
random.random()
```
```bash
0.7417869892607294
```
