# Set project
1. [https://start.spring.io/](https://start.spring.io/)
2. add Dependencies : web, thymeleaf, jpa, h2, lombok
    - groupId : jpabook
    - artifactId : jpashop
    - use Spring boot 2.1.x (min : 2.1.10) -> to use JUnit4 && H2 database ver 1.4.2000
    - use hibernate ver minimum 5.4.13.Final(to use H2 database ver 1.4.2000)
3. run main && test
    - error issue
        - Caused by: java.net.BindException: Address already in use: bind
        ```aidl
        >netstat -ano
        
        활성 연결
        
          프로토콜  로컬 주소              외부 주소              상태            PID
          TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       1140
          TCP    0.0.0.0:445            0.0.0.0:0              LISTENING       4
          TCP    0.0.0.0:902            0.0.0.0:0              LISTENING       6044
          TCP    0.0.0.0:912            0.0.0.0:0              LISTENING       6044
          TCP    0.0.0.0:1521           0.0.0.0:0              LISTENING       4824
          TCP    0.0.0.0:3306           0.0.0.0:0              LISTENING       5972
          TCP    0.0.0.0:5040           0.0.0.0:0              LISTENING       9600
          TCP    0.0.0.0:5357           0.0.0.0:0              LISTENING       4
          TCP    0.0.0.0:7522           0.0.0.0:0              LISTENING       4896
          TCP    0.0.0.0:7680           0.0.0.0:0              LISTENING       30228
          TCP    0.0.0.0:8080           0.0.0.0:0              LISTENING       4824
          TCP    0.0.0.0:12380          0.0.0.0:0              LISTENING       16572
          TCP    0.0.0.0:13411          0.0.0.0:0              LISTENING       36328
          TCP    0.0.0.0:14430          0.0.0.0:0              LISTENING       6084
        .
        .
        .
        
        >taskkill /f /pid 4824
        성공: 프로세스(PID 4824)가 종료되었습니다.
        ```

4. install Lombok (windows / intelliJ)
    - setting → plugins → install lombok & restart IDE
    - setting → Annotation Processeors → [v] Enable annotation processing
    