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