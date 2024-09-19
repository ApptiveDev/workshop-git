1.
Git은 버전관리 소프트웨어. 사용자 컴퓨터에 로컬 저장소를 만들어 변경사항을 기록 및 관리
GitHub는 git을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스. git 저장소를 원격으로 관리할 수 있게 해줌

2.
working directory는 현재 작업 중인 파일들이 위치하는 저장소이고, staging area는 commit 될 파일들이 임시로 저장되는 곳이다. 
git add를 하면 working directory에서 수정된 파일들이 staging area로 이동하고, 어떤 변경 사항이 local repo에 commit될지 선택할 수 있다. 
local repo는 git이 버전 관리를 하는 저장소로, commit 이력이 저장되는 곳이다. git commit을 하면 staging area에 있는 파일들이 local repo로 이동하게 된다.
remote repo는 GitHub 같이 원격 서버에 저장된 git 저장소이다. 팀원들이 코드를 공유하고 협업할 수 있도록 해준다. git push를 하면 local repo의 commit된 부분을 remote repo로 전송하여 팀원들이 변경 사항을 확인하고 공유할 수 있도록 한다.
git pull은 remote repo의 변경 사항을 working directory에 병합하는 명령어로, 변경된 사항을 내 브랜치에 적용시킬 때 사용한다.

3.
Commit은 파일의 특정 상태를 저장한 스냅샷이다. 
Branch는 commit의 포인터이며. 독립적으로 작업할 수 있는 경로이다. 즉, 특정 commit을 가리키는 것이다.
HEAD는 현재 체크아웃된 branch를 가리키는 포인터, 즉 현재 작업 중인 branch 혹은 commit을 가리킨다. branch는 commit을 가리키는 포인터이므로, HEAD는 branch를 통해 간접적으로 commit을 가리키고 있는 것.
checkout은 다른 branch로 이동하거나 특정 commit으로 이동하는데 사용된다.

4.
git clone은 remote repo의 전체 내용을 복사하여 local repo를 생성하는 명령어이다.
git init은 새로운 빈 repo를 생성하는 명령어이다. 현재 디렉토리가 git repo로 초기화 하며 새로운 프로젝트를 시작할 때 주로 사용한다.
origin은 remote repo의 기본 이름을 의미하며 git clone을 통해 저장소를 복제할 때 기본적으로 설정된다.

5.
soft reset은 커밋을 되돌리면서 변경 사항은 staging area에 그대로 남아있게 한다.
mixed reset은 커밋을 되돌리면서 변경 사항을 staging area에서 제거하지만, working directory에 남아있게 되어 수정할 수 있게 한다.
hard reset은 staging area와 working directory 모두에서 변경 사항이 삭제되며 해당 commit 상태로 되돌린다.

6.
pull request는 한 브랜치에서 발생한 변경 사항을 다른 브랜치에 적용하기 위한 요청이다.
merge는 두 개의 브랜치를 통합하는 가정으로, 한 브랜치에서 발생한 변경 사항을 다른 브랜치에 적용한다.
fast-forward merge는 변경 사항이 직선적으로 이루어져, 브랜치의 HEAD 포인터를 단순히 이동시킨다.
3-way merge는 두 브랜치가 서로 다른 commit을 가지고 있을 때 발생하며, 두 브랜치의 변경 사항을 비교하고 새로운 commit을 생성하여 두 브랜치의 변경 사항을 통합한다.