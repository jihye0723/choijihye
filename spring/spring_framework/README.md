# Spring Framework  
* Application Context

  - BeanFactory 인터페이스를 상속받은 하위 인터페이스로써, 스프링 컨테이너이다. 

  - SpringBean 을 관리 조회 하는 다양한 기능을 가지고 있다. 

   - xml 기반 또는 java 클래스 기반 모두 가능하다. 

 * ClassPathXmlApplicationContext(xml 경로) 

    - 해당 경로에 위치한 xml 파일을 읽어들여 설정정보를 로딩 한다 

    - 경로는 xml 파일의 경로이므로 `/` 로 구분한다. 

 * bean 설정 

    - id : spring container 에서 유일하게 식별 가능한 이름 

    - class : 해당 bean 객체의 full path ( 클래스의 경로이므로 `.` 로 구분 ) 

 * property 설정 

    - setter 클래스로 의존성 주입 시 , 사용 

    - name : class 에서 사용한 setter의 이름에서 첫 문자를 소문자로 

    - ref : setter 메서드에 주입할 bean 객체의 이름 ( 아이디 참조 ) 

* component-scan

    - 빈으로 등록 될 준비를 마친 클래스들을 스캔하여 , 빈으로 등록 

    - context:component-scan base-package="스캔할 패키지 경로"

    - 어노테이션 붙인 클래스 = 빈으로 등록 될 준비 마친 클래스 
