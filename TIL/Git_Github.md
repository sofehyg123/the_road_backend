### Git 및 Github  
* [초심자를 위한 Github 협업 튜토리얼](https://milooy.wordpress.com/2017/06/21/working-together-with-github-tutorial)  

* CLI - 
* GUI - 

#### Commit  
* CLI - git commit -m "변경이름"  
* GUI - Commit 버튼 클릭  
* 커밋은 꾸준히 쌓이고 연결되어 있다(의미있는 변동사항을 커밋으로 저장한다).  
  
#### PUSH
* 원격저장소에 내 코드를 저장  
  - 다른 사람들도 내 코드를 가져갈 수 있다.  
  - AWS, Github 등  
* CLI - git push origin master  
* GUI - Push 버튼 클릭  
  
#### PULL
* 다른사람의 코드를 내 로컬저장소에 가져오기.  
* CLI - git pull  
* GUI - Pull 버튼 클릭   
  
#### branch  
* 한 저장소에서 다른사람과 공동작업을 필요로 하는 경우 사용  
* 여러 줄로 커밋할 수 있게 해준다(n줄로 쌓는다).  
  - 왜 여러줄로 커밋해야 하나?  
    - 한 줄의 코드를 동시에 수정하는 경우 충돌이 발생할 수 있기 떄문.  
  - n줄로 쌓고 나중에 합칠 때 충돌이 발생하더라도 명시적으로 해결할 수 있다.  
* CLI - git branch branch-name  
* GUI - Branch 버튼 클릭  
  
#### Merge
* 브런치 공동작업이 끝난 후 합칠 때 사용  
* branch와 branch를 합침  
* CLI - git merge branch-name
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
