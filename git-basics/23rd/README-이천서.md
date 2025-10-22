# Git 기초

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

- Git: 분산 버전관리 도구, Local에서도 전 기능 동작.
- GitHub: Git 저장소를 호스팅하고 PR·리뷰·권한·CI 등을 제공하는 Remote 서비스 중 하나.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory: 실제 파일이 있는 작업 폴더. 수정·생성·삭제 발생.
- Git Add: 작업 파일을 Staging Area에 올림.
- Git Commit: Staging Area의 스냅샷을 로컬 저장소에 새 커밋으로 기록.
- Git Push: 로컬 브랜치의 새 커밋을 원격 저장소로 전송.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- commit: 시점 스냅샷 + 부모 참조 + 메시지. 불변.
- branch: 어느 커밋을 가리키는 이동 포인터. 새 커밋이 생기면 브랜치 참조가 앞으로 이동.
- HEAD: 현재 체크아웃한 브랜치를 가리키는 특수 포인터.

주요 명령
- git branch: 목록
- git branch <new>: 생성
- git switch <name>: 이동
- git switch -c <new>: 생성+이동
- git branch -d <name>: 병합된 브랜치 삭제
- git branch -D <name>: 강제 삭제

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git clone <url>: 원격 저장소를 통째로 복제하여 새 폴더를 만들고, 기본 원격 별칭을 origin 으로 자동 등록.
- git init: 현재 폴더에 빈 Git 저장소 생성. 기존 코드에서 버전관리 시작할 때 사용.
- origin: 가장 일반적으로 쓰는 원격 저장소 별칭. 변경 가능.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- --soft: 브랜치 포인터만 되돌림. 스테이징은 유지, 워킹 디렉터리도 유지.
- --mixed: 브랜치 포인터 이동 + 인덱스 초기화. 워킹 디렉터리의 파일 변경은 남음.
- --hard: 브랜치 포인터 이동 + 인덱스/워킹 디렉터리 모두 되돌림. 로컬 변경 완전 폐기.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- PR: 한 브랜치의 변경을 다른 저장소/브랜치로 병합해달라고 요청. 코드리뷰, CI, 승인 규칙 등을 통과한 뒤 Merge 수행.

Merge 유형
- Fast-Forward: 대상 브랜치가 소스 브랜치의 조상일 때 참조만 앞으로 이동.
- 3-Way Merge: 히스토리가 분기되어 공통 조상이 존재하면 새 머지 커밋을 만들며 통합.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase: 브랜치의 기반을 다른 커밋으로 바꾸면서, 내 커밋들을 다시 적용해 직선 히스토리를 만드는 작업.

- 리뷰 전 커밋 정리
- 오래된 분기를 최신 기반으로 업데이트하여 FF 머지 가능하게 만들 때
- 히스토리를 깔끔하게

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- git stash : 현재 작업 변경(스테이지드/언스테이지드)을 임시로 치워 브랜치를 바꾸거나 풀/리베이스 등을 안전하게 수행.

- 부분 적용
- 인덱스 유지 테스트
- 새 브랜치로 바로 빼기
- 특정 경로만 스태시

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
