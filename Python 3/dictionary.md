# get(key[, default])
* 딕셔너리의 key에 대응되는 값을 반환(dict[key]와 동일한 값 반환)
* 딕셔너리 내에 key가 존재하지 않으면 None 반환(dict[key]의 경우 KeyError 발생)
* default를 지정하면 딕셔너리 내에 key가 존재하지 않을 때 default를 반환

```python
dic = {"A":1, "B":2, "C":3}

print(dic.get("A")) # 1
print(dic.get("D")) # None
print(dic.get("A", 0)) # 1
print(dic.get("D", 0)) # 0
```
