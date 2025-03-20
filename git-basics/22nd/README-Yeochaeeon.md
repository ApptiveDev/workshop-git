# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
<!-- git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요. -->
- git 
    - 버전을 관리해주는 소프트웨어 
    - local에서 작동하며 로컬 저장소상의 코드의 변경사항을 추적하고 관리하는데 사용한다.
- github
    - git을 기반으로 한 원격(remote) 호스팅 웹 서비스이다. 
    - git 레포를 클라우드에 저장하고, 협업 및 코드 공유를 쉽게 할 수 있도록 돕는다.
    - github는 원격 저장소(remote repository)를 관리하는데 사용된다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
<!-- 위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다. -->
- Working Directory 
    - 현재 작업중인 파일들이 위치한 디렉토리. 파일을 수정 및 생성하는 곳.
    - Working Directory 에서는 파일을 tracked와 untracked로 구분한다. 
    > untracked 상태 
    - 저장소 내의 모든 파일은 untracked상태로 시작하며 untracked 상태의 파일들은 git이 코드 변경 이력을 추적하지 않음.
    > tracked 상태
    - tracked 상태의 파일들은 git에 의해 파일의 변경 이력이 추적된다. (ex.이전에 커밋된 파일)
- Git Add
    - `git add` 는 Working Directory 에서 변경된 파일을 **staging area** 로 이동시킨다.
    - 이 명령어를 사용하면 해당 파일을 tracked 상태로 등록한다.
    - tracked 상태의 파일들을 임시로 저장하는 공간.
    - `git add . `은 현재 디렉토리의 모든 변경 사항을 스테이징하는 명령어이다.
- Git Commit 
    - 스테이징 영역의 변경사항을 **로컬 레포**에 저장하는 명령어이다.
    - 커밋은 변경 사항의 스냅샷을 따서 Git 히스토리에 저장한다.
    - 커밋메시지를 함께 남겨 변경 사항에 대한 정보를 기록한다.
    - 이 단계는 **로컬**에서 이루어지며, 원격 레포에는 아직 반영되지 않는다.
- Git Push
    - 로컬 레포의 커밋을 **원격 레포로 전송**한다.
    - github에 변경 사항이 반영된다.
    - 로컬과 원격 간의 동기화를 해주는 역할을 한다.
- Git Merge 
    - 두 브랜치의 변경사항을 하나로 통합한다. 
- Git Fetch
    - 원격 레포의 최신 정보를 로컬로 가져온다.
    - 그러나 로컬 브랜치에 바로 반영하지는 않는다.
    - `git merge`나 `git pull`을 추가로 실행함으로써 변경사항을 반영할 수 있다.
- Git Pull
    - `git fetch`와 `git merge`를 합친 명령어

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
<!-- git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요. -->
- Branch
    - 브랜치 생성 후 전환 : `git checkout -b step-1-여채언`
    - 브랜치 전환 : `git checkout step-1`
- HEAD
    - HEAD는 현재 작업중인 커밋을 가리키는 포인터이다.
    - 보통 현재 브랜치의 최신 커밋을 가리킨다.
    - `git checkout`으로 브랜치를 전환하면, HEAD도 해당 브랜치로 이동한다.
## clone, init, origin
<!-- 리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지 -->
### `git clone` vs `git init`
> `git clone`
- 원격 레포지토리를 로컬로 복사하여 로컬 레포를 생성하는 명령어이다. 원격 레포의 모든 커밋 기록, 브랜치, 파일을 가져온다.
- 데이터를 로컬로 복사하면서, 원격 레포와 자동으로 연결된다.
> `git init`
- 현재 디렉토리를 새로운 git 로컬 레포로 초기화하는 명령어.
- 빈 레포를 생성하고, 원격 레포와의 연결은 설정되지 않은 상태로 시작한다. 
- init 으로 생성한 레포를 원격 레포와 연결하려면, 
`git remote add origin <원격레포URL>` 을 사용한다.
### Origin 이란?
- 원격 레포 (Remote Repository)의 기본 이름름
- origin은 원격 레포지토리의 URL을 가리키며, git push, git pull, git fetch 같은 명령어에서 사용됨.
- 원격 레포지토리의 브랜치는 origin/브랜치명 형식으로 표시됨(예: origin/step-0).
- 연결된 원격 저장소 확인 : `git remote -v`

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
<!-- reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다. -->
> `git reset`은 git에서 커밋 히스토리를 되돌리거나 변경사항을 취소하는데 사용되는 명령어이고 세가지의 타입이 있다.
- ` --soft`
    - HEAD를 지정한 커밋으로 이동시킨다. 하지만 스테이징 영역과 작업 디렉토리의 변경사항은은 그대로 유지된다.
    - 커밋만 취소하고 변경된 파일들은 그대로 스테이징 영역에 남아있다.- HEAD를 바로 직전 커밋으로 이동하고자 할 때 : `git reset  --soft HEAD^`
