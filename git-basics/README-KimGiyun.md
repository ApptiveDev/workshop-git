# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  

### git
- 분산형 버전관리시스템
- 소스 코드의 변경 사항을 체크하여 버전 관리에 유용하고, 다수 간 협업할 때 사용
- 로컬(local)과 원격(remote), 두 저장소에서 모두 작업할 수 있으며, 해당 작업물을 원격 저장소에 푸시하는 기능 탑재.

### github
- **Git**을 기반으로 하는 웹 기반 클라우드 플랫폼
- 소스 코드를 저장하는 원격 저장소
- 프로젝트 협업을 위한 다양한 도구 및 소셜 네트워크 기능 탑재

#### 따라서
- Git은 소스 코드 버전 관리를 위한 소프트웨어
- Github는 Git을 호스팅하며, 협업을 위한 편의 서비스를 제공하는 플랫폼.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

### 1. Working Directory
 - 실제로 파일을 생성하고 수정하는 공간.
 - 개발자가 현재 작업 중인 공간. (.git 폴더 제외)
 - 깃의 추적(tracked) 개념.
    + 필요한 파일만 추적하여 깃의 시스템 부하를 줄이고, 효율적인 관리를 가능하게 함.
    1. untracked
        + Working Directorty에 새로 생성된 파일은 모두 추적되지 않음(untracked) 상태.
        + untracked 상태의 파일은 Git에서 코드 변경 이력을 추적하지 않음.
    2. tracked
        + 추적되지 않는 상태의 파일들을 별도로 명령어 ($git add file name)를 이용해 추적(tracked) 상태로 변경하여 관리.
        + tracked 상태의 파일은 Git에서 코드 변경 이력을 추적함.

### 1-1. Git Add
- git add 명령어는 다음 변경(commit)을 기록할 때까지 변경분을 모아놓기 위해서 사용함.
- git commit 전까지는, git add 명령어를 실행해도 Git 저장소의 변경 이력에 어떤 영향도 주지 않음
- git add -p를 이용해 변경사항 확인 가능.
- rm--cached 파일명을 통해서 add 이전 상태로 복구 가능.

### 2. Staging Area
 - Working Directory에서 제출된 tracked 파일을 임시 저장 및 관리하는 공간.
 - Working Directory와 실제 저장 공간(Repository) 사이에 있는 영역.
    + 파일 컨텐츠를 직접 갖고 있는 것이 아닌, commit하려는 파일의 track 상태 정보만 기록함.
- commit을 빠르게 하기 위해 사용.
- stage / unstage 상태 개념
    + stage 내 파일은 위 두 상태로 구분.
    + stage 상태 확인 명령어는 $git status
    1. stage 상태
        + stage 영역 내 모든 파일은 tracked 파일.
        + stage 영역 내에서 나간 파일은 untracked 파일.
        + Git이 최종 변경 이력을 추적하려면, 해당 파일의 최종 상태가 stage 상태여야 함.
    2. unstage 상태
        + 파일 내 변경 이력이 있을 시, 해당 파일은 unstage 상태. (Working Directory 내 파일 =/= stage 내 파일일 시)

### 2-1. Git Commit
- 코드 변경 사항을 local repository에 영구적으로 기록하는 행위
- 프로젝트의 특정 시점을 안전하게 저장하고, 필요할 때 언제든지 그 시점으로 돌아갈 수 있음.
    + 기록을 남길 수 있어, 협업을 효율적으로 조율 가능.
        + 기록 내용 : 고유 ID, 변경 내역, 저자 정보, 설명(메시지)
- staging 영역에 add 된 파일을 commit하는 것.
- git log를 통해 commit 내역 확인 가능.

### 3. Local repository
- 파일이 저장되는 개인 전용 저장소이며, 주로 개인이 소유한 PC 등이 local repository
    - 내 PC에서 작업 == local에서 작업.
    - HEAD는 작업 중인 branch의 최신 commit을 가리키는 포인터
- Staging Area에서의 작업물을 local repository에 옮겨 하나의 버전을 생성.
- git log 명령어로 버전(히스토리)을 조회
- remote repository의 파일을 local로 pull할 수도 있음

