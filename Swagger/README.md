# Swagger 

- version 

    -	Swagger-UI 2.x 확인
        -/{your-app-root}/swagger-ui.html
    -	Swagger-UI 3.x 확인
        -/{your-app-root}/swagger-ui/index.html

-@ApiOperation

    - value : 대표 타이틀 
    
    - notes : 상세설명 
    
    
- Controller 

    - `@RestController` 추가 필수 

    - @ApiOperation 

          - value : 제목? 별칭 ?
          - notes : 부가 설명 

- SwaggerConfiguration 

    - @Configuration : swagger 설정을 작성해놓은 자바 클래스 파일

    - @EnableSwagger2 추가 
    - 

---

- 또 다른 프로젝트 명세서 

       - 클래스 다이어그램

       - 유즈케이스 다이어그램 : 사용자 입장에서 

        - 시퀀스 다이어그램 : 어떤 시점에 어떤 클래스가 호출되고 어떤 변수 날라가세요 ?

        - ER 다이어그램 : db 구조 파악 
