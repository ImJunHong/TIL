# random.random()
0.0과 1.0 사이의 랜덤한 실수(float) x 반환(0.0 <= x < 1.0)

# random.uniform(a, b)
a와 b 사이의 랜덤한 실수(float) x 반환(a <= x <= b)

# random.randint(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x <= b)

# random.randrange(a, b)
a와 b 사이의 랜덤한 정수(int) x 반환(a <= x < b)
만약 b 없이 a만 인자로 받았다면 0과 a 사이의 랜덤한 정수(int) x 반환 (0 <= x < a)

# random.choice(seq)
seq에서 무작위로 하나의 원소를 반환
※ seq이 비어있다면 indexError 발생
