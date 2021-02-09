# 데코레이터
* 함수를 인자로 받아 코드를 추가한 뒤 다시 함수를 반환함
* 기존의 함수를 수정하지 않으면서 기능을 추가할 때 사용

# 함수 데코레이터
```python
# 함수 데코레이터의 구조
def decorator(function):
    def inner_function(*args, **kwargs):
        # 추가 코드
        function(*args, **kwargs)
        # 추가 코드
    return inner_function
```
```python
# 함수 데코레이터 사용 1
decorator(function(*args, **kwargs))

# 함수 데코레이터 사용 2
@decorator
def function(*args, **kwargs):
    # 코드
    
# 함수를 그대로 호출하면 decorator가 실행됨
function(*args, **kwargs)
```

# 클래스 데코레이터
```python
# 클래스 데코레이터의 구조
class Decorator:
    def __init__(self, function):
        self.function = function
    
    # __call__메소드는 클래스의 객체를 호출가능(callable)하게 만들어 줌
    def __call__(self, *args, **kwargs):
        # 추가 코드
        self.function(*args, **kwargs)
        # 추가 코드
```
```python
# 클래스 데코레이터 사용
@Decorator
def function(*args, **kwargs):
    # 코드

# 함수를 그대로 호출하면 Decorator가 실행됨
function(*args, **kwargs)
```
