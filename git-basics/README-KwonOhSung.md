# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

1. Git
분산 버전 관리 시스템: Git은 소프트웨어 개발에서 소스 코드를 효율적으로 관리하기 위한 분산 버전 관리 시스템(DVCS)입니다. 프로젝트의 파일에 대한 변경 사항을 추적하고, 변경 내역을 기록하며, 여러 개발자가 동시에 작업할 수 있도록 지원합니다.
Local: Git을 사용할 때, 기본적으로 로컬 환경에서 작업합니다. 이는 개발자의 개인 컴퓨터에 Git 저장소(repository)가 있다는 의미입니다. 개발자는 로컬 저장소에서 파일을 추가하고 수정하며, 변경 사항을 커밋(commit)합니다. 이 로컬 저장소에는 프로젝트의 전체 히스토리와 파일 상태가 저장됩니다.

2. GitHub
호스팅 서비스: GitHub는 Git 저장소를 호스팅하는 클라우드 기반 서비스입니다. GitHub를 사용하면 로컬 저장소를 인터넷 상에 있는 원격 저장소(remote repository)에 업로드하고 공유할 수 있습니다. 이를 통해 여러 개발자가 협업하고, 프로젝트의 코드를 쉽게 공유할 수 있습니다.
Remote: GitHub에 저장된 저장소는 원격 저장소(remote)라고 부릅니다. 로컬 저장소의 변경 사항을 원격 저장소에 업로드하려면 git push 명령을 사용하고, 원격 저장소의 변경 사항을 로컬 저장소로 가져오려면 git pull 명령을 사용합니다.

요약하면, Git은 버전 관리를 위한 도구이고, GitHub는 Git을 사용하는 프로젝트를 위한 원격 저장소 호스팅 서비스입니다. 로컬과 원격의 개념을 통해 개발자들은 로컬에서 작업한 내용을 원격 저장소를 통해 공유하고 협업할 수 있습니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

1. Working Directory
설명: Working Directory는 현재 프로젝트의 실제 파일들이 있는 디렉토리입니다. 개발자가 코드를 추가, 수정, 삭제하는 작업을 하는 곳입니다.
역할: 변경 사항을 만들고 테스트하는 단계입니다. 이 단계에서 파일을 수정하면 해당 변경 사항은 아직 Git의 추적 대상이 아닙니다.

2. Staging Area (Index)
설명: Staging Area는 커밋할 변경 사항을 임시로 보관하는 영역입니다. Git은 이 영역을 "Index"라고도 부릅니다.
역할: Working Directory에서 변경된 파일 중에서 특정 파일만 선택해 커밋을 준비할 수 있도록 도와줍니다. 이 단계에서 변경 사항을 커밋할 준비를 합니다.

3. Local Repository
설명: Local Repository는 개발자의 로컬 컴퓨터에 저장되는 Git 저장소입니다. 모든 커밋의 히스토리와 프로젝트의 상태가 저장됩니다.
역할: 커밋한 변경 사항은 Local Repository에 저장됩니다. 이 저장소는 로컬에서 모든 Git 명령을 실행할 수 있는 독립된 환경입니다.

4. Remote Repository
설명: Remote Repository는 GitHub, GitLab, Bitbucket과 같은 호스팅 서비스에 저장되는 원격 저장소입니다.
역할: 여러 개발자들이 프로젝트를 공유하고 협업할 수 있는 저장소로, 로컬 저장소의 변경 사항을 이곳에 업로드하거나 다른 개발자의 작업 내용을 가져올 수 있습니다.

5. Git Add
설명: git add 명령은 Working Directory에서 변경된 파일을 Staging Area에 추가하는 역할을 합니다.
사용법: git add <file> 또는 git add . (모든 변경 사항 추가)
역할: 변경 사항을 커밋할 준비를 합니다. Staging Area에 추가되지 않은 변경 사항은 커밋되지 않습니다.

6. Git Commit
설명: git commit 명령은 Staging Area에 있는 변경 사항을 Local Repository에 저장합니다.
사용법: git commit -m "Commit message"
역할: 변경 사항을 기록하고 히스토리로 저장합니다. 각 커밋은 프로젝트의 특정 시점 상태를 나타냅니다.

7. Git Push
설명: git push 명령은 Local Repository의 변경 사항을 Remote Repository로 업로드합니다.
사용법: git push origin <branch>
역할: 로컬에서 작업한 내용을 원격 저장소에 공유하여 다른 팀원들이 접근할 수 있도록 합니다.

