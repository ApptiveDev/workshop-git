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
