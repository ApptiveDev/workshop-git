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

> __Pull Request__ 는 하나의 브랜치에 다른 브랜치를 병합(Merge) 하기 위해 요청하는 기능이다. 주로 Github, GitLab등의 서비스에서 제공하는
> 기능이다.
> 
> __Merge__ 는 서로 다른 두개의 브랜치를 합치는 것이다. Fast-Forward Merge, 3-Way Merge라는 병합 방식이 사용된다.
>
> __Fast-Forward__ 는 기존 브랜치보다 병합하려는 브랜치의 커밋이 더 앞서는 경우 사용되는 방식으로, 별도의 병합 커밋이 생성되지 않고
> 변경 사항이 그대로 브랜치에 적용된다.
> 
> 3-Way Merge는 병합하려는 두 브랜치에서 특정 시점 이후로 서로 다른 변경사항이 발생한 경우 사용하는 병합 방식이다.
> 가장 최근의 _공통된_ 커밋을 기준으로 두 브랜치의 변경 사항을 비교하여 병합된 하나의 새로운 커밋을 생성한다.
> 두 브랜치에서 서로 같은 파일의 같은 라인을 다르게 수정했거나, 한 브랜치에서 삭제한 파일을 다른 브랜치에서 수정한 경우에는 충돌이 발생하게 된다.
> 
> 충돌이 발생한 경우 git은 병합을 중지하고 개발자에게 수정을 요청한다. Staging 영역에 수정이 완료된 파일을 올리고 commit하면 병합 과정이 완료되고
> 병합 커밋이 생성된다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

> __rebase__ 는 한 브랜치의 커밋을 다른 브랜치 위로 적용하는 과정이다. merge의 경우 변경사항이 한 번에 통합되지만, rebase는
> 변경 사항까지의 커밋 내역이 대상 브랜치의 최신 커밋 위에 순차적으로 적용된다.
> 
> a라는 브랜치를 생성하여 로컬에서 작업하던 도중 다른 브랜치인 b에서 변경 내용이 발생했고 a 브랜치에 적용해야 하는 경우,
> rebase 명령어를 통해 로컬의 작업 내용을 유지한 채로 b 브랜치의 변경 내용을 적용할 수 있다.
> 
> 위에서 설명한 Merge와 마찬가지로 충돌이 발생할 수 있다. Merge의 경우 두 브랜치를 병합하는 도중 한 번만 충돌이 발생하지만, Rebase의 경우
> 순차적으로 커밋을 검토하므로 충돌이 여러 번 발생할 수 있다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

> git stash는 Git에서 제공하는 임시 저장 기능으로, Staging Area와 Working Directory에 저장된 변경 사항을 임시로 저장하고 
> HEAD 상태로 되돌리는 기능이다. 
> 
> 이 기능은 특정 브랜치에서 작업하던 도중 다른 브랜치로의 전환이 필요한 경우 유용하게 쓰일 수 있다.
> 가령 a 브랜치에서 작업하던 도중 b 브랜치에서 수정해야 할 부분이 생긴 경우, a의 변경 사항을 stash로 임시 저장하고
> b 브랜치로 이동해서 작업할 수 있다. 작업이 끝나면 a 브랜치에서 stash를 통해 임시 저장된 내용을 복원하여 계속 작업할 수 있다.
> 
> git stash <save|push>: 현재의 변경 사항을 스택에 저장
> git stash list: 저장된 stash 목록을 보기
> git stash apply: 가장 최근에 저장된 stash의 변경 사항 적용. 적용된 stash는 스택에서 제거되지 않음
> git stash pop: 가장 최근에 저장된 stash의 변경 사항을 적용하고 해당 stash를 스택에서 제거
> git stash drop [stash@{n}]: 지정된 stash를 스택에서 제거
> git stash clear: 스택에 존재하는 모든 stash 제거
> git stash branch <branchname>: 새로운 브랜치를 생성하고 해당 브랜치에 stash의 변경 사항 적용

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

