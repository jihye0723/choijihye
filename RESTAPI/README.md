# REST API 의 기본 

<h4> 자원 URI + GET/POST/PUT/DELETE </h4> 

----
- 구성요소  3 가지 

    - 자원 : `URI` 에 명시 
    - 행위 : HTTP method ( CRUD ) 
    - 표현

- 플랫폼 종속적이지 않음 

- 처리 후 반환 data 를 json 이나 xml 로 전달 ( 특정 language 에 종속 x ) 

    - 하나의 server 로 웹 / 모바일 모두 서비스 가능 한 느낌 ..? 

- view 에 대해서 신경 쓸 필요가 x 

- GET , POST ,  PUT ,  DELETE

    -`POST` : 글 쓰기
    
    -`GET` : 글 읽기 
    
    -`PUT` : 글 수정
    
    -`DELETE` : 글 삭제

- `URI` 를 통한 자원 명시 
   
   - `/` 를 통한 계층 구조 ( Collection - Document - .. ) 

- 어노테이션 

  - @RestController : 모든 메서드를 뷰가 아닌 JSON 과 같은 데이터로 return 하기 위해 respnosebody 를 다 붙여야할 때 모든 메서드에 responsebody 적용

  - @ResponseBody : jsp 같은 뷰로 전달 되는 것이 아니라 데이터로 전달 시켜. (ex) "" 문자열로 응답하면 jsp 로 인식할 수 있음 ) 

  - @PathVariable : url 경로 에 있는 {값}을 파라미터로 추출  

  - @RequestBody : json 으로 넘어온 것을 dto 에 매핑 

  - @CrossOrigin : 뒤에 url 설정에 있는 곳들만 접근 가능 ( 보안성 ) 

- dependency 
   
   - jackson-databind 라이브러리 : 객체를 JSON 포맷의 문자열로 변환시켜서 브라우저에 전송
        - @RestController + jackson 라이브러리 -> list가 자동으로 json 으로 반환되었다. 

   - JSONObject  

