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
