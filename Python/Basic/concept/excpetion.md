# Exception

* 에러를 발생시키는 방법 : `raise 에러종류`
* 예외의 경우 에러를 발생시켜 정해진 에러메시지를 출력한다.
* 사용자가 직접 예외 처리를 하면 코드의 직관성을 만들 수 있다.
* 파일을 하나 만들어 예외를 정의하는 것이 좋다.
    * 파이썬에서는 에러도 하나의 클래스다.
        * 에러의 최상위 클래스는 Exception Class다.
        * 따라서 새로 만드는 에러 클래스는 Exception을 상속받아 만든다.

```py
# 원하는 에러를 발생시키는 방법.
from UnexpectedRSPValue import UnexpectedRSPValue

value = "묵"
try:
    if value not in ['가위','바위','보']:
        raise UnexpectedRSPValue("가위바위보 중에 하나를 내 주세요")  # 이 문구는 따로 출력되지 않는건가...?
except UnexpectedRSPValue:
    print("가위바위 보 입력 에러가 발생했습니다.")

# UnexpectedRSPValue.py
class UnexpectedRSPValue(Exception):  # ValueError만 상속받아도 무관
    '''가위 바위 보 가운데 하나가 아닌 입력인 경우에 발생하는 에러'''

```

```py
# 예외처리를 세밀하게하면 에러를 잡아내기 쉽다.
try:
    sign_up( )
except BadUserName:
    print( "이름으로 사용할 수 없는 입력" )
except PasswordNotMatched:
    print( "입력한 패스워드 불일치")
```