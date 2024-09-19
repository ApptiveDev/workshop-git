# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

local은 사용자의 개인 컴퓨터 또는 개발 환경 내에서 관리되는 데이터나 파일이다.
remote는 서버나 클라우드와 같은 인터넷 기반의 저장소를 의미한다.

git은 분산 버전 관리 시스템으로서 여러 개발자들이 동시에 작업할 수 있도록 돕는다. 개발자가 자신의 로컬 컴퓨터에서 프로젝트의 버전을 관리하는 도구다.

github는 git repository를 호스팅하는 원격 저장소를 저장하는 서비스이다. github는 git을 기반으로 하여 개발자들이 코드를 공유하고 협업이 가능할 수 있도록 한다. 

개발자는 자신이 local에서 작업한 내용을 git 명령어를 통해 github의 원격 리포지토리에 업로드할 수 있고 다른 개발자가 작업한 내용을 로컬로 가져와서 협업할 수 있다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

-Working Directory
Working Directory는 git이 현재 작업하고 있는 파일들이 위치하는 로컬 폴더이다.
이 폴더에 존재하는 파일들은 삭제,추가,수정 등의 작업이 가능하다.

-git add
git add 명령어는 작업 디렉토리의 파일을 Staging Area로 추가하는 역할을 한다.
Staging Area(스테이징 영역)는 Git에서 변경된 파일들을 커밋할 준비가 된 상태로 만드는 곳이다. git add를 실행하면 해당 파일의 현재 상태가 git의 다음 커밋에 포함되도록 준비된다.

-git commit
git commit은 스테이징 영역에 있는 변경사항을 Local Repo(로컬 저장소)에 커밋하는 역할을 한다. 커밋은 변경사항을 기록하고 커밋 메세지와 함께 변경 사항의 내용을 설명할 수 있다. git commit -m "work"에서의 "work"가 커밋 메세지이다.

-git push
git push 명령어는 Local Repo에  커밋되어있던 변경사항을 Remote Repo(원격 저장소)로 업로드하는 역할을 한다.(Github가 Remote Repo라고 볼 수 있다.)
이를 통해 다른 사용자들과 변경 사항을 공유할 수 있다.


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

-Branch
branch는 독립적으로 작업할 수 있는 별도의 작업공간이다. 브랜치를 사용하면 여러 작업을 병행하거나 새로운 기능을 개발할 때, 기존 코드에 영향을 주지 않고 작업이 가능하다.
1. git branch 브랜치명 -> 새 브랜치 생성
2. git branch -d 브랜치명 -> 해당 브랜치 삭제
3. git branch -> 브랜치 목록
4. git checkout 브랜치명 -> 해당 브랜치로 이동

-HEAD
HEAD는 현재 작업 중인 브랜치를 가리키는 포인터를 뜻한다.
HEAD는 현재 체크아웃된 브랜치의 가장 최신 커밋을 참조한다.
git branch --show--current -> 현재 HEAD가 가리키고 있는 브랜치를 확인할 수 있다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

-git clone
git clone은 원격 저장소의 복사본을 로컬에 생성하는 명령어를 뜻한다.
git clone을 사용하면 원격 저장소의 모든 브랜치와 커밋기록이 로컬 저장소에 복제되며 기본적으로 origin이라는 이름의 원격 저장소가 자동으로 설정된다.
ex) git clone <원격 저장소 URL>

-git init
git init은 새로운 빈 git repository를 생성하는 명령어를 뜻한다.
ex)
mkdir project1
cd project1
git init
-> 위 명령어를 실행하면 project라는 디렉토리에 빈 git 저장소가 만들어진다.

-origin
origin은 위에서도 말했듯이 git clone 명령어를 사용할 때 자동으로 설정되고, 새로운 프로젝트에서 원격 저장소를 추가할 때 사용할 수 있다.

1. git remote add origin <원격 저장소 URL> -> 원격 저장소 추가
2. git remote set-url origin <새 원격 저장소 URL> -> 원격 저장소 변경
3. git remote remove origin -> 원격 저장소 삭제

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

1. git reset --soft
최근의 커밋을 취소하고, 그 커밋의 변경 사항을 다시 커밋할 수 있도록 스테이징 영역에 유지할 때 사용한다.

2. git reset --mixed
마지막의 커밋을 취소하고, 그 커밋의 변경 사항을 스테이징 영역에서 제거하지만, Working Directory에는 남겨둔다.

3. git reset --hard
마지막의 커밋을 취소하고 그 커밋의 스테이징 영역과 Working Directory 모두 그 커밋 상태로 되돌린다. (모든 변경 사항을 삭제)

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

