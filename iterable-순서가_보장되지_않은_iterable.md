# dictionary
Key-Value를 한 쌍으로 가지는 자료형  
인덱스가 아닌 키를 통해서 값을 찾는 방식으로 데이터를 참조한다   
순서가 없는 iterable 객체이다
>Key-Value 구조는 딕셔너리 뿐만 아닌, 웹에서 데이터를 주고 받는 형식 중 하나인 JSON에도 사용된다  
>중괄호로 묶어서 표현하며, 키와 값이 모두 있어야 한다  
>Value는 중복이 가능하나, Key는 중복되면 한 값을 제외한 나머지 Key들은 모두 무시된다  
```python
>>> dic = {'key': 'value', 'one': 1} # key-value 쌍의 나열로 이루어진 자료형이다
>>> dic = {'key': 'value', 'one'} # key-value 쌍으로 값을 전달하지 않으면, 문법에러를 토해낸다
  File "<stdin>", line 1
    dic = {'key':'value', 'one'} 
                               ^
SyntaxError: invalid syntax
>>> dic = {'key':'value', 'key':'apple', 'key':'banana'} # Key를 중복되도록 설정했더니,
>>> dic
{'key': 'banana'} # 한 개만 빼놓고 사라진 것을 볼 수 있다
```

## 값 조회
>딕셔너리 객체의 데이터 참조는 다음과 같이 한다  

    var_name.get('Key')
    var_name['Key']

```python
>>> dic = {'key':'value', 'one':1}
>>> dic.get('key')
'value'
>>> dic['key']
'value'
```

## 값 추가, 수정, 삭제
>딕셔너리 객체에 값을 추가하거나, 수정하거나, 삭제할 때는 다음과 같이 한다  

    var_name['add_key'] = 'add_value' # 키-값 추가

    del(var_name['del_key']) # 키-값 삭제
    var_name.pop('del_key') # 키-값 삭제(값 반환 후 삭제)

    var_name['existing_key'] = 'alter_value' # 값 변경
    var_name['new_key'] = var_name.pop('old_key') # 키 변경

원문 : https://ledgku.tistory.com/49

<br>

# set
>집합은 여러 개의 자료를 하나의 변수로 관리할 때 사용하는 자료형 중 하나이다  
>순서가 없고, 중복도 허용하지 않는다(딕셔너리랑 비슷함)
>공집합(비어있는 집합)은 중괄호({})를 사용하면 만들 수 있다  

```python
>>> s = {} # 공집합
>>> s = {1, 1, 2, 3, 4, 4, 5} # 중복된 값을 저장하면,
>>> s
{1, 2, 3, 4, 5} # 알아서 지워진다
>>> s[1] # 인덱스로 접근을 시도하면,
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'set' object is not subscriptable # 에러를 뱉어낸다
```
자료형의 이름이 집합인 만큼 여러 집합 연산을 할 수 있다
```python
>>> s_1 = {1, 2, 3, 4}
>>> s_2 = {4, 5, 6}
>>> s_1 & s_2 # 두 집합의 교집합을 구한다
set(4)
>>> s_1 | s_2 # 두 집합의 합집합을 구한다
{1, 2, 3, 4, 5, 6}
>>> s_1 - s_2 # 두 집합의 차집합을 구한다
{1, 2, 3}
```
## 값 접근
다음과 같은 함수로 집합의 값에 접근할 수 있다  

    add(값) - 집합에 새로운 값을 추가한다. (중복된 값은 무시)

    remove(값) - 전달받은 값을 삭제 (없을 때 에러 메시지를 출력)
    discard(값) - 전달받은 값을 삭제 (없을 때 그냥 무시)
    pop() - 임의의 값을 리턴하고 삭제
    clear() - 집한에 있는 모든 값을 삭제

    copy() - 집합을 복제하여 리턴

또 값이 있는지 확인하려면 in 연산자를 사용하면 된다

```python
>>> s = {1, 2, 3, 4}
>>> 1 in s
True
>>> 5 in s
False 
```

원문 : https://www.codingfactory.net/10043#i-3  
참조 : https://withcoding.com/77