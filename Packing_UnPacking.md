# Packing
>하나의 변수에 여러 값을 넣는 것  
>네, 리스트, 튜플, 딕셔너리, 집합, 문자열까지 앞에서 배운거 그거 맞워요 

<br>

# UnPacking
>패킹된 변수에서 여러개의 값을 꺼내오는 것  
```python
>>> li = [1, 2, 3, 4, 5] # 다섯 개의 값을,
>>> a, b, c, d, e = li # 다섯 개의 변수에 각각 저장
>>> a
1
>>> b
2
>>> c
3
>>> d
4
>>> e
5
```
```python
>>> dic = {'key':'value', 'one':1} # 딕셔너리는 키값만 저장됨
>>> key_1, key_2 = dic
>>> key_1
'key'
>>> key_2
'one'
>>> a, b, c, d = dic # value 까지 저장하려고 시도하면 뱉어내는 오류
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: not enough values to unpack (expected 4, got 2)
```