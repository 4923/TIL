# 연결리스트 Linked List


## 기본 용어
파이썬 python의 리스트 list는 메모리 memory가 연속된 형태로 할당되어 상수시간 안에 무작위한 위치에 접근할 수 있지만 자료의 삽입 insert, 삭제 remove 등에 O(N)시간이 소요되는 단점이 있다.
연결리스트는 파이썬의 리스트보다 더 오래된 자료구조로, 각각의 데이터가 연결되는 기차에 비유할 수 있다. 이 때 데이터는 노드 node, 데이터간의 연결을 에지 edge 또는 링크 link 라고 한다.

* 노드 node : key + next(link)

    데이터가 할당되는 공간으로 데이터를 위한 값과 다음 노드로 이어지는 링크 정보가 포함되어야 한다.
    
    이 때 저장된 데이터의 실제 값을 key, 추가정보를 value, 링크 정보를 next라고 말한다.
    ```py
    class None
        def __init__(self, key, value=None):
            self.key = key
            self.value = value
            self.next = None  # 초기값은 None이다. 다음에 연결될 주소를 이 곳에 연결한다.
        def __str__(self):
            return str(self.key)  # 노드를 대표하는 값은 key이므로 key를 출력한다.
    ```

## 한방향 연결리스트 Singly Linked List
