# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

★Git  

- 오픈 소스 버전관리 시스템
-로컬에서 버전 관리
- 소프트웨어 개발 및 소스 코드 관리에 사용
git은 브랜치를 생성 이전 브랜치로 복구,삭제,병합 가능.
하지만 로컬 저장소를 사용하기 때문에 다른 개발자와 실시간으로 작업을 공유할 수 없습니다.


★Git hub
- Git을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스
- 클라우드 서버를 사용해서 로컬에서 버전 관리한 소스코드를 공유 가능
- 분산 버전 제어, 액세스 제어, 버그 추적 작업 관리를 제공


Git은 버전 관리 프로그램이고, Github는 버전 관리,소스코드 공유가 가능한 원격 저장소 입니다.



## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.

Git Merge, Git Fetch는 생략해도 됩니다.

★Working Directory (작업 디렉토리):
 
 - 현재 작업 중인 프로젝트의 실제 파일이 저장된 디렉토리입니다. 작업 디렉토리 내에서 파일을 수정하고 변경을 추적하는 것이 Git의 주요 목적 중 하나입니다.

★Git Add:
- Git Add 명령어는 작업 디렉토리에서 파일을 스테이징 영역(Staging Area 또는 Index라고도 함)으로 추가합니다. 이 단계에서 Git은 스테이징 영역에 추가된 파일의 변경 사항을 추적하게 됩니다.
★Git Commit:
- Git Commit 명령어는 스테이징 영역에 있는 변경 사항을 로컬 저장소에 영구적으로 저장합니다. 이러한 커밋은 프로젝트의 버전 히스토리를 만듭니다. 각 커밋은 메시지와 함께 설명되어야 합니다.

★Git Push:
- Git Push 명령어는 로컬 저장소의 커밋을 원격 저장소로 전송합니다. 
이것은 다른 개발자들과 작업을 공유하거나, 
작업한 내용을 원격 저장소에 백업하는 데 사용됩니다. 주로 Git 서버에 변경 사항을 업로드하는 데 사용됩니다.
## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

★커밋(Commit):

- 커밋은 프로젝트의 변경 사항을 저장하는 기록입니다.
각 커밋은 고유한 해시값을 가지며, 변경된 내용, 작성자, 작성 일시 등의 정보를 포함합니다.\
커밋을 통해 프로젝트의 특정 시점의 상태를 저장하고 관리할 수 있습니다.

★브랜치(Branch):

- 브랜치는 커밋의 참조로, 프로젝트의 특정 기능 또는 작업을 개발하는 독립적인 경로를 나타냅니다.
각 브랜치는 커밋의 연속으로 이루어져 있으며, 하나의 브랜치에서 다른 브랜치로 전환할 수 있습니다.\
브랜치를 통해 여러 작업을 병렬로 진행하거나, 실험적인 변경을 테스트할 수 있습니다.

★HEAD:

- HEAD는 현재 작업 중인 브랜치를 가리키는 포인터입니다.
HEAD는 일반적으로 최신 커밋을 가리키며, 작업 디렉토리에 반영되는 변경 사항은 HEAD가 가리키는 커밋에 따라 결정됩니다.
★git checkout:

- git checkout 명령어는 브랜치를 변경하거나 특정 커밋으로부터 파일을 되돌리는 데 사용됩니다.\
브랜치를 변경할 때는 새로운 브랜치를 만들거나 기존의 브랜치로 전환할 수 있습니다.\
특정 커밋으로부터 파일을 되돌릴 때는 해당 커밋의 상태로 작업 디렉토리를 복원합니다.

브랜치 생성, 삭제, 이동
-
브랜치 생성: git branch <branch_name>

브랜치 삭제: git branch -d <branch_name>

브랜치 이동: git checkout <branch_name>


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

★git clone vs git init★

★git clone: 
- 이미 존재하는 원격 저장소의 내용을 로컬로 복제합니다. 원격 저장소에서 모든 히스토리와 브랜치를 가져옵니다.
bash
Copy code
git clone <repository_URL>

★git reset --mixed 
- <commit> 명령어를 사용합니다. (기본값)
이 명령어는 HEAD를 특정 커밋으로 이동시키고, 해당 커밋 이후의 변경 사항을 스테이징 영역에 유지하지 않습니다.
변경 사항은 작업 디렉토리에 유지되며, 스테이징 영역에서 삭제됩니다. 
이후에 변경 사항을 스테이징하고 다시 커밋할 수 있습니다.


