# round(number[, ndigits])
[참고](https://docs.python.org/ko/3/library/functions.html?highlight=round)

### 개요
* 내장함수
* 반올림
    * 사사오입 원칙을 따름

* 자리수 지정해서 반올림
    * round()함수는 소수점 아래 ndigits 정밀도로 반올림한 값을 돌려준다.
    * ndigits가 생략되었을 경우 입력에 가장 가까운 **정수**를 반환한다.

* `round(-0.5) vs roudn(1.5)`
    * 짝수를 우선하여 반올림한다.
    * `round(-0.5)` 는 -1이 아닌 0으로 반올림되고 `round(1.5)`는 2로 반올림된다.