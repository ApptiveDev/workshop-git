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
  
### Git init, Git clone
- **git init**: 새로운 프로젝트 디렉토리를 Git 저장소로 만들거나 기존 프로젝트를 Git으로 변환할 때 사용된다. 이 명령어를 실행하면 해당 디렉토리 내에 Git 저장소가 초기화되며, 이후에 변경 사항을 추적하고 commit할 수 있게 된다.
    ```bash
    cd 내_프로젝트_디렉토리
    git init
    ```

- **git clone**: 원격 Git 저장소의 프로젝트를 로컬 시스템으로 복제할 때 사용된다. 이 명령어를 실행하면 원격 저장소의 모든 파일과 히스토리가 로컬 시스템으로 복제되어 프로젝트를 가져올 수 있다.
    ```bash
    git clone 원격_저장소_URL
    git init
    ```

### origin
- **origin**: Git에서 원격 저장소를 가리키는 별칭이다. 원격 저장소의 URL을 `origin`이라는 이름으로 참조할 수 있다.

- **origin 설정 방법**
  - `git clone` 명령을 사용하여 원격 저장소를 복사하면 Git은 자동으로 `origin`이라는 이름의 원격 저장소를 설정한다. 따라서 별도의 설정이 필요없다.

  - `git remote add` 명령으로 원격 저장소를 직접 추가한다면 아래의 명령어를 사용하여 `origin`이라는 이름의 원격 저장소를 설정할 수 있다.
    ```bash
    git remote add origin 원격_저장소_URL
    ```

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

### git reset
- reset 명령어는 대표적으로 commit을 `취소`하는 명령어이다. 또한 Staging 취소가 가능하다. 옵션에 따라 디테일한 설정이 가능하다.

- 옵션
  - `--soft`: commit 취소, Staging 상태 유지
  - `--mixed`: commit 취소, Staging 취소, local은 변경 상태로 유지(옵션이 없을 시 default로 설정된다)
  - `--hard`: commit 취소, Staging 취소, local 변경 상태 취소
- HEAD의 옵션 (위의 3가지 옵션 뒤에 사용한다)
  - `HEAD^`: 최신 커밋 취소
  - `HEAD~(수량)`: 수량에 숫자를 적으면 최근 커밋부터 해당 숫자까지 커밋 취소
- 사용 예시
    ```bash
    # 소프트 리셋
    git reset --soft HEAD^

    # 믹스드 리셋
    git reset HEAD^
    git reset --mixed HEAD^

    # 하드 리셋
    git reset --hard HEAD^
    ```

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
- **Pull Request**: 한 브랜치에서 작업한 코드를 메인 프로젝트에 병합(Merge)하기 위해 레포지토리 관리자나 다른 팀원에게 요청하는 과정이다.
  
  - 시나리오 
    - branch 생성 및 작업
    - 변경 사항 commit 및 push
    - pull request 생성
    - 팀원들과 토론 및 수정
    
- **Merge**: Pull Request를 통해 검토된 변경 사항을 실제로 적용하여 branch를 병합하는 것이다.
  - 종류
    - Fast-Forward: main branch에 신규 커밋이 없는 경우, 최신 커밋이 있는 branch를 main branch로 하는 것이다.
    ![fast-forward-merge](https://codingapple.com/wp-content/uploads/2022/06/%EA%B7%B8%EB%A6%BC3-4.png)

    - 3-Way Merge: branch마다 신규 commit이 1회 이상 있는 경우, merge 명령을 내리면 두 브랜치의 코드를 합쳐서 새로운 commit을 생성한다.
    ![3-Way-merge](https://codingapple.com/wp-content/uploads/2022/06/merge1.png) 

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
- **rebase**: 신규 branch의 시작점을 main branch의 최근 commit으로 옮긴 다음 fast-forward merge를 하는 것이다.
![rebase](https://codingapple.com/wp-content/uploads/2022/06/merge3.png)

- **유용한 때**
  - branch가 너무 많을 때, 간단한 branch들을 rebase하면 commit history를 훨씬 깔끔하게 정리할 수 있다.
  
- **rebase & merge 방법**
  - 새로운 브랜치로 이동한다.
  - `git rebase main`을 한다.
  - 그러면 branch가 main branch 끝으로 이동하는 데 그것을 fast-forward merge 하면 된다.
  ```bash
    # 새로운 브랜치로 이동
    git switch 새로운_브랜치
    
    # main으로 rebase
    git rebase main

    # main branch로 이동
    git switch main

    # fast-forward merge 적용 (신규 커밋이 있는 branch를 main branch로 적용)
    git merge 새로운브랜치
  ```

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
- **stash**: 현재 작업 중인 변경 사항을 일시적으로 저장하는 Git의 기능이다. 작업 중인 변경 사항을 commit하지 않고 보관할 수 있어서 다른 작업을 할 대 유리하다.

- **관련 명령어**
  - 현재 작업 중인 변경 사항을 일시적으로 저장
  ```bash
  git stash

  # staging 된 것이든 안된 것이든 추적중인 파일은 다 이동된다.
  # 파일들이 최근 commit 상태로 되돌아 간다.
  ```

  - 현재 stash 되어있는 코드 목록 출력
  ```bash
  git stash list
  ```

  - 보관했던 코드 다시 불러오기
  ```bash
  git stash pop
  
  # git stash 했던 코드가 여러개 있으면 가장 최근에 보관했던 코드부터 불러온다.
  ```

  - stash 삭제
  ```bash
  # 특정 stash 삭제
  git stash drop 삭제할_id

  # 모든 stash 삭제
  git stash clear
  ```

  - 일부 코드만 git stash 하기
  ```bash
  git stash -p
  
  # 파일을 훑어주면서 stash 할 지 의견을 물어보는데 y/n으로 잘 대답하면 된다.
  ```
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
- pull request는 레포지토리를 fork한 상태에서만 가능할까? 레포지토리를 clone만 한 상태에는 pull request가 불가능할까?