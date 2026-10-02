Git 기초
Git != Github
Git과 Github는 같은 것이 아니다.
Git은 내 컴퓨터의 파일 변경 이력을 관리하는 버전 관리 도구이고,
Github는 Git으로 관리하는 프로젝트를 인터넷에 저장하고 다른 사람과 공유할 수 있게 해주는 원격 저장소 서비스이다.
즉,
- Local: 내 컴퓨터에 있는 Git Repository
- Remote: Github와 같이 인터넷에 존재하는 Repository
라고 생각할 수 있다.
Git만 사용해서 내 컴퓨터 안에서 버전을 관리할 수도 있지만, Github를 사용하면 다른 사람과 코드를 공유하거나 협업하기 편해진다.
예를 들어 내 컴퓨터에서 코드를 수정하고 commit한 뒤,
git push
를 사용하면 Github와 같은 Remote Repository에 변경 내용을 업로드할 수 있다.

Git Workflow
Git에서 파일은 크게 다음 과정을 거쳐 관리된다.
Working Directory → Staging Area → Local Repository → Remote Repository
Working Directory
현재 실제로 파일을 작성하거나 수정하고 있는 공간이다.
예를 들어 index.html을 수정하면 아직 Git에 저장된 것은 아니고 Working Directory에 변경 사항이 존재하는 상태이다.
변경 상태는 다음 명령어로 확인할 수 있다.
git status

Git Add
git add 파일명
또는
git add .
을 사용한다.
Working Directory에서 수정한 파일을 Staging Area에 올리는 명령어이다.
Staging Area는 다음 commit에 포함할 파일을 미리 선택해두는 공간이라고 이해했다.
예를 들어 여러 파일을 수정했더라도 특정 파일만 git add하면 해당 파일만 다음 commit에 포함시킬 수 있다.

Git Commit
git commit -m "메시지"
Staging Area에 올라온 변경사항을 하나의 버전으로 저장한다.
commit에는 고유한 ID가 생성되기 때문에 이전 상태를 확인하거나 돌아갈 수 있다.
예를 들어
git commit -m "로그인 기능 추가"
와 같이 해당 commit에서 무엇을 변경했는지 알아볼 수 있는 메시지를 함께 작성한다.
commit 기록은 다음 명령어로 볼 수 있다.
git log

Git Push
git push
Local Repository에 저장한 commit을 Github와 같은 Remote Repository로 전송하는 명령어이다.
즉,
파일 수정
↓
git add
↓
git commit
↓
git push
순서로 작업한다고 이해했다.