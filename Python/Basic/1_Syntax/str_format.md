# string formatting (built-in types)

* [Documentation](https://docs.python.org/3/library/stdtypes.html?highlight=문자열 포매팅#)

## 1. `format(*args, **kwargs)`

* 부호만 앞에 출력하는 방법
    `{}.format()` 방식에서 중괄호로 구분된 치환필드 `{}` 에 `>` 가 아닌 `=` 를 입력하면 부호만 따로 떨어져서 출력된다.
    ```py
    '''일반적인 방법'''
    '{:> + 30d}'.format(a)
    #                            +10
    
    '''부호만 맨 앞에 출력하기'''
    '{:= + 30d}'.format(a)
    '{:= + 30d}'.format(+a)
    # +                           10
    '{:= + 30d}'.format(-a)
    # -                           10
    ```


## 2. printf


## 3. f-string