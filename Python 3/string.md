# find(str[,idx])
* 문자열 내에서 str을 찾고 index를 반환
* idx가 있으면 문자열 내의 idx 위치부터 str을 찾아 index를 반환
* 문자열 내에 str이 없을 경우 -1을 반환

```python
st = "ABCDEFG"

print(st.find("C"))
print(st.find("C",4))
print(st.find("H"))
```
```bash
2
-1
-1
```

# startswith(str[,start])
* 문자열이 str로 시작하는지 여부를 확인하여 Boolean 반환
* start가 있으면 문자열의 start 위치부터 str로 시작하는지 여부를 확인하여 Boolean 반환

```python
st = "ABCDEFG"

print(st.startswith("A"))
print(st.startswith("B"))
print(st.startswith("C",2))
```
```bash
True
False
True
```

# endswith(str[,start[,end]])
* 문자열이 str로 끝나는지 여부를 확인하여 Boolean 반환
* start가 있으면 문자열[start:]이, end도 있으면 문자열[start:end]이 str로 끝나는지 여부를 확인하여 Boolean 반환

```python
st = "ABCDEFG"

print(st.endswith("G"))
print(st.endswith("E"))
print(st.endswith("E",2))
print(st.endswith("E",2,5))
```
```bash
True
False
False
True
```
