# Dictionay [참고](https://wikidocs.net/16#value-values)

### 요약
* 기본 형태
    ```py
        dict_ = {key1: value1, key2: value2}
    ```
* **key와 value**를 한 쌍으로 갖는다.
    * **key**는 **고유한 값**이므로 변하지 않는 값을 넣어야 하지만 **value**에는 변하는 값도 넣을 수 있다.
    * key는 하나에 **여러개의 value**가 들어 갈 수 있다.
    * 대응관계를 나타내는 자료형이라고 하는데, 다른 언어에서는 이를 *"연관 배열(Associative array) 또는 해시(Hash)라고 한다."*
* 인덱스로 접근이 불가하며 key를 통해 value 값을 찾는다.

### 사용방법
* k-v 추가
    * `딕셔너리이름[key값] = 'value값'`으로 추가한다.
        ```py
            example = {'A': 'apple', 'B': 'bananna'}
            example['C'] = 'cat'
            example  # {'A': 'apple', 'B': 'bananna', 'C': 'cat'}
        ```
    * 한 key값에 여러 value 값을 넣을 수 있다.
        ```py
            example2 = {'alphabet': ['a','b','c']}
            example2['number'] = [1, 2, 3]
            example2  # {'alphabet': ['a','b','c'], 'number':[1,2,3]}
        ```

* k-v 삭제
    * list와 같이 `del` 함수를 사용하면 된다.
        ```py
            del example['A']
            example  # {'B': 'bananna', 'C': 'cat'}

* key로 value 얻기
    * dict type은 인덱싱이나 슬라이싱 기법을 사용 할 수 없다.
    * `딕셔너리이름[key값]` 으로 value를 얻을 수 있다.
        ```py
            example3 = {'오늘날씨': '맑음', '내일날씨': '비'}
            example3[오늘날씨]  # '맑음'
        ```

### 관련 함수
* key 리스트 만들기: `dic.keys()`
    * 딕셔너리의 key만을 모아서 dict_keys 객체를 돌려준다.
        ```py
            >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
            >>> a.keys()
            dict_keys(['name', 'phone', 'birth'])
        ```
    * list처럼 사용 할 수 있지만 list 고유의 함수는 사용 할 수 없다.
* value 리스트 만들기: `dic.values()`
    * `dic.keys()`와 사용방법은 같다.
* k-v 쌍 얻기: `dic.items()`
    * key와 value를 튜플로 묶은 값을 돌려준다.
        ```py
            >>> a.items()
            dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])
        ```
* k-v 쌍 지우기: `dic.clear()`
    * 딕셔너리 안의 모든 요소를 삭제한다.
* key로 value 얻기: **`dic.get('keyvalue')`**
    * `dic['key']`와 동일한 기능을 하지만 존재하지 않는 key를 가져오려고 할 때 `dic['key']`는 key 오류를 발생시키고 `dic.get('key')`는 None을 돌려준다.
    * `dic.kget('key','default')`: 찾으려는 key 값이 없을 경우 default 값을 내보낼 수도 있다.
* key값이 딕셔너리 안에 있는지 확인: `'key' in dic`
    * bool값을 반환한다.