- ` --mixed` (default)
    - HEAD를 지정한 커밋으로 이동시키고, 스테이징 영역을 초기화하지만 작업 디렉토리의 변경 사항은 유지한다.
    - 즉, 커밋과 스테이징 상태를 되돌리지만 파일 자체의 변경 내용은 남아 있다.
- ` --hard`
    - HEAD를 지정한 커밋으로 이동시키고, 스테이징 영역과 작업 디렉토리까지 모두 해당 커밋 상태로 되돌린다.
    - 즉, 커밋, 스테이징, 작업 디렉토리의 모든 변경 사항이 삭제된다.
## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
<!-- Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요. -->
- Pull Request
    - 한 브랜치의 변경 사항을 다른 브랜치에 병합하기 위해 요청하는 기능
    - PR에서 병합하기 전에 코드리뷰, 테스트 등을 거치고 협업을 용이하게 한다.
    - 원격 레포에서 브랜치 간의 변경 사항을 비교하고 병합하는 과정을 제공한다.
- Merge
    - 두 브랜치의 변경 사항을 하나로 통합한다.
    > fast-forward Merge
    - 새로운 브랜치에만 commit이 있고 기준 브랜치에는 신규 commit이 없을 때.
    - 병합 커밋이 남지 않는다.
    - 충돌 가능성 없다. 
    ![fast-forward](https://codingapple-cdn.b-cdn.net/wp-content/uploads/2022/06/%EA%B7%B8%EB%A6%BC3-4.png)
    > 3-way Merge
    - 브랜치에 각각 신규 commit 이 1회 이상 존재하는 경우
    - 두개의 브랜치 코드를 합쳐 새로운 commit이 생성된다.
    ![3way](https://codingapple-cdn.b-cdn.net/wp-content/uploads/2022/06/merge1.png)

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
<!-- rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요. -->
- `git rebase`는 현재 브랜치의 커밋을 떼어내어, 지정한 브랜치의 최신 커밋 위에 재적용한다.
- rebase또한 병합 방법 중 하나이나, merge에 비해 커밋 기록을 한 줄로 깔끔하게 관리할 수 있다. 그러나 충돌 발생 가능성이 있다.
- 병합 커밋이 생성되지 않는다. 

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
<!-- git stash를 활용하는 방법에 대해 적어주세요.
 -->
- `git stash`는 작업 디렉토리와 스테이징 영역의 변경 사항을 임시로 저장하고, 작업 디렉토리를 깨끗한 상태로 되돌리는 명령어.
- 변경 사항을 스택(stack)에 저장하고, 작업 디렉토리와 스테이징 영역을 마지막 커밋 상태로 되돌린다.
> 활용 예시 
- branch-a 에서 파일을 수정했지만, 커밋하지 않고 다른 브랜치로 전환하고자 할 때 
```bash
# 현재 작업 중인 변경 사항 저장 후 작업 디렉토리를 깨끗하게 한다
git stash
# 스택에 쌓인 가장 최근의 변경 사항을 불러와 작업 디렉토리에 적용하고 스택에서 제거된다.
git stash pop
# 변경사항을 불러와 적용하지만, 스택에서 제거는 하지 않는다
git stash apply
# stash 목록을 확인한다 
git stash list
```
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
