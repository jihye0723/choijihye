# web.xml 작성 

- web application 개발에 있어서 필요한 전반적인 설정들을 작성해놓은 파일 

    - 비웹적인 요소들에 대한 설정을 작성해 놓은 root-context.xml (database 관련)

    - listener 를 통해, was 가 web.xml을 읽으면서, listener 로 root-context.. ? 

    - filter 로 , 인코딩 처리를 한다. ( post 방식에서는 한글 인코딩 필요 ) 
        
          - filter-mapping 을 통해, <url-pattern> 에 해당하는 모든 파일에 filter 설정 적용 

    - servlet 설정 : DispatcherServlet 을 웹적인 설정의 servlet-context.xml로 초기화 시킴 

    - Exception 처리를, DispatcherServlet 이 mapping 을 찾지 못했을 경우를 대비하여 설정 

          - servlet-mapping 을 통해, <url-pattern> 에 해당하는 모든 파일에 dispatcher 적용 

---

```

<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee https://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

	<!-- The definition of the Root Spring Container shared by all Servlets and Filters -->
	<context-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/spring/root-context.xml</param-value>
	</context-param>
	
	<!-- Creates the Spring Container shared by all Servlets and Filters -->
	<listener>
		<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
	</listener>
	
	<!-- POST 방식의 한글 처리. -->
	 <filter>
        <filter-name>encodingFilter</filter-name>
        <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
        <init-param>
          <param-name>encoding</param-name>
          <param-value>UTF-8</param-value>
        </init-param>
     </filter>
     
     <filter-mapping>
        <filter-name>encodingFilter</filter-name>
        <url-pattern>/*</url-pattern>
     </filter-mapping>

	<!-- Processes application requests -->
	<servlet>
		<servlet-name>appServlet</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		<init-param>
			<param-name>contextConfigLocation</param-name>
			<param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
		</init-param>
		<!-- DispatcherServlet이 해당 mapping을 찾지 못할 경우 NoHandlerFoundException를 throw하게 설정 -->
		<init-param>
			<param-name>throwExceptionIfNoHandlerFound</param-name>
			<param-value>true</param-value>
		</init-param>
		<load-on-startup>1</load-on-startup>
	</servlet>
		
	<servlet-mapping>
		<servlet-name>appServlet</servlet-name>
		<url-pattern>/</url-pattern>
	</servlet-mapping>

</web-app>

```
