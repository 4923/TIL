# Module

## Contents
1. [모듈 Module 이란](# 1. 모듈 Module 이란)

<hr>
<br>

## 1. 모듈 Module 이란
* 모듈이란?
    * 미리 만들어진 코드를 가져와 쓰는 방법
    * 보통 하나의 `.py` 파일이 하나의 모듈이 된다.
    * 모듈에는 함수, 클래스, 변수, 실행코드 등 다양한 요소가 포함될 수 있다.

    * 사용방법
        ```py
        import module
        module.function(argument)

        # 원 둘레를 구하는 예시
        import math

        R = 2  # 반지름
        circumference = 2 * math.pi * R  # 원둘레
        ```
    
    * `import A, B, C` 처럼 한 줄에 여러 모듈을 import 할 수 있으나 PEP8은 모듈명을 한 줄에 하나씩 쓰는 것을 권장한다.

* 모듈과 함수
    * 모듈 하나에는 여러 함수가 존재할 수 있다.
    * 모듈에서 함수 하나만을 불러오기 위해서는 다음과 같은 표현을 사용한다.
        ```py
        from module import function
        
        # as 로 약칭을 지정 할 수도 있다.
        # 예시
        from matplotlib import pyplot as plt 
        ```
    * 파이썬의 내장함수, 외장함수 모두 import 해서 사용 할 수 있지만 새로 모듈을 제작 할 수도 있다. (이후에 추가)