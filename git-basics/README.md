# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git은 local에서 사용되는 버전 관리 시스템이고 github는 git으로 remote에서 관리하는 프로젝트를 올려둘 수 있는 사이트이다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working Directory는 사용자의 작업 공간으로 파일 수정 및 생성을, Staging Area는 임시로 저장하는 공간, Git Add는 작업 디렉토리에서 변경된 파일을 스테이징 영역에 추가,  Git commit는 깃이 코드의 변화를 기록하는 것, Git Push는 변경 사항을 원격 저장소에 업로드 하는 것, Git Pull은 원격 저장소에서 변경 사항을 가져와서 로컬 저장소에 병합하는 과정을 의미한다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

Commit은 Git 저장소에서 변경 사항을 기록하는 단위.
Branch는 독립적인 작업 영역을 만들어 여러 작업을 동시에 진행할 수 있게 해주는 것. HEAD는 현재 작업 중인 브랜치의 가장 최신 커밋. git checkout은 브랜치 전환/특정 커밋 상태로 작업 디렉토리 업데이트/새로운 브랜치 만들기에 사용

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git clone은 원격 저장소의 전체 내용을 복제하여 로컬 저장소를 만듦
git init은 빈 Git 저장소를 로컬에서 초기화함
origin은 기본 원격 저장소 이름, 원격 저장소를 추가하거나 변경할 때 사용함

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

soft: 지정한 커밋으로 HEAD를 이동하지만, staging area와 working directory는 변경하지 않음
mixed: HEAD를 이동시키고 staging area를 해당 커밋 상태로 리셋하지만 working directory는 변경하지 않음
hard: HEAD를 이동시키고, staging area와 working directory 모두를 지정한 커밋 상태로 완전히 리셋함.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Requset: 소스 코드 변경 사항을 다른 브랜치에 통합하기 위해 코드 리뷰와 승인을 요청하는 과정
Merge: 두 브랜치의 변경 사항을 통합하는 과정
Fast Forward Merge: 브랜치가 변경사항을 추가하지 않고 HEAD 포인터를 최신 커밋으로 이동시키는 병합 방식
3 Way Merge: 두 브랜치 간의 공통 조상을 기반으로 세 개의 커밋을 사용하여 병합을 수행하는 방식

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

Rebase: 지정한 브랜치의 변경 사항을 다른 브랜치의 최신 커밋 위에 덮어쓰는 방식으로 히스토리 재구성
더 깔끔하고 관리하기 쉬운 Git 히스토리 유지 가능

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

git stash: 현재 작업 중인 변경 사항을 임시로 저장하고, 다른 브랜치로 전환하거나 급한 작업을 처리한 후에 다시 원래 작업으로 돌아올 때 사용됨

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
