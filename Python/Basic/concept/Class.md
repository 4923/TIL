# Class
##### 참고 : [점프 투 파이썬](https://wikidocs.net/28)

## Contents
1. [클래스 Class 의 필요성](#클래스-class-는-왜-필요한가?)
2. 문법[#문법]
3. 용어[#용어]
    * [객체 object 란?](#객체-object-란?)
        1. [객체와 인스턴스의 차이](#1\)-객체와-인스턴스-instance는-어떻게-다른가?)
        2. [클래스와 인스턴스의 관계](#2\)-클래스와-인스턴스는-어떤-관계인가?)
    * [메소드 method 란?](#메소드-method-란?)
    * [생성자 constructor 와 소멸자 destructor](#생성자-constructor-와-소멸자-destructor)

<hr>
<br>

## 클래스 Class 는 왜 필요한가?
여러대의 계산기로 계산을 수행한다고 할 때, 계산기 함수를 여러개를 만들 수도 있지만 클래스를 사용 할 수도 있다.<br>
클래스를 사용하면 함수 여러개를 사용 했을 때와 동일한 효과를 볼 수 있기 때문이다.<br>

## 문법
* 클래스와 인스턴스를 이용하면 데이터와 코드를 사람이 이해하기 쉽게 포장할 수 있다.
* 생성된 클래스는 함수 처럼 `()`를 붙여 호출할 수 있다. `Class()`
* 클래스의 사용 예
    ```py
    class Human():
        '사람'

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

    # 함수를 클래스에 적용하려면 아래처럼 함수를 대입하면 된다. (클래스 안에 함수가 포함될 수 있으므로 블럭 안에 포함시켜도 쿠관)
    Human.speak = speak()

    # 사용
    # 아래 두 출력값은 같은 형식으로 출력된다.
    speak(person1)  # 한국인은 한국어를 사용합니다.
    person2.speak  # 인도인은 English를 사용합니다.
    ```
<br>

## 용어
### 객체 object 란?
클래스로 만들어진 별개의 프로그램을 객체라고 하는데, 이 객체는 다른 객체의 값에 영향을 받지 않는다.<br>
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

#### 1) 객체와 인스턴스 instance는 어떻게 다른가?
> 객체는 개념이고 인스턴스는 실체다.

클래스로 만든 객체를 인스턴스라고도 한다. OOP (Object Oriented Programming, 객체 지향 프로그래밍) 에서 객체와 인스턴스는 혼용이 가능하나 **인스턴스는 클래스와 함께 사용되는것이 자연스럽다.**<br>

**객체는 클래스의 인스턴스이므로 실체에 가까운 개념은 인스턴스다.** 예를들어, MMORPG 게임에서 *던전*이라는 **클래스**가 있다면 **객체**는 모든 플레이어가 플레이하는 *A라는 이름의 던전*이고 **인스턴스**는 플레이어인 *내가 직접 플레이하는 던전 A의 복제* (통칭 인던, 인스턴스 던전) 이다.<br>

* 인스턴스 여부를 확인하는 방법 : `isinstance(instance, type)`<br>
    * instance: 검사하고자 하는 인스턴스
    * type: 확인하고자 하는 클래스 또는 데이터 타입

#### 2) 클래스와 인스턴스는 어떤 관계인가?
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

### 메소드 method 란?


### 생성자 constructor 와 소멸자 destructor