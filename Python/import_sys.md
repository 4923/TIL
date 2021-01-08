# sys Module
### "sys모듈은 파이썬 인터프리터가 제공하는 변수와 함수를 직접 제어하게 해주는 모듈이다" - [점프투파이썬](https://wikidocs.net/33#sys)

* `sys.stdin`
    * `input()` 과 유사한 기능을 수행한다.
    * `input()` 문은 사용자의 입력을 받고 문자열로 변환한 후 반환
    * 여러 줄을 입력받을 수 있다.
    * `^Z` 로 입력을 종료 할 수 있다.
* `sys.stdin.readline()`
    * 한 줄을 입력받는다.
    * 개행문자까지 입력받는다.
        * 개행문자를 제외하려면 `.rstrip()` 사용
* `sys.stdout.write()`
    * `print()` 과 유사한 기능을 수행한다.
    * 문자열만 출력 할 수 있다.
    * `print()` 문은 자동으로 개행되지만 `sys.stdout.write()` 를 사용하면 개행 없이 출력된다.