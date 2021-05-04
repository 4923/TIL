# 삼항연산자 in Python
##### [참고1](https://book.pythontips.com/en/latest/ternary_operators.html) [참고2](https://jamanbbo.tistory.com/9)

### 개요

파이썬에서도 삼항연산자를 사용할 수 있다. 삼항 연산자 ternary operator는 조건이 참일 때 value1을 반환하고 거짓일 때 value2를 반환하는 연산자다.

##### C에서의 삼항연산자
```c
// ternary operator in C
condition ? value_if_true : value_if_false
```
C나 Java에서는 위와 같이 `?` 를 사용하지만 파이썬은 조금 더 영어에 가까운 형태를 취한다.


##### Python에서의 삼항연산자
```py
# ternary operator in python
value_if_true if condition else value_if_false
```

삼항연산자는 조건문을 빠르게 한 줄로 검사할 때 사용하는데, 이는 코드를 compact 하게 작성하거나 유지보수할 때 편리하다.

* tuple을 활용한 예
    ```py
    # Blueprint
    (if_test_is_false, if_test_is_true)[test]
    ```
    ```py
    # Examples
    nice = True
    personality = ("mean", "nice")[nice]
    print("The cat is ", personality)
    # Output: The cat is nice
    ```

* list comprehension과 함께 사용할 수도 있다.
    1. 사용방법 1
        ```py
        [i for i in range (1, 6) if i %2 == 0]
        # Output: 2, 4
        ```
        for문 이후의 if문이 삼항연산자다. if문이 참일 때 if문 좌측의 for문이 돌아간다.
    2. 사용방법 2
        ```py
        [i if i != 0 else 0 for i in range (1, 6)]
        # Output: 0,2,0,4,0
        ```
        for문 좌측에 if문을 사용할 경우 else문과 함께 사용해야 한다. 그러지 않을 시 Syntax Error가 발생한다.
    
