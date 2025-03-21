# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
Git (Local)
버전 관리 시스템: Git은 소스 코드의 변경 내역을 추적하고 관리할 수 있는 분산 버전 관리 시스템입니다.

로컬 저장소: 개발자가 자신의 컴퓨터에 Git을 설치하고, 프로젝트의 버전 기록을 로컬 저장소에 저장합니다. 이로 인해 인터넷 연결 없이도 버전 관리 작업(커밋, 브랜치 생성 등)을 수행할 수 있습니다.

GitHub (Remote)
원격 저장소 서비스: GitHub는 Git을 기반으로 하는 클라우드 기반 플랫폼입니다.

협업 및 공유: 로컬에서 관리하는 Git 저장소를 원격 저장소로 업로드(push)하여 여러 개발자와 협업할 수 있으며, 다른 사람의 프로젝트를 복제(clone)하거나 기여(pull request)할 수 있습니다.

추가 기능: 이슈 추적, 코드 리뷰, 위키, CI/CD 등 협업에 유용한 다양한 기능을 제공합니다.

결론
Local vs Remote: Git은 로컬에서의 버전 관리 도구이며, GitHub는 이러한 Git 저장소를 원격으로 관리, 공유 및 협업하기 위한 플랫폼입니다. 따라서 둘은 동일한 것이 아니라, Git이 로컬 작업에 중점을 둔다면 GitHub는 원격 협업 및 저장소 관리에 초점을 맞춘 서비스입니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  

위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working Directory
정의: 프로젝트의 실제 파일들이 위치한 폴더입니다.

역할: 개발자가 코드를 작성하고 수정하는 작업 공간입니다.

특징: 파일을 편집하면 변경 사항이 바로 Working Directory에 반영됩니다.

Git Add
정의: 변경된 파일을 스테이징 영역(Staging Area)에 추가하는 명령어입니다.

역할: 작업 디렉토리의 변경 사항 중에서 어떤 파일을 커밋에 포함할지 선택합니다.

특징: git add 파일명 명령어를 사용하여 특정 파일 또는 git add .로 전체 변경 사항을 스테이징 할 수 있습니다.

Git Commit
정의: 스테이징 영역에 있는 파일의 변경 사항을 로컬 저장소에 저장하는 명령어입니다.

역할: 현재까지의 작업 상태를 하나의 스냅샷으로 기록하며, 커밋 메시지를 통해 변경 내역을 설명합니다.

특징: 커밋은 변경 사항의 기록으로서, 프로젝트의 이력을 관리하고 필요 시 이전 상태로 복원할 수 있는 기반이 됩니다.

Git Push
정의: 로컬 저장소에 저장된 커밋을 원격 저장소(예: GitHub)로 전송하는 명령어입니다.

역할: 여러 개발자와 협업할 때 로컬 변경 사항을 공유하고, 원격 저장소를 최신 상태로 유지합니다.

특징: git push origin 브랜치명 형식으로 사용하며, 원격 저장소와 동기화를 통해 프로젝트의 버전 관리가 이루어집니다.

이렇게 Git은 Working Directory에서 변경된 파일을 git add를 통해 스테이징하고, git commit으로 로컬 저장소에 기록한 후, git push를 통해 원격 저장소에 반영하는 과정을 통해 버전 관리와 협업이 이루어집니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

Git은 commit과 branch를 기본 단위로 동작하며, 이 두 요소를 중심으로 다양한 명령어를 통해 버전 관리가 이루어집니다.

Commit
정의: 프로젝트의 특정 시점의 상태(스냅샷)를 기록한 단위입니다.

특징: 각 commit은 고유한 해시값을 가지며, 변경 사항과 커밋 메시지를 포함합니다.

역할: 프로젝트 이력 관리 및 필요 시 이전 상태로 복원할 수 있게 해줍니다.

Branch
정의: commit들을 가리키는 포인터로, 개발의 흐름(라인)을 의미합니다.

역할: 여러 기능 개발이나 버그 수정을 동시에 진행할 때, 독립적인 작업 공간을 제공하여 주 작업(main/master branch)에 영향을 주지 않도록 합니다.

생성: git branch 브랜치명으로 새로운 branch를 생성할 수 있습니다.

삭제: 작업이 끝난 branch는 git branch -d 브랜치명 (안전 삭제) 또는 git branch -D 브랜치명 (강제 삭제) 명령어로 제거할 수 있습니다.

