# Vue.js

- MVVM 패턴 : Model + View + ViewModel 

    - Model : 순수 JS 자바스크립트 

    - View : DOM ( html ) 

    - ViewModel : Vuejs ( 자바스크립트와 dom 중간에서 둘을 연결 ) 
    
        - view 와 model 을 연결하고 자동으로 바인딩하므로, 양방향 통신이 가능하다 ( 알아서 양쪽 값이 매핑이 됨 ) 

- vue install 

    - `<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>` : title 밑에 

- vue instance 

    - `<script>` 내부에 `vue` 객체 ( 인스턴스 ) 생성 

         - el : 어떤 dom 과 연결 시킬 것인지 
          
         - data : 변수 

         - template 
         
         - methods : 마우스 클릭이벤트와 같이 화면 처리 동작  

         - created : 뷰 인스턴스가 생성되자마자 실행할 로직 
         ```
           new Vue({
            el : "#app",
            data() {
                return {
                    message : "안녕 vue js ~ !!" , 
                } ; 
            },
           });
          
    - `created` : 백앤드와 통신해서 데이터를 미리 얻어옴 
    
    - beforeMount : view 객체와, dom 객체의 div 가 연결되기 전 

    - mounted : 함수 호출 시 view 와 div 연결 ( el 값으로 ) 

    - `updated` : 데이터가 바뀌면서 호출 , created 와 비슷하게, 백앤드와 통신해서 데이터를 얻어옴 
           
     
    - vue 객체 안에 있는 변수를 vue 객체 안에서 사용할 때에는 `this` 사용해줘야함 . (ex )  this.count ) 

    - created 이전에, vue 안에 있는 변수를 사용하면 undefined 출력 됨 , created 이전에는 단순 깡통 vue 객체만 만들어주고, 안에 el 이나 data는 생성 안된 시점 

    - created 가 호출되면, data 생성 및 초기화 됨 / el 은 아직 undefined 

    - mounted 가 호출되면, el 생성 및 초기화 

- 보간법 
    
    - {{ 속성명 }} : 속성명에 자바스크립트의 문법이 들어갈 수는 있지만, 표현식만 들어갈 수 있음 

    - v-once : 데이터 변경시 업데이트 되지 않는 일회성 보간 
    
    ```
    <h2>{{message}}</h2>
    <h2 v-once>{{message}}</h2>
      : 콘솔에서 messgae 를 변경해도 위만 바껴요
    ```  
    - v-html : html로 작성한 데이터가 문자열로 인식되지 않고, html로 해석함 

