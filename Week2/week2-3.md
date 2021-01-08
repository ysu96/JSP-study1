웹 기능
====================
## 1. 홈 화면 추가

* 홈 컨트롤러 추가 ( @GetMapping("/") )
* /resources/templates 에 home.html 추가
#### 컨트롤러가 static 파일보다 우선순위가 높아 /static/index.html(welcome page)은 무시

- - -
## 2. 회원 등록
* 등록 컨트롤러 추가 ( @GetMapping("members/new")
* /resources/templates/members/createMemberForm.html 추가 (등록 화면)
* 웹에서 데이터 전달 받을 폼 객체 추가 (MemberForm)
* 실제 등록하는 기능 컨트롤러 추가 (@PostMapping("/members/new")) (폼에 값 포스트 시 동작)
  * 리턴값으로 "redirect:/" 하면 홈 화면으로 다시 이동
  * <input type="text" id="name" name="name" placeholder="이름을 입력하세요">
    * "name"을 보고 스프링이 MemberForm의 setName을 호출해 name필드 값 넣어줌

- - -
## 3. 회원 조회
  * 컨트롤러 조회 기능 추가
    * model attribute에 key: members, value : members 추가
  * 회원 리스트 html 추가
    * <tr th:each="member : ${members}">
      * ${members} 가 컨트롤러에서 모델에 추가한 attribute의 값
      * 받아온 값에서 하나씩 꺼내 "member"에 넣음
      * id와 name이 private이라 자바가 getName, getId로 스스로 가져옴?
