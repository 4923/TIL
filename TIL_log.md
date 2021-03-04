### 코딩일지

* 2021-01-03
    * 하드 정리

* 2021-01-05
    * user 디렉토리 이름을 바꾸고 싶어서 손댔다가 registry editor에 두시간이나 갇혔다. 파이썬 path를 일일이 수정해야 하던데 하다가 지쳐서 싹 지우고 다시깔았다. 그러고 나니까 VSCode 파이썬 기본 인터프리터가 conda로 바뀐거같은데 어딜 손대야할지 모르겠어서 일단 방치했다.
    * Java 스터디
        * 코드편집기를 통일하고 싶어서 VSCode에 세팅했는데 Eclipse로 시작하는게 맞을거같아서 새로 설치했다.
        * 생활코딩 Java (2013) 강의를 12강까지 수강하고 예제 해설을 준비했다. (담당 회차 5, 10)

* 2021-01-06
    * 백준 1, 2단계 완료

* 2021-01-07
    * Ebs SW 2-2-2 이미지 데이터 표현까지 완료

* 2021-01-08
    * 백준 3단계 완료: `sys`, RecursionError

* 2021-01-09
    * Kaggle titanic (Score: 0.77272)
        * 기본세팅으로 0.77272
        * 타이틀 high 추가, 나이 10단위로 세분화 했을 때 0.77272
        * Pclss -> Cabin 결측치 보완 중
            * 정규식으로 Cabin 알파벳만 추출
            * Pclass별 Cabin 평균값 넣었더니 오버피팅 (랜덤포레스트 95.85) + 미세하게 점수 떨어짐 0.76076
        * 상류층 여성만 모아서 `High_f` 로 묶음
        * 상류층 남성/군인 남성을 따로 모으는건 의미 없으니 `Mr`로 통합
    * BOJ 4단계 완료
        * 10951 `try-except` 오답

* 2021-01-10
    * BOJ 5단계 완료

* 2021-01-11
    * BOJ 6단계 완료
    * TIL 정리 (BOJ 4-6단계)
        * `.round()` 자리수 지정해서 반올림
        * dict 복습 정리
    * Coursera : Machine Learning 1주차
        * Introduction 완료: 기본개념, 지도학습(분류,회귀) 비지도학습 등

* 2021-01-12
    * BOJ ~7-2
    * 42 서울: 기수당 한번이라던 썰... 어디발 낭설인지 모르겠지만 같은 명의 새 계정으로 시도해도 무관하다는 답변 받음. 초기화 기간은 에꼴 42에서 정하고 몇 달정도 걸린다고 (13/11)
    * Coursera : Machine Learning 1주차
        * Model and Cost Function 수강 중 -> 선형회귀 보충

* 2021-01-13
    * 새벽에 BOJ 몇 문제 풀고 오후엔 휴식

* 2021-01-14
    * BOJ ~7-5
    * Coursera : Machine Learning 1주차
        * Model and Cost Function 수강 완료, 선형회귀 보충 완료, 정리 완료 (*머신러닝, 딥러닝에 필요한 기초수학 with 파이썬 참조*)
        * Parameter Learning 수강 완료
        * Review Test 완료
    * 42Seoul: Check-in meeting register (1/28 10:00 예정)

* 2021-01-15
    * BOJ 1152,2908,5622

* 2021-01-16
    * 외출로 일일커밋 X

* 2021-01-17
    * 겨울방학 코딩테스트 대비 캠프 OT
    * [LeeBrosCode](https://leebroscode.com) 기본문제 54제 - 단순 반복문 (1) 까지

* 2021-01-18
    * 코딩테스트 캠프
        * 컨디션 난조... 코테캠프 1일차 기본문제 과제 풀이 (진행중)
        * Class 보충 필요
    * BOJ 2941, 1316 Failed (재시도 필요)
    * Coursera : Machine Learning 1주차 마무리 / 과제 마감일 (완료)

* 2021-01-19
    * 코딩테스트 캠프
        * 이틀째 컨디션 난조라 낮에 종일 자고 새벽에 19일자 할 일 해야 함
        * 코테캠프 1일차 기본문제 남은것들 + 2일차 기본문제

* 2021-01-19~23
    * 코딩테스트 캠프 문제만 주구 장창 풀었음... ... 사람살려
    * 23: 멋사 9기 웹 스터디, 강의자료 PPT로 제작 (Web/Webserver, Git Hosting, HTML/Form Tag)
    * 사람살려...

* 2021-01-24~31
    * 유사 휴가... 하루에 한문제씩만 풀었음

* 2021-01-30
    * 웹 스터디 자료 (Py 자료형부분) 만들고 공유

* 2021-02-01
    * LBC 기본문제 54 - 1차원 Array (6) 까지

* ~2021-02-03
    * LBC 기본문제 54 - 완료

* 2021-02-07
    * 신찬수교수님 자료구조 강의 수강

* 2021-02-08
    * Coursera Machine Learning - Andrew Ng
        * 1주차 마무리: Linear Algebra Review 단원 끝내고 Review test 통과
        * 2주차 Enviroment Setup Instructions: Octave 설치

* 2021-02-11~13
    * 설 연휴 휴가

* 2021-02-14
    * BOJ 10250, 1193, 2775, 
    * TIL/Python/error_message_report 문법오류 문서 추가

* 2021-02-15
    * BOJ 2839, 1978, 2581, 11653
        * 1929 시간초과 실패

* 2021-02-16
    * HUFS Missing Semester - 2. Shell & Shell Editors 수강 완료 및 실습
        * PowerShell 권한 조정방법 문서 추가
        * WSL 및 Ubuntu 설치, vi 실습

* 2021-02-17
    * HUFS Missing Semester - 3. Git & GitHub 수강 완료 및 실습
        * commit message 틀을 만들 수 있음을 배움
        * copy con 명령어 개념 습득
    * BOJ 1929

* 2021-02-18
    * BOJ 4948
    * HUFS Missing Semester - 4. Google Workspace & Google Colab 수강 완료 및 실습
        * Google Apps Script로 주소 메일로 보내는 실습
        * Mail Merge 실습
        * Google CoLab과 Github, Google Drive 연동하는 실습
        * Youtube 데이터 분석 자동화 실습 및 해당 내용 Pandas로 시각화하는 실습

* 2021-02-20 ~ 21
    * 이사로 휴식

* 2021-02-22
    * BOJ 9020
        * 소수를 여러번 활용해야하는 문제는 시작할 때 소수만으로 이루어진 에라토스테네스의 체를 설정하는 것이 빠르다.
        * 계속 헷갈리는 for문의 범위 정리
            * 큰 수에서 작은수로 범위를 지정할 때:
                `for i in range(시작할 큰 수, 끝낼 수보다 1 작은 수, -1):`

* 2021-02-25
    * BOJ 3009 4153

* 2021-02-26
    * HUFS Missing Semester : 5. AWS 강의 수강
    * 심리테스트 개발 방법 조사

* 2021-02-27
    * BOJ 10872 10870
    * 셀레니움으로 크롤링하기 조사

* 2021-02-28
    * BOJ 2447 FAIL
        * 별찍기 재귀로 어떻게 풀어야 할 지 감이 안와서 풀다가 실패함. 규칙은 알겠는데 어떻게 재귀로 구현해야하지...?

* 2021-03-01
    * BOJ 3053

* 2021-03-02
    * 택시기하학 정리하다가 pandas, conda 명령어 가물가물한 부분 다시 정리함.

* 2021-03-03
    * BOJ 2798

* 2021-03-04
    * BOJ 2231
    * 자료구조 (전공) - 파이썬 클래스 단계별 복습