# Git 기초

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  

Git은 분산형 버전 관리 시스템. 로컬에서 코드의 변경 사항을 추적하기 위해 사용하는 도구이다.

GitHub는 Git을 기반으로 한 원격 저장소 호스팅 서비스이다.

Local : 사용자 컴퓨터에서 동작하는 Git저장소
Remote : GitHub, GitLab, Bitbuchet과 같은 원격 저장소.

로컬에서의 Git 저장소롤 원격 저장소에 push해서 공유하는 형태.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  

### Working Directory
소스 코드가 실제로 존재하는 작업 공간

### Git Add
git add를 사용하면 변경된 파일을 Staging Area로 올린다.

### Staging Area
커밋 전 변경 사항을 저장하는 공간.

### Git Commit
git commit -m ""형식. 변경 사항을 로컬 저장소에 저장한다.

### Git Push
git push origin <브랜치> 형식. 로컬에서 커밋된 변경 사항을 원격 저장소에 업로드한다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
### Branch
독립적인 작업 공간.

### HEAD
현재 작업 중인 브랜치를 가리키는 포인터

### 관련 명령어
git branch <> : 새 브랜치 생성
git checkout <> : 브랜치 변경
git switch <> : 브랜치 변경
git branch -d <> : 브랜치 삭제
git merge <> : 현재 브랜치에 지정된 브랜치 병합

## clone, init, origin
1. git clone
원격 저장소를 복제해서 로컬 저장소를 생성한다.

2. git init
새로운 Git 저장소를 로컬에서 초기화한다.

3. origin
Git에서 원격 저장소의 기본 이름. git remove add origin <url>명령어로 설정 가능.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
1. git reset --soft
HEAD를 이전 커밋으로 이동하지만, 변경 사항은 Staging Area에 남긴다.

2. git reset --mixed
HEAD를 이전 커밋으로 이동하고 Staging Area를 초기화하지만, Working Directory에는 변경 사항이 남는다.

3. git reset --hard
HEAD를 이전 커밋으로 이동하고, Staging Area와 Working Directory 모두 초기화한다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
1. Pull Request(PR)
협업할 때 다른 브랜치의 변경 사항을 병합하기 전에 검토 요청

2. Merge
(1) Fast-Forward Merge
변경 사항이 직선적인 경우 빠르게 병합된다.

(2) 3-Way Merge
서로 다른 브랜치의 변경 사항을 병합할 때 공통 조상을 고려해서 새로운 커밋을 생성한다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
브랜치를 다른 브랜치의 최신 상태로 업데이트 하는 방법이다.
git rebase <브랜치> 형식.
커밋 히스토리를 깔끔하게 유지할 때 유용하다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 사용하면 현재 작업 내용을 임시로 저장하고 나중에 복원할 수 있다.

git stash save "메시지" : 변경사항 임시 저장
git stash list : 저장된 stash 목록 확인
git stash apply : 마지막 stash 복원
git stash drop : stash 삭제

## Advanced
- GitHub Flow : 메인 브랜치에서 작업 후 바로 배포
- Git Flow : feature, develop, release 브랜치를 활용해서 관리

- `git rebase --interactive`란?
커밋을 합치거나 수정하는 데 사용

- branch의 upstream이란? (`git push --set-upstream origin <브랜치>`)
기본 원격 브랜치를 설정한다.

- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
다른 사용자의 저장소 복제해서 독립적으로 개발할 때 사용.

- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
git fetch : 원격 저장소의 변경 사항을 가져오기만 하고 병합하지 않는다.
git pull : 원격 저장소의 변경 사항을 가져오고 자동 병합.

- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
제외시킬 파일 지정

- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지.
Git에서 브랜치 자체를 디렉토리로 관리하기 때문이다.

- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지
브랜치 없이 특정 커밋을 Checkout한 상태. 이 상태에서 커밋하면 브랜치 없어서 사라질 수 있음. 이런게 왜 생기는거지

git log --oneline --graph --decorate --all
커밋 로그 확인

## Questions
1. git reset --soft
HEAD를 이전 커밋으로 이동하지만, 변경 사항은 Staging Area에 남긴다.

2. git reset --mixed
HEAD를 이전 커밋으로 이동하고 Staging Area를 초기화하지만, Working Directory에는 변경 사항이 남는다.
이 둘의 차이가 체감이 잘 안됩니다.

3. detached HEAD 발생상황

4. fetch에서 변경사항은 가져오는데 병합하지 않는다는게 잘 이해 안됨.