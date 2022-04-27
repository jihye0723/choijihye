# Mybatis 에서의 DB 연동 및 설정 동작 

- 비웹적인 요소 설정을 다루고 있는 root-context.xml 에서 시작 

- context:component-scan으로, db 관련된 파일들을 스캔 시작 
    - context 를 사용하기 위해, namespaces 에서 context 체크 

- SqlMapConfig.java 클래스 스캔 
     - 기존의 dbUtil.java 와 비슷한 동작 

- MySql 과 Mybatis 를 연결하기 위한 SqlSessionFactory, SqlSession 객체를 생성하는 곳 

- 먼저, "mybatis-config.xml" 설정 파일을 읽으면서 MySql 정보와 mapper.xml 파일을 통해 sql문 스캔

- 이후, SqlMapConfig 에서 openSession 을 통한 객체 생성  
---
# dao 와 mapper.xml 의 매핑 동작 

- dao 에서, SqlSession.method(호출하려는 xml내의 sql문 id, 매개변수로 넘겨줄 값0

- xml 파일에서 id 값으로는 `다른 xml 과 헷갈리지 않도록 namespace 지정해주면, namespace.id로 찾으면 된다 .> 

- 즉, xml 파일에서의 아이디 = 해당 mapper.xml의 namespace.id , dao 에서 `namespace.id` 로 호출 

    - dao 
    ``` 
    private final String NAMESPACE="com.ssafy.guestbook.model.dao.MemberDao.";
    @Override
	public void registerMember(MemberDto memberDto) throws Exception {
		try(SqlSession sqlSession = SqlMapConfig.getSqlSession()){
			sqlSession.insert(NAMESPACE+"registerMember", memberDto);
			sqlSession.commit();
		}	
	}
    ``` 
    
    NAMESPACE+"registerMember" 와 같은 id 를 가진 것을 mapper xml 파일에서 찾아서 실행, 매개변수로 form input 값 담은 memberDto
    
    - member.xml
    ```
    <mapper namespace="com.ssafy.guestbook.model.dao.MemberDao">
	    <insert id="registerMember" parameterType="member">
	    insert into ssafy_member(userid, username, userpwd, email, joindate)
	    values(#{userId},#{userName},#{userPwd},#{email}, now())
	    </insert>
    </mapper>
    ```

    id 값은 `namespace.id`이다. parmeterType 은 dto 의 풀네임을 작성해주어야 하지만, typeAlias 로 별칭을 지어주었다. 그게 member 
    ` but !!! parameterType 에 dto 말고, java의 wrapperclass ex) Map, Integer, .. 은 앞글자를 소문자로 하고 그냥 적어주면 됨 `
    - #{} 로, 매개변수에서 불러올 변수값을 넣어주었다. 해당 이름은 기존에 넣어주던 값과 이름이 같아야지 자동으로 매핑되어진다. 
