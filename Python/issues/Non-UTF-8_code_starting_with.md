# SyntaxError: Non-UTF-8 code starting with '\xeb' in file 

### 문법 오류
<br>

1. 문제 상황
* 백준 10250: 파일명 바꾸고 실행하려는데 해당 에러 발생

2. 원인
* 코드의 한글을 파이썬이 읽지 못하는 경우 발생하는 에러

3. 해결
* 코드 최상단에 한글 인코딩 옵션 추가

```py
# -*- coding: utf-8 -*- 
```
