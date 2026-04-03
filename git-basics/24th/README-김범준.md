# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  local, remote와 연관지어 적어주세요.

- ### git
    로컬에서 사용하는 버전 관리 시스템,  
- ### github
    git기반으로 개발된 웹 클라우드 기반 시스템. github를 통해 코드를 공유하며 협업할 수 있음.  


## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  Git Merge, Git Fetch는 생략해도 됩니다.


- ### Working Directory
    실제로 파일을 수정하고 있는 공간.
- ### Staging Area
    Working Directory에서 수정한 파일 중 commit(기록)할 파일을 골라 저장하는 공간. 
    - `git add <파일명>`
- ### Local Repo
    local에 있는 git 저장소. staging된 파일을 `commit`을 통해 하나의 버전으로 묶어 repository 생성.
    - `git commit -m "메시지"` 
- ### Remote Repo
    클라우드 서버에 있는 git 저장소. commit한 repo를 `push`를 통해 업로드할 수 있음.
    - `git push origin <브랜치명>`

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- ### branch
    '가지' 라는 뜻 처럼 기존 흐름(main)에서 옆으로 나와 독립적인 작업을 할 수 있는 분기 역할을 함.
    - 목록 확인: `git branch`
    - 생성: `git branch <이름>`
    - 이동: `git checkout <이름>`
    - 삭제: `git branch -d <이름>`
-  ### HEAD
    현재 작업중인 위치를 나타내는 포인터.  
    보통 HEAD는 브랜치를 가리키고, 그 브랜치는 특정 커밋을 가리킴.  
    HEAD 기준으로 이동하는 법
    - `HEAD~`: 이전 커밋
    - `HEAD~3`: 3단계 전 커밋

    *Detached HEAD: HEAD가 브랜치를 통하지 않고 특정 커밋을 가리키는 것.  
    - 브랜치 이름이 아니라 커밋ID로 checkout할 때 발생. 이 상태에서 커밋하면 어떤 브랜치에도 속하지 않은 미아 커밋이 됨.
- ### *git checkout
    git 2.23 이후 checkout이 switch와 restore로 나뉨
    |기능|과거|현재|
    |---|---|---|
    |브랜치 이동|`git checkout <브랜치명>`|`git switch <브랜치명>`|
    |브랜치 생성/이동|`git checkout -b <이름>`|`git switch -c <이름>`|
    |브랜치 이동|`git checkout -- <파일명>`|`git restore <파일명>`|

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법 origin이란 키워드는 무엇인지, 어떻게 설정하는지

- ### git init vs clone
    | |`git init`|`git clone`|
    |---|---|---|
    |언제?|새 프로젝트를 시작할 때|github에 있는 기존 프로젝트를 가져올 때|
    |저장소 상태|빈 저장소|기존의 모든 파일 + 커밋 이력|
    |원격 연결|없음(remote add 해줘야 함)|자동으로 연결(기본 이름:origin)|
  
- ### origin 
    origin은 대표적으로 사용되는 원격 저장소의 별명. clone 하면 origin 이름으로 자동 등록 됨.
    - 별칭 등록: `git remote add <별칭> <원격저장소_주소>`
    - 연결된 주소 변경: `git remote set-url <별칭> <새로운_주소>`
    - 별칭 변경: `git remote rename <기존이름> <새이름>`
    - 별칭 삭제: `git remote remove <별칭>`

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  각 타입에 대해 작성 바랍니다.

- ### soft vs mixed vs hard
    - soft: head가 과거 커밋을 가리킴
    - mixed: soft + staging area를 해당 커밋 상태로 초기화함.
    - hard: mixed + working directory를 해당 커밋 상태로 초기화. 

    |옵션|Local Repo|Staging Area|Working Directory|특징|
    |---|---|---|---|---|
    |`--soft`|변경됨|유지됨|유지됨|커밋 이력만 지울 때|
    |`--mixed`|번경됨|번경됨|유지됨|add까지 취소, 파일은 살림|
    |`--hard`|변경됨|번경됨|번경됨|전부 삭제|

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- ### Pull Request
    내가 작업한 브랜치를 main 브랜치로 merge하기 위한 요청
- ### Merge
    1. Fast-Forward Merge
        - main에서 브랜치를 따서 작업할 동안 main에 아무런 커밋이 생기지 않았을 때
        - main 브랜치의 포인터가 새로운 브랜치로 이동만 함
        - 히스토리가 한 줄의 직선으로 남음
    2. 3-Way Merge
        - main에서 브랜치를 따서 작업할 동안 main에 변화가 생겼을 때(barnch가 갈라진 상태)
        - 두 브랜치의 공통 조상(base), 갈라진 브랜치 2개 총 3개를 비교해서 병합함.
        - 두 줄기로 갈라졌다가 합쳐지는 모양(다이아몬드형)

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- ### rebase
    - 브랜치의 시작 지점을 최신 커밋 뒤로 옮겨 '줄기를 다시 심는' 작업
    - Merge와 달리 합병 커밋을 남기지 않아, 히스토리를 깔끔한 직선으로 유지 가능
    - 이미 GitHub에 Push한 브랜치는 팀원들의 이력과 충돌할 수 있으니 절대 Rebase히면 안 됨.



## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- ### stash
    하던 작업을 잠시 '임시 저장소'에 넣어두고, 워킹 디렉토리를 깨끗하게 비울 때 사용함.(다른 브랜치로 잠시 이동할 때 등)
    - `git stash`: 현재 수정 사항을 스택에 저장하고 워킹 디렉토리를 비움
    - `git stash save "메시지"`: 이름을 붙여서 저장
    - `git stash list`: 리스트 확인
    - `git stash apply`: 가져오기
    - `git stash pop`: 가져오면서 스택에서 삭제
    - `git stash clear`: 전체 삭제


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
