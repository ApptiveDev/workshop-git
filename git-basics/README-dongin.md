# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
**Git**
- 버전 관리 시스템. 하나의 프로젝트에 여러 사람이 작업할 때 작업의 히스토리(변경 사항)를 관리할 수 있게 해주는 도구이다.
**Github**
- Git을 사용하여 관리되는 프로젝트를 올려두고, 협업을 쉽게 할 수 있도록 도움을 주는 웹 기반 플랫폼. 프로젝트의 버전을 관리하기 때문에 협업할 때 편리하다.
**Repository**
- Local Repository는 자신의 컴퓨터에 있는 저장소를 의미하고, Remote Repository는 인터넷 상에 위치한 저장소를 의미한다. 보통, Local 저장소에서 Git을 통해 프로젝트를 작업한 후, Remote 저장소(Github)에 올려 다른 팀원들과 공유하는 방식으로 협업을 진행한다.
> 이렇게, Git과 Github를 통해 코드의 변경 사항을 확인하고, 다양한 개발자와 원할한 작업이 가능하다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
**Working Directory**
- 사용자가 실제로 작업하고 있는 로컬 파일 시스템의 디렉토리. 개발자가 코드를 수정, 생성하는 곳.
**git add**
-  Working Directory에서 변경된 파일들을 임시저장공간(Staging Area)로 이동시키는 명령어. Git이 추적해야 할 변경 사항을 선택하는 과정으로, 사용자는 commit할 파일들을 고를 수 있다.
**git commit**
- Staging Area에 있는 변경 사항들을 Local Repository에 영구적으로 저장하는 명령어. 각 commit은 해당 프로젝트의 버전을 나타내며, 커밋 메시지를 통해 해당 변경 사항에 대한 설명을 추가할 수 있다.
**git push**
- Local Repository의 commit을 Remote Repository (ex. Github)에 업로드하는 명령어. 코드의 최신 버전을 팀원들과 공유, 백업하는 데 사용된다.
**git fetch**
- Remote Repository의 최신 변경 사항을 Local로 가져오는 명령어. 원격 저장소의 최신 상태를 확인하고 싶을 때 사용한다. git fetch 후, git merge나 git rebase를 사용해서 원격 변경 사항을 현재 작업 브랜치에 반영할 수 있다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
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
