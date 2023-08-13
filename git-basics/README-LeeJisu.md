# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
### git
- 오픈 소스 '버전 관리' 시스템
- local에서 버전 관리
- branch 생성 및 이전 branch로 복구, 삭제, 병합 가능
- 로컬 저장소를 사용하기 때문에 **다른 개발자와 실시간으로 작업 공유 불가능**
### github
- git repository를 위한 웹 기반 '호스팅' 서비스
- 클라우드 서버를 사용해서 local에서 버전 관리한 소스 코드를 업로드하여 **공유 가능**

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
### Working Directory
개발하는 위치(=어떤 프로젝트를 진행할 때 그 프로젝트가 위치하고 있는 공간)이다.
### Staging Area
commit을 수행할 대상 파일들이 위치하는이다. Working directory에 존재하는 파일을 'git add [파일명]'을 통해서 Staging Area으로 위치시킨다.
### Local Repo
로컬에 존재하는 Git directory(.git 폴더)로, 프로젝트의 메타 데이터나 commit 등의 정보가 저장되는이다.
### Remote Repo
실제 Github에 존재하는 Repository이다.

### Git Add
다음 변경(commit)을 기록할 때까지 변경분을 모아놓는 작업이다.
### Git Commit 
Staging Area에 저장되어 있는 변경 사항들을 로컬저장소에 등록하는 것이다. => 변경사항 확정
### Git Push
commit된 파일들을 원격(remote) 저장소에 모두 업로드하는 것이다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
### branch
branch는 독립적으로 어떤 작업을 진행하기 위한 개념이다. 필요에 의해 만들어지는 각각의 branch는 다른 branch의 영향을 받지 않기 때문에 여러 작업을 동시에 진행할 수 있다. 다른 branch와의 병합(Merge)을 통해 작업한 내용을 다시 새로운 하나의 branch로 모을 수도 있다.
- 생성 : git branch [브랜치명]
- 삭제 : git branch -D [브랜치명]
- 이동 : git checkout [브랜치명]
- 생성 + 이동 : git checkout -b [브랜치명]

### HEAD
HEAD는 현재 checkout된 branch의 '가장 최신' commit을 가리킨다. 따라서 branch를 변경하게 되면 변경한 branch의 가장 최신 commit을 가리키게 된다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

### git init
기존 프로젝트에 git을 초기화하는 명령으로, 로컬 저장소가 생기며 원격 저장소에 대한 정보(remote)는 없다. 

### git clone
반대로 'git clone'은 원격 저장소의 정보를 불러와 로컬 저장소를 생성하는 것이기 때문에 원격 저장소에 대한 정보가 있다.

### origin
원격 저장소를 의미한다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
### git reset –hard
- Working Directory와 Staging Area 모두 초기화

### git reset –mixed
- Working Directory 변경 X
- Staging Area 초기화 O

### git reset –soft
- Working Directory와 Staging Area 모두 변경 X

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
### Pull Request
사용자가 원격 저장소에 push하여 새로운 사항이 적용됐을 경우, 이를 다른 사용자에게 알리는 것을 말한다. 

### Merge
git branch를 다른 branch로 합치는 것이다.
- Fast-Forward : 
- 3-way Merge : 

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push/pull --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 `parent/child-1`, `parent/child-2`는 가질 수 있지만 `parent`, `parent/child`는 가질 수 없다. 무슨 이유 때문인지. 
- 리포지토리의 두 타입인 bare, non-bare

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.