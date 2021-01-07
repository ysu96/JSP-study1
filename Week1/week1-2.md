프로젝트 환경설정
=========================
# 1. 스프링 프로젝트 생성
  * 스프링 부트 스타터 사이트로 이동해서 스프링 프로젝트 생성
  * https://start.spring.io
    * Project: Gradle Project
    * Spring Boot: latest version ( SNAPSHOT x )
    * Language: Java
    
    * artifact : 빌드 시 나오는 결과물 이름
    
    * dependencies
      * spring web (웹프로젝트)
      * thymeleaf (html을 만들어주는 템플릿 엔진)
      
    * GENERATE
    
### build.gradle
  * 버전 설정
  * 라이브러리
    * mavenCentral()에서 받아옴
    
### 동작 확인
  * 기본 메인 클래스 실행
  * 스프링 부트 메인 실행 후 에러페이지로 간단하게 동작 확인( http://localhost:8080 )
  
### IntelliJ Gradle 대신에 자바 직접 실행
  * 최근 IntelliJ 버전은 Gradle을 통해서 실행 하는 것이 기본 설정이다. 이렇게 하면 실행속도가 느림
  * File - Setting - gradle 검색
  * Build and run using: Gradle -> IntelliJ IDEA
  * Run tests using: Gradle -> IntelliJ IDEA
  
### IntelliJ 단축키 검색
  * File - Settings - Keymap
  * 단축키 이름 검색
  
- - -
# 2. 라이브러리 살펴보기
  Gradle은 의존관계가 있는 라이브러리를 함께 다운로드 (External Libraries)
  ### 스프링 부트 라이브러리
    * spring-boot-starter-web
      * spring-boot-starter-tomcat: 톰캣 (웹서버)
      * spring-webmvc: 스프링 웹 MVC
    * spring-boot-starter-thymeleaf: 타임리프 템플릿 엔진(View)
    * spring-boot-starter(공통): 스프링 부트 + 스프링 코어 + 로깅
      * spring-boot
        * spring-core
      * spring-boot-starter-logging
        * logback, slf4j
  ### 테스트 라이브러리
    * spring-boot-starter-test
      * junit: 테스트 프레임워크
      * mockito: 목 라이브러리
      * assertj: 테스트 코드를 좀 더 편하게 작성하게 도와주는 라이브러리
      * spring-test: 스프링 통합 테스트 지원
  
- - -
# 3. View 환경설정
  ### Welcome Page 만들기
  * resources/static/index.html 작성
  * static/index.html을 올려두면 Welcome page 기능을 제공
  * localhost:8080 접속 후 확인
  * https://docs.spring.io/spring-boot/docs/2.3.1.RELEASE/reference/html/spring-boot-features.html#boot-features-spring-mvc-welcome-page
  
  ### Thymeleaf 템플릿 엔진
  1. controller 패키지 생성
  2. 컨트롤러 클래스 생성
  
    @Controller
    public class HelloController {
      @GetMapping("hello")
      public String hello(Model model) {
        model.addAttribute("data", "hello!!");
        return "hello";
      }
    }
    
  3. resources/templates/hello.html
  
    <!DOCTYPE HTML>
    <html xmlns:th="http://www.thymeleaf.org">
    <head>
     <title>Hello</title>
     <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    </head>
    <body>
    <p th:text="'안녕하세요. ' + ${data}" >안녕하세요. 손님</p>
    </body>
    </html>
    
  4. thymeleaf 템플릿엔진 동작 확인
  * 실행 : http://localhost:8080/hello
  
  ![Alt text](./images/1.png)
  
  
  
