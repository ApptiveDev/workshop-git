# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
<!-- git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요. -->

- Git
    - 로컬에서 코드를 버전 관리하는 시스템
    - 개발자가 자신의 컴퓨터에서 코드의 이력을 관리하고 협업할 수 있는 도구

- GitHub
    - 원격 저장소를 제공하는 서비스
    - Git을 사용하는 프로젝트들을 온라인에서 관리하고 공유한다.


- Local
    - 내 컴퓨터에서 실행되는 Git 저장소
    - 로컬에서 코드 변경 사항을 추적하고 버전 관리를 한다.

- Remote
    - Github와 같은 원격 서버에 있는 저장소
    - 로컬에서 작업한 내용을 업로드하거나 다른 사람의 변경 사항을 받아올 때 사용된다.





## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
<!-- Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다. -->

- Git Merge 
    - 실제로 파일을 작업하는 디렉토리

- Git Add 
    - 작업 디렉토리에서 변경된 파일을 Git의 stage에 올리는 작업
    - `git add` 명령어로 특정 파일 또는 전체 파일을 스테이징할 수 있다.

- Git Commit
    - 스테이징된 파일을 로컬 저장소에 저장하는 과정

- Git Push
    - 로컬 저장소의 변경 사항을 원격 저장소에 업로드하는 작업



## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
<!-- branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요. -->

- Branch 
    - 서로 다른 작업 흐름을 나누기 위한 git의 기능
    - 여러 작업을 독립적으로 진행할 수 있으며, 각 브랜치에서 작업한 내용은 나중에 합칠 수 있다.
    - `git branch <브랜치명>` : 브랜치 생성
    - `git checkout <브랜치명>` : 브랜치 이동
    - `git branch -d <브랜치명>` : 브랜치 삭제


- Head
    - 현재 작업 중인 브랜치나 커밋을 가리키는 포인터
    - `git checkout` 명령어로 HEAD를 다른 브랜치나 커밋으로 이동시킬 수 있다.



## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
<!-- - git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지 -->

- `git clone`
    -  원격 저장소를 로컬에 복제하는 명령어
    - `git clone <원격 저장소 URL>`로 GitHub 등의 원격 저장소를 복제할 수 있다.
- `git init` 
    - 새 프로젝트를 시작할 때 로컬에서 Git 저장소를 초기화하는 명령어
    - `git init`을 실행하면 현재 디렉토리에 `.git` 폴더가 생성되어 Git으로 버전 관리가 시작된다.
- `origin`
    - 기본적인 원격 저장소 이름
    - `git remote add origin <원격 URL>`로 설정한다.



## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
<!-- 각 타입에 대해 작성 바랍니다. -->
- `--soft`: 가장 최근 커밋을 취소하지만, 스테이징된 상태는 유지한다.
- `--mixed`: 커밋을 취소하고 스테이지에서도 제거하지만, 작업 디렉토리에는 그대로 남아있다.
- `--hard` : 커밋, 스테이지, 작업 디렉토리 모두를 취소하여 완전히 이전 상태로 되돌린다.


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
<!-- 특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요. -->
- `Pull Request` : GitHub에서 새로운 브랜치에서 작업한 내용을 다른 브랜치로 병합하기 전에 코드 리뷰를 요청하는 절차
- `Merge` : 브랜치를 병합하는 작업
    - `Fast-Foward` : 다른 브랜치와 커밋 히스토리가 이어질 때, 단순히 HEAD만 앞으로 이동하는 방식
    - `3-Way Merge` : 두 브랜치가 다른 커밋 히스토리를 가질 때, 공통 조상 커밋을 기준으로 세 개의 커밋을 비교하여 병합한다.



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