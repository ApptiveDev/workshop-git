# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.
local, remote와 연관지어 적어주세요.

### Git

- 버전 관리 시스템
- local(로컬 저장소, 사용자의 컴퓨터에 설치된 git 환경)에서 소스 코드의 변경 사항을 추적하고 관리, 버전을 기록, 변경 사항 되돌리기, 다른 사람의 소스 코드와 합칠 수 있는 기능을 제공하는 도구

### Github

- git을 사용해 로컬에서 관리한 코드를 인터넷 상에서 호스팅
- 프로젝트의 remote(원격 저장소) 역할

### Git과 Github

- git을 통해 local(로컬 저장소)와 remote(원격 저장소)를 동기화
- local에서 작업한 내용을 remote에 push하면 변경 사항을 공유 가능
- 다른 사람의 작업을 나의 local로 가져오기 위해서는 원격 remote에서 pull 실행

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- **Working Directory** (작업 디렉토리)
  : 사용자가 파일을 생성, 수정, 삭제하며 작업하는 로컬 환경
- **Git Add**
  : Working Directory에서 변경된 파일들을 Staging Area로 이동
- **Staging Area** : 커밋한 파일이 임시로 저장되는 단계
- **Git Commit** : Staging Area의 변경 사항을 로컬에 저장
- **Local Repo (HEAD)** : 사용자의 컴퓨터에 저장된 Git 저장소로, 커밋된 모든 변경 이력을 저장
- **Git Push** : 로컬 저장소에서 커밋된 변경 사항을 Remote Repo에 업로드
- **Remote Repo (MASTER)** : GitHub와 같은 원격 서버에 위치한 저장소

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

### Commit

- 코드 변경 사항을 기록하는 단위

### Branch

- git 저장소 내에서 작업 흐름을 *분리*하여 관리할 수 있는 가상의 포인터(각 브랜치는 특정 commit를 가리킴)
- 브랜치를 사용하면 메인 코드에 영향을 주지 않고 안전하게 기능 개발, 테스트, 버그 수정 진행 가능
- 특정 branch나 commit으로 이동하여 해당 시점의 파일 상태를 확인하거나 작업 가능
- 명령어
  - 생성 : `git branch <branch>`
  - 특정 브랜치로 이동 : `git checkout <branch>`
  - 생성과 동시에 이동 : `git checkout -b <branch>`
  - 작업 완료 후 브랜치 삭제 : `git checkout -d <branch>`
  - **HEAD** :현재 체크아웃된 브랜치

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
origin이란 키워드는 무엇인지, 어떻게 설정하는지

### git clone <원격 저장소 URL>

- 원격 저장소를 복제하여 로컬에 동일한 저장소를 생성
- **origin** : git에서 원격 저장소의 이름을 지정하는 기본 별칭
  - git clone을 할 때 원격 저장소의 url를 origin이라는 이름으로 설정

### git init

- 현재 로컬 디렉토리에 git 저장소를 생성
- 로컬에서 새로운 프로젝트를 시작하거나 로컬에 있는 기존 프로젝트를 git으로 관리하고자 할 때

### clone vs init

- clone : 이미 존재하는 원격 저장소를 로컬에 복제
- init : 새로운 프로젝트 시작하거나 기존 프로젝트를 git으로 관리를 시작하고자 할 때

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

### git reset

지정한 커밋으로 이동, 커밋 취소

1. --soft
2. --mixed(default)
3. --hard

| git reset             | Commit (커밋)                            | Staging Area (스테이징 영역)                           | Working Directory (작업 디렉토리) | 사용 시나리오                                                                      |
| --------------------- | ---------------------------------------- | ------------------------------------------------------ | --------------------------------- | ---------------------------------------------------------------------------------- |
| **--soft**            | 지정한 커밋으로 이동, 이후의 커밋을 취소 | 변경된 파일이 스테이징 상태로 유지                     | 변경된 파일이 그대로 남아 있음    | 커밋을 되돌리되 파일 변경 사항은 보존하고 싶을 때                                  |
| **--mixed (default)** | 지정한 커밋으로 이동, 이후의 커밋을 취소 | 스테이징 영역 초기화 (변경 사항이 스테이징에서 제거됨) | 변경된 파일이 그대로 남아 있음    | 커밋과 스테이징을 초기화하고 파일은 그대로 두고 싶을 때                            |
| **--hard**            | 지정한 커밋으로 이동, 이후의 커밋을 취소 | 스테이징 영역 초기화                                   | 변경된 파일이 모두 삭제됨         | 모든 변경 사항을 완전히 제거하고 지정한 커밋 상태로 돌아가고 싶을 때 (복구 불가능) |

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

### Pull Request(PR)

- 원격 저장소 서비스에서 사용
- 특정 브랜치의 변경 사항을 다른 브랜치에 반영하도록 요청
- 팀원들이 코드 변경 사항을 검토하고 피드백 제공 가능

### Merge

- 두 브랜치의 변경 사항을 하나의 브랜치로 통합
- PR을 통해 검토된 브랜치를 메인 브랜치에 반영할 때 주로 사용
- 타입

1. **Fast-Forward Merge**
   - 두 브랜치 간의 변경 사항이 직선 경로로 연결
   - 한 브랜치가 다른 브랜치에서 파생된 이후, 단순히 현재 브랜치의 포인터(HEAD)를 앞으로 이동
2. **3-Way Merge**
   - 두 브랜치 간의 병합이 직선 경로가 아닌 서로 독립적으로 커밋이 이루어졌을 때 사용
   - 공통 조상와 각 브랜치의 최신 커밋, 세 가지 지점을 비교하여 병합
   - 새로운 병합 커밋 생성
   - 충돌 발생 가능

## rebase

![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

### Rebase

- 브랜치의 변경 사항을 다른 브랜치의 변경 사항 앞이나 뒤로 재배치
- 두 브랜치의 커밋 기록을 하나로 합쳐 깔끔한 직선의 커밋 이력 만들 수 있음
- 상황
  1. 깔끔한 커밋 히스토리를 유지하고 싶을 때
  2. 브랜치를 최신 상태로 유지하고 싶을 때
     - 기능 개발 중에 main 브랜치가 업데이트된 경우
     - 최신 커밋을 자신의 브랜치 위로 재적용 가능
  3. 커밋 충돌을 미리 해결하고 싶을 때
     - 충돌을 커밋별로 나누어 처리 가능

## stash

![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

### stash

- Working Directory와 Staging Area에서 작업 중인 변경 사항을 임시로 저장
- 변경 사항이 커밋되지 않은 상태에서 다른 브랜치로 전환하거나 다른 작업을 수행 가능

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
