# bytes
bytes는 1바이트 단위의 값을 연속적으로 저장하는 시퀀스 자료형이다  

bytes로 바이트 객체를 만드는 방법은 3가지이고, 다음과 같다
>bytes(길이): 정해진 길이만큼 0으로 채워진 바이트 객체를 생성  
>bytes(반복가능한객체): 반복 가능한 객체로 바이트 객체를 생성  
>bytes(바이트객체): 바이트 객체로 바이트 객체를 생성  
```python
>>> bytes(10) # 0이 10개 들어있는 바이트 객체 생성
b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'

>>> bytes([10, 20, 30, 40, 50]) # 리스트로 바이트 객체 생성
b'\n\x14\x1e(2'

>>> bytes(b'hello') # 바이트 객체로 바이트 객체 생성
b'hello
```
>bytes는 요소의 변경이 불가하다
```python
>>> a = b'hello'
>>> a[0] = ord('a')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'bytes' object does not support item assignment
```

# bytearray
>bytes와 같으나, 요소를 변경할 수 있다  
```python
>>> a = bytearray(b'hello')
>>> a[0] = ord('a')
>>> a
bytearray(b'aello')
```

>파이썬에서 문자열의 기본 인코딩은 UTF-8인데, b'hello'와 같이 문자열을 바이트 객체로 만들면 각 문자를 ASCII 코드로 저장하기 때문에 보통 문자열을 UTF-8이 아닌 ASCII 코드로 처리하고 싶을 때 바이트 객체를 사용한다

```python
>>> 'hello'.encode()
b'hello'
```
>문자열을 바이트 객체로 바꾸려면 encode 메서드를 사용한다
```python
>>> b'hello'.decode()
'hello'
```
>반대로 바이트 객체를 문자열로 바꾸려면 decode 메서드를 사용한다  

또 바이트 객체가 특정 인코딩으로 되어 있다면 decode에 인코딩을 지정해주면 된다  

원문 : https://dojang.io/mod/page/view.php?id=2462