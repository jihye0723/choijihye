# Mybatis 에서의 DB 연동 및 설정 동작 

- 비웹적인 요소 설정을 다루고 있는 root-context.xml 에서 시작 

- context:component-scan으로, db 관련된 파일들을 스캔 시작 
    - context 를 사용하기 위해, namespaces 에서 context 체크 

- SqlMapConfig.java 클래스 스캔 
     - 기존의 dbUtil.java 와 비슷한 동작 

- MySql 과 Mybatis 를 연결하기 위한 SqlSessionFactory, SqlSession 객체를 생성하는 곳 

- 먼저, "mybatis-config.xml" 설정 파일을 읽으면서 MySql 정보와 mapper.xml 파일을 통해 sql문 스캔

- 이후, SqlMapConfig 에서 openSession 을 통한 객체 생성  