HEAD
정의: 현재 작업 중인 branch 또는 commit을 가리키는 포인터입니다.

역할: 현재 체크아웃된 상태를 나타내며, HEAD가 가리키는 branch의 최신 commit이 작업의 기준점이 됩니다.

특징: HEAD가 branch를 가리키는 경우, 해당 branch의 최신 commit에 위치하게 되고, 특정 commit을 직접 가리키면 'detached HEAD' 상태가 됩니다.

Git Checkout
역할:

Branch 전환: 다른 branch로 이동할 때 사용합니다. 예를 들어, git checkout 브랜치명 명령어를 통해 다른 branch로 전환하면, HEAD가 해당 branch를 가리키게 됩니다.

새로운 Branch 생성 및 이동: git checkout -b 새브랜치명 명령어로 branch를 생성하고 즉시 전환할 수 있습니다.

특정 Commit 체크아웃: 특정 commit의 상태로 작업 디렉토리를 전환할 수 있으나, 이 경우 detached HEAD 상태가 되어 커밋을 직접 추가하면 branch와 연동되지 않습니다.

주의사항:

Detached HEAD 상태에서는 작업 후 별도의 branch를 생성하지 않으면, 이후 변경 내용이 반영되지 않을 수 있으니 주의해야 합니다.

최근 Git 버전에서는 branch 전환에 특화된 git switch 명령어도 함께 제공되므로 상황에 맞게 활용할 수 있습니다.

Branch 관리 커맨드 요약
Branch 생성:

git branch 새브랜치명

또는 git checkout -b 새브랜치명 (생성과 동시에 전환)

Branch 목록 확인: git branch

Branch 전환: git checkout 브랜치명 또는 git switch 브랜치명

Branch 삭제:

안전 삭제: git branch -d 브랜치명

강제 삭제: git branch -D 브랜치명

결론
Git에서 commit은 개별 작업의 단위를 기록하며, branch는 이러한 commit들의 흐름을 관리하는 역할을 합니다. HEAD는 현재 활성화된 branch나 commit을 나타내며, git checkout 명령어를 통해 branch 간 전환이나 특정 commit 상태로의 변경이 이루어집니다. 이들 명령어와 개념을 활용하면 여러 개발 작업을 독립적으로 진행하면서도, 전체 프로젝트의 이력을 체계적으로 관리할 수 있습니다.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

Git 리포지토리를 로컬에 생성하는 방법에는 크게 두 가지가 있습니다. 아래에서 **git init**과 **git clone**의 차이점 및 사용 방법, 그리고 **origin** 키워드에 대해 설명합니다.

---

## git init vs git clone

### git init
- **목적**: 현재 디렉토리를 새로운 Git 리포지토리로 초기화합니다.
- **사용 상황**: 새로운 프로젝트를 시작할 때 또는 기존 폴더를 버전 관리 대상으로 만들고 싶을 때 사용합니다.
- **동작 방식**:  
  - 명령어를 실행하면 해당 디렉토리에 `.git` 폴더가 생성되어, Git이 버전 관리를 위한 모든 메타데이터를 저장하게 됩니다.
- **사용 방법**:
  ```bash
  git init
  ```
- **추가 설정**:  
  - 초기화 후, 원격 저장소가 필요한 경우 `git remote add origin <저장소 URL>` 명령어로 원격 저장소를 설정할 수 있습니다.

---

### git clone
- **목적**: 기존의 원격 또는 로컬 Git 리포지토리를 복제하여 새로운 로컬 리포지토리를 생성합니다.
- **사용 상황**: 이미 존재하는 프로젝트를 복사하여 작업을 시작할 때 사용합니다.
- **동작 방식**:  
  - 지정한 URL의 리포지토리를 그대로 복제하며, 커밋 내역과 브랜치 정보 등 모든 Git 기록을 함께 가져옵니다.
  - 복제한 후, 기본 원격 저장소 이름으로 `origin`이 자동으로 설정됩니다.
- **사용 방법**:
  ```bash
  git clone <리포지토리 URL>
  ```
- **예시**:  
  ```bash
  git clone https://github.com/username/project.git
  ```

---

## origin이란 키워드와 설정 방법

