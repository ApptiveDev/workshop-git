# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

> git은 로컬 소스코드의 버전 관리 시스템이다. github은 git으로 관리하는 소스코드를 업로드하여 
> 다른 사용자와 공유할 수 있는 원격 저장소이며, PR, Fork, Clone 등 협업에 필요한 기능을 제공하는 서비스이다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

> __Working Directory__: 현재 작업 중인 로컬 git 프로젝트의 디렉토리
> __Staging Area__: commit 이전에 변경 사항을 임시로 저장하는 공간.
> 
> __Local Repo__: 사용자의 개인 컴퓨터에 위치한 git 저장소.
> 
> __Remote Repo__: 원격 서버에 위치한 git 저장소. 
> 
> __Git Add__: Working Directory에서 변경 사항이 있는 파일들을 commit 이전에 Staging Area에 추가하는 것.
> 
> __Git Commit__: Staging Area에 추가된 변경 사항을 Local Repo에 영구적으로 저장하는 것. 변경 사항을 저장하는 하나의 기본 단위가 된다.
> 
> __Git Push__: Local Repo의 commit을 Remote Repo에 업로드하는 것.
> 
> __Git Pull__: Remote Repo의 최신 commit들을 Local Repo에 불러와 변경 사항을 합치는 것.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

> __commit__ 은 프로젝트의 변경 사항을 저장하고 관리하는 기본 단위. 현재 작업 중인 커밋의 지시자를 HEAD라고 한다.
> __branch__ 는 코드의 특정 commit을 가리키는 지시자이자, 배포 가능한 코드의 안정성을 유지하면서 독립적인 개발 흐름을 만들 수 있도록 해준다.
> 
> 프로젝트를 진행하던 도중 새로운 기능을 만들어야 하는 경우를 가정해보자.
> 기존 프로젝트에 새로운 기능을 추가하려면, 배포 가능한 현재 코드와 독립된 개발 흐름을 만들기 위해 브랜치를 생성해야 한다.
> feature/new-feature (이하 feature 브랜치) 이라는 이름의 브랜치를 생성하려면 Working Directory에서 해당 명령을 실행하면 된다.
> ```bash
> git branch feature/new-feature
> ```
> 브랜치를 생성했다면, master브랜치가 아닌 new-feature 브랜치에 변경 사항(커밋)을 저장하기 위해 feature 브랜치로 이동해야 한다.
> 아래 명령어를 통해 feature 브랜치로 이동할 수 있고, 이동한 시점 이후의 커밋은 모두 feature 브랜치에 쌓인다.
> ```bash
> git checkout feature/new-feature
> ```
> 
> 위의 과정을 한 번에 통합할 수도 있다.
> ```bash
> git checkout -b feature/new-feature
> ```
> 새로운 기능이 완성되고 변경사항을 모두 커밋했다면, 안정성 테스트를 거친 후 master 브랜치로 다시 돌아와 feature 브랜치와 병합하여 
> 변경 사항을 적용할 수 있다. 
> 
> ```bash
> git checkout master(main)
> git merge feature/new-feature
> ```
> 위 명령어가 실행되면 HEAD에 해당하는 feature 브랜치의 모든 변경사항이 master브랜치에 적용된다.
> 기능구현이 모두 끝난 후 생성했던 브랜치를 삭제할 수 있다. 이는 권장 사항이며 필수는 아니다.
> 
> ```bash
> git branch -d feature/new-feature
> ```


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

> __git init__ 은 현재의 디렉토리를 git 레포로 초기화하는 것이다.
> 주로 빈 git 프로젝트를 새로 생성하거나 기존의 프로젝트를 git을 사용하여 관리하고 싶을 때 사용한다.
> 
> __git clone__ 은 이미 존재하는 원격 git 레포를 복제하여 로컬에 저장하는 것이다. 이때의 원격 저장소를 origin이라고 하고,
> origin은 git clone 명령어를 실행한 시점에 자동으로 설정된다.
> 
> origin이 지정되지 않은 로컬 저장소의 경우 아래 명령어로 프로젝트에 origin을 추가할 수도 있다.
> ```bash
> git remote add origin <원격 레포 url>
> ```
> 
> 또는 기존에 존재하던 origin이 다른 url을 가리키도록 변경할 수도 있다.
> ```bash
> git remote set-url origin <새로운 원격 리포지토리 url>
> ```
> 
> 변경 사항을 조회하려면 `git remote -v` 명령어를 사용할 수 있다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

> git reset 명령어는 기본적으로 HEAD를 특정 커밋으로 이동시키는 명령어이다. 
> 
> ```bash
> git reset [<mode>] [<commit>]
> ```
> git reset의 mode 인자에는 세 가지 값이 들어갈 수 있는데, --hard, --soft, --mixed이다.
> 지정되지 않은 경우 기본값으로 --mixed가 적용된다.
> commit 인자는 이동하려는 커밋 식별자(커밋 해쉬, 브랜치, 태그 이름)를 값으로 가진다. 기본값은 HEAD이다.
> 
> `--soft`는 HEAD를 지정된 커밋으로 이동시켜 현재 작업중인 커밋을 해당 커밋으로 설정하지만 Staging Area와 Working Directory의
> 변경사항은 그대로 남는다. 예를 들어, HEAD A라는 시점으로 --soft 모드를 사용하여 이동한 경우 A 이후의 변경 사항이 Staging Area에 올라간
> 상태가 되고, 그 상태에서 커밋할 경우 A 시점 이후의 커밋들이 하나로 합쳐지게 된다.
> 
> `--mixed`는 HEAD와 Staging Area를 지정된 커밋으로 이동시키지만 Working Directory의 변경사항은 그대로 유지된다. 따라서
> Working Directory의 변경사항은 Unstaged 상태가 된다.
> 
> `--hard`는 HEAD와 Staging Area, Working Directory를 모두 지정된 커밋의 상태로 이동시킨다. 로컬에서 지정된 커밋 이후의
> 모든 변경 사항은 삭제된다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

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