8. Git Merge
설명: git merge 명령은 다른 브랜치의 변경 사항을 현재 브랜치에 통합합니다.
사용법: git merge <branch>
역할: 분기된 개발 작업을 하나로 합쳐 프로젝트를 통합하고 발전시킵니다.

9. Git Fetch
설명: git fetch 명령은 Remote Repository에서 변경 사항을 가져오지만, Local Repository의 브랜치에 자동으로 병합하지는 않습니다.
사용법: git fetch origin
역할: 원격 저장소의 변경 사항을 로컬로 가져와 확인할 수 있게 합니다. git pull과 달리 바로 병합하지 않습니다.

10. Git Pull
설명: git pull 명령은 git fetch와 git merge를 합친 것입니다. Remote Repository의 변경 사항을 가져와서 현재 브랜치에 병합합니다.
사용법: git pull origin <branch>
역할: 원격 저장소의 변경 사항을 로컬 저장소에 병합하여 최신 상태로 유지합니다.

Git Workflow 요약
Working Directory에서 파일을 생성하거나 수정합니다.
git add 명령으로 Staging Area에 변경 사항을 추가합니다.
git commit 명령으로 Local Repository에 변경 사항을 저장합니다.
git push 명령으로 Remote Repository에 변경 사항을 업로드하여 공유합니다.
협업 시에는 git fetch나 git pull 명령으로 Remote Repository의 변경 사항을 로컬로 가져옵니다.
필요한 경우 git merge를 사용하여 여러 브랜치의 변경 사항을 통합합니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

1. Branch
설명: 브랜치는 프로젝트의 독립적인 개발 라인을 의미합니다. 기본적으로 main(혹은 master) 브랜치가 있으며, 새로운 기능을 추가하거나 버그를 수정할 때 브랜치를 생성하여 작업합니다.
역할: 브랜치는 작업을 분리하고 관리할 수 있게 해주며, 여러 개발자들이 동시에 여러 작업을 수행할 수 있도록 도와줍니다. 브랜치를 사용하면 프로젝트의 주요 흐름을 방해하지 않고도 안전하게 변경 작업을 수행할 수 있습니다.

브랜치 관련 명령어
브랜치 생성
git branch <branch-name>
새 브랜치를 생성하지만, 생성된 브랜치로 이동하지는 않습니다.

브랜치 이동 및 생성
git checkout -b <branch-name>
새 브랜치를 생성하고, 동시에 해당 브랜치로 이동합니다.

브랜치 삭제
git branch -d <branch-name>
브랜치를 삭제합니다. 병합된 브랜치만 삭제할 수 있습니다. 병합되지 않은 브랜치를 삭제하려면 -D 옵션을 사용합니다.
git branch -D <branch-name>

브랜치 목록 확인
git branch
로컬 저장소에 존재하는 모든 브랜치를 확인할 수 있습니다. 현재 체크아웃된 브랜치는 별표(*)로 표시됩니다.

2. HEAD
설명: HEAD는 현재 체크아웃된 브랜치를 가리키는 포인터입니다. 현재 작업 중인 브랜치를 나타내며, 커밋을 수행하면 이 HEAD가 가리키는 브랜치에 변경 사항이 추가됩니다.
역할: 작업 위치를 제어하고 추적합니다. 예를 들어, main 브랜치에 있으면 HEAD는 main을 가리키고, 다른 브랜치로 이동하면 HEAD도 그 브랜치를 가리킵니다.

3. git checkout
설명: git checkout 명령은 다른 브랜치로 이동하거나 특정 커밋으로 워킹 디렉토리를 업데이트하는 데 사용됩니다.
역할: 프로젝트의 다른 상태나 브랜치로 전환할 수 있도록 도와줍니다. 브랜치 전환 시 HEAD가 해당 브랜치를 가리키게 됩니다.

git checkout 관련 명령어
브랜치로 이동
git checkout <branch-name>
지정된 브랜치로 이동합니다. HEAD도 이 브랜치를 가리키게 됩니다.

특정 커밋으로 이동 (Detached HEAD)
git checkout <commit-hash>
특정 커밋으로 이동하며, 이 상태에서는 HEAD가 어느 브랜치도 가리키지 않습니다. "detached HEAD" 상태로 커밋을 만들면 브랜치에 연결되지 않으므로, 주의가 필요합니다.

특정 파일 체크아웃
git checkout <branch-name> -- <file-path>
다른 브랜치에 있는 특정 파일을 현재 브랜치로 가져옵니다.

