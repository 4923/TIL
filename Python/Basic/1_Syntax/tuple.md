# Dictionay 

### 요약
1. tuple은 여러가지 방식으로 선언할 수 있다.
    ```py
    # 프로그래머스 > 파이썬 입문
    tuple1 = (1,2,3)
    tuple2 = 1,2,3
    list3 = [1,2,3]
    tuple3 = tuple(list3)

    if tuple1 == tuple2 == tuple3:
        print("tuple1과 tuple2와 tuple3은 모두 같습니다.")
    ```
2. list처럼 index로 호출 가능
3. tuple의 값은 수정하거나 삭제할 수 없다.
4. tuple의 값은 정해진 순서를 바꿀 수 없다. (수정이 불가능하므로)
5. 함수에서 여러개의 값을 한번에 `return` 할 때 유용

### Packing, Unpacking
1. Packing
    * 하나의 변수에 여러개의 값을 저장하는 것.
    * 여러개의 값을 하나의 객체로 합친다.

2. Unpacking
    * packing된 변수에 저장된 여러개의 값을 꺼내는 것
    * Unpack 하려는 객체의 앞에 *(asterisk)를 붙이면 된다.

* 변수간의 값을 교환하는 예제
    ```py
    a, b = 1, 2
    a  # 1
    b  # 2
    ```
    ```py
    # packing : variable & int
    c = (3, 4)

    # unpacking : variable & variable
    d, e = c
    # c에 packing된 각 값이 d와 e에 unpacking된다.
    d  # 3
    e  # 4

    # packing : variable & variable
    f = d, e
    f  # (3, 4)
    ```

    * C 등의 언어에서는 두 변수의 값을 교환하기 위해 temp 변수를 추가로 사용했는데 파이썬에서는
        ```py
        # 변수 선언
        x = 10
        y = 20

        # 교환
        x, y = y, x

        # 결과
        x  # 20
        y  # 10
        ```

* map 함수와는 뭐가 다른가?
    * map
        * 파이썬 내장함수
        * 리스트에서 사용
        * 리스트의 원소마다 특정 함수를 적용
        * 수행결과 : map object
    * Unpacking은 iterable한 함수 (list, tuple, dict, map...)에 사용되는 개념이다.
        * iterable function : 인덱스로 접근할 수 있는 함수
            ```py
            list1 = [1, 2, 3, 4]
            print(list1)  # [1, 2, 3, 4]
            print(*list1)  # 1, 2, 3, 4
            ```

* 함수와 튜플
    여러개의 값을 리턴하기 위해 튜플을 사용한다.
    ```py
    def tuple_test():
        return 1, 2
    
    var1, var2 = tuple_test()

    print(var1, var2)  # 1, 2
    ```
    * 튜플을 활용한 함수의 리턴 값
    1. for문을 사용할 때 지금까지는
        ```py
        for ind, val in enumerate(list):
            print('{}번째 값: {}'.format(ind, val))
        ```
        위와 같이 변수 두개를 사용했다.

    2. 하지만 unpacking을 사용하면 `ind` 와 `val`를 `a`로 대체할 수 있다.
        ```py
        for a in enumerate(list):
            print('{}번째 값: {}'.format(a[0], a[1]))
        ```
        
    3. unpacking이므로 *를 사용할 수도 있다.
        ```py
        for a in enumerate(list):
            print('{}번째 값: {}'.format(*a))
        ```

    1, 2, 3번에서 실행한 코드의 값은 모두 동일하다.