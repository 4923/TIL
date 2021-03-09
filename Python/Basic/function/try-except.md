# try-except

### 개요
* try-except는 먼저 try절의 조건을 실행하고, 에러가 발생했을 때 except절의 조건을 수행하는 예외처리 문장이다.
* try 문은 하나 이상의 except 절을 가질 수 있다.
* except절은 tuple로 여러개의 에러 종류를 지정할 수 있다.
    ```py
    # 예시
    ... except (RuntimeError, TypeError, NameError):
    ...     pass
    ```
* except 절은 무시할 에러 종류를 생략 할 수 있으나 `except:` 실제 프로그래밍 에러를 가리기 쉽기 때문에 주의를 요한다.
* try-except문은 try 절이 예외를 일으키지 않을 경우에 실행하는 `else` 절을 포함할 수 있다.

### 기본 형태
```py
try:
    # 에러가 발생할 가능성이 있는 코드
except Exception: # 에러 종류
    #에러가 발생 했을 경우 처리할 코드

# 예시
>>> while True:
...     try:
...         x = int(input("Please enter a number: "))
...         break
...     except ValueError:
...         print("Oops!  That was no valid number.  Try again...")
...
```
### 예외의 이름을 모를 때
```py
try:
    # 에러가 발생할 가능성이 있는 코드
except Exception as ex: # 에러 종류
    print('에러가 발생 했습니다', ex) # ex는 발생한 에러의 이름을 받아오는 변수
```

### 참고
* [파이썬 공식문서 - 에러와 예외](https://docs.python.org/ko/3/tutorial/errors.html)
* [프로그래머스 > 파이썬 입문](https://programmers.co.kr/learn/courses/2/lessons/293)
* [BOJ 10951](https://github.com/4923/Algorithm/blob/master/BOJ/Solutions/10951_try-except_for_exception.md)