4. 브랜치 워크플로우 예시
새로운 기능을 개발하기 위해 feature라는 새 브랜치를 생성하고 이동합니다.
git checkout -b feature

feature 브랜치에서 코드를 작성하고 커밋합니다.
git add .
git commit -m "Add new feature"

작업이 끝나면 main 브랜치로 돌아가서 feature 브랜치를 병합할 수 있습니다.
git checkout main
git merge feature

병합이 완료되면 feature 브랜치를 삭제해도 됩니다.
git branch -d feature

요약
Branch는 독립적인 개발 라인입니다. 새 브랜치를 생성하여 작업을 분리하고, 필요에 따라 병합할 수 있습니다.
HEAD는 현재 작업 중인 브랜치를 가리킵니다. HEAD가 가리키는 곳에서 커밋이 추가됩니다.
git checkout은 브랜치나 특정 커밋으로 이동하는 데 사용됩니다. git checkout -b로 브랜치를 생성하고 이동할 수 있습니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git clone
설명: git clone은 원격 저장소(Remote Repository)를 복제하여 로컬 환경에 새로운 디렉토리를 생성하고, 해당 디렉토리에 저장소의 모든 이력을 가져옵니다. 이미 존재하는 Git 저장소를 복사하는 데 사용됩니다.
이용 방법: 주로 프로젝트를 시작하거나 다른 사람이 작업 중인 프로젝트에 참여할 때 사용합니다. 복제한 저장소는 자동으로 원격 저장소에 연결됩니다.
git clone <repository-url>
<repository-url>은 GitHub, GitLab, Bitbucket 등의 원격 저장소 URL입니다.
주요 특징:
원격 저장소의 모든 이력을 가져옵니다.
로컬 저장소를 자동으로 원격 저장소(origin)에 연결합니다.

git init
설명: git init은 현재 디렉토리를 새로운 Git 로컬 저장소로 초기화합니다. 프로젝트를 처음 시작할 때 사용되며, 이 명령을 실행하면 .git 디렉토리가 생성되어 Git이 해당 디렉토리와 하위 파일을 추적하게 됩니다.
이용 방법: 새로운 프로젝트를 시작할 때, 즉 기존에 Git이 없는 프로젝트를 Git 저장소로 만들고자 할 때 사용합니다.
주요 특징:
새 로컬 저장소를 초기화합니다.
원격 저장소를 연결하지 않으므로, 원격 저장소를 사용하려면 추가로 git remote add 명령을 사용해야 합니다.

origin이란?
설명: origin은 기본적으로 원격 저장소의 기본 이름을 나타냅니다. 로컬 저장소를 원격 저장소와 연결할 때 사용되며, git clone을 통해 저장소를 복제하면 자동으로 origin이라는 이름으로 원격 저장소가 설정됩니다.
역할: 원격 저장소의 URL에 대한 별칭 역할을 합니다. 원격 저장소와 상호작용할 때 더 간단한 이름으로 지정할 수 있습니다.
origin 설정 방법
설정하기: 이미 git init으로 로컬 저장소를 만들고 나서 원격 저장소를 연결하려면 git remote add 명령을 사용하여 origin을 설정할 수 있습니다.
git remote add origin <repository-url>
origin 변경하기
git remote set-url origin <new-repository-url>

요약
git clone: 원격 저장소를 복제하여 로컬에 새로운 저장소를 만듭니다. 자동으로 원격 저장소에 연결됩니다.
git init: 새 프로젝트를 시작하기 위해 로컬 저장소를 초기화합니다. 원격 저장소와 연결하려면 추가 설정이 필요합니다.
origin: 원격 저장소의 기본 이름입니다. 원격 저장소를 쉽게 참조하기 위한 별칭으로 사용되며, 원격 저장소를 설정하고 관리할 때 사용됩니다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

git reset은 Git에서 커밋의 위치를 변경하거나 파일의 상태를 변경하기 위해 사용되는 강력한 명령어입니다. reset 명령에는 크게 세 가지 유형이 있습니다: soft, mixed, hard. 이 각각은 워킹 디렉토리, 스테이징 영역, 커밋 히스토리에 대해 서로 다른 수준의 변경을 수행합니다.