- **origin의 의미**:  
  - `origin`은 Git에서 기본 원격 저장소의 별칭(alias)으로 사용됩니다.
  - 클론 시, 자동으로 복제된 리포지토리의 원격 저장소가 `origin`으로 설정되며, 이후 `git push`, `git pull` 등의 명령어에서 기본 원격 저장소로 참조됩니다.

- **설정 방법**:
  - **자동 설정**:  
    - `git clone` 명령어를 사용하면, 원격 저장소 URL이 자동으로 `origin`이라는 이름으로 설정됩니다.
  - **수동 설정**:  
    - 새로 생성한 로컬 리포지토리에서 원격 저장소를 추가할 때, 다음 명령어를 사용하여 `origin`이라는 이름을 지정할 수 있습니다.
    ```bash
    git remote add origin <원격 저장소 URL>
    ```
  - **원격 저장소 확인**:  
    - 현재 설정된 원격 저장소 목록은 아래 명령어로 확인할 수 있습니다.
    ```bash
    git remote -v
    ```

---

## 요약

- **git init**: 새로운 리포지토리를 로컬에서 시작할 때 사용합니다. 이후 필요에 따라 원격 저장소(`origin`)를 추가할 수 있습니다.
- **git clone**: 기존 리포지토리를 복제할 때 사용하며, 클론 시 원격 저장소가 자동으로 `origin`으로 설정됩니다.
- **origin**: 기본 원격 저장소의 별칭으로, `git clone` 시 자동 설정되거나 `git remote add origin <URL>`로 수동 설정할 수 있습니다.

이와 같은 방식으로 로컬에서 Git 리포지토리를 생성하고 관리할 수 있습니다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

1. --soft
동작 방식:

HEAD 포인터만 지정한 커밋으로 이동합니다.

스테이징 영역(index)과 작업 디렉토리(working directory)는 그대로 유지됩니다.

사용 예: git reset --soft <커밋 해시>

마지막 커밋을 취소하고, 변경 사항을 그대로 스테이징 영역에 남겨두고 싶을 때 사용합니다.

2. --mixed (기본 옵션)
동작 방식:

HEAD 포인터를 지정한 커밋으로 이동합니다.

스테이징 영역을 해당 커밋 상태로 재설정하지만, 작업 디렉토리의 파일은 그대로 남깁니다.

특징:

변경 사항은 작업 디렉토리에 남아 있으므로 다시 스테이징하거나 수정할 수 있습니다.

별도로 옵션을 주지 않고 git reset <커밋 해시>로 사용하면 기본적으로 --mixed 모드가 적용됩니다.

git reset --mixed <커밋 해시>

3. --hard
동작 방식:

HEAD 포인터, 스테이징 영역, 작업 디렉토리 모두를 지정한 커밋 상태로 되돌립니다.

특징:

변경 사항이 모두 삭제되므로, 작업 중인 내용이 모두 사라질 수 있습니다.

되돌릴 수 없는 파괴적인(reset) 작업이므로 주의해서 사용해야 합니다.

이와 같이, --soft는 커밋만 취소하고 스테이징 상태를 유지하며, --mixed는 스테이징 영역까지 초기화하지만 작업 내용은 보존하고, --hard는 모든 변경 사항을 완전히 제거하는 방식으로 작동합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request (PR)
개념:

Pull Request는 개발자가 특정 기능이나 버그 수정 작업을 완료한 후, 해당 변경 사항을 메인 또는 다른 기준 브랜치에 병합(merge)해달라고 요청하는 절차입니다.

주로 GitHub, GitLab, Bitbucket 등의 원격 저장소 서비스에서 사용되며, 팀원 간의 코드 리뷰, 논의, 테스트를 거쳐 코드 품질을 보증하는 데 중요한 역할을 합니다.

작업 과정:

분기(Branch) 생성: 새로운 기능 또는 버그 수정을 위한 독립적인 브랜치에서 작업을 진행합니다.

커밋: 작업 내역을 여러 커밋으로 기록합니다.

PR 생성: 변경 사항이 반영된 브랜치를 기준 브랜치(예: main 또는 master)로 병합해달라고 요청합니다.

리뷰 및 승인: 다른 팀원들이 코드 리뷰를 진행하며, 수정 및 토론을 거친 후 최종 승인이 이루어집니다.

Merge: 승인된 PR은 Merge되어 기준 브랜치에 변경 사항이 반영됩니다.

Merge
Merge는 서로 다른 브랜치의 변경 사항을 하나로 합치는 작업입니다. Merge에는 주로 두 가지 타입이 있습니다.

