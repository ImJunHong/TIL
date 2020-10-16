# sys.stdin.readline(int)
- input()과 마찬가지로 입력받은 문자열 반환
- input()과는 다르게 맨 마지막에 개행문자 \n을 포함한 문자열을 반환함
- 매개변수로 입력 크기를 제한할 수 있다.
- input()보다 속도 면에서 더 빠름

```python
for i in sys.stdin.readline():
    print(i)
```
```
abc
a
b
c  

```

```python
for i in sys.stdin.readline(3):
    print(i)
```
```bash
abcde
a
b
c
```
