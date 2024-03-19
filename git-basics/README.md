# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git : 로컬 저장소의 모든 변경사항을 기록하여 파일 버전관리
git hub : git을 사용하는 웹 호스팅 서비스
로컬 저장소의 코드를 업로드하고, 공유 할 수 있음

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working directory : 로컬 저장소에 접근할 수 있으며, 실제로 파일을 생성하고 수정하는 공간, 현재 작업중인 공간

Staging area : 곧 commit할 파일에 대한 정보를 저장하는 곳

local repository : 내 컴퓨터 안에 있는 저장소, 네트워크 필요 X

remote repository : 원격 서버에 있는 저장소, 네트워크 필요(github, gitlab...)

Git add : 작업 위치(Working directory 이하 WD)폴도에 작업한 파일이 있을 경우, add를 통해서 staging Area로 옮길 수 있음

Git commit : staging area에 저장되어있는 변경 사항들을 로컬저장소에 등록

Git push : 원격 저장소에 commit된 파일들을 모두 업로드

Git pull : 원격 리포지토리에서 로컬로 변경 내용을 가져와 병합

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

commit : 의미있는 변경 작업들을 저장소에 기록하는 동작

branch : 여러 개발자들이 동시에 작업을 할 수 있게 만들어주는 기능
각자 독립적인 작업 영역(저장소)안에서 코드 변경 가능

Head : 모든 브랜치에는 HEAD값이 존재하는데, 해당 브랜치의 마지막 커밋을 뜻함

git checkout : 코드저장소(repository)에서 특정 브랜치로 전환하는 작업


Git branch 주요 명령어
git branch [-l](-l생략 가능) : 로컬 branch 정보를 보여줌
git branch -v : 로컬 branch의 정보를 마지막 커밋 내역과 함께 보여줌
git branch -r : remote repo의 branch 정보를 보여줌
git branch -a : 로컬/리모트 저장소의 모든 branch 정보 보여줌
git branch (이름) : 로컬에 새로운 branch 생성
생성과 동시에 해당 branch로 이동하려면 -b 사용
git branch -d (branch이름) : branch 삭제


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
