# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
Git은 분산 버전 관리 시스템이며, 코드를 추적하고 관리하는 데 사용됩니다. 
GitHub는 Git 저장소를 호스팅하고 협업을 촉진하는 온라인 플랫폼입니다

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
    Working Directory (작업 디렉토리):
        작업 중인 프로젝트의 실제 파일이 저장되는 디렉토리입니다.
        이 디렉토리 내에서 파일을 생성, 수정, 삭제 등의 작업을 수행합니다.

    Git Add:
        작업 디렉토리에서 변경된 파일을 스테이징 영역에 추가하는 명령입니다.
        변경 내용을 Git이 추적할 수 있도록 하며, 스테이징 영역에 추가된 파일은 다음 커밋에 포함됩니다.

    Git Commit:
        스테이징 영역에 있는 변경 사항을 로컬 저장소에 영구적으로 저장하는 명령입니다.
        변경 내용에 대한 설명과 함께 커밋 메시지를 작성하여 기록합니다.
        커밋은 프로젝트의 버전 히스토리를 관리하고 추적하는 데 사용됩니다.

    Git Push:
        로컬 저장소에 있는 변경 사항을 원격 저장소로 전송하는 명령입니다.
        다른 개발자와 변경 사항을 공유하거나, 백업을 만들기 위해 사용됩니다.
        원격 저장소로 푸시하면 다른 개발자가 변경 사항을 가져올 수 있게 됩니다.
Git Merge, Git Fetch는 생략해도 됩니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
    Branch (브랜치):

    프로젝트의 특정 작업이나 기능을 분리하여 독립적으로 개발하기 위한 개념입니다.
    기존의 커밋 기록을 기반으로 새로운 브랜치를 생성할 수 있습니다.
    각 브랜치는 프로젝트의 특정 상태를 나타내며, 독립적으로 변경되고 관리됩니다.

HEAD:

    현재 작업 중인 브랜치의 가장 최근 커밋을 가리키는 포인터입니다.
    HEAD는 작업 디렉토리에서 작업하는 중인 커밋을 가리킵니다.

Git Checkout:

    특정 브랜치로 이동하거나, 커밋의 상태를 볼 때 사용하는 명령어입니다.
    git checkout <branch_name> 명령어를 사용하여 다른 브랜치로 이동할 수 있습니다.
    또한 git checkout <commit_hash>를 사용하여 특정 커밋의 상태를 확인할 수도 있습니다.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
    Git Clone:
        기존에 원격 저장소에 있는 프로젝트를 로컬로 복제하는 명령어입니다.
        주로 GitHub, GitLab, Bitbucket 등의 원격 저장소를 복제할 때 사용됩니다.
        사용 방법: git clone <원격 저장소 URL> 명령어를 사용하여 실행합니다.

    Git Init:
        로컬 디렉토리를 Git 저장소로 초기화하는 명령어입니다.
        새로운 프로젝트를 시작하거나, 기존 프로젝트를 Git으로 관리하기 시작할 때 사용됩니다.
        사용 방법: git init 명령어를 사용하여 실행합니다. 이 명령어를 실행한 디렉토리가 Git 저장소로 초기화됩니다.
    Origin

        Origin은 일반적으로 원격 저장소를 가리키는 단어입니다. 주로 Git에서 기본적으로 설정되는 원격 저장소의 별칭으로 사용됩니다.
        원격 저장소의 URL을 복제하거나 저장소에 푸시할 때 사용됩니다.
        원격 저장소를 설정할 때 보통 "origin"이라는 이름으로 설정됩니다.
## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
    Soft Reset (소프트 리셋):
        Soft Reset은 HEAD를 이전 커밋으로 이동시키지만, 변경 내용을 유지합니다.
        변경 내용은 스테이징 영역에 그대로 남아 있습니다.
        주로 최신 커밋을 취소하고, 변경 내용을 다시 스테이징 영역에 추가하기 위해 사용됩니다.
        사용 방법: git reset --soft HEAD~1

    Mixed Reset (믹스드 리셋):
        Mixed Reset은 HEAD를 이전 커밋으로 이동시키며, 변경 내용을 unstaged 상태로 되돌립니다.
        변경 내용은 로컬 저장소에는 그대로 남아 있지만, 스테이징 영역에서는 사라집니다.
        주로 최신 커밋을 취소하고, 변경 내용을 다시 수정한 후 다시 스테이징하는 경우에 사용됩니다.
        사용 방법: git reset HEAD~1

    Hard Reset (하드 리셋):
        Hard Reset은 HEAD를 이전 커밋으로 이동시키며, 변경 내용을 완전히 삭제합니다.
        변경 내용은 로컬 저장소와 작업 디렉토리에서 모두 삭제됩니다.
        주로 최신 커밋을 완전히 취소하고 이전 상태로 되돌리는 경우에 사용됩니다. 주의가 필요한 명령어입니다.
        사용 방법: git reset --hard HEAD~1

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request (풀 리퀘스트):

    Pull Request는 코드 변경 사항을 다른 개발자들에게 검토하고 병합하기 위해 사용되는 기능입니다.
    주로 협업하는 프로젝트에서 개발자들 간에 코드 리뷰와 피드백을 주고받는 데 사용됩니다.

Merge (병합):

    Merge는 두 개의 다른 브랜치를 하나로 합치는 것을 의미합니다.
    주로 Pull Request를 통해 코드 검토를 완료하고, 브랜치를 기존 브랜치에 병합할 때 사용됩니다.

Fast-Forward Merge (패스트 포워드 병합):

    Fast-Forward Merge는 두 브랜치가 일직선적인 관계에 있을 때 발생하는 병합 방식입니다.
    즉, 기존 브랜치의 커밋 기록이 단순히 앞으로 이동하면 되는 경우에 사용됩니다.
    별도의 병합 커밋이 생성되지 않고, 단순히 HEAD를 이동시켜서 기존 브랜치의 커밋 기록을 통합합니다.

3-Way Merge (3-way 병합):

    3-Way Merge는 두 브랜치가 서로 다른 변경 사항을 가지고 있을 때 발생하는 병합 방식입니다.
    즉, 각 브랜치에서 변경된 내용을 비교하여 자동으로 최종 결과물을 생성합니다.
    병합 커밋이 생성되며, 충돌이 발생할 수 있으며 이를 해결해야 합니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
Rebase (리베이스):

Rebase는 Git에서 브랜치의 기록을 재배치하거나 합치는 작업을 의미합니다. 특히, 다른 브랜치의 변경 내용을 현재 브랜치의 기록에 적용할 때 사용됩니다.


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
Git Stash 활용 방법:

Git Stash는 현재 작업 중인 변경 사항을 임시로 보관하고, 깨끗한 작업 디렉토리에서 작업할 수 있도록 도와주는 기능입니다. 주로 작업 중에 갑작스런 다른 작업을 해야 할 때나, 브랜치를 변경해야 할 때 유용합니다

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
