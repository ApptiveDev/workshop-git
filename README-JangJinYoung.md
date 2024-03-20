# Git 기초

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
먼저 Git 과 Github에 대해서 알아보겠습니다.

Git
- 분산 버전 관리 시스템
- 로컬 및 원격 저장소 모두에서 작동하며, 개발자는 로컬에서 변경 사항을 커밋하고, 이것을 원격 저장소에 푸시 할 수 있다.

GitHub
- Git 저장소를 위한 클라우드 기반 플랫폼
- 코드 공유 및 협업을 위한 다양한 기능 제공

정리를 하자면 Git은 소프트웨어 개발에서 코드 버전 관리를 위한 도구이고, GitHub은 Git 저장소를 호스팅하고, 협업 기능을 제공하는 서비스

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  

Git의 흐름을 이해하기 위해 각 정의를 알아봅시다.

1. Working Directory
- 개발자가 실제 파일을 수정하고 있는 디렉토리
- 말 그대로 현재 작업 중인 디렉토리
- **add** 를 통해 수정된 파일을 Staging Area 에 저장한다.
2. Staging Area
- 파일들이 **commit** 되기 전에 대기하는 장소
3. Local Repo (HEAD)
- Local Repo : 개인(Local) 저장 공간
- HEAD : 현재 작업 중인 브랜치의 가장 최근 커밋을 가르키는 포인터
4. Remote Repo (MASTER)
- 원격 저장소 : 예를들어 GitHub
- MASTER : 프로젝트에서 주요 브랜치로써, 최종적인 또는 안정적인 버전의 코드가 유지되는 곳 (최근엔 MASTER를 사용하지 않고 main이라는 이름 사용)
- Local Repo 에서 **push** 를 통해 원격 저장소에 저장

git pull : 원격저장소에 있는 프로젝트의 변경사항을 그대로 로컬저장소에 옮겨와 자동으로 병합

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  

commit
- 프로젝트의 소스 코드에 대한 변경 내용을 기록하는 행위
  
branch
- 독립적인 개발 라인
- 생성 : git branch [branch 이름]
- 이동 : git checkout [branch 이름]
- 삭제 : git branch -d [branch 이름]

HEAD
- HEAD : 현재 작업 중인 브랜치의 가장 최근 커밋을 가르키는 포인터

## clone, init, origin
git **clone**
- 원격의 Git 저장소를 로컬에 복제할 때 사용하는 명령어

git **init**
- Local 에서 Git 저장소를 생성할 때 사용하는 명령어

origin
- 원격 저장소를 의미
- origin이란 이름은 관행적 이름이라서 변경 가능
- 설정 : git remote add origin [URL]

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  

reset
- 시간을 과거의 특성 사건(commit)으로 되돌린다.
- 현재를 없던것 처럼 한다.
  
hard
- 지정된 커밋으로 HEAD를 이동시키고, 스테이징 영역, 작업 디렉토리 모두를 지정된 커밋의 상태로 되돌린다.

mixed
- 지정된 커밋으로 헤드가 이동하고, 스테이징 영역도 초기화된다. 하지만 작업 디렉토리의 파일은 그대로 유지된다.
- 즉, 이전 커밋 이후의 변경사항들은 작업 디렉토리에 남아 있게 되고, 이를 다시 스테이징 할 필요가 있다.

soft
- 지정된 커밋으로 HEAD를 이동시키고, 작업 디렉토리는 변경되지 않는다.
- 즉 이전 커밋 이후의 모든 변경사항들은 스테이징 여역에 남게 된다.

명령어
- git reset --[hard, mixed, soft]

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request
- 한 브랜치의 변경사항을 다른 브랜치에 병합하기 전에 리뷰와 토론을 요청하는 기능
- 검토가 완료되면, Pull Request는 최종적으로 Merge 될 수 있다.

Merge
- 두 브랜치를 하나로 합치는 과정
- Fast-Forward Merge
  - 병합하려는 브랜치의 모든 커밋이 병합 대상 브랜치의 Head 커밋으로 이동되는 방식
  - 즉 별도의 병합 커밋을 생성하지 않고, 대상 브랜치의 포인터만 병합하려는 브랜치의 최신 커밋으로 옮깁니다.
- 3-Way Merge
  - 두 브랜치의 최신 커밋과 공통 조상 커밋을 사용하여 병합을 수행합니다. 
  - 필요한 경우 별도의 병합 커밋을 생성하여 두 브랜치의 변경사항을 통합합니다.
  - 병합 과정에서 충돌이 발생할 수 있으며, 사용자가 수동으로 충돌을 해결해야 할 수 있습니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase
- 두 개의 공통 Base를 가진 Branch에서 한 Branch의 Base를 다른 Branch의 최신 커밋으로 Branch의 Base를 옮기는 작업.

장점
- 공유 Branch의 최신 변경사항을 즉각 반영할 수 있다.
- commit History를 깔끔하게 관리 할 수 있다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash
- 현재 작업 디렉토리의 변경 사항을 일시적으로 저장하고, 깨끗한 작업 트리로 돌아갈 수 있게 해주는 기능입니다. 
- 즉 변경사항은 유지하고, 다른 Branch 로 이동하고 싶을때 사용하면 좋음
  
명령어
- git stash
- git stash apply [stash_id]
- got stash drop [stash_id]


## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
  - git rebase 명령어를 대화형으로 실행
  
- branch의 upstream이란? (`git push --set-upstream`)
  - 다른 사람의 저장소를 Fork 한 경우 나는 origin이 되고 fork 한 저장소가 upstream이 된다.

- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