### ChatGPT를 통해 생성한 답변을 바탕으로 이해한 내용
> **`git rebase --interactive`:**
> - interactive rebase는 사용자가 커밋의 순서를 변경하거나, 커밋을 합치거나, 커밋을 삭제하거나,
> - 커밋 메시지를 수정하는 등의 작업을 수행할 수 있게 해주는 도구입니다.
>
> **branch의 upstream:**
> - 브랜치의 upstream은 로컬 브랜치가 추적하는 원격 브랜치를 의미합니다. `git push --set-upstream` (또는 `-u` 옵션)을 사용하여 
> 로컬 브랜치와 원격 브랜치 간의 추적 관계를 설정할 수 있습니다.
>
> > 원래라면 자동으로 origin/branch-1이라는 원격 브랜치와 branch-1이라는 로컬 브랜치가 연결되어 있지만, 자동으로 연결된 브랜치 외의
> > 다른 브랜치로 변경 사항을 커밋하고 싶다면 upstream을 변경하면 되는 것 같다. 근데 안써봐서 와닿지는 않는다.
>
> **Fork와 PR:**
> - Fork는 다른 사람의 리포지토리를 자신의 계정으로 복사하는 것을 의미합니다. Fork는 원본 리포지토리에 직접적인 변경 권한이 없을 때 유용하며,
> - Fork한 리포지토리에서 변경 사항을 만든 후 원본 리포지토리에 Pull Request를 통해 변경 사항을 제안할 수 있습니다.
>
> > push/merge 권한이 없는 제 3자가 자신의 계정으로 레포를 복제하여 
> > 개발을 이어나갈 수 있도록 하는 중요한 기능이라고 알고 있다.
>
> **`git fetch` vs `git pull`:**
> - `git fetch`는 원격 리포지토리의 변경 사항을 로컬로 가져오지만 자동으로 병합하지 않습니다.
> > 궁금해서 찾아본 결과, git fetch로 가져온 변경 사항은 Staging area나 Working directory에는 영향을 주지 않고
> > 로컬 레포의 원격 브랜치 참조에 저장된다고 한다. 
> 
> > 원격 브랜치 참조는 원격 레포의 상태를 로컬에서 추적하기 위해 있는 포인터라고 하는데 써본적이 없어서 왜 있는지 와닿지는 않는다.
> 
> - `git pull`은 `git fetch`와 `git merge`의 조합으로, 원격 리포지토리의 변경 사항을 가져와서 자동으로 현재 브랜치에 병합합니다.
> - `git fetch`는 원격 변경 사항을 확인하고 싶지만 아직 병합하고 싶지 않을 때 사용됩니다.
>
> **`reset --hard`와 `push/pull --force`:**
> - `git reset --hard`는 HEAD, Staging Area, Working Directory를 특정 커밋 상태로 되돌립니다.
> - `--force` 옵션은 Git의 안전 장치를 무시하고 강제로 push나 pull을 수행합니다. 주의해서 사용해야 합니다.
> 
> > `git reset --hard`는 특정 시점 이후의 모든 것이 완전히 잘못돼서 정말 복구할 수 없게 됐을 때 써본 경험이 있다.
> > 특정 커밋 이후의 모든 변경 사항이 사라지므로 주의해서 사용해야 한다는 것은 이미 알고 있었다.
>
> **`.gitignore`:**
> - `.gitignore` 파일은 Git이 추적하지 않아야 할 파일 또는 디렉토리 패턴을 지정하는 데 사용됩니다.
> 
> > 변경 사항이 있는 모든 파일을 스테이징 영역에 추가하는 git add -A를 실행하더라도, .gitignore에 존재하는 패턴을 갖는 파일 또는 디렉터리는
> > 스테이징 영역에 추가되지 않는다.
> 
> > node로 채팅봇을 개발하던 도중 .gitignore에 node_modules 폴더를 깜빡하고 추가를 안 한 채로 모든 파일을 스테이징 영역에 추가한 후
> > 커밋했다가 변경 사항에 파일 수백개가 있었던 경험이 있었다. 끔찍했다.
>
> **브랜치 이름 제한:**
> - `parent/child-1`와 같은 브랜치 이름은 가능하지만, `parent`와 `parent/child`를 동시에 가지는 것은 불가능합니다. 
> - 이는 `parent`가 파일로도, 디렉토리로도 해석될 수 있기 때문에 혼란을 초래할 수 있습니다.
>
> **리포지토리의 두 타입: bare, non-bare:**
> - **bare 리포지토리**: 워킹 디렉토리가 없는 Git 리포지토리. 주로 서버에서 사용됩니다.
> - **non-bare 리포지토리**: 워킹 디렉토리가 있는 일반적인 Git 리포지토리. 개발자들이 일반적으로 사용하는 리포지토리 형태입니다.

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
