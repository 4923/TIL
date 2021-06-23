# RecursionError: maximum recursion depth exceeded in comparison

### 재귀에러: 재귀 깊이의 최대값을 초과했다
<br>

1. 문제 상황
* 백준 8393: for문제를 재귀로 풀던 과정

2. 원인
* 재귀함수를 과도하게 호출 할 때 메모리 소비량은 비재귀함수보다 크다.
* 파이썬은 메모리를 경제적으로 사용하기 위해 재귀 호출 제한을 1000으로 설정한다.

3. 해결
* 재귀 호출 제한을 임의로 풀어준다

```py
import sys
sys.setrecursionlimit(10000)
```
