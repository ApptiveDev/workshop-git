# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
-Git (Local): 컴퓨터(로컬)에서 코드의 변경 이력을 기록하는 도구입니다.
-GitHub (Remote): 인터넷(원격)에 코드를 저장하고 다른 사람과 공유하는 공간입니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

-Working Directory: 현재 실제로 코드를 수정하고 있는 폴더입니다.
-Git Add: 수정한 파일 중 커밋할 것들을 Staging Area에 담는 과정입니다.
-Git Commit: Staging area에 담긴 변경 사항을 로컬 저장소에 저장하는 스냅샷입니다.
-Git Push: 컴퓨터 내에 저장된 커밋들을 원격 저장소로 업로드하는 것입니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

-Branch: 기본 코드에서 뻗어 나온 별도의 작업선입니다. 원래 코드를 건드리지 않고 새로운 기능을 만들 때 사용합니다.
-HEAD: 내가 현재 어떤 브랜치나 커밋 위에 있는지 가리키는 포인터 입니다.
-Git Checkout: 다른 브랜치로 이동하거나 특정 커밋으로 돌아갈 때 사용하는 명령입니다.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

-Git Init: 새로운 폴더에서 Git 관리를 처음 시작할 때 사용합니다.
-Git Clone: GitHub에 있는 기존 프로젝트를 컴퓨터 내로 그대로 복사해 올 때 사용합니다.
-Origin: 컴퓨터와 연결된 GitHub 주소의 별명입니다. 매번 긴 주소를 치지 않기 위해 사용합니다.
**origin 설정 방법**
  - `git clone` 명령을 사용하여 원격 저장소를 복사하면 Git은 자동으로 `origin`이라는 이름의 원격 저장소를 설정한다. 따라서 별도의 설정이 필요없다.

  - `git remote add` 명령으로 원격 저장소를 직접 추가한다면 아래의 명령어를 사용하여 `origin`이라는 이름의 원격 저장소를 설정할 수 있다.
    ```bash
    git remote add origin 원격_저장소_URL
    ```
  

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

-Soft: 커밋만 취소하고, 파일 수정 내역과 Add(staging) 상태는 유지합니다.
-Mixed: 커밋과 Add를 취소하지만, 수정한 코드 내용은 유지합니다.
-Hard: 커밋, Add, 수정 내용을 모두 지우고 이전 상태로 완전히 되돌립니다.


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request (PR): 작성한 코드를 원본 브랜치에 합치기를 요청하는 과정입니다.
Merge: 두 개의 브랜치를 하나로 합치는 것입니다.
-Fast-Forward: 갈라진 이후 원본에 변화가 없어서 단순히 앞으로 이동하며 합치는 방식입니다.
-3-Way Merge: 양쪽 브랜치에 모두 변화가 있을 때, 새로운 커밋을 만들어 합치는 방식입니다.


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

Rebase: 브랜치의 시작점(Base)을 최신 커밋으로 다시 설정하는 것입니다. 복잡한 Merge 기록 없이 히스토리를 일직선으로 깔끔하게 관리할 수 있습니다.


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

Stash: 하던 작업을 잠시 임시 보관함에 넣어두는 기능입니다. 커밋하기에는 코드가 미완성인데, 갑자기 브랜치를 바꿔야 할 때 사용합니다.


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
