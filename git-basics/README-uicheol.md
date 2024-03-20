# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

local(로컬): 개발자가 작업하는 자신의 컴퓨터 환경을 의미함.
remote(원격): 다른 컴퓨터에 위치한 git 저장소로 github같은 서비스를 통해 호스팅됨. 다른 개발자와 협업을 가능하게함.

git: 분산 버전 관리 시스템으로 소스코드의 변경사항을 추적, 관리하는 도구임. 개발자는 git을 사용해 로컬에서 프로젝트를 관리할 수 있다.
github: git 저장소를 호스팅하고 협업하는 웹 플랫폼으로 원격 저장소를 만들고 프로젝트를 공유하며 협업할 수 있다.

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

1. working directory

- 개발자가 실제 파일을 작업하는 디렉토리

2. staging area

- 변경된 파일을 임시로 준비하는 공간, 차후 commit할 변경사항들을 담고있다.

3. local repository

- staging area의 변경사항을 저장하는 레포지토리, 개발자의 컴퓨터에 위치한다.
- git commit 명령어를 통해 staging area에 있는 변경사항을 로컬에 저장한다.

4. remote repository

- github의 레포지토리를 의미
- git push 명령어를 통해 local repository에 저장해둔 변경사항을 remote repository(github)에 올려준다.

1. git add

- 변경사항을 staging area에 추가함.

2. git commit

- staging area에 추가된 변경사항들을 local repository에 저장함.

3. git push

- local repo에 있던 변경사항을 remote repo(github)에 올림.

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

1. branch

- 코드의 분기를 나타내는 개념, 작업을 독립적으로 진행시키기 위해 브랜치를 생성한다.
- 브랜치는 만들거나 삭제, 이동이 가능함.
  '''
  생성: git branch <branch name>
  삭제: git branch -d <branch name>
  이동: git checkout <branch name>
  생성 및 이동: git checkout -b <branch name>
  '''

2. HEAD

- 현재 작업중인 커밋의 상태를 가리키며, 변경사항을 추가하거나 커밋할 때 사용됨.

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

1. git clone

- remote repo(github)의 프로젝트를 local repo로 클론함.
- 이때 origin은 remote repo의 기본 이름임.

2. git init

- 새로운 local repo를 생성함. 이미 존재하는 프로젝트를 git으로 관리하려거나, 새로운 프로젝트를 시작할때 로컬 디렉토리를 git 저장소로 초기화할때 사용함.
- 현재 디렉토리를 git 저장소로 초기화하며, '.git'이라는 폴더가 생성됨.

3. origin

- git에서 remote repo의 기본 이름이다. git clone을 할 때 remote repo의 이름이 origin으로 자동 설정됨.
- origin은 remote repo의 url 변수이다.
- git remote add origin <repoitory url> 을 통해 remote repo url을 설정할 수 있다.

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

reset은 되돌아가는 것이다.
3가지는 working directory, staging area, repo가 어디까지 되돌아가는가에 따라 다르다.

1. git reset --soft

- working directory: 그대로 남음
- staging area: 그대로 남음
- repo: 이전 상태

2. git reset --mixed

- working directory: 그대로 남음
- staging area: 이전 상태
- repo: 이전 상태

3. git reset --hard

- working directory: 이전 상태
- staging area: 이전 상태
- repo: 이전 상태

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

pull request

- 다른 branch에서 작업한 내용들을 기존 코드에 병합하기 전 리뷰와 토론을 요청하는 기능.
- 변경사항에 대해 검토가 완료되면, 병합될 수 있다.

merge

1. fast-forward merge

- main branch에 신규 커밋이 없는 경우, branch의 최신 커밋을 main branch으로만 바꿔주면 간단하게 merge를 진행할 수 있다.

2. 3-way merge

- main branch와 나의 branch에 각각 신규 커밋이 있을 때, main에 새로운 commit을 생성하면서 각 branch의 신규 커밋들을 합쳐준다.

## rebase

![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

rebase

- git에서 branch의 위치를 재정렬 하는 것을 말함.
- branch를 깔끔하게 정리하는데 좋다.
- rebase 후 fast-forward merge를 해서 branch를 정리한다.
- 아래 명령어로 branch를 main으로 rebase 후 fast-forward merge 할 수 있다.
  '''
  git checkout <branch name>
  git rebase main
  git checkout main
  git merge <branch name>
  '''

## stash

![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

1. 임시로 변경사항을 저장하고 다른 작업 수행

- 현재 작업중인데 다른 branch로 이동해야하는 경우, 변경사항을 commit하지 않고 다른 branch로 이동가능.
- 'git stash'를 이용해 변경사항을 임시로 저장한 후 다른 branch로 이동하고, 작업 수행 후 stash에 있는 변경사항을 다시 가져올 수 있다.

2. 작업중인 변경사항을 정리하고 임시로 저장

- 여러개의 파일을 수정하고 있을 때, 일부 변경사항을 commit 하기전 다른 변경사항을 진행해야하는 경우, 변경사항을 'git stash'를 사용해 작업중인 파일을 임시로 저장할 수 있다.

3. 변경사항을 임시로 저장하고 충돌 해결

- merge나 rebase를 수행하는 동안 conflict가 발생하는 경우, 충돌을 해결하기 전 변경사항을 'git stash'로 임시로 저장할 수 있다.
- 충돌을 해결한 후 변경사항을 다시 적용할 수 있다.

`git stash`
: 현재 작업 중인 변경사항을 스택에 임시로 저장

`git stash list`
: stash list 확인

`git stash pop`
: 가장 최근 stash를 pop해 적용함

`git stash apply <stash_id>`
: 특정 stash를 적용

`git stash drop <stash_id>`
: 특정 stash 삭제

`git stash clear`
: 모든 stash 삭제

## Advanced

다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다.

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
