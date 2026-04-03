# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

1. Git
내 컴퓨터 안에서 코드의 변경 이력을 기록하고 관리하는 소프트웨어이다.
인터넷 연결 없이도 버전 관리(커밋)이 가능하다.
2. GitHub 
Git으로 관리한 프로젝트를 올리는 온라인 저장소이다.
내 컴퓨터의 코드를 푸시하여 백업하고 타인과 협업하는 공간이다



## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

1. Working Directory
실제 파일을 수정하고 있는 내 컴퓨터의 폴더로, Git이 아직 관리하지 않거나 수정 중인 현재 작업 영역이다.
2. Staging Area
커밋을 하기 위해 파일을 올리는 곳으로, git add 명령어를 통해 수정된 파일 중 기록할 것만 골라낸다.
3. Local Repository
내 컴퓨터 속 Git 저장하는 곳으로, git commit을 하면 버전 이력이 내 컴퓨터에 영구 저장된다.
4. Remote Repository
GitHub 같은 온라인 저장소이다. git push를 통해 내 컴퓨터의 기록을 서버로 전송하여 공유한다.



## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

1. Branch
독립적인 작업을 위해 만든 코드의 가지이다. 메인 줄기에서 뻗어 나와 서로 영향을 주지 않고 안전하게 새로운 기능을 개발할 수 있다.
2. HEAD
현재 내가 작업 중인 브랜치나 커밋을 가리키는 포인터이다. 내 작업 위치가 어디인지 Git에게 알려주는 역할을 한다.
3. Git Checkout
다른 브랜치로 이동하거나 특정 커밋 시점으로 되돌아갈 때 사용한다. HEAD의 위치를 옮겨 작업 환경을 전환하는 명령어이다.
생성: git branch [이름] - 새로운 가지를 만든다.
이동: git switch [이름] (또는 checkout) - 해당 브랜치로 작업 위치를 옮긴다.
목록 확인: git branch - 만들어진 브랜치 리스트를 확인한다.
삭제: git branch -d [이름] - 사용이 끝난 브랜치를 지운다.



## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

1. git init
새로운 Git 저장소를 내 컴퓨터 로컬에서 직접 만드는 명령어이다. 빈 폴더에서 실행하면 .git 폴더가 생성되며 이때부터 해당 폴더의 모든 변경 사항을 Git이 관리하기 시작한다.
2. git clone
GitHub 같은 원격 저장소 Remote에 이미 존재하는 프로젝트를 내 컴퓨터로 통째로 내려받는 명령어이다. 기존의 모든 커밋 이력과 설정이 함께 복사되어 즉시 작업을 시작할 수 있다.
3. origin
내 로컬 저장소와 연결된 원격 저장소의 기본 이름이다. 긴 서버 주소 URL을 매번 입력하기 번거롭기 때문에 origin이라는 별칭을 붙여서 사용한다.
연결: git remote add origin [URL]
내 로컬 폴더에 원격 저장소 주소를 origin이라는 이름으로 등록한다.
확인: git remote -v
현재 연결된 원격 저장소의 이름과 주소를 확인한다.
변경: git remote set-url origin [NEW_URL]
연결된 원격 저장소의 주소를 수정한다.
  


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

1. git reset --soft
커밋 내역만 취소하고 수정 파일과 add 상태는 유지한다.
커맨드: git reset --soft [COMMIT_ID]
2. git reset --mixed
커밋과 add 상태를 취소하고 수정 파일만 남겨둔다. 기본 설정값이다.
커맨드: git reset --mixed [COMMIT_ID]
3. git reset --hard
커밋, add 상태, 파일 수정 내역을 모두 지우고 특정 시점으로 복구한다.
커맨드: git reset --hard [COMMIT_ID]



## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

1. Pull Request
내가 작업한 브랜치의 변경 사항을 다른 사람들에게 검토받고 메인 코드에 합쳐달라고 요청하는 기능이다. 코드 리뷰를 통해 오류를 방지하고 협업의 품질을 높이는 단계이다.
2. Merge
서로 다른 브랜치에서 작업한 내용을 하나로 합치는 과정이다. 주로 기능 개발이 완료된 브랜치를 메인 브랜치에 통합할 때 사용한다.
3. Fast-Forward Merge
메인 브랜치에 새로운 커밋이 없어 단순히 HEAD 포인터를 최신 커밋으로 이동시키는 방식이다. 별도의 Merge 커밋이 생성되지 않고 기록이 일직선으로 남는다.
4. 3-Way Merge
두 브랜치가 공통 조상 이후 각자 다른 커밋을 가졌을 때 사용한다. 양쪽의 변경 사항과 공통 조상을 비교하여 합치며 새로운 Merge 커밋을 생성한다.



## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

1. git rebase
브랜치의 공통 조상이 되는 베이스 지점을 최신 커밋으로 변경하는 작업이다. 내 작업 내역을 대상 브랜치의 최신 커밋 뒤로 옮겨 붙여서 마치 한 줄로 작업한 것처럼 만든다.
복잡하게 갈라진 브랜치 기록을 깔끔한 일직선으로 정렬할 수 있다. 불필요한 머지 커밋을 줄여서 프로젝트의 히스토리를 파악하기 쉽게 만든다.



## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

1. git stash
현재 작업 중인 변경 사항을 잠시 "보관함"에 저장하고, 워킹 디렉토리를 최근 커밋 상태로 되돌릴 때 사용한다.
git stash 로 임시저장, git stash pop 로 실행하면 보관했던 변경 사항을 다시 불러와 작업을 이어할 수 있다.



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
