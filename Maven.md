### 메이븐
* 스프링5 - 최범균 저서  
  
  
  
* pom.xml  
  메이븐 프로젝트에 대한 **설저 정보**를 관리하는 파일로서 프로젝트에서 필욜 하는 의존 모듈이나 플러그인 등에 대하 설정을 담는다.  
  
* 메이븐은 한 개의 모듈을 Artifact 단위로 관리한다.  
  
```
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>5.0.7.RELEASE</version>
</dependency>
```
* 의존을 추가한다는 것은 일반적인 자바 어플리케이션에서 클래스 패스에 spring-context 모듈을 추가한다는 의미.  
  - 즉, 위 설정은 메이븐 프로젝트의 소스 코드를 컴파일하고 실행할 때 사용할 클래스 패스에 spring-context-5.0.7.RELEASE.jar 파일을 추가한다는 의미  
  - 중복) 메이븐은 코드를 컴파일하거나 실행할 때 <dependency>로 설정한 아티팩트 파일을 사용한다.  
* [그룹ID]\[아티팩트ID]\[버전] 폴더에 아티팩트 ID-버전.jar 형식의 이름을 갖는 파일이 있는지 검사 ->존재하면 사용함.  
  - 없다면? 메이븐 중앙 리포지토리에서 로컬 리포지토리로 복사해와 사용  
* 메이븐 기본적인 폴더 : [사용자홈폴더]\.m2\repository  
* Maven Dependencies에 등록된 jar파일들은 앞서 설명한 메이븐 로컬 리포지토리에 위치함.  
  - (중복)이클립스는 메이븐 프로젝트를 임포트 할 때 필요한 모든 jar 파일을 로컬 리포지토리에 다운로드한 뒤 그 파일을 클래스패스에 추가한다.  
  
* 메이브은 jar를 다운로드 할 때 해당 프로젝트와 의존된 다른 프로젝트들도 같이 다운로드 해준다.  
  - 이를 '의존전이'라고 부른다.  
  
* src\main\java : 메이븐에 정의되어 있는 기본 폴더 구조  
  - 자바 소스코드가 위치함  
* src\main\resources : 자바 소스 이외의 자원파일(XML,properties)이 위치함  
> 두 개의 폴더는 프로젝트 소스로 사용되므로 이클립스에서 메이븐 프로젝트를 import하면 두 폴더 모두 이클립스의 소스 폴더가 된다.  
* src\main\webapp : 웹 어플리케이션 기준 폴더
  - jsp 소스코드  
  - WEB-INF\web.xml 파일들이 위치함.  






