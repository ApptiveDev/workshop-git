# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
- Git : 버전관리 시스템, 소스코드 변경 내역을 추적하고 협업을 용이하게 해준다.
	- 내 컴퓨터에 저장된 Local Git 저장소
- Github : Git을 이용한 프로젝트 저장 및 공유가 가능한 웹 기반 플랫폼 
	- 원격 서버에 저장된 Remote Git 저장소

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
1. Working Directory
2. git add : stage영역에 추가
3. git commit : stage영역 파일들을 커밋
4. git push : commit 내역을 원격 저장소로 푸쉬

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
- Branch : Git에서 독립적으로 작업할 수 있는 가지
	- 기본적으로 main 브랜치에서 작업하지만, 새로운 기능 개발 등을 위해 새로운 브랜치를 만들 수 있음
	- git checkout으로 특정 브랜치나 커밋으로 이동 가능
- Head : 현재 작업중인 브랜치를 가리키는 포인터

### 명령어
- `git branch 브랜치명` : 브랜치 생성
- `git checkout 브랜치명` : 브랜치 이동
- `git branch -d 브랜치명` : 브랜치 삭제

## clone, init, origin
- `git clone`: 원격 저장소를 로컬로 복사합니다. 주로 Github 등에서 프로젝트를 받을 때 사용
- `git init`: 새로운 Git 저장소를 로컬에서 초기화할 때 사용
- `origin`: 원격 저장소의 기본 이름입니다. git remote add origin <url> 명령어로 설정 가능


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
- `--soft`: 최근 커밋을 취소, 변경 사항을 스테이징
- `--mixed`: 최근 커밋을 취소, 변경 사항을 스테이징에서 제외
- `--hard`: 최근 커밋을 취소, 모든 변경 사항을 삭제

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
- Pull Request: 다른 사람이 자신의 브랜치를 본 프로젝트에 병합해달라고 요청하는 과정
- Merge: 브랜치를 병합
	- Fast-Forward: 브랜치 간에 커밋 기록이 변동 없이 일직선으로 이어질 때 사용
	- 3-Way Merge: 두 브랜치 간에 충돌이 발생했을 때, 세 방향의 커밋을 비교해 병합


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
- 커밋을 한줄로 정리
- 여러 브랜치를 합칠때 충돌없이 작업 이력을 직렬화

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
- 현재 작업내용을 임시로 저장하고 워킹 디렉토리를 비움
- `git stash apply`로 다시 작업 복원가능

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