### 4. Remote repository
- 파일이 저장되는 원격 저장소이며, 주로 Github 등의 클라우드 서버.
- local에서 작업한 파일을 remote repository에 push하여 코드를 공유 및 협업 가능.

### 4-1. Git Push
- local repository에 commit 된 작업 내용을 remote로 push할 때 사용하는 명령어.
- 협업을 위해 소스 코드의 최신 버전을 팀원 간 공유하거나, 백업하는 용도로 사용.

### 4-2. git fetch
- Remote Repository의 최신 변경 사항을 Local로 가져오는 명령어.- 다른 개발자들이 Remote Repository에 업로드한 코드 변경 사항이 있을 때, 이를 Local로 가져오기 위해 사용. 
    + git merge, git rebase로 remote에서의 변경 내역을 현재 local branch의 작업물에 반영.
    + rebase는 커밋 이력이 재정렬되므로 주의.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

### Branch
- 주 흐름에서 벗어나, 독립적으로 어떤 작업을 진행하기 위한 가상의 작업환경.
- 협업 시, 상호 간 영향을 주는 걸 방지하기 위해, 팀 프로젝트에서 많이 활용.
    + 서로에게 영향을 주지 않고 내용을 모두 기록하기 위함.
- 명령어

``` bash
    # 생성
    git branch <branch명>
    # 이동
    git checkout <branch명> // branch 간 switch
    # 삭제
    git branch -d <branch명>
```

### HEAD
- 현재 작업 중인 branch의 최신 commit을 가리키는 포인터.
- 협업 시 어느 시점의 코드로 작업 중인지 알 수 있음.

### Git Checkout
- 저장소에서 특정 시점의 commit이나 branch로 돌아가고 싶을 때 사용
- branch 간 switch 할 때 사용

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

### Git Clone
- 기존의 Remote repository로부터 Local로 프로젝트를 복제하는 것.
    - 소스 코드, 히스토리, branch 등 모든 데이터가 복제되어 local에 저장됨.
```bash
   git clone <프로토콜> <프로젝트 주소.git> 
```
- Local, HTTP, SSH, Git 4가지 방식의 프로토콜 제공.

### Git Init
- Local에서 새로운 Git 저장소(repository)를 생성/초기화하고 프로젝트 버전 관리할 때 사용.
    - 버전 관리를 위한 .git 파일을 생성함.

#### Git Clone vs Git Init
- git clone은 기존 프로젝트를 local로 복사해올 때 사용. clone 시 init 할 필요 X.
- git init는 프로젝트 자체를 처음부터 시작할 때 사용. 

### origin
- remote repository의 일반적인 별칭. 
    - clone 시 별칭이 origin으로 자동 등록됨.
    - 별칭은 중복 사용 불가능.
```bash
    # 연결
    git remode add <별칭> <remote repository URL>
    # 별칭 변경
    git remode rename <변경 전 별칭> <변경 후 별칭>
    # 연결 내역 확인
    git remote -v
    # 삭제
    git remote rm <별칭>
```

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
### reset
- commit이나 staging을 취소할 때 사용하는 명령어.
    - 옵션에 따라 설정이 달라짐.
```bash
    # 직전 commit으로 되돌림.
    git reset HEAD^
    # 여러 commit 이전으로 되돌림.
    git reset HEAD~<number> or git reset <hash> 
        # 1, 2, 3 commit이 있을 시 number가 2라면, 
        # 2, 3번째 commit을 건너뛰고 commit 1으로 되돌림.
```
#### reset option
1. --soft : commit을 취소하고, staging 상태를 유지할 때 사용.
    - staging area에 남아있기에 다시 commit 가능.
2. --mixed : commit을 취소하고, staging도 취소하나, local(Working Directory)은 변경 상태를 유지할 때 사용.
    - Working Directory에 수정 내역이 남아, 수정 후 다시 Staging 가능.
3. --hard : commit, staging, local(Working Directory) 변경 내역을 전부 취소할 때 사용.
    - 다시 이전 상태로 되돌릴 수 없기에 사용에 신중을 기해야 함.
    - git reset --hard <hash>

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
### Pull Requset
- 

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
