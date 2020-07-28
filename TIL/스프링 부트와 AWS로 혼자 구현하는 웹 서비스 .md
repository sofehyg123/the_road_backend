# 스프링 부트와 AWS로 혼자 구현하는 웹 서비스  

* 몰랐던 것들을 정리해서 업데이트 할 예정입니다.  
* 선수지식이 없으면 외워야 하는 수밖에 없다.(업데이트 예정)  
  - 외우기 -> 모르는 개념을 찾아서 학습 -> 흐름이 어떻게 흘러가는지 분석 -> 이해되면 안보고 다시 짜보기 -> 왜 이렇게 코드를 짤 수 밖에 없는지 코드품질이 높은건지(효율성 등) 따져보기  
  - 많은 인내과 체력이 필요한 것이 큰 부담이지만,  두가지 학습 방법에서 나는 거꾸로 가는 학습패턴을 선택함.  
    +  시간이 없었음.  
    +  독학이다보니 더 이상 재면서 하나씩 습득하기에는 멘탈력이 없음  
  
2020.7.20 시작.

* 리펙토링<기준:책을 끝까지 보고 난 후에 진행함.>
  - 느낌적인 것들, 글을 쓰는 것보다는 복습하기 위한 간단한 메모이기 때문에 정리되지 않았습니다. 1회독이 완료되면 리펙토링을 할 예정입니다.  

**<1회독>**  

* 트랸잭션의 의미 - 최범균 저서 참고.

* 138p  
  mustache 에 작성된 div 구성을 처음 봤다. 낯설었다. role이라는 개념도 처음 알게 되었다.  
  div를 3개를 감싼 이유, 각 클래스 명은 무엇을 의미하는지 모르겠다(ex. class="col-md-6"). 6하고 12는 무슨 차이지?  
  구글에 검색해봤는데 부스트 트랩과 관련되어 있는 듯 하다.  
  
* 139p  
  - label 태그의 for속성에 대해서 처음 알게 되었다. [for 속성에 대해 알아보기](https://www.codingfactory.net/11008)  
  - CSS의 기본적인 공부가 필요하다.  
  - role 속성에 대한 참고 : [role](https://happycording.tistory.com/entry/HTML-Role-왜-사용해야만-하는가)  
  - btn btb primary 는 버튼 꾸미기, 부스트트랩과 관련되어 있다. 부스트트랩도 공부하자.  [btn-btn-xxx](https://www.codingfactory.net/10731)  
  
* 141p  
  var_this = this;  [참고](https://hyunseob.github.io/2016/03/10/javascript-this/), [참고2](https://mobicon.tistory.com/189)  
  자바의 전역변수로 받아들이면 될 것 같다.  
  
* 149p
  .map(PostsListResponseDto::new) : [람다식을 참고](https://m.blog.naver.com/2feelus/220695347170)  
  
* 조회화면을 만드는 로직과 수정, 삭제 화면을 만드는 로직은 어떤 차이가 있는거지?
  - PostsApiController 에서 조회관련 mapping은 없었음.  
  
* 174p  
  Open Id Provider가 뭐지?  
  
git과 github에 대해서 공부해야 함.  
  
* 178p  
  enum 타입이 뭐지?  
  
* 179p  
  optional[참고](http://homoefficio.github.io/2019/10/03/Java-Optional-바르게-쓰기/)
  
* 스프링 시큐리티  
  [okky-초보가 이해하는 스프링 시큐리티](https://okky.kr/article/382738)  
  [스프링 공식 레퍼런스](https://spring.io/projects/spring-security)  
  [스프링 oauth2](https://github.com/spring-projects/spring-security/wiki/OAuth-2.0-Migration-Guide)  
  [Spring Security 스프링 시큐리티](https://velog.io/@jayjay28/2019-09-04-1109-작성됨)  
  
  
  
