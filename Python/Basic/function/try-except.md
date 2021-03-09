# try-except

try-except는 먼저 try절의 조건을 실행하고, 에러가 발생했을 때 except절의 조건을 수행하는 예외처리 문장이다.
### 기본 형태
```py
try:
    # 에러가 발생할 가능성이 있는 코드
except Exception: # 에러 종류
    #에러가 발생 했을 경우 처리할 코드
```
### 예외의 이름을 모를 때
```py
try:
    # 에러가 발생할 가능성이 있는 코드
except Exception as ex: # 에러 종류
    print('에러가 발생 했습니다', ex) # ex는 발생한 에러의 이름을 받아오는 변수
```

### 참고
* [BOJ 10951](https://github.com/4923/Algorithm/blob/master/BOJ/Solutions/10951_try-except_for_exception.md)
* [프로그래머스 > 파이썬 입문](https://programmers.co.kr/learn/courses/2/lessons/293)