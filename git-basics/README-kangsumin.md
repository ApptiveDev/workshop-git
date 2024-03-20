# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

### Git과 GitHub의 의미
- **Git**: local에서 소스 코드의 변경 사항을 추적하고, 버전을 관리하는데 사용되는 도구이다.
  
- **GitHub**: Git 저장소를 클라우드(원격 서버)에 호스팅하고, 여러 사용자가 협업할 수 있게 하는 서비스이다. GitHub를 사용하면 로컬 시스템뿐만 아니라 원격 서버에도 Git 저장소를 보유할 수 있다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
- **Working Directory**: 현재 개발자가 작업하는 공간으로 현재 프로젝트의 소스코드 및 파일이 저장되어 있는 로컬 시스템의 디렉토리이다. Git은 여기에 있는 파일들의 변경사항을 추적하고 관리한다.
  
- **Git Add**: Working Directory에 있는 변경 사항 중 일부를 Staging Area에 추가하는 명령이다. 이는 Git에게 해당 변경 사항을 다음 commit에 포함하는 것임을 알려준다.
  
- **Git Commit**: Staging Area의 변경 사항을 로컬 저장소에 저장하는 명령어이다. 이는 변경 사항을 영구적으로 기록하고, commit 메시지와 함께 변경 사항의 스냅샷을 생성한다.
  
- **Git Push**: 로컬 저장소에 있는 commit을 원격 저장소(예: GitHub)로 전송하는 명령이다. 이는 다른 개발자들과 변경 사항을 공유하거나, 백업을 위해 사용된다.
  
- **Git Merge**: 두 개의 다른 branch를 병합하는 명령어이다. branch는 개발의 흐름을 나누어 관리하기 위한 독립적인 작업 공간으로 사용되는데, 두 branch의 변경 사항을 합치는 작업을 수행한다.
  
- **Git Fetch**: 원격 저장소에서 최신 변경사항을 가져오는 명령어이다. 이는 로컬 저장소에는 변경 사항을 적용하지 않고, 단순히 원격 저장소의 상태를 확인하는 역할이다. 이후에 필요에 따라 Git Merge나 Git Pull과 함께 사용하여 로컬 저장소에 변경 사항을 반영할 수 있다.
  
## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- **commit**: Git에서 변경 사항을 영구적으로 기록하는 작업이다. 각 commit은 파일의 변경 사항을 스냅샷으로 기록하고, 해당 지점의 상태를 저장한다. commit을 통해 이전 상태로 rollback하거나 변경 이력을 추정할 수 있다.
  
- **branch**: Git에서 병렬적인 작업을 수행하기 위한 개념이다. 각 branch는 독립적인 작업 경로를 나타내며, 개발자는 여러 branch를 생성하여 동시에 여러 기능을 개발할 수 있다.
  
- **HEAD**: 현재 작업 중인 branch의 가장 최근 commit을 가리키는 포인터이다.
   
- **Git checkout**: Working directory의 HEAD와 branch 간의 이동을 담당하는 명령어이다.

### branch 관련 명령어

- **branch 생성**:
    ```bash
    # 새로운 브랜치 생성
    git branch <branch_name>

    # 새로운 브랜치 생성 후 해당 브랜치로 이동
    git checkout -b <branch_name>
    ```

- **branch 삭제**:
    ```bash
    # 브랜치 삭제
    git branch -d <branch_name>

    # 강제로 브랜치 삭제 (변경 사항이 포함되지 않은 경우)
    git branch -D <branch_name>
    ```

- **branch 이동**:
    ```bash
    # 특정 브랜치로 이동
    git checkout <branch_name>

    # 새로운 브랜치 생성 후 해당 브랜치로 이동
    git checkout -b <branch_name>
    ```

- **branch 목록 보기**:
    ```bash
    # 브랜치 목록 보기
    git branch
    ```

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
git clone:
git init:
origin:

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
reset:

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
Pull Request:
Merge:

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
rebase:

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
git stash:

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
