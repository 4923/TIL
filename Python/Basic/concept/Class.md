# Class

## Contents
1. [클래스의 필요성](#클래스는-왜-필요한가?)
2. [문법](#문법)
3. [용어](#용어)
    * [1. 객체란?](#1-객체란?)
        1. 객체와 인스턴스의 차이
        2. 클래스와 인스턴스의 관계
    * [2. 메소드란?](#2-메소드란?)
        1. `self`
    * [3. 특수한 메소드](#3-특수한-메소드)
        1.  `__new__(cls)`
        2. `__init__(self)`
        3. `__str__(self)`
    * [4. 멤버변수](#4-멤버변수)
    * [5. 생성자와 소멸자](#5-생성자와-소멸자)
        1. 생성자
        2. 소멸자
    * [6. 상속과 오버라이드](#6-상속과-오버라이드)
        1. 상속
        2. 오버라이드
---

## 클래스는 왜 필요한가?
여러대의 계산기로 계산을 수행한다고 할 때, 계산기 함수를 여러개를 만들 수도 있지만 클래스를 사용 할 수도 있다.<br>
클래스를 사용하면 함수 여러개를 사용 했을 때와 동일한 효과를 볼 수 있기 때문이다

## 문법
* 클래스와 인스턴스를 이용하면 데이터와 코드를 사람이 이해하기 쉽게 포장할 수 있다.
* 생성된 클래스는 함수 처럼 `()`를 붙여 호출할 수 있다. `Class()`
* 클래스의 사용 예
```py
class Human():
    '''인간'''

person1 = Human()  # 인스턴스 생성
person2 = Human()  # 인스턴스 생성

# 인스턴스를 클래스처럼 사용할 수 있다.
person1.language = '한국어'
person2.language = 'English'

person1.person = '한국인'
person2.person = '인도인'

# 함수 선언
def speak():
    print(f'{person.person}은 {person.language}를 사용합니다.')

# 함수를 클래스에 적용 : 메소드 X -> 메소드 사용방법은 하단 참조
Human.speak = speak()

# 사용
# 아래 두 출력값은 같은 형식으로 출력된다.
speak(person1)  # 한국인은 한국어를 사용합니다.
person2.speak  # 인도인은 English를 사용합니다.
```

## 용어
### 1 객체란?
클래스로 만들어진 별개의 프로그램을 객체 object 라고 하는데, 이 객체는 다른 객체의 값에 영향을 받지 않는다.<br>
다시 말해, 객체는 각각 **고유한 성격**을 가진다. <br>
과자를 여러 개 만들 때, 과자 틀을 클래스에 비유한다면 과자 틀로 만들어진 각각의 과자는 객체라고 할 수 있을 것이다.<br>

    ```py
    # class
    class Cookie:
        pass

    # object
    # 클래스의 결과값을 돌려받은 a와 b가 객체다.
    a = Cookie()
    b = Cookie()
    ```

1. 객체와 인스턴스는 어떻게 다른가?
    > 객체는 개념이고 인스턴스는 실체다.

    클래스로 만든 객체를 인스턴스라고도 한다. OOP (Object Oriented Programming, 객체 지향 프로그래밍) 에서 객체와 인스턴스는 혼용이 가능하나 **인스턴스는 클래스와 함께 사용되는것이 자연스럽다.**<br>

    **객체는 클래스의 인스턴스이므로 실체에 가까운 개념은 인스턴스다.** 예를들어, MMORPG 게임에서 *던전*이라는 **클래스**가 있다면 **객체**는 모든 플레이어가 플레이하는 *A라는 이름의 던전*이고 **인스턴스**는 플레이어인 *내가 직접 플레이하는 던전 A의 복제* (통칭 인던, 인스턴스 던전) 이다.<br>

    * 인스턴스 여부를 확인하는 방법 : `isinstance(instance, type)`<br>
        * instance: 검사하고자 하는 인스턴스
        * type: 확인하고자 하는 클래스 또는 데이터 타입

2. 클래스와 인스턴스는 어떤 관계인가?
    > 너와 나는 모두 인간 클래스의 인스턴스이지만 같은 인스턴스는 아니다.
    ```py
    # 예시
    list1 = list("instance")
    list2 = list("instance")

    if list1 == list2:  # == 는 값을 비교하는 연산자다.
        print('list1과 list2의 값은 같지만'))
        if list1 is list2:  # is 는 같은 인스턴스인지 확인한다. 
            print('list1과 list2는 같은 인스턴스다.')  # 이 줄은 실행되지 않는다.
        else:
            print('list1과 list2는 다른 인스턴스다.')  # 이 줄은 실행된다.
    ```

### 2 메소드란?
* 메소드 method 란 클래스 안의 함수를 이르는 명칭이다. 
* 선언 및 사용방법은 함수와 다르지 않다.
```py
# 메소드를 활용한 클래스 활용 예
class Human():
    '''인간'''

    # person이라는 인스턴스에 name, weight 변수를 만들어 return하는 함수
    def create(name, weight):
        person = Human()
        person.name = name
        person.weight = weight
        return person

    def eat(self):
        self.weight += 0.1

    def walk(self):
        self.weight -= 0.1

person = Human.create("철수", 60.5)
eat()  

# 메소드가 아닌 함수를 호출하려면 person.eat = eat(person)을 선언하고
# eat(person) 또는 person.eat을 호출해야했다.
```
1. **`self`**
    * 생성된 객체 자기자신을 나타내는 예약어
    * 메소드의 첫번째 인자는 `self`이며 인스턴스를 호출할 때 `self`를 사용한다.
    * 단, 인스턴스의 매개변수를 전달할 때 self 인자는 **호출하지 않는다.**  
        * 예를들어 Class_example 이라는 클래스의 method_example(self) 라는 메소드를 호출하려면 `Class_example.method_example()` 만 사용하면 된다. 
        * 그러나 메소드의 인자가 다음과 같이 두개 method_example2(self, argument_example) 라면 호출 방법은 다음과 같아진다. `Class_example.method_example2(argument_example)`


### 3 특수한 메소드
* Python 에서 특수한 메소드는 메소드를 `__` 언더바 두개로 감싼다.
* Special Method, Magic Method 라고도 부른다.
* Python이 내부적으로 구현한 내장 메소드다.

1. **`__new(cls[,...])__`** : 객체 생성 함수
    1. 클래스 cls의 새 인스턴스를 만들기 위해 호출된다.
    2. 인스턴스를 생성할 때 가장 먼저 실행되는 함수다.
    3. 클래스 자기 자신 (cls) 을 숨겨진 인자로 받는다.
    4. 반드시 cls, 생성된 인스턴스를 return 한다.
        * 이 때 cls 인스턴스를 돌려주지 않으면 `__init__()`은 호출되지 않는다.
    5. Allocator (할당함수) 로, Constructor (생성자)가 아니다.

2. **`__init__(self[,...])`** : 초기화 함수
    1. `__new__()`에 의해 인스턴스가 만들어진 후, 호출자에게 돌려주기 위해 호출된다.
    2. 다시 말해, 인스턴스를 만드는 순간에 자동으로 호출된다.
        * 정리: `__new__()` 메소드가 인스턴스를 생성하면 `__init__()` 메소드가 이를 커스터마이징한다. (변수전달 등)
        * `__init__()`은 Class에 메모리를 할당하지 않는다.
    3. 주의! `__init__()` 메소드가 `None` 이외의 값을 돌려주면 실행 시간에 `TypeError`가 발생된다.
        ```py
        # __init__ 예시
        class Human():
            '''인간'''
            def __init__(self):
                print("__init__이 실행되었습니다.")

        # 출력
        person = Human()
        # __init__이 실행되었습니다.
        ```

    4. 인자
        * `self`는 새 인스턴스이며 그 외의 다른 인자를 포함 할 수 있다.
        * 이 때 self는 외의 다른 인자는 객체 생성자다.
        ```py
        # self 활용 예시
        class Human():
            '''인간'''
            def __init__(self, name, weight):
                print("__init__이 실행되었습니다.")
                print(f"이름은 {name}이고 몸무게는 {weight} 입니다.")

        # 출력
        person = Human("철수", 60)
        # __init__이 실행되었습니다.
        # 이름은 철수이고 몸무게는 60입니다.

        # 아무것도 하지 않았는데도 init 함수 안의 내용이 실행됨을 확인할 수 있다.
        ```

    5. 위에서 사용한 create 함수/메소드를 대체할 수 있다.
        ```py
        # create 함수와 비교
        class Human():
            '''인간'''
            def __init__(self, name, weight):
                '''초기화 함수'''
                self.name = name
                self.weight = weight

        # 출력
        person = Human ("철수", 60)
        print(person.name)
        print(person.weight)
        # 철수
        # 60

        # 이전에 사용한 create 메소드
        # 인스턴스명인 person이 self로 교체됨을 확인할 수 있다.
        class Human():
            '''인간'''

            # person이라는 인스턴스에 name, weight 변수를 만들어 return하는 함수
            def create(name, weight):
                person = Human()
                person.name = name
                person.weight = weight
                return person
        ```

3. **`__str__(self)`** : 문자열화 함수
    1. 인스턴스를 출력할 때 어떤 문자열을 출력할지 결정한다.
    2. 따로 print 처리 하지 않고 문자열을 return한다.
        ```py
        # __str__ 예시
        class Human():
            '''인간'''
            def __init__(self, name, weight):
                self.name = name
                self.weight = weight

            def __str__(self):
                return f"{name}(몸무게 : {weight}kg)"

        person = Human("철수", 60)
        # 출력
        print(person)
        # 철수(몸무게 : 60)
        ```
            
### 4 멤버 변수
* 클래스 안에 정의된 변수를 말한다.

### 5 생성자와 소멸자
1. 생성자 Constructor
    * `def __init__(self[,...]):`
    * 파이썬의 생성자는 객체를 생성할 때 호출되는 메소드다.
    * 객체를 생성할 때 초기화 작업을 위해 존재한다.
    * 생성 되는 객체의 변수를 세팅할 수 있다.
    * 참고사항
        * 객체를 직접 생성하지는 않는다.
        * 생성자는 인스턴스를 원하는 대로 사용하도록 커스터마이징하는 함수다.

2. 소멸자 Destructor
    * `def __del__(self)`
    * 객체가 소멸할 때 호출된다. finalizer라고도 부른다.
    * CPython에서는 오직 한번만 호출된다.
    * 리소스 해제 등 종료 작업을 위해 사용된다.

### 6 상속과 오버라이드
* 상속 inheritance
    * 클래스의 인자로 다른 클래스를 받는 것.
    * 중복된 코드를 줄이기 위해 사용한다.
    * 사용 방법
        1. 공통되는 메소드를 부모클래스에 선언한다.
        2. 독립된 기능을 하는 클래스의 인자로 부모 클래스를 받는다. == 자식클래스
        3. 자식클래스에 자식클래스만의 메소드를 추가한다.
        4. 사용방식은 일반적인 메소드 사용법과 동일하다.
* 오버라이드 override
    * 부모 클래스의 메소드를 자식클래스에서 덮어쓰는 것
    * 사용방법
        1. 자식클래스에서 덮어쓰기를 원하는 메소드를 생성한다.
            * 예: `wave(self)`, `wag(self)`
        2. 부모클래스의 메소드 이름과 동일한 메소드를 만든다.
            * 예: `greet()`
        3. 동일한 이름의 메소드에서 덮어쓰기를 원하는 메소드를 `self.덮어쓰기를원하는메소드()` 형식으로 호출한다.
            * 예: `person.wave()`, `dog.wag()`
        4. 부모클래스의 메소드가 아닌 자식 클래스의 메소드가 호출된다.

```py
class Animal():  # 부모 클래스
    def greet(self):
        print("인사하다")

class Cow():
    '''소'''  # 아무것도 안적으면 에러 발생하므로 주석을 추가한다.
    
class Human(Animal):  # 자식 클래스
    def wave(self):
        print("손을 흔들다")
    def greet(self):
        self.wave()

class Dog(Animal):  # 자식 클래스
    def wag(self):
        self.wag()

# 출력
cow = Cow()
cow.greet()  # 인사하다

person = Human()
person.greet()  # 손을 흔들다

dog = Dog()
dog.greet()  # 꼬리를 흔들다.
```





## 참고
* [점프 투 파이썬](https://wikidocs.net/28)
* [프로그래머스/파이썬 입문](https://programmers.co.kr/learn/courses/2)
* [__new__와 __init__의 차이](https://weeklyit.code.blog/2019/12/24/2019-12월-3주-python의-__init__과-__new__/)
* [Python 공식 문서 3.3: 특수 메서드 이름들](https://docs.python.org/ko/3/reference/datamodel.html#object.__new__)
* [파이썬 강좌 8-2편. 생성자와 소멸자(Constructor and Destructor)](https://blog.hexabrain.net/285)