-Pull Request
pull request는 Github와 같은 플랫폼에서 브랜치를 병합하기 전에 코드 리뷰를 요청하는 것이다. 팀원들이 코드를 리뷰하고 해당 코드를 승인하면 병합이 가능해지고, 병합을 하게되면 메인 브랜치와 해당 브랜치가 병합된다.

-Merge
두 개의 브랜치를 통합하여 하나의 브랜치로 만드는 과정이다.
1. Fast-Forward Merge
브랜치가 직선적으로 이어지는 경우의 병합방식으로 브랜치가 공통 기반 브랜치에서부터 일련의 커밋이 이어져있고, 중간에 다른 커밋이 없는 경우이다.

2. 3-Way Merge
브랜치 간에 변경 사항이 서로 다른 경우이고, 공통 조상을 기준으로 병합한다. 이 방식은 git이 자동으로 변경 사항을 통합하며, 경우에 따라 수동으로 충돌을 해결해야 할 수도 있다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

git rebase는 브랜치의 커밋들을 다른 브랜치의 최신 커밋 위에 재적용하여 히스토리를 선형으로 만드는 명령어이다.

1. git pull origin main --rebase
해당 명령어를 사용하면 원격 저장소에서 main 브랜치의 최신 변경 사항을 로컬 브랜치에 통합할 수 있다.
git push를 하기전에 git pull origin main --rebase를 해주면 최신 변경 사항이 적용된 로컬 브랜치를 원격 저장소에 푸시할 수 있다.


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

-git stash
git stash 명령어는 현재 Working Directory의 변경사항을 임시로 저장하고 Working Directory를 깨끗한 상태로 되돌리는 것이다.

1. git stash list -> 저장된 stash의 목록을 확인
2. git stash apply -> 가장 최근의 stash 복원
3. git stash pop -> 복원 후에 stash 목록에서 삭제
4. git stash drop stash@{n} -> 특정 stash 삭제
5. git stash clear -> 저장된 모든 stash를 목록에서 삭제
5. git stash save "message" -> stash에 메세지를 추가하여 기록을 남김



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

1. git rebase --interactive
커밋 히스토리를 수동으로 수정할 수 있는 명령어

2. branch의 upstream이란? (`git push --set-upstream`)
Upstream Branch는 로컬 브랜치가 원격 브랜치와 연결되어 있을 때, 원격 브랜치를 의미. git push --set-upstream를 통해 로컬 브랜치와 원격브랜치를 연결가능.

3. PR and Fork
PR(Pull Request)는 브랜치뿐만 아니라 Fork한 리포지토리에서도 생성가능.(주로 Fork는 오픈소스 프로젝트에 기여할때 사용)

4. git fetch, git pull

-git fetch
원격 저장소에서 변경 사항을 가져오지만, 로컬 브랜치에는 적용하지 않는다. 로컬 상태를 유지하면서 원격의 최신 상태를 확인할때 사용한다.

-git pull
fetch와 merge를 결합한 명령어로 원격 저장소의 변경 사항을 가져옴과 동시에 이를 로컬 브랜치에 자동으로 병합한다.

5. reset --hard, push --force

-reset --hard
로컬에서만, 로컬 브랜체의 작업중인 내용일 되돌릴 때 유용하다.(원격에는 영향 X)

-push --force
원격 브랜치의 커밋 히스토리를 강제로 덮어쓴다. 로컬 브랜치의 히스토리와 원격 브랜치의 히스토리가 다를 때 사용된다.

6. .gitignore
프로젝트 루트에 .gitignore 파일을 생성하고, 무시할 파일 패턴을 작성하면 git이 버전 관리에서 제외할 파일 및 디렉토리를 정의한다.

7. 브랜치 이름 계층 구조
같은 계층 구조 내에서 브랜치 이름이 충돌할 수 있기 때문에 동시에 존재 할 수 없다.

8. Detached HEAD 상태
해당 상태는 HEAD가 브랜치가 아닌 특정 커밋을 직접 가리키고 있을 때 발생한다. 이 상태에서는 브랜치가 아닌 커밋에 대해 작업을 진행한다.

-Detached HEAD 상태에서 커밋
이 상태에서 생성한 커밋은 브랜치에 연결되어 있지 않기 때문에 HEAD가 다른 커밋을 가리키게 되면 이 커밋을 접근할 수 없게 될 수 있다.

-Detached HEAD 상태가 발생 할 수 있는 상황
1. 특정 커밋을 직접 체크아웃 할 때 커밋 해시를 사용하거나 특정 태그를 체크아웃 할 때 Detached HEAD 상태가 된다.

2. 브랜치가 없는 상태로 작업할 때

3. 태그 체크아웃
태그를 체크아웃할 때, 태그는 브랜치가 아니기 때문에 Detached HEAD 상태가 된다



## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
