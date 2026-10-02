# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
Git은 내 컴퓨터에서 파일의 변경사항을 관리하는 도구이고, GitHub는 Git으로 관리한 파일을 온라인에 올리는 서비스 자체를 말합니다. Git 저장소 중 내 컴퓨터에 있는 저장소를 local repository, GitHub와 같이 온라인에 있는 저장소를 remote repository라고 합니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
Working Directory는 현재 내가 작업중인 폴더를 말합니다. Working Directory에서 뭔가 수정사항이 생기면 git add 를 통해 staging area로 변경사항을 커밋하기전 임시로 올릴 수 있습니다. 이후 git commit을 하면 local repository에 변경사항이 올라가며, 이를 최종적으로 github와 같은 remote repository에 올리는 것을 git push라고 합니다. 그리고 반대로 remote repository에서 파일을 당겨오는 것을 git pull이라 합니다. 


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
commit은 파일의 변경사항을 하나의 기록으로 저장한 것이고, branch는 특정 commit을 가리키면서 작업 흐름을 나누어 관리하는 기능입니다. HEAD는 현재 내가 작업하고 있는 branch나 commit을 가리킵니다.
git checkout 브랜치명을 사용하면 다른 branch로 이동할 수 있고, git checkout -b 브랜치명을 사용하면 새로운 branch를 만들면서 바로 이동할 수 있습니다. branch를 만들 때는 git branch 브랜치명, 삭제할 때는 git branch -d 브랜치명을 사용하며, 현재 branch 목록은 git branch로 확인할 수 있습니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
git clone은 이미 존재하는 remote repository를 내 컴퓨터에 그대로 복사해서 local repository를 만드는 방법이고, git init은 현재 폴더를 새로운 Git repository로 만드는 방법입니다. 기존 GitHub repository를 받아서 작업할 때는 git clone 주소를 사용하고, 내가 만든 폴더를 처음부터 Git으로 관리하려면 해당 폴더에서 git init을 사용합니다.
origin은 local repository와 연결된 remote repository의 기본 이름입니다. git clone을 하면 보통 복사해온 remote repository가 자동으로 origin이라는 이름으로 등록됩니다. git init으로 만든 repository는 remote repository가 자동으로 연결되지 않기 때문에 git remote add origin 주소를 사용해 직접 설정해야 합니다.
  

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
git reset은 commit을 이전 상태로 되돌릴 때 사용하고, 그림과 같이 --soft, --mixed, --hard 세 가지 방식이 있습니다.
git reset --soft는 commit만 되돌리고, 변경사항은 staging area에 그대로 남겨둡니다. 다시 commit만 하고 싶을 때 사용할 수 있습니다.
git reset --mixed는 commit과 staging area를 되돌리고, 변경사항은 working directory에 남겨둡니다. 기본 git reset도 --mixed 방식입니다.
git reset --hard는 commit, staging area, working directory까지 모두 되돌립니다. 수정한 내용도 같이 사라지기 때문에 사용할 때 주의해야 합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
Pull Request는 내가 작업한 branch의 내용을 다른 branch에 합쳐달라고 요청하는 기능입니다. 보통 작업이 끝난 뒤 Pull Request를 만들고, 내용을 확인한 후 Merge해서 branch를 합칩니다.
Merge에는 Fast-Forward와 3-Way Merge가 있습니다.
Fast-Forward는 다른 branch를 만든 뒤 원래 branch에 새로운 commit이 없는 경우에 사용됩니다. 이때는 원래 branch가 작업한 branch의 최신 commit 위치로 그대로 이동하면서 합쳐집니다.
3-Way Merge는 branch가 나뉜 뒤 양쪽 branch에 모두 새로운 commit이 생긴 경우에 사용됩니다. 이때는 두 branch의 내용을 합친 새로운 merge commit을 만들어서 합칩니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
rebase는 한 branch의 commit들을 다른 branch의 최신 commit 뒤로 옮기는 기능입니다. branch가 나뉜 뒤 main branch에 새로운 commit이 생겼을 때, 내가 작업한 branch를 최신 main branch 기준으로 이어서 정리할 수 있습니다.
merge와 달리 중간에 merge commit을 만들지 않아서 commit 기록을 한 줄처럼 깔끔하게 정리할 수 있다는 장점이 있습니다. 다만 기존 commit의 기록 자체가 바뀌기 때문에 이미 다른 사람과 공유한 branch에서는 주의해서 사용해야 합니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
git stash는 아직 commit하지 않은 변경사항을 잠시 저장해두는 기능입니다. 작업 중에 다른 branch로 이동해야 할 때 현재 수정사항을 commit하지 않고 잠깐 보관할 수 있습니다.
git stash를 사용하면 현재 변경사항이 임시로 저장되고 작업 폴더는 이전 상태로 돌아갑니다. 이후 git stash pop을 사용하면 저장해둔 변경사항을 다시 불러오면서 stash에서 제거할 수 있습니다.
여러 stash를 저장했다면 git stash list로 목록을 확인할 수 있고, 특정 stash를 다시 적용할 때는 git stash apply를 사용할 수 있습니다.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- 브랜치관리전략에 대표적으로 Github Flow, Git Flow가 있습니다. 두 방식에서는 리포지토리를 어떻게 관리할까요?
Github Flow는 main branch를 기준으로 필요한 작업마다 새로운 branch를 만들어 작업하고, 작업이 끝나면 Pull Request를 통해 main에 merge하는 방식입니다. 구조가 단순해서 자주 배포하거나 빠르게 개발하는 프로젝트에서 사용하기 좋습니다.
Git Flow는 main, develop 같은 여러 branch를 역할에 따라 나누어 관리합니다. 보통 develop에서 기능을 합치고, 기능 개발은 feature branch, 배포 준비는 release branch, 긴급 수정은 hotfix branch를 사용합니다.
즉 Github Flow는 branch 구조가 단순하고, Git Flow는 branch를 역할별로 더 세분화해서 관리하는 방식입니다.
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
git fetch는 remote repository의 최신 변경사항을 가져오기만 하고, 내가 작업 중인 branch에는 바로 적용하지 않습니다. 그래서 remote repository에 어떤 변경사항이 생겼는지 먼저 확인하고 싶을 때 사용할 수 있습니다.
git pull은 remote repository의 변경사항을 가져온 뒤 현재 branch에 바로 합칩니다. 즉 git pull은 보통 git fetch를 한 뒤 merge까지 하는 것과 비슷합니다.
그래서 다른 사람의 변경사항을 바로 적용해도 되는 경우에는 git pull, 먼저 확인한 뒤 적용하고 싶을 때는 git fetch를 사용할 수 있습니다.
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
