# random.random()
0.0과 1.0 사이의 랜덤한 실수(float) x 반환(0.0 <= x < 1.0)

```
>>> random.random()
0.38472789375250527
```

# random.uniform(a, b)
a와 b 사이의 랜덤한 실수(float) x 반환(a <= x <= b)

```
>>> random.uniform(3, 9)
5.531850848384932
```

# random.randint(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x <= b)

```
>>> random.randint(3, 9)
3
```

# random.randrange(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x < b)  
만약 b 없이 a만 인자로 받았다면 0과 a 사이의 랜덤한 정수(int) x 반환 (0 <= x < a)

```
>>> random.randrange(3, 9)
4
>>> random.randrange(3)
1
```

# random.choice(seq)
seq(문자열, 튜플, 리스트, range)에서 무작위로 하나의 원소를 반환

```
>>> random.choice([1, 2, 3, 4, 5])
2
```

# random.shuffle(seq)
seq(리스트) 내 데이터의 순서를 무작위로 바꿈

```
>>> x = [1, 2, 3, 4, 5]
>>> random.shuffle(x)
>>> print(x)
[1, 3, 2, 5, 4]
```

# random.sample(seq or set, k)
seq(문자열, 튜플, 리스트, range) 또는 set에서 k개의 unique한 element를 뽑아 리스트를 만들어 반환

```
>>> random.sample([1, 2, 3, 4, 5], 3)
[3, 5, 4]
```
