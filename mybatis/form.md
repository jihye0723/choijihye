# form input 값 dto 자동 주입 

- form 에 어떠한 input 정보들을 입력한 후 post 방식으로 controller 에게 넘겨줬을 때, 

- 넘겨주는 input 값의 name 속성 값과 , Controller 에서의 DTO 의 property, 즉 변수명이 동일하다면 ,

- 별 다른 설정없이 자동으로 해당 값이 객체의 값으로 주입된다. 

- 반드시 모든 값이 일치할 필요는 없으며, 없는 값은 default 값으로 자동 처리되어진다 . 

---

- MemberDto.java
```
package com.ssafy.guestbook.model;

public class MemberDto {

	private String userName;
	private String userId;
	private String userPwd;
	private String email;
	private String joinDate;
  
  
  ```
  
  - join.jsp (form 가지고 있음)
```
 <div class="container text-center mt-3">
        <div class="col-lg-8 mx-auto">
            <h2 class="p-3 mb-3 shadow bg-light"><mark class="orange">회원가입</mark></h2>
            <form id="memberform" class="text-left mb-3" method="post" action="">
            <input type="hidden" id="email" name="email">
                <div class="form-group">
                    <label for="username">이름</label>
                    <input type="text" class="form-control" id="username" name="userName" placeholder="이름입력...">
                </div>
                <div class="form-group">
                    <label for="userid">아이디</label>
                    <input type="text" class="form-control" id="userid" name="userId" placeholder="아이디입력...">
                    <div id="idresult" class="mt-1"></div>
                </div>
                <div class="form-group">
                    <label for="userpwd">비밀번호</label>
                    <input type="password" class="form-control" id="userpwd" name="userPwd" placeholder="비밀번호입력...">
                </div>
                <div class="form-group">
                    <label for="pwdcheck">비밀번호재입력</label>
                    <input type="password" class="form-control" id="pwdcheck" name="pwdcheck" placeholder="비밀번호재입력...">
                </div>
                
 ```
 
        - form 내부의 input 값의 `name` 값과, dto 의 변수명이 동일한 것을 확인할 수 있다 ( userName, userId .. ) 
        
- MemberController.java
```
public String register(MemberDto memberDto) throws Exception {
		memberService.registerMember(memberDto); // 결국 내가 입력한 form 이 memberDto 객체에담겨서 service 로 이동 
		return "user/login";
	}
```

- Controller 의 인자에 Dto 가 있고, post 방식으로 넘어온 form 의 값이 자동으로 주입된다. 
- memberDto 에 내가 입력한 값들이 담겨서 service 의 인자로도 넘어간다 
       
