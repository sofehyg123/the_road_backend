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
* 스프링 컨테이너 : `BeanFactory`, `ApplicationContext` 등.  
* 싱글톤 객체  

> 스프링의 특징  
* 의존(Dependency Injection) : 객체간의 의존  
  - 한 클래스가 다른 클래스의 메서드를 실행할 때 이를 의존이라고 표현한다(ex. service -> dao의 메서드 호출)  
  > service클래스가 dao 클래스에 의존한다.  
  - 의존하는 대상이 있으면 구하는 방법이 필요한대 가장 쉬운 방법은 객체를 직접 생성하는 것
    - service 클래스에 dao객체를 생성해서 사용하는 모습.  
    - 이는 service 객체를 생성하면 동시에 dao객체도 생성하게 된다.  
    - 하지만 유지보수 관점에서, 문제점이 생길 수 있다.  
  - 의존을 구하는 방법 중 `Di`와 `서비스 로케이터` 방법도 있다. 
  > 의존  
  
  

> 설정정보  
* @Configuration : 해당 클래스를 스프링 설정 클래스로 지정한다.  
* AnnotationConfigApplicationContext 클래스  
  - 자바 클래스(@Configuration 애노테이션이 설정된)에서 정보를 읽어와 빈 객체를 생성하고 관리한다.(스프링의 핵심 기능)  
  - ApplicationContext 인터페이스에 정의되어 있는 것을 알맞게 구현한 클래스 중 하나.  
  - 구현된 AnnotationConfigApplicationContext 클래스는 설정 정보로부터 Bean이라고 불리는 객체를 생성하고 그 객체를 내부에 보관한다.  
  - 그리고 getBean()메서드를 실행하면 해당하는 빈 객체를 제공한다.  
  - 계층도에서 `BeanFactory` 인터페이스가 최상위에 위치하는데 객체 생성 및 검색에 대한 기능을 제공함.  
  
* ApllicationContext 인터페이스  
  - 메세지, 프로필/환경 변수 등을 처리할 수 있는 기능을 추가로 정의  
  - 객체 생성, 초기화, 보관, 제거 등을 관리해서 `컨테이너` 라고 부른다.
  
* BeanFactory  
  - 생성된 객체를 검색하는데 필요한 getBean()메서드가 BeanFactory에 정의되어 있다.  
  - 싱글톤/프로토타입 빈인지 확인하는 기능도 제공  
  