1. git reset --soft
설명: --soft 옵션은 HEAD를 지정된 커밋으로 이동하지만, 워킹 디렉토리와 스테이징 영역은 그대로 유지합니다. 즉, 이동한 커밋 이후의 변경 사항이 스테이징 영역에 남아있게 됩니다.
사용 시나리오: 마지막 커밋을 취소하고 그 변경 사항을 스테이징 영역에 유지하고 싶을 때 사용합니다. 예를 들어, 커밋 메시지를 수정하고 싶을 때 유용합니다.
사용법:
git reset --soft <commit>
<commit>은 이동하고자 하는 커밋의 해시입니다.
동작:
HEAD 포인터만 이동합니다.
스테이징 영역과 워킹 디렉토리는 변경하지 않습니다.

2. git reset --mixed (기본 옵션)
설명: --mixed 옵션은 HEAD를 지정된 커밋으로 이동하고, 스테이징 영역을 초기화합니다. 즉, 이동한 커밋 이후의 변경 사항은 워킹 디렉토리에는 남아 있지만, 스테이징 영역에서는 제거됩니다.
사용 시나리오: 커밋을 취소하고 그 변경 사항을 워킹 디렉토리로만 되돌리고 싶을 때 사용합니다. 예를 들어, 특정 커밋을 취소하고 수정된 파일을 다시 선택적으로 스테이징하려는 경우에 유용합니다.
사용법:
git reset --mixed <commit>
<commit>은 이동하고자 하는 커밋의 해시입니다.
동작:
HEAD 포인터를 이동합니다.
스테이징 영역을 초기화합니다.
워킹 디렉토리는 변경하지 않습니다.

3. git reset --hard
설명: --hard 옵션은 HEAD를 지정된 커밋으로 이동하고, 스테이징 영역과 워킹 디렉토리를 모두 해당 커밋의 상태로 되돌립니다. 즉, 이동한 커밋 이후의 변경 사항을 모두 삭제합니다.
사용 시나리오: 커밋과 변경 사항을 완전히 삭제하고 워킹 디렉토리를 특정 커밋 상태로 되돌리고 싶을 때 사용합니다. 이는 매우 위험할 수 있으므로 신중하게 사용해야 합니다.
사용법:
git reset --hard <commit>
<commit>은 이동하고자 하는 커밋의 해시입니다.
동작:
HEAD 포인터를 이동합니다.
스테이징 영역과 워킹 디렉토리를 모두 해당 커밋 상태로 되돌립니다.
취소된 변경 사항은 복구할 수 없습니다(물론, git reflog을 사용하면 어느 정도 복구할 수 있지만 복잡합니다).

요약
git reset --soft: HEAD를 이동하며, 스테이징 영역과 워킹 디렉토리는 그대로 유지. 취소된 변경 사항을 스테이징 영역에 유지.
git reset --mixed: HEAD를 이동하고, 스테이징 영역을 초기화. 취소된 변경 사항은 워킹 디렉토리에 남음.
git reset --hard: HEAD를 이동하고, 스테이징 영역과 워킹 디렉토리를 모두 되돌림. 취소된 변경 사항을 완전히 삭제.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request와 Merge
1. Pull Request
설명: Pull Request(PR)는 GitHub, GitLab, Bitbucket과 같은 Git 호스팅 서비스에서 제공하는 기능으로, 변경 사항을 프로젝트에 병합하기 전에 리뷰와 논의를 진행할 수 있게 합니다. PR은 주로 협업을 위한 도구로 사용됩니다.
역할: 새로운 기능 추가나 버그 수정 등의 작업을 완료한 후 이를 프로젝트에 병합해달라고 요청할 때 사용합니다. 이 과정에서 팀원들이 코드를 검토하고, 의견을 제시하거나 수정 요청을 할 수 있습니다.
과정:
새로운 브랜치를 생성하여 작업을 진행합니다.
작업이 완료되면 해당 브랜치를 원격 저장소에 푸시합니다.
원격 저장소에서 Pull Request를 생성하여 병합 요청을 제출합니다.
팀원들이 PR을 검토하고 승인 또는 추가 수정을 요청합니다.
PR이 승인되면 해당 브랜치를 메인 브랜치(main 또는 master)에 병합합니다.

2. Merge
설명: Merge는 다른 브랜치의 변경 사항을 현재 브랜치에 통합하는 작업입니다. 예를 들어, feature 브랜치에서 새로운 기능을 개발한 후 이를 main 브랜치에 병합하여 프로젝트의 최신 상태로 만들 수 있습니다.
역할: 브랜치의 작업을 병합하여 프로젝트를 한 단계 발전시키고, 여러 개발자들의 작업을 하나로 모을 수 있습니다.

