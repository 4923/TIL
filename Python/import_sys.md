# sys Module
### "sys모듈은 파이썬 인터프리터가 제공하는 변수와 함수를 직접 제어하게 해주는 모듈이다" - [점프투파이썬](https://wikidocs.net/33#sys)


### 입출력
* `sys.stdin`
    * `input()` 과 유사한 기능을 수행한다.
    * `input()` 문은 사용자의 입력을 받고 문자열로 변환한 후 반환
    * 여러 줄을 입력받을 수 있다.
    * `^Z` 로 입력을 종료 할 수 있다.
* `sys.stdin.readline()`
    * 한 줄을 입력받는다.
    * input()과는 다르게 개행문자까지 입력받는다.
        * 개행문자를 제외하려면 `.strip()` 사용
        * `.readline.strip()` readline으로 입력받고 strip으로 개행을 제거해도 `input()`보다는 `readline()`이 더 빠르다.
    * 언제 사용하는가? [1/18 코테캠프]
        * input()보다 readline()이 속도가 빠르므로 코딩테스트에서는 readline()을 사용하는것이 효율적이라는 말이 있다. 맞는말이나 대부분의 코딩테스트는 효율적인 알고리즘을 구축했는지를 평가하므로, input()때문에 시간 초과가 날 일은 없다.
    * **문자열로** 입력받는데, 이를 int type으로 변환하려면 list comprehension으로 받는것보다 high-order-function인 map을 사용하는것이 좋다.
        * `[for e in sys.stdin.readline().strip().split()]` 보다 `list(map(int, sys.stdin.readline().strip().split()))`를 사용하는것이 낫다.
* `sys.stdout.write()`
    * `print()` 과 유사한 기능을 수행한다.
    * **문자열만** 출력 할 수 있다.
    * `print()` 문은 자동으로 개행되지만 `sys.stdout.write()` 를 사용하면 개행 없이 출력된다.
<br>

### 최대 최소
* `sys.maxsize`
    * int의 최대값을 반환하는 함수.
        * python2에서는 `sys.maxint`를 사용했다.
    * 최대값 또는 최소값을 구하는 알고리즘에서 처음 숫자를 기준 삼는 경우가 많다.
        ```python
        maxnum = numbers[0]
        for i in range(0, len(numbers))
            if maxnum < numbers[i]:
                maxnum = numbers[i]
        ```
        그러나 처음 숫자를 언제나 알 수 있는 것도 아니고, 알아내기 위해서 또 다른 조치를 취해야 할 수 있으므로 절대적으로 큰 값 또는 작은 값을 비교대상으로 삼는다. (어떤 숫자와의 크기 비교에서도 우위를 점하는 `inf`를 사용하기도 한다.) <br>
        `sys.maxsize`로 최대값을 구하는 방법은 다음과 같다.
        ```python
        # 가장 작은 수를 maxnum에 할당.
        maxnum = -sys.maxsize
        for i in range(0, len(numbers))
            if maxnum < numbers[i]:
                maxnum = numbers[i]
        ```
