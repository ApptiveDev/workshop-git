# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git : 내 컴퓨터에 소스 코드의 버전을 관리해 주는 버전 관리 시스템 프로그램. 즉, 로컬에서 코드의 변경 이력을 추적하고 저장한다.

github : git으로 관리하는 저장소를 온라인 공간에 올려두고 다른 사람들과 협업할 수 있게 해주는 원격 클라우드 호스팅 서비스이다. 이때 인터넷 서버에 만들어준 클라우드 백업 공간을 remote라고 한다 


## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

working directory : 현재 코드를 작성하고 수정하는 실제 작업 공간이다. 예를 들면 VS code의 에디터 화면이 working directory라고 할 수 있다

git add : staging area 기능. 다음 버전에 포함시킬 파일들만 골라서 모아두는 임시 대기실이다.

git commit : local repository 기능. git add로 올라온 대기실에 올라온 파일들의 스냅샷을 찍어 하나의 버전으로 로컬 저장소에 영구히 기록한다.

git push : remote repository 기능. 내 컴퓨터에 기록된 커밋들을 깃허브 같은 원격 저장소로 업로드하여 다른 사람들과 공유한다. 


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

branch : 기존 코드에 영향을 주지 않고 새로운 기능 개발이나 버그 수정을 하기 위해 뻗어나온 독립적인 작업 공간이다.

HEAD : 현재 내가 위치해 있는 branch나 commit을 가리키는 포인터다.

관련 명령어
    1. git branch <브랜치명> : 새로운 브랜치 생성한다.
    2. git checkout <브랜치명> : HEAD를 해당 브랜치로 이동한다. (git switch 로도 사용할 수 있다)
    3. git branch -d <브랜치명> 브랜치 삭제한다.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
  
git init : 현재 내 컴퓨터에 있는 일반 폴더를 새로운 git 저장소로 초기화할 때 사용한다. (아직 github와 연결되지 않은 상태일때 사용)

git clone : github 등에 이미 존재하는 원격 저장소를 내 컴퓨터로 복제해 올 때 사용한다. 폴더 생성부터 초기화, 원격 연결까지 한 번에 처리된다. 

origin : 원격 저장소의 UFL을 매번 입력하기 번거롭기 때문에 이를 대체하기 위해 사용하는 기본 별칭이다.
-> git remote add origin <URL>로 사용할 수 있다


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

1. --soft : 커밋 이력만 되돌린다. 따라서, 수정했던 파일들은 대기실에 git add 된 상태 그대로 남아있다
2. --mixed : 기본값이다. 커밋 이력을 되돌리고 파일들을 대기실에서 내린다 파일 들의 수정내역은 working directory에 남아있어서 다시 add 할 수 있다
3. --hard : 커밋 이력을 되돌리고 수정했던 파일 내역까지 완전히 삭제해서 과거의 상태로 똑같이 맞춘다



## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

pull request : 내가 작업한 브랜치를 원격 저장소에 push한 뒤 팀원에게 코드를 리뷰 한 후 메인 브랜치에 합쳐달라고 요청하는 것

merge : 두 개의 브랜치를 하나로 합치는 작업이다
 - 1. Fast-Forward : 기준 브랜치에 새로운 커밋이 없다면 단순히 기준 브랜치의 HEAD를 내 브랜치의 최신 커밋으로 이동시키기만 하는 것
 - 2. 3-way merge : 두 브랜치가 각각 커밋이 진행되었다면 두 갈래의 변경 사항을 모두 합친 새로운 merge 커밋을 생성하여 병합한다. 

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

rebase : 브랜치의 베이스를 다시 설정하는 명령어. 이 때 베이스는 시작점을 말한다. 시작점을 메인 브랜치의 가장 최신 커밋으로 끌어다 옮긴다
-> 3-Way Merge 커밋이 무수히 생겨 git 히스토리가 복잡해지는 것을 방지하고 히스토리를 한 줄로 깔끔하게 정리하고 싶을 때 사용한다. (특히 깔끔하게 pull request 할 때 사용)


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

git stash L: 하던 작업을 임시 서랍에 보관하는 기능
-> 코드가 완성되지 않았거나 작업 중 급하게 다른 브랜치로 넘어가 버그를 수정해야할 때 git stash를 하면 아직 커밋하지 않은 변경 사항들이 임시 저장된다. 이후 다시 돌아와 git stash pop을 하면 보관했던 작업물을 다시 꺼내올 수 있다. 


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
