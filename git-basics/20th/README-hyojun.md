# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

- git
  버전관리 소프트웨어
  개인의 컴퓨에서 돌아간다.
- github
  git 소프트웨어를 지원하는 일종의 클라우드 서비스
  원격의 서버에 올라간다.

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory
  현재 작업하고 있는 영역, 작업을 하고 있는 프로젝트 디렉토리
  아직 추적(track)하고 있지 않은 상태
- Git Add
  working directory상의 변경 내용을 staging area 추가하기 위해서 사용하는 git명령어
- Git Commit
  의미있는 변경 작업들을 저장소에 기록하는 동작
  코드 변경 시점을 저장했다가 잘못된 동작을 할 경우 돌아갈 수 있게함
- Git push
  원격 저장소(remote repository)에 코드 변경분을 업로드하기 위해서 사용하는 git 명령어

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- branch
  독립적으로 어떤 작업을 진행하기 위한 개념
  각각의 브랜치는 다른 브랜치의 영향을 받지 않기 때문에, 여러 작업을 동시에 진행
- HEAD
  현재 체크아웃된 브랜치의 가장 최신 커밋
- checkout
  브런치 간의 switch를 하기 위한 명령어

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git init : 빈 git 저장소를 만들거나 기존 저장소를 다시 초기화하는 명령어
  > git init
- git clone : git 저장소를 복제해 새 디렉터리로 가져오는 명령어
  > git clone <원격 저장소 url>

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- --soft 옵션
  커밋 취소
  Staging 상태 유지(add)
- --mixed 옵션
  커밋 취소
  Staging 취소
  local은 변경 상태로 유지
- --hard 옵션
  커밋 취소
  Staging 취소
  local 변경 상태 취소

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request
  사용자가 원격 저장소에 Push하여 새로운 사항이 적용됬을 경우, 다른 사용자에게 푸쉬된 상황을 알리는 것
- Merge
  서로 다른 브랜치에서 작업한 내용을 합쳐야 하는 경우 사용
  - Fast-Forward방시
    branch간의 병합을 진행할 때 커밋이 생기지 앟고 merge 명령어를 실행하는
    branch의 Head Commit이 병합되는 branch의 Head Commit으로 이동
  - 3-Way Merge
    각 브랜치의 마지막 커밋 두 개와 공통 조상의 총 3개의 커밋을 이용하여 병합하는 방식
    서로 다른 브랜치가 동일 선상이 아닐 경우 사용

## rebase

![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase
  공통 Base를 가진 두 개의 Branch에서 한 Branch의 Base를 다른 Branch의 최신 커밋으로 Base를 옮기는 작업
- 유용한지
  내가 작업하던 브랜치에 main 브랜치 내용이 필요해서 적용시키고 싶을 때 사용

## stash

![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- stash
  작업중에 갑작스럽게 다른 작업을 진행해야 할 떄, 작업중인 사항을 잠시 치워두는 방법
  - git stash
    현재 적용된 commit 이후로 변경된 모든 사항들이 stash 공간으로 이동
  - git stash pop
    다른 브랜치의 commit에 stash로 따로 저장해둔 코드들을 적용
  - git stash -p
    -p 옵션을 통해서 hunk 기준으로 변경사항을 하나씩 확인하며 원하는 변홤나 stash에 담을 수 있음
  -

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