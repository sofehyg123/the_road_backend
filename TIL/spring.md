> 들어가며  
* 최범균 저자의 초보자 웹 개발자를 위한 스프링5 프로그래밍 입문 선택
* 스터디 참고용 도서 및 기본적인 내용을 학습하기 위해서  
  

> 스프링이란?  
* 의존 주입 지원(Dependency Injection : DI  
* AOP(Aspect-Oriented Programing) 지원  
* MVC 웹 프레임워크 제공  
* JDBC, JPA 연동, 선언적 트랜잭션 처리 등 DB 연동 지원  
  
> 스프링 기능  
* 스프링은 객체(=Bean)를 생성하고 초기화하는 기능을 제공함.  
  - 스프링이 관리하는 Bean 객체로 등록  
  - @Bean 들을 구분하기 위해서 메서드 이름을 사용한다.  
* 스프링 컨테이너  

> 설정정보  
* @Configuration : 해당 클래스를 스프링 설정 클래스로 지정한다.  
* AnnotationConfigApplicationContext 클래스  
  - 자바 클래스(@Configuration 애노테이션이 설정된)에서 정보를 읽어와 빈 객체를 생성하고 관리한다.(스프링의 핵심 기능)  
  - ApplicationContext 인터페이스에 정의되어 있는 것을 알맞게 구현한 클래스 중 하나.  
  - 계층도에서 `BeanFactory` 인터페이스가 최상위에 위치하는데 객체 생성 및 검색에 대한 기능을 제공함.  
  
* beanFactory  
  - 
  
