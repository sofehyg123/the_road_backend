### Exception  

> Exception 내용들  
1. UnsatisfiedDependencyException  
  UnsatisfiedDependencyException: Error creating bean with name 'InfoPrinter':   
  Unsatisfied dependency expressed through method 'setPrinter' parameter 0; nested  
  exception is org.springframework.beans.factory.NoUniqueBeanDefinitionException:  
  No qualifying bean of type 'spring.MemberPrinter' available: expected single matching bean but found 2: memberPrinter,memberPrinter1  
  
* 자동 주입 빈이 2개 이상일 때 발생되는 Exception
* Qualifier 애노테이션으로 해결.  
  
  
  ***
  