Merge의 두 가지 타입: Fast-Forward와 3-Way Merge
1. Fast-Forward Merge
설명: Fast-Forward Merge는 현재 브랜치에서 다른 브랜치로 변경 사항을 병합할 때, 현재 브랜치가 다른 브랜치의 선행 커밋인 경우에 발생합니다. 이 경우 브랜치의 커밋 이력이 선형이기 때문에, 단순히 HEAD 포인터를 앞으로 이동시키는 것으로 병합이 완료됩니다.
특징:
커밋 이력이 직선(선형)으로 유지됩니다.
병합 커밋이 생성되지 않습니다.
예시: main 브랜치에서 feature 브랜치를 생성하여 작업을 완료한 후 main 브랜치로 병합할 때, main 브랜치에 새로운 커밋이 없으면 Fast-Forward 병합이 가능합니다.

2. 3-Way Merge
설명: 3-Way Merge는 두 브랜치가 공통 조상 커밋이 있는 경우에 발생합니다. 즉, 두 브랜치에서 각각 커밋이 진행되어 Fast-Forward로 병합할 수 없는 상황에서 사용됩니다. 3-Way Merge는 두 브랜치의 최신 커밋과 공통 조상 커밋을 비교하여 병합을 수행합니다.
특징:
병합 커밋이 생성됩니다.
브랜치 이력이 비선형(그래프)으로 유지됩니다.
충돌이 발생할 수 있으며, 충돌이 발생하면 수동으로 해결해야 합니다.
예시: main 브랜치에서 feature 브랜치를 생성하여 작업하는 동안 main 브랜치에도 새로운 커밋이 추가된 경우.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

Rebase란?
git rebase는 한 브랜치의 변경 사항을 다른 브랜치 위에 다시 적용하여 커밋 이력을 재구성하는 Git 명령어입니다. 브랜치의 시작 지점을 새로운 베이스로 이동시켜, 깔끔하고 일관된 커밋 히스토리를 만들 수 있습니다. 단순히 병합(Merge)하는 것과는 달리, rebase는 커밋 이력을 다시 작성하여 프로젝트의 역사(Historical Record)를 정리할 때 유용합니다.

Rebase의 동작 방식
rebase를 수행하면 선택한 브랜치의 변경 사항이 다른 브랜치 위에 하나씩 순서대로 재적용됩니다. 이 과정에서 각 커밋은 새로운 커밋으로 생성되며, 기존의 커밋 해시는 변경됩니다. 이를 통해 브랜치의 커밋 이력을 깔끔하게 재구성할 수 있습니다.

Rebase가 유용한 경우
커밋 이력 정리:
rebase를 사용하면 커밋 이력을 깔끔하게 정리할 수 있습니다. 예를 들어, 여러 커밋이 하나의 기능과 관련되어 있고 이 커밋을 하나의 커밋으로 묶거나 다른 브랜치 위로 재정렬하고 싶을 때 유용합니다.
브랜치를 병합하면 비선형적인 그래프 구조를 갖게 되지만, rebase는 이력을 선형적으로 만들어 이력 추적을 용이하게 합니다.

팀 협업 시 변경 사항 적용:
협업 중인 프로젝트에서 다른 개발자의 최신 커밋을 자신의 브랜치에 통합할 때 유용합니다. 예를 들어, main 브랜치에 새로운 변경 사항이 푸시되었을 때, rebase를 통해 feature 브랜치의 커밋을 main 위로 재적용하여 병합 충돌을 최소화하고 최신 상태를 유지할 수 있습니다.

Pull Request 전에 이력 정리:
Pull Request(PR)를 제출하기 전에 rebase를 사용하여 커밋 이력을 정리하면 리뷰어가 변경 사항을 더 쉽게 이해할 수 있습니다. 예를 들어, 작업하는 동안 여러 번의 "작업 중" 커밋을 한 후, PR 전에 이들을 하나의 논리적인 커밋으로 합칠 수 있습니다.

Rebase와 Merge의 차이
Merge:
브랜치의 변경 사항을 통합하고, 새로운 병합 커밋을 생성하여 두 브랜치의 이력을 모두 유지합니다.
커밋 히스토리는 비선형(그래프) 구조를 갖게 됩니다.
Rebase:
한 브랜치의 변경 사항을 다른 브랜치 위에 재적용하고, 새로운 커밋으로 만들어 커밋 이력을 재구성합니다.
커밋 히스토리는 선형 구조가 되어 더 깔끔하고 이해하기 쉬워집니다.

