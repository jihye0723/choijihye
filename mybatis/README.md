# mybatis

- Java Object 와 SQL 문 사이의 자동 Mapping 기능 

- 별도의 SQL 파일 관리 (resources/mappers/.xml) -> annotation 도 가능 

- 복잡한 JDBC 코드 다 벗어냄 ( ResultSet , Prepared.. , connection 등등 ) 

- Mybatis 에서 DB 구현을 하기 위해서는 SqlSession 이 필요하다 

- pom.xml

    - mybatis  , mybatis-spring 추가 
        - sqlSession 사용 가능 해짐 

- mybatis-config.xml 

    - src/main/resources  : 외부 라이브러리에 대한 설정 파일 

    - db 정보를 담고있는 `<environments>` / mapper 역할의 `<mappers>` 필수 

    - dtd : 문서의 형식 정의해놓은 파일 

        - properties, settings, typeAliases, typeHandlers, objectFactory .. 의 순서 

        - xml 에 dtd 설정이 되있기 때문에 , 순서를 잘 지켜야 한다. 

    > - config 파일을 읽으면서 `<mappers>`을 같이 읽게 됨 
    > - mappers 에 정의 되어있는 xml 파일 스캔  
    > - 내부 파일 메모리에 올리면서 자바 객체와 maapping 

- SqlMapConfig.java

  - 이전의 dbUtil.java 와 비슷한 역할 

  - db 연결하는 connection 역할  =  sqlSession 

  - SqlSession 을 위해 설정 파일 (mybatis-config.xml) 먼저 읽고 시작 

  - SqlSessionFactory 로부터 openSession 으로 SqlSession 생성 

- mapper.xml 
    
     - `namespace` : 다른 mapper.xml과 구별하기 위한 , 호출되어지는 곳 (dao 또는 Mapper) 의 풀네임 권장 
      
     - sql 문을 작성 

         - `#{}` 안에 propertyName 을 작성하면, parameterType 의 getter 자동 실행 

     - insert , select 등 : id 와 parameter 속성 지정 

         - id : 고유 명시 ( 실제 dao 에서 만들어놓은 메서드의 이름 ) 
         - parameter : 해당 속성들이 어떤 dto 에 있는지, ( mybatis-config.xml 의 `<typeAlias>` 에서 별칭 지정 가능 ) 
         - parameter 에서 java와 관련된 wrapper 클래스들 (map, char, list 등등 ) 은 이미 지정되어있음, 그냥 소문자로 쓰면 끝 ! 
         - resultType : select 이후 어떤 타입으로 반환할껀지 지정 , select 에 있는 setter 자동 실행 
                 
- daoImpl.java

    - sqlSession 얻은 후, insert("mapper.xml 에있는 sql 문의 위치" , dto ) 같이 .. go og 
    
    
