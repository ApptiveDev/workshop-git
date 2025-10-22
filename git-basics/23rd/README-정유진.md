# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git은 "local 파일"의 변경 사항을 추적하고 관리하는 분산 버전 제어 시스템이고,
github는 "remote 저장소"에서 git을 기반으로 프로젝트를 인터넷에서 관리할 수 있는 온라인 플랫폼이다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : 사용자가 작업하는 로컬 파일들이 위치한 디렉토리이다.
- Git Add : Working Directory에서 변경된 파일들을 Staging 상태(커밋 준비 상태)로 올린다.
- Git Commit : Staging 상태 파일들의 변경 사항을 로컬 저장소에 새 버전으로 기록한다.
- Git Push : 로컬 저장소에서 원격 저장소(GitHub)로 변경 사항을 업로드한다.
- Git Pull : 원격 저장소의 변경 사항을 가져와, 로컬 저장소의 작업과 합친다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- Commit: 변경 사항을 기록해놓은 것으로, 각 commit은 고유한 해시값인 커밋 번호를 가진다.
- Branch: 독립적인 개발 라인으로, 기능 개발/버그 수정을 다른 작업과 분리하여 안전하게 진행하게 한다.
- HEAD: 특정 branch의 가장 최신(마지막으로 수행된) commit
- git checkout [브랜치명]: 특정 브랜치/커밋으로 전환
- git switch -c [새로운 브랜치명]: 새 브랜치를 생성 후 해당 브랜치로 이동
- git branch [새로운 브랜치명]: 새로운 브랜치를 생성하지만 그 브랜치로 전환하지는 않는다.
- git branch -d [브랜치명]: 로컬 브랜치 삭제
- git push origin --delete [브랜치명]: 원격 저장소의 브랜치 삭제

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git init : 현재 디렉토리를 Git 로컬 저장소로 만든다.
- git clone : 원격 저장소의 정보들을 내 로컬시스템으로 복제해온다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- git reset --soft [커밋ID] : 지정한 커밋으로 HEAD만 이동하고, 변경 사항은 Staging Area(=index)에 유지됩니다. 최근 커밋을 수정할때 유용합니다.
- git reset --mixed [커밋ID] : 지정한 커밋으로 HEAD와 Staging Area를 이동하지만, Working Directory는 그대로 유지됩니다. 커밋은 취소되지만 파일 변경 사항은 남아있어 다시 커밋할 수 있습니다.
- git reset --hard [커밋ID] : 지정한 커밋으로 HEAD, Staging Area, Working Directory를 모두 이동시켜 변경 사항을 완전히 삭제합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request : 특정 branch의 코드 변경 사항을 원본 저장소의 다른 branch에 병합을 요청하는 과정이다.
- Merge : 2개 이상의 branch를 하나로 통합하는 과정이다. git merge [브랜치명] 명령어로 수행된다.
1) Fast-Forward Merge : 병합되는 branch에는 신규 commit이 없을 때, 별도의 병합 커밋 없이 브랜치의 HEAD만 이동해 병합한다.
2) 3-Way Merge : 각 branch에 신규 commit이 있을 경우, 새로운 병합 커밋이 생성되면서 병합한다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase : merge와 결과는 비슷하지만, merge와 달리 커밋 히스토리에 여러 갈래 branch를 남게 하지 않고 한 줄로 정리하는 기능이다. 커밋 히스토리를 깔끔하게 관리하고 싶을 때 유용하다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- git stash : 작업중인 파일의 변경 내용을 일시적으로 기록해두는 명령이다. 작업 중 갑작스럽게 다른 작업을 진행해야 할 때, 임시로 이를 저장하고 해당 작업이 끝난 후 저장한 작업을 진행하는 방식으로 활용할 수 있다.

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
