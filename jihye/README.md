- xml 

    - 특정 언어에 종속적이지 않다는 가장 큰 매력을 가지고 있기 때문에 , json 과 같이 `데이터 전달용 문서`로 사용

- jsp 

    - parent : 바로 위 부모 / parents : 계속 부모를 타고 올라가면서, 원하는 거 나올 때 까지 찾기 

    - document .click -> 클릭 / 동적으로 할당되는 페이지는 click 사용 못함 , on 으로 !! 

- 응답 코드 

    - 4xx : 클라이언트 오류 

    - 5xx : 서버 오류 

- export 

    - web / war file 로 단순히 외부로 보낼때

    - 일반적으로 배포시 : run as / maven build / goals : package 하면, 

    - workspace / 파일명 / target / 들어가면 war 파일 생성 되어있음 

    - tomcat / webapps 에 war 파일 가져다 놓고 

    - tomcat / bin / startup 하면 , localhost:8080 입력시,  자동으로 war 압축 풀림 

    - context-root 입력하면 페이지 나옴 

- 라이브러리에서 아무이유 없이 에러났을 때

    - maven update 해보고 

    - project clean 해보고

    - jar 파일 다운로드에서 문제가 생긴 것일 수도 

    - c:/user/jihye/.m2/repository 날렸다가, 다시 maven update 하면 jar 파일 다시 다운로드 받아옴 
