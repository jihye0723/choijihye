# SPRING BOOT 

- New Spring Starter Project 

    - jar 
    - java version 8
    - spring boot version 2.6.7
    - Available에서 dependecy 설정 : spring boot devtools/ spring web 

- library 들이 미리 조합 되어 있다. 

- 내장 서버를 가지고 있어서, was 를 추가 설치할 필요 x 

- jar 파일로도 web application 실행 가능하다 
    - 기존  : jar - class 압축 / war - 웹에 관련된 것들 

- application.properties

    - 기존 xml 에서 부가적으로 해왔던 설정이나 property 를 정의한다.

    - server.port = 포트번호

    - prefix , suffix  ( springboot에서는 jsp 지원을 안하는데 , 억지로 쓰려고 하니까 설정을 일일히 해줘야함 ) 
  
- HelloSpringbootApplication 

    - main 메서드 포함 
  
    - ctrl + f11  / spring boot app 으로 실행 

- src/main/resources/static 

    - html / css / js 등의 파일 

- pom.xml

    ```
    	<!--  jsp setting -->
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
		</dependency>
    ```
    
    - springboot 에서는 jsp 지원을 해주지 않기 때문에, jsp 파일을 사용하려면 위와 같은 설정을 해줘야 함 

    - `<parent>` 타고 타고 올라가보면, dependencies 설정 다 되어 있음
    
    - 라이브러리 버전을 바꾸고 싶다면, starter 의 version 을 변경하는 것이 나음 

    - 타고 들어가서 바꾸지는 않음, 아니면 차라리 dependency 에서 변경하던가 ~~ 덮어써줌 

- jsp 사용  ( springboot 에서는 jsp 지원 해주지 않음 ) 

  - src/ main / webapp / WEB-INF / 에 직접 설정해 주어야 함 

  - application.properties 파일에 설정해줘야한다 prefix, suffix 

  - pom.xml 에 dependency 설정 해주어야 함 
