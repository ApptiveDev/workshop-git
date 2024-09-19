1.
Git은 버전관리 소프트웨어. 사용자 컴퓨터에 로컬 저장소를 만들어 변경사항을 기록 및 관리
GitHub는 git을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스. git 저장소를 원격으로 관리할 수 있게 해줌

2.
working directory는 현재 작업 중인 파일들이 위치하는 저장소이고, staging area는 commit 될 파일들이 임시로 저장되는 곳이다. 
git add를 하면 working directory에서 수정된 파일들이 staging area로 이동하고, 어떤 변경 사항이 local repo에 commit될지 선택할 수 있다. 
local repo는 git이 버전 관리를 하는 저장소로, commit 이력이 저장되는 곳이다. git commit을 하면 staging area에 있는 파일들이 local repo로 이동하게 된다.
remote repo는 GitHub 같이 원격 서버에 저장된 git 저장소이다. 팀원들이 코드를 공유하고 협업할 수 있도록 해준다. git push를 하면 local repo의 commit된 부분을 remote repo로 전송하여 팀원들이 변경 사항을 확인하고 공유할 수 있도록 한다.
git pull은 remote repo의 변경 사항을 working directory에 병합하는 명령어로, 변경된 사항을 내 브랜치에 적용시킬 때 사용한다.