Rebase의 주의 사항
공유된 브랜치에서 Rebase 금지: 이미 다른 사람과 공유한 브랜치에서 rebase를 사용하면 커밋 이력이 변경되어 다른 사람의 작업에 혼란을 줄 수 있습니다. 따라서 로컬 브랜치나 아직 공유되지 않은 브랜치에서만 사용하는 것이 안전합니다.
충돌 처리: rebase 중 충돌이 발생할 수 있으며, 이를 수동으로 해결해야 합니다. 충돌을 해결하고 나면 git rebase --continue를 사용하여 rebase 과정을 이어갑니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

Git Stash란?
git stash는 현재 작업 중인 변경 사항(수정된 파일이나 스테이징된 파일)을 임시로 저장해두고 워킹 디렉토리를 깨끗한 상태로 되돌리는 Git 명령어입니다. 나중에 언제든지 임시로 저장한 변경 사항을 다시 적용할 수 있습니다. 이는 브랜치를 전환하거나 다른 작업을 수행해야 할 때 유용합니다.

Git Stash 사용 방법
1. 변경 사항 임시 저장 (git stash)
설명: 현재 작업 중인 변경 사항을 스택(stack) 형태로 저장합니다. 워킹 디렉토리와 스테이징 영역의 모든 변경 사항이 저장되며, 워킹 디렉토리는 깨끗한 상태로 되돌아갑니다.
옵션:
특정 메시지를 추가하려면:
git stash save "작업 내용 설명"

스테이징된 파일만 저장하고 워킹 디렉토리의 변경 사항은 유지하려면:
git stash --keep-index

트래킹되지 않은 파일도 함께 저장하려면:
git stash -u

트래킹되지 않은 파일과 무시된 파일 모두 저장하려면:
git stash -a

2. 저장된 변경 사항 목록 보기 (git stash list)
설명: 현재 저장된 모든 스택을 확인합니다. 이 목록은 각 스택에 대해 인덱스를 표시하며, 가장 최근에 저장된 항목이 맨 위에 표시됩니다.

3. 저장된 변경 사항 적용 (git stash apply)
설명: 가장 최근에 저장된 변경 사항을 현재 브랜치에 다시 적용합니다. 이때, 스택에서 제거되지는 않고 그대로 남아있습니다.
옵션:
특정 스택을 적용하려면:
git stash apply stash@{2}

4. 저장된 변경 사항 적용 후 제거 (git stash pop)
설명: 가장 최근에 저장된 변경 사항을 적용하고, 스택에서 해당 항목을 제거합니다. 즉, git stash apply와 git stash drop을 한 번에 수행하는 명령입니다.

5. 특정 스택 삭제 (git stash drop)
git stash drop stash@{0}
설명: 특정 스택을 삭제합니다. 이 명령을 사용하여 불필요한 스택을 정리할 수 있습니다.

6. 모든 스택 삭제 (git stash clear)
설명: 저장된 모든 스택을 제거합니다. 이 명령은 한 번 실행하면 되돌릴 수 없으므로 주의해서 사용해야 합니다.

7. 새 브랜치로 스택 적용 (git stash branch)
git stash branch new-branch-name
설명: 새로운 브랜치를 생성하고, 스택의 변경 사항을 그 브랜치에 적용합니다. 이 명령은 주로 다른 브랜치에서 변경 사항을 적용하고자 할 때 유용합니다.

Git Stash 활용 상황
긴급한 버그 수정: 현재 작업 중인 변경 사항을 임시로 저장하고, 긴급하게 다른 버그를 수정해야 하는 경우 git stash를 사용하여 변경 사항을 저장하고 main 브랜치로 전환하여 버그를 수정할 수 있습니다.
브랜치 전환: 작업을 완료하기 전에 브랜치를 전환해야 할 때 변경 사항을 저장하여 안전하게 다른 브랜치로 이동할 수 있습니다.
이력 정리 및 리베이스: rebase 작업을 수행하기 전에 변경 사항을 임시로 저장하여 이력을 정리하고 나서 다시 변경 사항을 적용할 수 있습니다.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
git rebase --interactive(또는 git rebase -i)는 커밋 히스토리를 세밀하게 관리하고 편집할 수 있게 해주는 Git 명령어입니다. 이 명령어를 사용하면 커밋을 재정렬, 수정, 결합, 삭제할 수 있으며, 이를 통해 깔끔하고 의미 있는 커밋 히스토리를 만들 수 있습니다. 특히, 협업 프로젝트에서 Pull Request(PR)를 제출하기 전에 커밋 이력을 정리하는 데 유용합니다.
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.