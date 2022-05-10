# axios 

- promise 기반의 http 통신 라이브러리 

      - 데이터를 요청하고 받아올때까지 기다렸다가, 화면에 나타나는 로직을 실행해야 할때 Promise 활용 
      - 기존의 ajax 는 서버와 통신하면서, 자바스크립트는 계속 실행 

- axiox 통신을 하게 되면, promise 객체르 ㄹ리턴한다. 

- promise 객체로 then / catch / finally 

    - promise 객체 (resolve, reject) 에서 성공하면, 자동으로 resolve 생성 -> then (response) , finally 실행 
  
    - 실패하면 reject -> catch(error) , finally 

``` 
비동기처리는 , 서버에 요청을 보내놓고 javascript 는 계속 실행된다. 

그것의 결과나 응답을 기다려 주지 않음 . 

그렇기 때문에 axios 의 요청을 받은 후 그것을 사용하는 then 을 사용하기도 하고 

`async` 와 `await` 사용이 가능하다. 

`async`는 함수 앞에 붙이고 `await` 는 async 를 붙힌 함수 안에서만 사용이 가능하다 !!! 

그러면 응답이 올때 까지 기다려줘 . 
```

