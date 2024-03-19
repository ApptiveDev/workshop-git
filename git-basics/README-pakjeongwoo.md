# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
로컬 저장소는 개발자의 컴퓨터에 있는 Git 저장소입니다.
원격 저장소는 GitHub와 같은 원격 서버에 호스팅된 Git 저장소입니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
Working Directory : 개발자가 작업하는 로컬의 디렉토리
Git Add : 작업 디렉토리에서 변경된 파일을 스테이징 영역에 추가하는 명령어
Git Commit : 스테이징 영역에 있는 변경사항을 로컬 저장소에 기록하는 명령어
Git Push : 로컬 저장소에 커밋된 변경사항을 원격 저장소에 업로드하는 명령어
Git Merge : 다른 브랜치의 변경 사항을 현재 브랜치에 통합하는 명령어
Git Fetch : 원격 저장소의 최신 변경 사항을 로컬 저장소로 가져오는 명령어

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
branch 생성 : git branch <branch-name>
branch 삭제 : git branch -d <branch-name> 강제삭제시 -D 옵션사용
branch 목록확인 : git branch -r하면 원격 저장소의 브랜치 목록을 알수있음
HEAD : 현재 작업중인 브랜치를 가리키는 포인터 일반적으로 HEAD는 브랜치의 최신커밋을 가리킨다
git checkout : 명령어는 브랜치 간 전환이나 특정 커밋으로 이동할 때 사용된다


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
git clone : 이미 존재하는 원격 리포지토리를 로컬 컴퓨터에 복제할 때 사용
git init : 로컬 컴퓨터에 새로운 Git 리포지토리를 초기화할 때 사용
orgin : Git에서 원격 리포지토리의 기본 별칭
설정방법 : git init으로 초기화한 로컬 리포지토리에서는 git remote add origin <repository-url>
차이점 : git clone은 원격 리포지토리를 복제하여 로컬에 생성하는 반면, git init은 로컬에 새로운 리포지토리를 초기화합니다
## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
soft : 브랜치가 가리키는 커밋을 변경하지만, 스테이징 영역과 작업 디렉토리는 그대로 유지합니다.
mixed : 옵션은 브랜치가 가리키는 커밋을 변경하고, 스테이징 영역을 해당 커밋과 동일한 상태로 만듭니다. 작업 디렉토리는 그대로 유지됩니다.
hard : 브랜치가 가리키는 커밋을 변경하고, 스테이징 영역과 작업 디렉토리를 해당 커밋과 동일한 상태로 만듭니다.
## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
Pull Request : 자신의 변경 사항을 원본 리포지토리에 통합하기 위한 요청
Merge : 두 개의 브랜치를 통합하는 과정
Fast-Forward Merge : 브랜치의 변경 사항을 master 브랜치에 적용할 때, master 브랜치의 포인터를 브랜치의 최신 커밋으로 이동시키는 것으로 병합이 완료
3-Way Merge : 두 브랜치의 공통 조상 커밋과 각 브랜치의 최신 커밋을 사용하여 병합이 이루어집니다.

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
