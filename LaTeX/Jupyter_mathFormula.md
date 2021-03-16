# Jupyter Notebook에서 수식 표현하기

Created: Jan 3, 2021 3:01 PM
언어: LaTeX

### LaTeX

논문을 작성할 때 주로 사용되는 언어로, 노션이나 주피터 노트북에서 수식을 작성할 때 사용한다.

### 주피터 노트북

- 마크다운 셀에서 사용할 수 있다.
- inline 수식 : $ 수식 $
- block 수식 : $$ 수식 $$ 또는 $$$ 수식 $$$

### 노션에서는

`/math` 로 호출할 수 있다.

---

## 문법

### 연산

- 나누기
    $\frac{a}{b}$ : `\frac{a}{b}`

### 수 표현

- 위첨자

    $x^{n}$ : `x^{n}`

- 아래첨자

    $x_{n}$ : `x_{n}`

- log

    $\log_밑 진수$ : `\log_a b`

### 수열

- 시그마

     $\sum$ :  `\sum`

    $\sum_{n}^{k}n$ : `\sum_{n}^{k}n`

### 집합

- 논리곱

    $\wedge$ : `\wedge`

- 논리합

    $\lor$ :  `\lor`

### 증명

- 따라서

    $\therefore$ : `\therefore`

- 왜냐하면

    $\because$ : `\because`
### 통계

- 추정

    $\hat{b}$ : `\hat{b}` 추정을 의미한다.

### 기타

- 식 번호

    $\tag{1}$ : `\tag{1}` 식 번호를 매길 때 사용한다. block equation에서만 사용 가능하며 식번호는 우측정렬되어 표기된다.