# The public type class_name must be defined in its own file

### 공용 형식 class_name은 자체 파일에 정의되어야 한다.
<br>

1. 클래스 이름과 파일 이름이 일치하지 않을 때 발생
    ```java
        // test.java
        public class print {

        }
    ```
    클래스 이름을 test로 바꾸거나 파일 이름을 print로 변경하면 해결