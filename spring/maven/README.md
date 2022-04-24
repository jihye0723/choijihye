# MAVEN 프로젝트 작성 

- pom.xml

    - `<properties>` : 중복 속성 방지를 위해 설정 정의 , java 및 spring version , context=root 확인 
  
    - `<dependencies>` : 의존성 라이브러리 정보 , groupId / artifactId / version 정보 필요 
      
    - `<build>` : 빌드 정보 , 하위태그 `<plugin>` 포함 
    
- web.xml

   > - 가장 먼저 비웹 관련 root-context.xml 을 읽어들인다 . ( was 가 web.xml을 실행하면서, listener 동작으로 읽음 ) 
   > - 다음으로 웹 관련 servlet-context.xml 실행, 그 외 웹관련 설정 실행 
   > - DispatcherServlet 은 사실상 깡통이지만, init-param 으로 servlet-context.xml로 깡통의 내부를 채워주는 느낌 ?

    - `<context-param>` : 사용자가 직접 컨트롤 하는 xml 파일 지정 

    - `<listener>` : 설정 정보 읽어들임 

    - servlet : spring 은 DispatcherServlet 이 모든 요청을 받고, controller 로 요청 전달 

    - filter : 한글 깨짐 문제 처리 , `/*` /이하의 모든 것에 적용 
