스프링 빈과 의존관계
========================

* 컨트롤러는 스프링이 처음 시작될 때 생기는 스프링 컨테이너에 객체를 생성해서 넣어둠
-> 스프링 컨테이너에서 스프링 빈이 관리된다고 표현

* 컨트롤러에서 서비스 객체를 새로 new 생성할 필요 x, 하나만 공용으로 쓰면 됨

* 스프링 컨테이너에 등록해서 사용 (컨테이너에는 하나만 등록 가능, 싱글톤 : 같은 스프링 빈이면 같은 인스턴스)

* 생성자에 @Autowired가 있으면 스프링이 연관 객체를 스프링 컨테이너에서 찾아 넣어줌->DI
(컨트롤러와 서비스를 연결)

### 컴포넌트 스캔 & 자동 의존관계 설정
* 서비스, 컨트롤러, 레파지토리를 스프링 빈으로 등록해야함
* 컴포넌트 어노테이션이 있으면 스프링이 빈으로 자동등록
    * @Component
        * @Service
        * @Controller
        * @Repository
* 메인 어플리케이션의 하위나 동일 패키지들만 자동등록 가능

- - -

### 자바 코드로 직접 스프링 빈 등록하기
* 새 클래스에 @Configuration
* 등록할 객체 생성 함수에 @Bean
* 컨트롤러는 x

#### DI는 필드 주입, setter주입, 생성자 주입이 있다. 생성자 주입 권장
#### @Autowired는 스프링이 관리하는 객체에서만 동작(스프링 빈으로 등록된 것들)