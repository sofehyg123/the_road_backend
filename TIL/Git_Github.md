### Git 및 Github  
* [초심자를 위한 Github 협업 튜토리얼](https://milooy.wordpress.com/2017/06/21/working-together-with-github-tutorial)  
* [Git의 기초개념 알기](https://backlog.com/git-tutorial/kr/intro/intro1_3.html)  
* [Git 사용방버 정리](https://wordbe.tistory.com/entry/Git-사용-방법-정리commit-push-pull-request-merge-등)
* Homebrew를 통해 깃을 설치했다. 설치경로를 알고 싶으면? 맥기준, 터미널에서 which git 명령을 보내면 경로를 알려준다.  
#### Git 영역
* Working Directory(Local)  
  - 개인 코드 작성  
* Staging 영역  
  - git add 를 통해서 수정된 코드를 올리는 영역  
* Repository  
  - git commit 을 통해서 최종 수정본을 제출  
  
#### 저장소 생성
* git init  
  - 해당 폴더를 git으로 관리하는 폴더(.git)가 생성.  
* git clone (git 저장소의 URL)  
  - git 저장소를 내 로컬저장소에 복사.  
  
#### Staging 영역에 추가  
> 코드 수정이 완료되면 스테이징에 추가한다.  
* `git add .`  
  - 현재 디렉토리에 있는 업데이트 된 파일을 전부 스테이징 영역으로 추가한다.  
* `git add -A`  
  - 수정된 파일 전부를 스테이징 영역에 추가한다.  
* `git status`  
  - 현재 add 내역을 확인.  

#### Commit  
* CLI - `git commit -m "변경이름"`  
* GUI - Commit 버튼 클릭  
* 커밋은 꾸준히 쌓이고 연결되어 있다(의미있는 변동사항을 커밋으로 저장한다).  
* 옵션:  
    -m [메세지] : 커밋 메세지와 함께 커밋  
    -a : 자동으로 add를 진행한 후 커밋  
    -v : 커밋 메세지에 diff의 내용 포함  
  
#### PUSH
* 원격저장소에 내 코드를 저장  
  - 다른 사람들도 내 코드를 가져갈 수 있다.  
  - AWS, Github 등  
* `PUSH` 하기 위해서 원격 저장소와 내 로컬을 연결해야 한다.  
  ```$ git remote add origin (원격 저장소 github URL) ```  
  ```$ git push origin master```  
* orgin은 remote repository 이름.  
* GUI - Push 버튼 클릭    

#### PULL
* 다른사람의 코드를 내 로컬저장소에 가져오기. 
* 다른 사람이 원격 저장소(Remote repository)에 업데이트한 파일이 있을 때, 원격저장소와 내 로컬저장소의 상태를 동일하게 만들기 위해 pull을 이용함.  
* CLI - `git pull`  
* GUI - Pull 버튼 클릭   
  
#### branch  
* 한 저장소에서 다른사람과 공동작업을 필요로 하는 경우 사용  
* 여러 줄로 커밋할 수 있게 해준다(n줄로 쌓는다).  
  - 왜 여러줄로 커밋해야 하나?  
    - 한 줄의 코드를 동시에 수정하는 경우 충돌이 발생할 수 있기 떄문.  
  - n줄로 쌓고 나중에 합칠 때 충돌이 발생하더라도 명시적으로 해결할 수 있다.  
* CLI - `git branch branch-name`  
* GUI - Branch 버튼 클릭  
  
#### Merge
* 브런치 공동작업이 끝난 후 합칠 때 사용  
* branch와 branch를 합침  
* CLI - `git merge branch-name`
* GUI - Merge 버튼 클릭  

### 협업 시나리오  
> 협업개발한 경험이 없기 때문에 참고 사이트에서 그대로 복사/붙여넣기 합니다.  
1. 내 컴퓨터에서 코드 작업.    
2. 단계벌로 커밋 만들기.  
3. Github에 저장소를 만들어 커밋을 푸시.  
4. 동료 개발자와 인사한다. Hi!  
5. 동료 개발자가 본인 컴퓨터에 저장소를 Pull.  
6. 동료 개발자가’ fix/click-bug’ branch를 만들어 버그를 고쳐준다  
7. fix/click-bug 브랜치에서 작업이 끝나면 master브랜치와 병합한다.  

### 여러가지 상황  
* FullRequest  
  - 병합요청편지  
    - 병합하기 전 리뷰/컨펌을 받을 때  
    - 코드 변경사항에 댓글을 달 수 있다.  
    - 변경후 github에서 merge버튼을 누르면 자동 병합 된다.  
  
#### 알아두면 편리한 명령  
1. Stash  
2. Discard(변경사항 삭제)/ Remove(파일 삭제  
3. Cherry pick  
4. Ammend last commit  
5. rebase  
  
#### Question  
1. Origin 이 붙은 것과 안 붙은것?  
2. 2 behind의 뜻?  
3. unstage와 stage 차이?  
4. changes 다 없애고 싶을 때 방법?  
	stash/ reset/ discard(+remove)  
5. reset soft/mixed/hard  
6. reset, revert 언제 해야 하는지?  

***  
  
* Git 에서 권장하는 메세지 형식  
1번째 줄: 커밋 내의 변경 내용을 요약  
2번째 줄: 빈 칸  
3번째 줄: 변경한 이유  
  
* 작업트리와 인덱스  
  - 작업트리 : 디렉토리  
  - 인덱스 : 커밋을 실행하기 전의 저장소와 작업트리 사이의 공간  
    - 작업트리의 변경 내용을 인덱스에 등록되어야만 커밋을 실행할 수 있다.  
    > "변경부분을 바로 commit하지 않고 staging 시킨다" 라고 표현.  
    - 따라서, 모든 변경사항이 인덱스에 존재해야 한다. 왜? 커밋하기 위해서(중복)  
    - 덕분에?
      - 원하는 일부를 변경할 수 있다.  
      - 원하지 않는 부분을 포함시키지 않을 수 있다.  
      - ex) 원격 저장소에 10개 중 7개만 공개하고 싶은 경우, 7개만 포함(선택하는 작업)시킬 때 이를 7개를 스테이징한 상태임.  

* 원격 저장소에 푸시하기
  - 변경 이력이 원격 저장소에 업로드되어 공유되어 로컬저장소의 상태와 동일해짐(변경된 부분들을 등록한것들만).  
  
* 원격 저장소 복제(Clone)하기  
  - 변경 이력도 함께 로컬 저장소에 복제되어 오므로, 원래 원격 저장소와 똑같이 이력을 참조하고 커밋을 진행할 수 있다.  
  