1. Fast-Forward Merge
상황:

병합 대상 브랜치가 기준 브랜치의 직계 후손인 경우 발생합니다.

기준 브랜치에 변경 사항이 없고, 병합 대상 브랜치의 변경 사항만 추가된 상황입니다.

동작 원리:

기준 브랜치 포인터를 단순히 병합 대상 브랜치의 최신 커밋으로 "앞으로 이동"시킵니다.

별도의 merge commit 없이 단순하게 브랜치 포인터가 이동되므로 커밋 기록이 깔끔하게 유지됩니다.

명령어 예시:
git checkout main
git merge feature-branch

위 명령어에서 만약 main 브랜치가 feature-branch의 부모라면, Fast-Forward Merge가 적용됩니다.

2. 3-Way Merge
상황:

기준 브랜치와 병합 대상 브랜치 모두에 독자적인 변경 사항이 있을 때 발생합니다.

두 브랜치가 서로 다른 방향으로 발전하여 공통 조상(commit)이 존재하는 경우입니다.

동작 원리:

Git은 세 개의 지점을 사용합니다:

공통 조상 (Common Ancestor)

기준 브랜치의 최신 커밋

병합 대상 브랜치의 최신 커밋

이 세 지점을 비교하여 두 브랜치의 변경 사항을 통합한 새로운 merge commit을 생성합니다.

이 merge commit은 두 부모(commit)를 가지게 됩니다.

명령어 예시:
git checkout main
git merge feature-branch

기준 브랜치와 feature 브랜치가 모두 변경 사항을 포함하고 있다면, Git은 3-Way Merge를 수행하여 새로운 merge commit을 생성합니다.

요약
Pull Request는 코드 변경 사항을 기준 브랜치로 병합하기 전, 팀원들과 리뷰 및 토론을 진행하는 협업 절차입니다.

Merge는 두 브랜치의 변경 사항을 하나로 합치는 작업이며,

Fast-Forward Merge는 병합 대상 브랜치가 기준 브랜치의 직계 후손인 경우 단순히 포인터를 이동하는 방식으로,

3-Way Merge는 서로 다른 변경 사항을 통합하기 위해 공통 조상과 두 브랜치의 최신 커밋을 비교하여 새로운 merge commit을 생성하는 방식입니다.

이와 같이 PR과 Merge는 팀 프로젝트에서 코드의 변경 사항을 효과적으로 통합하고 관리하기 위한 핵심 절차로 활용됩니다.


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

Rebase의 정의
Rebase란?

Rebase는 한 브랜치의 커밋들을 다른 브랜치 위에 순차적으로 재적용하는 과정입니다.

기존의 커밋 기록을 새로운 기반(commit) 위에 "붙여" 이력을 재구성합니다.

Rebase의 동작 원리
작업 방식:

예를 들어, feature 브랜치가 있고 이 브랜치에서 여러 커밋을 진행한 상황에서, 기준 브랜치(main)에 새로운 커밋들이 추가되었다고 가정합니다.

Rebase를 사용하면 feature 브랜치의 커밋들이 main 브랜치의 최신 커밋 이후에 순서대로 재적용됩니다.

결과:

커밋 기록이 선형화되어, 복잡한 병합 기록 없이 깔끔한 이력이 만들어집니다.

Rebase가 유용한 경우
이력 정리 (Clean History):

여러 기능 브랜치에서 작업한 커밋들이 산재해 있을 때, rebase를 통해 선형적인 이력을 유지하면 코드 리뷰나 버그 추적이 용이해집니다.

업스트림 변경사항 반영:

팀원들이 기준 브랜치(main, master 등)에 새로운 커밋을 추가한 경우, rebase를 사용하여 자신의 작업을 최신 기준 위에 올림으로써 충돌 가능성을 줄일 수 있습니다.

피쳐 브랜치 업데이트:

병합 전에 최신 기준 브랜치의 변경사항을 피쳐 브랜치에 반영할 때 사용합니다. 이렇게 하면 나중에 병합 시에 불필요한 merge commit 없이 변경 사항을 반영할 수 있습니다.

주의사항
공유된 브랜치에서의 Rebase:

이미 다른 팀원과 공유된 브랜치에서 rebase를 수행하면, 커밋 해시가 변경되어 협업에 혼란을 줄 수 있으므로, 주로 개인 작업이나 공유되지 않은 브랜치에서 사용하는 것이 좋습니다.

