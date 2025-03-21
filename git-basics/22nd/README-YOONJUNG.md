# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  

- Git : 분산 버전 관리 시스템
- Github : Git으로 관리하는 프로젝트의 공유 및 협업을 위한 플랫폼
- 개인 컴퓨터의 저장소 : local / 서버의 원격 저장소 : remote
- local에서 작업한 프로젝트를 remote에 업로드하는 방식으로 변경 사항 반영 및 협업을 진행함. 

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  

- Working Directory : 사용자의 작업 공간. 
- Git Add : 변경 사항을 임시 공간 stage에 올림. 
- Git Commit : 변경 사항에 대해 저장 및 기록함. 
- Git Push : 변경 사항을 remote로 업로드함. 

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  

- Branch : Commit을 가리키는 포인터
- HEAD : Branch를 가리키는 포인터
- HEAD가 가리키는 Commit에 따라 Working Directory가 달라지며, checkout을 통해 HEAD가 가리키는 Branch를 변경할 수 있음.

----
**# Branch Command**
- Branch 생성 : git branch [branch]
- Branch 삭제 : git branch -D [branch]
- Branch 이동 : git checkout [branch]


## clone, init, origin
- clone, init은 모두 Git 저장소를 만드는 Command이나, 방법의 차이가 존재함. 
- git clone : 기존의 다른 Git 저장소를 복사하는 방법. 
- git init : 버전 관리를 하지 않던 프로젝트 파일을 Git 저장소에 추가하는 방법. 
- origin : 작업중인 local과 연결된 remote의 주소를 가리키는 단축 키워드. 
- 일반적으로 origin은 git clone 할 때 자동으로 생성되며, origin이 가리키는 주소를 통해 데이터 동기화 및 업데이트가 가능함. 

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
- reset : HEAD의 위치를 과거 혹은 미래의 commit으로 이동시킬 수 있음. 
- type1) --soft : HEAD가 특정 commit을 새롭게 가리키지만, 작업 중인 working directory와 staging area는 영향을 받지 않음. 
- type2) --mixed : HEAD가 특정 commit을 새롭게 가리키며 staging area도 동일하게 변하나, working directory는 영향을 받지 않음. 
- type3) --hard : HEAD가 새롭게 가리키는 commit과 동일하게 staging area와 working directory가 모두 변함. 

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
- Fork : 다른 사용자의 저장소를 복사하는 것. 
- Pull Request : Rork를 통해 복사한 내용을 개인 작업 공간에서 업데이트 후, 원본 저장소에 적용되도록 다른 사용자에게 pull 요청을 보내는 것.
- --
- Merge : 서로 다른 브랜치에서 작업한 내용을 합쳐야 하는 경우 사용. 
- type1) Fast-Forward : merge commit이 생기지 않고, merge가 실행된 branch의 HEAD가 병합되는 branch의 HEAD commit으로 이동하는 방식. 
- type2) 3-Way Merge : 두 branch가 commit history 상에서 분리된 2개의 선에 각각 존재할 때, merge commit을 새로 생성하는 방식. 

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
- rebase : 서로 다른 branch에서 작업한 내용을 합칠 때 사용하는 것으로, branch의 base commit을 재설정함. 
- 깃 히스토리가 직렬로 정리되어 깔끔한 관리가 가능함. 

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
- stash : 변경사항을 일시적으로 저장하는 기능. 
- commit하기에 이르거나, 다른 branch로 checkout하면서 변경 사항을 유지하고 싶은 경우 사용함. 일시적 저장 후 나중에 다시 사용이 가능함.
- 작업 중인 변경 사항을 stack에 저장하고, working directory를 깨끗한 상태로 만듦. 

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- 브랜치관리전략에 대표적으로 Github Flow, Git Flow가 있습니다. 두 방식에서는 리포지토리를 어떻게 관리할까요?
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
