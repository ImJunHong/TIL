# os.getcwd()
현재 경로를 반환

```python
print(os.getcwd())
```
```bash
C:\Users\tesse\OneDrive\바탕 화면\파이썬
```

# os.listdir(path)
path 내에 존재하는 파일과 디렉터리 목록을 리스트로 반환

```python
print(os.listdir())
```
```bash
['.vscode', 'adfadf.py', 'array_comprehensions.py', 'basic.txt', 'basic2.txt', 'beautiful_flask.py', 'beautiful_weather.py', 'binary_download.py', 'boolean.py', 'break.py', 'break01.py', 'call_with_func.py', 'class_func.py', 'class_var.py', 'compare_func.py', 'condition.py', 'date.py', 'date01.py', 'date02.py', 'date03.py', 'dddddddd.py', 'deco01.py', 'default_param.py', 'dfd.py', 'enumerate.py', 'ex.py', 'except01.py', 'except02.py', 'except_as.py', 'except_multi.py', 'factorial_for.py', 'factorial_recursion.py', 'false_value.py', 'fibonacci_memo.py', 'fibonacci_recursion01.py', 'fibonacci_recursion02.py', 'file_open.py', 'file_read.py', 'file_readlines.py', 'file_write.py', 'finally_loop.py', 'flask_basic.py', 'flask_basic.txt', 'format01.py', 'format02.py', 'format03.py', 'format04.py', 'format05.py', 'format06.py', 'format07.py', 'format_basic.py', 'for_dict.py', 'for_list.py', 'for_list01.py', 
'for_range.py', 'func_as_param.py', 'func_deco.py', 'fun_basic.py', 'garbage01.py', 'generator.py', 'generator01.py', 'getter_setter.py', 'handle_with_condition.py', 'handle_with_try.py', 'hello.py', 'hello.txt', 'if_string.py', 'if_string01.py', 'if_string02.py', 'infinite_loop.py', 'info.txt', 'inherit01.py', 'inherit02.py', 'inherit03.py', 'inherit04.py', 'input.py', 'input_error.py', 'int_convert.py', 'int_float01.py', 'int_float02.py', 'isinstance.py', 'items.py', 'iterator01.py', 'lambda01.py', 'lambda02.py', 'list01.py', 'list02.py', 'list03.py', 'list_in.py', 'list_range01.py', 'main.py', 'math_simple.py', 'minmax.py', 'minmax.txt', 'module_datetime.py', 'module_datetime_add.py', 'module_example', 'module_main', 'module_os.py', 'module_random.py', 'module_sys.py', 'module_time.py', 'module_urllib.py', 'object_1_basic.py', 'object_2_dict.py', 'object_3_seperate.py', 'object_4_class.py', 'Omok', 'omok_v1.0', 'output.png', 'output.py', 'param_basic.py', 'param_examples.py', 'param_keyword01.py', 'pass_keyword.py', 'pass_keyword01.py', 'private_var.py', 'pt.py', 'pyqt', 'PyQt5 연습', 'Q_black.txt', 'return_only.py', 'return_with_data.py', 'reversed.py', 'reversed_for01.py', 'reversed_for02.py', 'str.py', 'string01.py', 'string02.py', 'string03.py', 'string_operator.py', 'string_operator01.py', 'string_operator02.py', 'str_func.py', 'sum_all_basic.py', 'sum_all_with_default.py', 'tesseract', 'test.py', 'test_package', 'TIL', 'try_except_else.py', 'try_except_else_finally.py', 'try_pass.py', 'try_return01.py', 'try_return02.py', 'tuple_basic.py', 'tuple_return.py', 'tuple_use01.py', 'tuple_use02.py', 'variable.py', 'variable_param.py', 'while_as_for.py', 'while_with_condition.py', 'while_with_time.py', '__pycache__', '강화학습', '딥러닝', '실험용.py', '연습.py', '오목', '웹크롤링', '자료구조
_알고리즘', '코딩도장', '파이게임', '폴더01', '폴더02']
```

# os.mkdir(path)
새로운 폴더 생성

# os.makedirs(path)
* 새로운 폴더 생성
* 여러 개의 디렉터리를 생성할 수 있음
  (os.mkdir()는 중간 경로의 디렉터리가 존재하지 않으면 에러 발생, os.makedirs()는 존재하지 않는 중간 경로의 디렉터리도 생성)

```python
os.makedirs('./A')
os.makedirs('./B/C/D')
os.mkdir('./E/F/G')
```
```bash
Traceback (most recent call last):
  File "test.py", line 5, in <module>
    os.mkdir('./E/F/G')
FileNotFoundError: [WinError 3] 지정된 경로를 찾을 수 없습니다: './E/F/G'
```

# os.rmdir(path)
* 빈 폴더 삭제
* 폴더가 비어있지 않다면 OSError 발생

# os.remove(path)
* path(파일)를 삭제
* 폴더와 그 안의 파일을 동시에 모두 삭제하려면 [shutil 모듈](https://github.com/ImJunHong/TIL/blob/master/Python%203/Modules/shutil.md#shutilrmtreepath) 사용

# os.path.isdir(path)
path(폴더)가 존재하는지 확인하여 Boolean 반환

```python
print(os.path.isdir('./A'))
```
```bash
True
```

# os.path.isfile(path)
path(파일)가 존재하는지 확인하여 Boolean 반환

```python
print(os.path.isfile('./A/a.txt'))
```
```bash
False
```

# os.path.join(path, \*paths)
path들을 병합한 새 경로 반환

```python
print(os.path.join(".", "A", "B"))
```
```bash
.\A\B
```
