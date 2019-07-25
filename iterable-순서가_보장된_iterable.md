# List
>가장 일반적인 iterable 자료형이자, 대표적인 sequence타입의 자료형이다  
>개인적으로는 자료형과 크기 제한이 없는 배열로 받아들였다  
>C에서 배열 쓰다가 이거 쓰면 짱편함  


```python
>>> li_1 = [1, 2, 3, 4, 5] # 배열처럼 사용
>>> li_2 = [1, 'two', 3, 'four', 5] # 여러개의 자료형을 한번에 담을 수 있음
>>> li_3 = [[1, 'one'], [2, 'two']] # 리스트에 리스트를 넣는 것이 가능하다!
```
리스트의 인덱스로 내부에 있는 값을 참조할 수 있다  

```python
>>> li_1[0]
1
>>> li_2[1]
'two'
>>> li_3[0][1]
'one'
```
리스트의 인덱스로 내부에 있는 일부 값을 변경할 수 있다

```python
>>> li_2[1] = 2
>>> li_2[3] = 4
>>> li_2
[1, 2, 3, 4, 5]
```

<br>

# Tuple
>리스트와 거의 똑같음(constanted list)  
>다만, 값을 초기화한 후 값 변경이 불가함  
>리스트를 쓰고싶은데 내부의 값은 고정된 상태로 유지하고 싶으면 튜플을 사용한다

```python
>>> tup = (1,2,3,4,5)
>>> tup[0] = 0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
>값 덮어쓰기는 가능
```python
>>> tup = (1, 2, 3)
>>> tup
(1, 2, 3)
>>> tup = (1, 2, 3, 4, 5)
>>> tup
(1, 2, 3, 4, 5)
```

# 인덱싱과 슬라이싱, 합과 곱
## 인덱싱
>인덱싱이란 여러 iterable에서 멤버에 접근할 수 있도록 하는 것이다  
>~~앞에서 이미 했죠..? 미안...~~
```python
>>> li = [1, 2, 3, 4, 5]
>>> li[0] # li라는 리스트의 0번째 요소를 참조한다
1
```
```python
>>> tup = (1, 2, 3, 4, 5)
>>> tup[0] # tup라는 튜플의 0번째 요소를 참조한다
1
```
>리스트와 튜플 외에도 iterable한 객체들은 모두 인덱싱을 할 수 있다

## 슬라이싱
>슬라이싱이란 iterable 중에서도 sequence type에서의 멤버들을 연속적으로 인덱싱하여 가져올 때 사용한다  
>슬라이싱을 하는 방법은 다음과 같다

    var_name[start:end-1]

```python
>>> li = [1, 2, 3, 4, 5]
>>> li[1:4] # 끝으로 적힌 인덱스는 참조하지 않는다!
[2, 3, 4] # 끝으로 적힌 인덱스 -1까지 참조한다
```
>시작 번호를 지정해주지 않으면 맨 처음부터 시작한다  
>마찬가지로 끝 번호를 지정해주지 않으면 맨 끝까지 참조한다  
>음수는 뒤에서부터 센다
```python
>>> li = [1, 2, 3, 4, 5]
>>> li[:3] # 0, 1, 2번 인덱스를 슬라이싱
[1, 2, 3]
>>> li[3:] # 3, 4번 인덱스를 슬라이싱
[4, 5]
>>> li[0:-1] # 뒤에서부터 1개를 배제하고 슬라이싱
[1, 2, 3, 4]
```

## 합과 곱  
>같은 자료형의 iterable 한 객체들에서 합 연산을 할 경우 합쳐진다  
```python
>>> li_1 = [1, 2, 3]
>>> li_2 = [4, 5]
>>> li_1 + li_2
[1, 2, 3, 4, 5]
```
>자료형이 다르면 에러를 토해낸다
```python
>>> li = [1,2,3]
>>> tup = (4,5)
>>> li+tup
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate list (not "tuple") to list
```
>iterable한 객체에 곱 연산은 정수형밖에 할 수 없다  
>곱 연산을 할 경우, 곱해진 정수만큼 객체가 반복된다  
```python
>>> li = [1, 2, 3, 4, 5]
>>> li * 3
[1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
```
실수형 곱셈연산도 에러,
```python
>>> li * 1.2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'float'
```
같은 리스트형 곱셈연산도 에러가 발생한다
```python
>>> li * li
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'list'
```
