# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.
local, remote와 연관지어 적어주세요.

- git은 버전 관리 시스템이고 github는 git으로 관리하는 프로젝트를 올려둘 수 있는 사이트입니다.
- git은 로컬 저장소에서 소스 코드의 변경 사항을 추적하고 관리, 버전을 기록, 변경 사항 되돌리기, 다른 사람의 소스 코드와 합칠 수 있는 기능을 제공하는 도구입니다.
- github는 git을 사용해 로컬에서 관리한 코드르 인터넷 상에서 호스팅하여 다른 개발자와 공유하고 협업할 수 있게 합니다.
- local (로컬) : 사용자의 컴퓨터에 설치된 git 환경으로 로컬에서 코드를 작성하고, 변경 사항을 커밋하고 브랜치를 관리할 수 있습니다.
- remote (원격) : github는 프로젝트의 원격 저장소 역할을 하는데 git을 통해 원격 저장소와 로컬 저장소를 동기화할 수 있습니다. 로컬에서 작업한 내용을 원격 저장소에 푸시하면 다른 사람들의 변경 사항을 공유할 수 있습니다. 다른 사람의 작업을 나의 로컬로 가져오기 위해서는 원격 저장소에서 pull을 실행하면 됩니다.

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory (작업 디렉토리)
  - 사용자가 파일을 생성, 수정, 삭제하며 작업하는 로컬 환경입니다.
- Git Add
  - Working Directory에서 변경된 파일들을 Staging Area로 이동시킵니다.
- Staging Area
  - 커밋한 파일이 임시로 저장되는 단계입니다.
- Git Commit
  - Staging Area의 변경 사항을 로컬에 저장합니다.
- Local Repo (HEAD)
  - 사용자의 컴퓨터에 저장된 Git 저장소로, 커밋된 모든 변경 이력을 저장합니다.
- Git Push
  - 로컬 저장소에서 커밋된 변경 사항을 Remote Repo에 업로드합니다.
- Remote Repo (MASTER)
  - GitHub와 같은 원격 서버에 위치한 저장소로, 팀원들이 접근할 수 있는 공간입니다.

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- Commit
  - git에서 코드 변경 사항을 기록하는 단위
- Branch
  - 작업 흐름을 관리하는 기능, 저장소에 각자의 버전을 생성 가능
  - 하나의 저장소에서 다른 개발자들과 함께 작업할 때 브랜치를 통해 새로운 commit line을 만들어서 다른 작업 가능
    - 생성과 동시에 이동 : git checkout -b <new-branch>
    - 작업 완료 후 브랜치 삭제 : git checkout -b <new-branch>
  - HEAD : 현재 체크아웃된 브랜치를 나타냄, 가장 최근의 커밋을 가리킴
    - 커밋과 브랜치를 잇는 역할, 현재 작업 위치를 알려줌
  - Git Checkout : 특정 브랜치나 커밋으로 이동하여 해당 시점의 파일 상태를 확인하거나 작업 가능
    - 브랜치로 이동 : git checkout <브랜치이름>
    - 커밋 체크아웃 : git checkout <커밋해시>

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
  - git clone <원격 저장소 URL>: 원격 저장소를 복제하여 로컬에 동일한 저장소를 생성, 원격에 있는 프로젝트를 그대로 가져와서 로컬에서 작업
  - git init : 빈 로컬 디렉토리에 git 저장소를 초기화, 로컬에서 새로운 프로젝트를 시작하거나 기존 프로젝트를 git으로 관리하고자 할 때 사용
  - 차이점
    - clone : 이미 존재하는 원격 저장소를 로컬에 복제
    - init : 새로운 프로젝트 시작하거나 기존 프로젝트를 git으로 관리를 시작하고자 할 때
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
  -

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

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
