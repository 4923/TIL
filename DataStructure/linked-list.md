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
한방향 연결리스트는 한쪽으로만 연결되는 일방통행 연결리스트다. 반대편으로는 이동할 수 없다.

리스트처럼 인덱스로 이동할 수 없지만 시작과 끝을 정의할 수는 있는데, 시작 노드를 `head` 라고 하며 끝 노드를 `tail`이라고 한다.

필요에 따라 노드의 수, 또는 데이터의 수를 저장하는 `size`도 포함할 수 있다. (optional)

```py
class SinglyLinkedList:
    def __init__(self):
        self.head = None  # 초기값 None, head 노드를 저장
        self.size = 0  # 초기값 0, 연결리스트의 노드 개수
    
    def __len__(self):
        return self.size  # len(list) == 데이터의 개수
```

* 한방향 연결리스트의 연산

    연산을 SinglyLinkedList의 메소드 method로 정의한다.
    
    빈 리스트라면 head도 tail도 None이다. (None이 기본값이므로)

    1. `pushFront`
    * 리스트의 가장 앞 head 노드에 새로운 노드 삽입
    * stack의 `push`와 같은 연산이다.
        ```py
        # SinglyLinkedList의 메소드
            def pushFront(self, key, value=None):
                new_node = Node(key, value)  # 노드를 생성
                new_node.next = self.head  # (원래) head와 연결
                self.head = new_node  # head 노드를 새로 생긴 노드로 변경
                self.size += 1  # 새 노드를 추가했으므로 size에 1 추가
        ```

    2. `pushBack`
    * 리스트의 가장 마지막 tail 노드에 새로운 노드 삽입
    * tail 노드를 찾는 방법은 모든 링크를 따라가는 방법 뿐이다. (while을 쓰는 이유)
    * 일반 리스트의 append보다 느리다. (append : O(1), pushBack : O(N))

        ```py
        # SinglyLinkedList의 메소드
            def pushBack(self, key, value=None):
                new_node = Node(key, value)  # 노드를 생성
                # case 1
                if self.size == 0:  # 빈 리스트이면
                    self.head = new_node  # 새 노드가 head가 된다.
                # case 2
                else:  # 빈 리스트가 아니면
                    tail = self.head
                    while tail.next != None: # 다음 노드가 None이란건 그 노드가 마지막 노드라는 말
                        tail = tail.next  # 마지막 노드가 아닐 때에만 while이 돌아가므로 그 다음노드로 교체
                    tail.next = new_node  # tail을 교체
                self.size += 1  # 새 노드를 추가했으므로 size에 1 추가
        ```
    
    3. `popFront`
    * head를 삭제한 후 head의 (key, value)쌍 반환.
    * 빈 리스트라면 error가 아니라 (None, None)을 반환해야한다.
    * 일반 리스트의 list.pop(0)보다 빠르다. (pop : O(N), popFront : O(1))

    ```py
    def popFront(self):
        key = value = None  # None으로 기본세팅
        if len(self) > 0:   # 빈 리스트가 아닐 경우 head를 교체하는 작업 필요
            key = self.head.key  # 반환하기 위해 key에 값 할당
            value = self.head.value  # 반환하기 위해 value에 값 할당
            self.head = self.head.next  # head 교체
            self.size -= 1  # 노드를 삭제하므로 size에 1 감소
        return key, value
    ```

    4. `popBack`
    * tail을 삭제한 후 (key, value)쌍 반환
    * 빈 리스트라면 (None, None) 반환
    * 마지막보다 하나 이전 노드를 tail로 설정해야하므로 `previous` 노드를 탐색한다.

    ```py
    def popBack(self):
        # 빈 리스트일 때
        if len(self) == 0:
            return None, None
        # running technique
        else:
            previous, tail = None, self.head
            # step 1 : tail에 도달할 때 까지 이동
            while tail.next != None:  # 다음 노드가 None이란건 current == tail이라는 것
                previous, tail = tail, tail.next
            # step 2 : tail이 실제로 마지막 노드를 향할 때
            key, value = tail.key, tail.value
            # step 3 : tail을 교체
            if self.head == tail:  # size == 1 일 때, previous == None이고 head == tail
                self.head = None
            else:
                previous.next = tail.next  # tail 교체
            # step 4 : size 감소
            self.size -= 1
            return key, value
    ```

    4. `search`
    * 노드를 차례로 방문하는 연산이다.
    * 인자인 key와 동일한 값을 갖는 노드를 반환하고 없을 시 **None을 반환한다.`
    ```py
    def search(self, key):
        v = self.head
        while v != None:  # while v라고 작성해도 무관하다.
            if v.key == key:
                return v
        return None  # None이 아닌 v를 반환해도 된다. v가 향하는 마지막 값은 None이고 v에 실제 값이 할당되었다면 if문에서 이미 값이 반환되었을것이기 때문이다.
    ```

    