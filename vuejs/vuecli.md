# vue.cli

- vue, router, axios 등등 자동 세팅 가능 

- create vue 파일명 

- manually 

- router 선택 (space bar) 

- 2.x

- history mode : Y ( 대문자면 default 값이라는 뜻 , 그냥 엔터 누르면 됨 )

- prettier

- save 

- (babel, eslint 기타 등등을 내부적으로 사용, 이들에 대한 config( 설정 ) 필요)

          - package.json : 하나로 묶기 
          - 또 댜른거는  독립적으로 

- cd cli 블라블라 

- npm run server 블라블라 

- home / about 누를때 마다 router 화면 바뀌는 지 확인 !! 


---
# vs code 에서 열기 
- node_modules 파일은 사이즈가 너무 크기때문에 gitignore 로 git 에 올라가지 않음 

- public / index.html : `html 파일 하나만 있음`  -> SPA (single page application ) 

- 많은 js 파일이나, vue 파일 등을 webpack 이 압축해서 index.html 에서 사용할 수 있게 해줌 !! 

- `view : 화면 / component : 그 화면안에서 갈아끼우는 블럭들 !! `

          - view : ( template : 화면에 뿌리는 html - `root element 하나 !!`) , (script : javascript ) , (style : css ) 

- LF / CRLF : 기본적인 vieew 는 lf 임 , 우리가 만들면 crlf 라서 (error  Delete `␍`) 발생 
- "prettier/prettier": ["error", { "endOfLine": "auto" }]  를 package.json(설정파일) 에 rules 에 추가 
          - 설정 파일 따로 만들게 했을때는, .eslintrc.js 의 rules 에 

- npm run serve : 실행 

- npm i axios : axios 설치 

- router 에 import 에서 상대경로는 위험도가 있기 때문에 `jsconfig.json` 파일에 

```
  "@/*": [
        "src/*"
``` 
로 src -> @ 로 지정 

- 

