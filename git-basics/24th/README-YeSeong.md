# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git은 local에서 즉 내 컴퓨터 안에서 동작하며 소프트웨어의 버전, 형상을 관리하는 프로그램으로 이 프로그램이 언제 어떤 코드를 어떻게 수정했는지를 상세히 기록하여 사용자가 언제든지 원하는 시간대 ,원하는 버전으로 복구할 수 있도록 해주는 프로그램입니다.
그리고 github는 이 git을 이용하여 remote 저장소를 만들어 다른 환경(예를들어 데스크탑과 랩탑)에서도 동일한 코드의 소프트웨어 작업을 지속할 수 있도록 해주거나 다른 사람과 협업을 할때 서로 다른 기능을 개발하고 나중에 합치거나 문제가 생겼을때 이전 버전으로 복구하는 등의 작업을 할 수 있도록 하는 호스팅 서비스입니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working Directory : 현재 내 컴퓨터 저장소(HDD or SSD)에 실제로 저장되어 있는 작업 폴더
Git Add : working directory의 코드와 git의 코드의 차이점들 중에서 커밋할 코드를 선택하는 것
Git Commit : add로 선택한 코드들을 내 local git에 코멘트와 함께 저장하는것
Git Push : 내 local git에 저장된 것을 github와 같은 remote git 저장소에 업로드하는  것
Git merge : 내 local git과 remote git의 차이점이 존재 할때 병합하는 과정
Git fetch : remote git의 변경사항을 받아오는 것

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

commit은 사용자가 코드를 수정한 내용을 설명과 함께 기록한 것이고 branch는 이러한 commit들의 크게 보면 분기를 의미하고 처음 git을 만들면 main branch가 생성되고 여기서 따로 개발을 하기위해 새로운 branch를 생성하고 main과 따로 새로운 branch에 commit을 할 수 있게 되고 이것은 main에는 영향을 주지 않을 수 있게 된다. HEAD는 현재 내가 어떤 branch에 있는지 표시하는 것이고 git checkout을 통해 다른 branch로 이동하거나 새로운 브랜치를 만들거나 할 수 있다.

git checkout -b [branch name] : [branch name] 브랜치를 생성하고 이동
git checkout [branch name] : [branch name] 브랜치로 이동

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