충돌 해결:

Rebase 도중 충돌이 발생할 수 있으며, 이 경우 충돌을 해결한 후 rebase를 계속 진행해야 합니다.

결론
Rebase는 브랜치의 커밋 기록을 재구성하여 선형적이고 깔끔한 이력을 만들고, 최신 기준 브랜치의 변경사항을 반영하는 데 유용한 도구입니다. 단, 공유된 브랜치에서는 사용에 주의해야 하며, 충돌 해결 과정이 필요할 수 있습니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

Git stash는 현재 작업 중인 미완성 변경 사항(수정된 파일, 추가된 파일 등)을 임시 저장해 두어, 워킹 디렉토리를 깨끗한 상태로 만들고 다른 브랜치로 전환하거나 긴급한 작업을 처리할 때 유용하게 활용됩니다. 아래에 git stash의 주요 활용 방법과 관련 명령어들을 정리했습니다.

---

## 주요 명령어와 활용 방법

### 1. 변경 사항 임시 저장
- **git stash / git stash push**  
  - 현재 작업 디렉토리와 스테이징 영역의 변경 사항을 임시 저장소에 저장합니다.
  - 기본적으로 추적된(tracked) 파일의 변경 사항을 저장하며, 미추적(untracked) 파일까지 저장하려면 `-u` 옵션을 추가합니다.
  - 예시:
    ```bash
    git stash
    git stash push -u
    git stash push -m "작업 중인 변경 사항 저장"
    ```

---

### 2. 저장된 Stash 목록 확인
- **git stash list**  
  - 저장된 stash들을 확인할 수 있습니다.
  - 출력 예시:
    ```
    stash@{0}: WIP on main: 1234567 작업 내용 메시지
    stash@{1}: WIP on main: 89abcd0 이전 작업 내용
    ```

---

### 3. Stash 적용 및 제거
- **git stash apply**  
  - 지정한 stash(또는 기본으로 가장 최근 stash)를 현재 작업 디렉토리에 적용합니다.
  - 적용 후에도 stash 목록에는 남아 있으므로, 필요에 따라 삭제할 수 있습니다.
  - 예시:
    ```bash
    git stash apply stash@{0}
    ```
  
- **git stash pop**  
  - 지정한 stash(또는 기본으로 가장 최근 stash)를 적용하면서, stash 목록에서 자동으로 제거합니다.
  - 예시:
    ```bash
    git stash pop
    ```

---

### 4. 특정 Stash 삭제
- **git stash drop**  
  - 더 이상 필요 없는 특정 stash 항목을 삭제합니다.
  - 예시:
    ```bash
    git stash drop stash@{1}
    ```
  
- **git stash clear**  
  - 저장된 모든 stash 항목을 삭제합니다.

---

## 사용 사례

- **브랜치 전환**:  
  미완성 작업을 보류하고 다른 브랜치로 전환해야 할 때,
  ```bash
  git stash        # 현재 변경 사항 저장
  git checkout 다른-브랜치
  # 긴급 작업 후 돌아와서...
  git checkout 원래-브랜치
  git stash pop    # 저장된 변경 사항 복원
  ```

- **긴급 수정**:  
  작업 도중 버그 수정 등 긴급한 작업이 필요할 때, 현재 진행 중인 작업을 임시 저장한 후 수정 작업을 진행하고 나중에 다시 복원할 수 있습니다.

- **작업 정리**:  
  실험적인 코드나 아직 완성되지 않은 변경 사항을 커밋 전에 임시로 보관하여, 커밋 기록을 깔끔하게 관리할 수 있습니다.

---

## 주의 사항
- **충돌 가능성**:  
  stash를 적용할 때 변경 사항 간 충돌이 발생할 수 있으며, 이 경우 수동으로 해결해야 합니다.
  
- **임시 저장소 관리**:  
  오래된 stash는 혼란을 줄 수 있으므로, 주기적으로 `git stash list`로 상태를 확인하고 필요 없는 항목은 `git stash drop` 또는 `git stash clear`로 정리하는 것이 좋습니다.

---

Git stash는 이러한 명령어와 활용 방법을 통해 작업 흐름을 유연하게 관리하고, 임시 작업 보류나 브랜치 전환 시 유용하게 사용할 수 있는 도구입니다.

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
