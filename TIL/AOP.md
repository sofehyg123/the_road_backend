### AOP/#1  

* 수행시간을 출력하기 위한 가장 간단한 방법.  
  - ```System.currentTimeMillis()```  를 통해서 구할 수 있다.  
  - start, end 를 구한다음, 뺸다(-) : 수행시간.    
  ```
  long start = System.currentTimeMillis();
  factorial(4)
  long end = System.currentTimeMillis();
  long 수행시간=end-start;
  ```

#### 문제점?
* 시간 단위를 밀리 -> 나노로 구하려고 한다면, 앞 서 작성된 start, end 코드를 다시 작성해야한다.  
* 이를 해결하기 위해, `프록시` 라는 객체를 사용한다.  

#### 프록시?
* 다른 클래스에 위임해서 수행시간을 얻어오기  
  - 어떤 이점이 있을까?  
  - 상속만 받으면, 객체만 넣어주면 다음과 같은 **이점**을 얻는다.  
    - 기존 코드를 변경하지 않고 실행 시간을 출력할 수 있다.  
      - `Impe`, `Rec` 클래스 코드를 변경하지 않음.  
    - 실행 시간을 구하는 코드의 중복을 제거할 수 있다.  
      - `start`, `end` 코드 라인.  
      - `nano` -> `millis` 로 바꾸고 싶다면 ExeT만 바꾸면 됨.  
      
  ```  
  public class Main {
    public static void main(String[] args) {
        ExeTimeCalculator exeT = new ExeTimeCalculator(new ImpeCalculator()); //객체주입
        System.out.println(exeT.factorial(20));
        ExeTimeCalculator exeT2 = new ExeTimeCalculator(new RecCalculator()); //객체주입
        System.out.println(exeT2.factorial(20));
    }
  }
  /*
  * ExeTimeCalculator 안에는 주입받은 객체에 연산을 시키고 nano 시간차를 구하는 메서드가 구현되어 있다.  
  */
  ```  
  
#### 정리
* 핵심 기능의 실행은 다른 객체에 위임하고, 부가적인 기능을 제공하는 객체를 프록시(proxy)라고 한다.  
* `ExeTimeCalculator` 은 **프록시**이고, `ImpeCalculator()`, `RecCalculator()`은 **대상객체**이다.  
  
*** 
### AOP/#2

* 프록시 특징  
  - 핵심기능은 구현하지 않는다!(ExeTimeCalculator처럼)  
  - 대신 여러 객체에 공통으로 적용할 수 있는 기능을 구현.  
  - 즉, 공통 기능 구현과 핵심 기능 구현을 분리하는 것이 AOP의 핵심이다.  
  
* AOP(Aspect Oriented Programming)  
  - 여러 객체에 공통으로 적용할 수 있는 기능을 분리해서 재사용성을 높여주는 프로그래밍 기법.  
  - 스프링도 프록시를 이용해서 AOP를 구현하고 있다.  
  
*  핵심 기능에 공통 기능을 삽입하는 세 가지 방법.  
  - 컴파일 시점에 코드에 공통 기능을 삽입하는 방법.  
    - AOP 개발 도구(AspectJ)  
  - 클래스 로딩 시점에 바이트 코드에 공통 기능을 삽입하는 방법.   
  - 런타임에 프록시 객체를 생성해서 공통 기능을 삽입하는 방법(스프링이 제공).  
  
* AOP 주요 용어 : `Advice`, `Joinpoint`, `Pointcut`, `Weaving`, `Aspect`  
  
* Advice의 종류 : `Before Advice`, `After Returning Advice`, `After Throwing Advice`, `After Advice`, `Around Advice`  
  - Around Advice : 다양한 시점에 원하는 기능을 삽입할 수 있기 떄문에 많이 사용됨.  
    - 메서드 실행 전, 후 또는 익셉션 발생 시점에 공통 기능을 실행하는데 사용.  
    - 캐시 기능, 성능 모니터링 기능과 같은 Aspect 구현할 때 사용.  
    
* 스프링 AOP 구현(P.161 참고)  
1. Aspect로 사용할 클래스에 @Aspect 애노테이션을 붙인다.
2. @Pointcut 애노테이션으로 공통 기능을 적용할 Pointcut을 정의한다.
3. 공통 기능을 구현한 메서드에 @Around 애노테이션을 적용한다.

* 공통 기능을 적용하는데 필요한 코드를 구현하면, 스프링 설정 클래스 작성  




*** 

