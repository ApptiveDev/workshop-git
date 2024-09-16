# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다. local, remote와 연관지어 적어주세요.

Git은 소스 코드를 관리하는 버전 관리 도구로 개발자가 컴퓨터에서 작업한 변경 사항을 중앙 서버에 업로드 할 수 있게 합니다. 
로컬 저장소(사용자의 컴퓨터)에서 Git을 이용해 파일을 관리하고, 브랜치를 만들거나 커밋을 하여 버전을 관리할 수 있습니다.

Github는 Git으로 관리하는 코드를 온라인에 저장하고 공유할 수 있는 서비스입니다.
원격 저장소(Github 서버)를 통해 협업을 진행하며, 각각의 개발자가 원격 저장소에 접근해 작업을 공유할 수 있습니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  

Working Directory: 실제로 코드 작성 및 파일 수정을 하는 공간으로 Staging Area에 추가되기 전까지 Git에 반영되지 않습니다.
Staging Area: Working Directory에서 변경된 파일을 커밋할 준비가 된 임시 저장 공간을 가리킵니다.
Local Repo(HEAD): 컴퓨터에 위치한 Git 저장소로 프로젝트 파일과 변경 이력을 관리하는 장소입니다.
HEAD는 현재 작업 중인 브랜치의 가장 최신 커밋을 가리킵니다. 
Remote Repo(MASTER): Local Repo와 달리 인터넷이나 네트워크 상에 위치하여 협업, 백업을 위한 중앙 저장소를 가리킵니다.
MASTER은 프로젝트의 주요 작업을 관리하는 기본 브랜치를 말합니다.

Git Add: Working Directory에서 수정된 파일을 스테이징 영역으로 이동시킵니다. 현재 변경 사항을 추적하고, 커밋할 준비를 합니다.
(git add *filename* \n git add .)
Git Commit: Staging Area 파일을 Local Repo에 저장(Commit)합니다. 
(git commit -m *commitmsg*)
Git Push: Local Repo에 저장된 커밋을 Remote Repo에 전송합니다.
(git push origin *branchname*)
Git Merge: 두 브랜치를 하나로 통합된 버전으로 합칩니다. 개발이 완료된 후 메인 브랜치에 병합할때 사용합니다.
(git checkout master /n git merge *branchname*)
Git Fetch: 원격 저장소의 변경 사항을 로컬로 가져옵니다. 이때 로컬 브랜치에는 병합하지 않습니다. 병합 작업을 수동적으로 하려고 할때 사용합니다.
(git fetch origin)
Git Pull: 원격 저장소의 변경 사항을 가져오고 자동으로 로컬 브랜치에 병합합니다. Git Fetch와 Git Merge를 한번에 수행하게 됩니다.
(git pull Origin *branchname*)

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

git reset --soft는 Commit은 취소하나 Working Directory와 Staging Area의 변경 사항은 유지하는 것을 말합니다.
git reset --mixed는 Working directory는 유지하나 Commit을 취소하고 Staging Area의 변경 사항을 Discard하는 것을 말합니다.
git reset --hard는 Commit, Working Directory, Staging Area 모두를 재설정하여 변경 사항이 삭제되는 것을 말합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request(PR)은 코드 변경사항을 검토받기 위해 팀원들에게 제안하는 협업 도구입니다.
팀원들의 검토, 피드백 이후 수정을 통해 병합을 승인하면 반영됩니다.
Merge는 두 브랜치의 변경 사항을 하나로 통합하는 명령어입니다.
(git checkout main \n git merge feature)
Merge의 두 타입 중 Fast-Forward는 새로운 브랜치에만 Commit이 있고 기준이 되는 브랜치에 신규 Commit이 없을때 새로운 브랜치를 main으로 만드는 것입니다.
이때, 중간에 변경이 없을때만 동작하며 다른 커밋이 끼여있다면 Conflict가 발생하여 동작하지 않게 됩니다.
3-Way Merge는 merge의 기본 작동방식으로 브랜치에 신규 commit이 있을 경우 두 브랜치를 합쳐 새로운 Commit을 생성해주는데 이를 3-Way Merge라 부릅니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

git rebase는 한 브랜치의 커밋 기록을 다른 브랜치 위로 옮겨놓습니다. 이를 통해 브랜치 기록이 직선형으로 유지되어 관리가 용이해집니다.
여러 브랜치의 작업을 통합하는데 유용하게 사용됩니다. 
git merge는 병합 Commit을 만들어 두 브랜치를 합쳐 기록이 모두 남지만 git rebase는 커밋 기록이 직선형으로 재구성됩니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

git stash는 Working Directory와 Staging Area에 있는 변경 사항을 임시로 저장하고 Working Directory를 깨끗하게 만듭니다.
긴급 수정이 필요하거나, 실험 코드를 임시로 저장할때 변경 사항을 임시로 저장하고 다른 작업을 할 수 있게 만듭니다.
(git stash //변경 사항을 임시 저장)
(git stash apply //저장된 변경 사항 불러오기)
(git stash pop //저장된 변경 사항 불러오기 + 삭제)
(git stash list //stash 목록 확인)
(git stash drop stash@{0} //특정 stash 삭제)
(git stash clear //모든 stash 삭제)

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
