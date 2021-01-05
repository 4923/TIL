# Java 개발환경 세팅

### Java 란
* 범용적: 국내 대부분의 통합 프로젝트가 Java로 구현되고 있으며 Java는 다양한 곳에서 사용되고 있다.
* 객체지향언어: C처럼 운영체제를 가리지 않고 C++와 함께 객체지향 언어에 속한다.
* 종류:
    1. Java SE (Java Standard Edition) : 기본기능 제공
    2. Java EE (Java Enterprise Edition) : 보편적으로 사용되고 있음
    3. Java ME (Java Micro Edition) : 과거 전자제품 등에 사용되었으나 현재 안드로이드 점유율이 상승하며 사용되지 않고 있음

### Java 개발환경 이론
* 대표적으로 사용되는 에디터 : NetBeans 넷빈즈, Eclipse 이클립스
* Java 프로그래밍에 사용되는 3대 핵심기술 패키지: Java 플랫폼 구성요소 (JDK), Java 가상머신 (JVM), Java 런타임 환경 (JRE)
    * JDK: compiler와 class library를 포함하는 java 플랫폼 사양서의 구현
        * 개발자가 Java로 개발할 때 다운로드하는 소프트웨어로 개발자들이 Java 프로그램을 생성할 수 있게 한다
    * JRE: JVM을 생성하는 디스크 상의 부분으로 JDK에 포함된다.

### Java 개발환결 세팅
1. JDK 설치
JDK에는 다양한 버전이 있으며 모든 JDK 버전은 Java 표준에디션 **S**tandard **E**dition을 포함하고 있다.

    * **J**ava **D**evelopment **K**it
    * Java Compiler를 포함하여 Java 애플리케이션을 구축하기 위한 핵심 구성요소.
    * Java를 관리하는 [Oracle 공식사이트](https://www.oracle.com/index.html)에서 설치 가능.
        * Menu > Products > Software > Learn more about Java > Download Java > Java SE/EE/ME


    - 설치 확인: CMD에서 `java` 명령어 입력시 오류가 나지 않으면 설치 성공

2. 환경변수 설정
    1. Window 검색창에 `path` 검색: `System Properties -> Enviroment Variables...`
    2. 환경변수를 설정할 수 있는 창이 열린다. 상단의 `User variables for (Username)`가 아닌 하단의 `System variables`에서 `Path`에 접근한다.
    3. 환경변수를 추가, 수정, 삭제 할 수 있는 창이 열린다.
    4. 여기에 `java\bin` 경로를 붙여넣는다.
        * `java\bin` 경로는 바꾸지 않는 한 다음과 같다. (버전의 차이가 있을 수는 있다.) : `C:\Program Files\Java\jdk-15.0.1\bin`
    5. 모든 창에서 `Ok` 를 누르고 나오면 된다. 추가로 `Apply` 할 것은 없다.

    - 설치확인 : CMD에서 `javac`를 입력했을 때 오류가 나지 않으면 성공
    - [참고](https://livefordev.tistory.com/1)


3. VSCode 설정

    1. Java Configure 확인
        * Configure? : 'Configure 스크립트는 **개발중인 프로그램을 각기 다른 수많은 컴퓨터에서 실행할 수 있도록 도와주도록** 설계된 **실행스크립트**. 소스코드로부터 컴파일하기 직전에 사용자 컴퓨터 라이브러리의 존재 여부를 확인하고 연결.' (위키백과)
        
        * Commant Palette (`Ctrl + Shift + P`)에서 `Java: Configure Java Runtime` 검색
            => JDK를 여기서도 설치할 수 있는 모양
    
    2. Java 프로그램 만들기
        * Comman Palette 에서 `Java: Getting Started` 를 입력하면 열리는 창에서 Java 프로그램을 만드는 방법을 확인 할 수 있다.
    
        1) 폴더 생성
        2) 파일 생성: 확장자 `.java`
        3) Run 또는 Debug 버튼으로 실행: 단축키 `f5`

        * `Hello World` 출력
            * 기본 출력 함수로는 `System.our.println()`가 있다.
            * 파일명과 클래스 이름이 같아야 한다.

            ```java
                public class test{
                    public static void main(String[] args){
                        System.out.println("Hello Java!");
                    }
                }
            ```

    - [참고](https://allonsyit.tistory.com/10)