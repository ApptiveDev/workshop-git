# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

***Git***은 `local`의 개념이고, ***GitHub***는 `remote`의 개념입니다.

> ***Git***

파일의 변경사항을 시간에 따라 추적하는 버전 관리 시스템(Version Control System)입니다.
이것을 통해 이전 버전으로 되돌아가거나, 수정사항을 비교, 프로젝트에 여러 사람들과 함께 공동작업이 가능합니다.

- **저장소(Repository/Repo)**
: 저장소는 파일과 그들의 수정 기록의 모음입니다. 
로컬 저장소는 여러분의 기계에, 원격 저장소는 서버에 호스팅됩니다.


> ***GItHub***

Git 저장소를 호스팅하는 웹 기반 플랫폼입니다.
Git 위에 GUI를 추가하고 협업을 위한 추가 기능을 제공합니다.

**원격 저장소(Remote Repository)**
: 코드를 중앙 서버에 저장하고 여러 개발자가 공유하며 작업하기에 용이합니다.


## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

 Git은 작업을 하는 공간, 임시로 저장하는 공간, 실제로 저장하여 기록하는 공간으로 나눌 수 있습니다.

> ***Working Directory***

작업을 하는 공간으로, 로컬 저장소에 접근할 수 있으며,
실제로 파일을 생성하고 수정하는 공간입니다.
워킹 디렉토리 내부 파일들은 *untracked*와 *tracked*로 구분됩니다.
- *tracked*는 *unmodified*와 *modified*로 나눌 수 있습니다. 

> ***Git Add***

commit의 전단계로서, commit을 하고자 하는 파일들은
commit하기 전에 add를 해줘야 commit할 수 있습니다.
```git add.``` 명령어를 사용해서 모든 변경사항을 add 할 수 있습니다.

> ***Git Commit***

git에 저장하는 단계입니다.
commit을 한 곳으로 언제든지 다시 돌아올 수 있기 때문에
코드의 추가, 삭제가 자유로워질 수 있습니다.
```git commit -m "커밋 메시지 작성"```를 이용해서 commit을 할 수 있습니다.

> ***Git Push***

로컬 저장소에 커밋된 내용 중 원격 저장소에 반영되지 않은 작업들을 원격 저장소에 적용하는 것입니다.
```git push```나 ```git push <원격 저장소 이름> <브랜치 이름>```을 이용하면 해당 브랜치의 원격 저장소에 적용할 수 있습니다.


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

티스토리(https://charles098.tistory.com/24)

> ***Branch***

독립적으로 어떤 작업을 진행하기 위한 개념입니다.
Git Branch를 활용하면, 코드를 통째로 복사한 후, 원래 코드에 영향을 주지 않고 독립적으로 개발할 수 있습니다.

> ***HEAD***

HEAD는 브랜치를 통해 간접적으로 커밋을 가리키고 있습니다.
커밋을 하면 HEAD가 가리키는 브랜치가 최신 커밋으로 이동하게 됩니다.
`git checkout -b`을 하면 HEAD가 다른 브랜치를 가리키게 됩니다.
브랜치를 변경하면서 서로 다른 흐름에서 커밋을 하는 것을 *분기한다*라고 합니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

> ***clone***

Git 저장소를 복제하는데 사용되는 명령어입니다.
원격 저장소(remote repository)에 있는 프로젝트를 로컬 컴퓨터에 그대로 복사하여 가져오는 기능을 수행합니다.
주로 프로젝트의 소스 코드를 처음 받아올 때 사용되며 파일, 디렉토리 구조, 커밋 기록 등을 로컬 저장소로 가져올 수 있습니다.
`git clone<리포지토리 주소>` 를 사용하면 됩니다.

> ***init***

파일을 Git으로 관리하기 위해서는 먼저 Git 저장소를 초기화해야 합니다.
저장소를 초기화(로컬저장소 생성)하기 위해 사용하는 명령어가 `git init`입니다.
- .git 폴더 내에는 git 관리에 필요한 파일들이 있습니다.

> ***origin***

origin은 원격 저장소의 단축 이름으로, 저장소를 clone하면 단축 이름이 자동으로 origin으로 등록됩니다.


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

> ***--soft***

HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 
현재 작업 중인 working directory와 staging area는 아무런 영향을 받지 않습니다.

> ***--mixed***

HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 그리고 staging area도 해당 커밋의 모습과 동일하게 변합니다. 
하지만 현재 작업 중인 working directory는 아무런 영향을 받지 않습니다. 

> ***--hard***

HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 
그리고 staging area와 현재 작업 중인 working directory도 해당 커밋의 모습과 동일하게 변합니다.

- 주의 ) 커밋을 하지 않고, working directory에서 작업을 하는 경우
—hard 옵션으로 git reset을 해버리면 이때까지 작업했던 게 다 날아가버리기 때문에 주의가 필요합니다.


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

> ***Pull Request***

*PR*로 줄여서 많이 사용됩니다. 서버에 업데이트되어 있는 내용을 받아와 주세요.라는 요청입니다.
남의 저장소의 내용을 Fork해서 내가 업데이트한 경우, 변경된 내용에 대한 업데이트를 요청하는 것입니다.

> ***Merge***

Git branch를 다른 branch로 합치는 과정을 Merge라고 합니다. 

>> ***Fast-Forward***

가장 기본적인 merge 방법입니다.
현재 브랜치의 HEAD가 대상 브랜치의 HEAD까지 옮기는 것 입니다. 
**이 방법은 중간에 변경이 없을 때만 동작합니다.**
만약 중간에 다른 커밋이 껴있고, 해당 커밋이 같은 부분을 수정했다면 **충돌**이 일어나 제대로 동작하지 않습니다.


>> ***3-Way Merge***

각 브랜치의 마지막 커밋 두 개와 브랜치의 공통 조상 커밋 총 3개의 커밋을 비교하여 새로운 커밋을 만들어 머지를 수행합니다.
3-way merge를 수행하면 명확하게 변경된 내용만을 가지고 merge를 할 수 있습니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

> ***rebase***

Git에서 한 브랜치에서 다른 브랜치로 합치는 방법에 두 가지가 있는데, Merge와 Rebase입니다.
브랜치의 공통 조상이 되는 base를 다른 브랜치의 커밋 지점으로 변경하는 것입니다.
C 커밋 이후에 D 커밋이 일어난 것처럼 보이게 하기 위해서 공통 조상인 B 커밋을 변경하여 C가 되도록 하는 것입니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

> ***git stash***

Git stash는 변경사항을 일시적으로 저장하는 기능입니다.
- 아직 커밋하기엔 이른 경우
- 다른 브랜치로 체크아웃할 때 변경사항을 유지하고 싶은 경우
- 변경사항을 일시 저장하고 싶은 경우에 사용합니다.

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