★git reset --hard 
-  <commit> 명령어를 사용합니다.
이 명령어는 HEAD를 특정 커밋으로 이동시키고, 해당 커밋 이후의 변경 사항을 모두 삭제합니다.
스테이징 영역과 작업 디렉토리의 변경 사항이 모두 제거되므로 주의해야 합니다. 
 다시 되돌릴 수 없는 변경 사항을 삭제할 때 사용합니다.


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
★Pull Request (풀 리퀘스트):

- Pull Request는 코드 변경 사항을 다른 개발자들과 검토하고 병합하기 위해 사용됩니다.
일반적으로 Pull Request는 원격 저장소(예: GitHub, GitLab)에서 생성되며, 코드 변경 사항을 포함한 특정 브랜치를 기준으로 다른 브랜치로 병합하고자 할 때 사용됩니다.
Pull Request를 생성하면 다른 개발자들이 변경 사항을 검토하고 논의할 수 있으며, 코드 변경 사항에 대한 피드백을 주고 받을 수 있습니다.

Merge (병합):

- Merge는 두 개의 다른 브랜치를 하나로 합치는 과정을 의미합니다.
Git에서는 주로 두 가지 타입의 Merge가 사용됩니다: 

★Fast-Forward Merge와 3-Way Merge.

★Fast-Forward Merge:

- Fast-Forward Merge는 브랜치 간의 차이가 없는 경우에만 발생합니다.
예를 들어, 특정 브랜치에서 작업한 변경 사항을 모두 커밋하고, 해당 브랜치가 기준 브랜치의 최신 커밋을 가리키게 될 때 Fast-Forward Merge가 발생합니다.
이 경우 Git은 단순히 브랜치 포인터를 앞으로 이동시켜 기준 브랜치의 최신 커밋을 가리키게 합니다.

★3-Way Merge:

- 3-Way Merge는 두 브랜치 간에 충돌이 발생할 때 사용됩니다.
예를 들어, 두 개의 브랜치에서 동일한 파일의 동일한 부분을 동시에 수정한 경우에 충돌이 발생합니다.\
Git은 두 브랜치의 공통 조상 커밋을 찾아내고, 각 변경 사항을 비교하여 충돌을 해결합니다.\
충돌이 발생한 파일에 대해 개발자가 직접 수정하고 충돌을 해결한 후,  
수정 사항을 다시 커밋하여 Merge를 완료할 수 있습니다.
\
Pull Request와 Merge를 통해 팀원들 간의 협업을 원활하게 할 수 있으며, 코드 변경 사항을 효율적으로 검토하고 병합할 수 있습니다. Fast-Forward Merge는 단순한 상황에서 사용되며, 3-Way Merge는 충돌이 발생한 경우에 사용됩니다.



## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

★Rebase
- Git에서의 Rebase(리베이스)는 브랜치의 커밋 히스토리를 재정렬하거나 변경하는 작업을 의미합니다. 기본적으로 Rebase는 두 브랜치를 합치는 Merge 작업과 유사하지만,커밋 히스토리를 보다 깔끔하게 유지할 수 있도록 도와줍니다.

★Rebase를 사용하는 경우에는 보통 다음과 같은 상황에서 유용합니다:

★커밋 히스토리 정리:

- 여러 개의 작은 커밋을 하나의 큰 커밋으로 합치거나, 불필요한 중간 커밋을 삭제할 때 Rebase를 사용할 수 있습니다.
이를 통해 브랜치의 커밋 히스토리를 보다 깔끔하고 의미 있게 관리할 수 있습니다.

★베이스 변경:

- 현재 브랜치가 다른 브랜치의 최신 상태를 반영해야 할 때 Rebase를 사용할 수 있습니다.
예를 들어, 기능 브랜치를 개발하는 동안 메인 브랜치가 업데이트된 경우, 기능 브랜치를 메인 브랜치의 최신 상태로 리베이스하여 충돌을 최소화하고 통합할 수 있습니다.

★병합 충돌 최소화:

- Rebase를 사용하면 Merge와 달리 두 브랜치의 공통 조상부터 변경 사항을 적용하기 때문에, 충돌이 발생할 가능성이 낮아집니다.
따라서 Rebase를 사용하여 병합 충돌을 최소화하고, 코드를 더 빠르고 쉽게 통합할 수 있습니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

★Stash 
- 현재 작업 중인 변경 사항을 임시로 저장하고, 작업 디렉토리를 깨끗한 상태로 만들어주는 Git의 유용한 기능입니다.  변경 사항을 나중에 다시 적용하고 싶을 때 사용됩니다. 

★ 명령어 모음 
- $git stash 
// git stash (변경 내용 임시저장하기)

- $git stash list
(내가 stash 했던 내용 보기)

- $git stash apply
(가장 최근 stash 가지고 오기)
- $git stash drop (가장 최근 stash 지우기)

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