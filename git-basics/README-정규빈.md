# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

**git은 소스 코드 관리를 위한 버전 관리 도구입니다.** 
 
> git을 사용하면 프로젝트에 참가하는 개발자들이 메인 저장소를 복제하여 자신의 local 환경에서 작업을 하는 것이 가능하며, 코드를 수정할 때마다 새로운 버전으로 저장하여 여러 파일로 나뉘는 것을 방지하면서 이전 상태로 돌아가기도 쉽습니다. 

허나, 각 local들이 서로 다른 상태를 가질 수 있기에 실무적으론 이상적이진 않은데, 이때 필요한 것이 github입니다. 

**github는 git에서 작성한 코드를 저장하는 코드 저장소이며 하나의 파일을 여러 local에서 작업할 수 있게 하는 서비스입니다.**

> 웹에서 메인 저장소 역할을 하는 remote 리포지터리를 각 local에서 복제하여 git으로 작업을 수행하고 이때 수정된 사항들(깃 히스토리)를 github에 push하여 누가 어디를 어떻게 수정하였는지, 특정 부분에서 오류 발생시 누가 어떤 실수를 하였는지 등을 빠르게 확인할 수 있습니다. 이렇듯 git과 github는 개발자들에게 많은 편리함을 주고 있습니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

> 먼저 개발자들의 개인 `Working Directory`에서 깃으로 개발을 진행하다가 소스 코드의 버전을 관리하고자 할때, **`Git Add`를 통해 stage area에 내 프로젝트를 임시로 저장**합니다.
>
> 후에 이 저장사항을 특정 버전으로 저장하고 싶을때 **`Git Commit`을 통해 hash 값이 발행된 특정 버전으로 local git repository에 저장**하면 백업이나 복구를 원할때 코드를 원하는 상태로 복구할 수 있습니다.
>
>이렇게 관리된 버전들은 아직 local에 있는 상태이기 때문에 협업이나 오픈소스로 개발중이라면 해당버전들을 **`Git Push` 명령어를 통해 Remote repository인 github에 저장하여 관리**합니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- 예시로 설명하자면, **Working Directory에서 작업하던 파일 A**를 깃에 commit하면 
> A의 해쉬값을 가진 `master라는 branch`와 현재 작업 위치(master)를 알려주는 `HEAD`가 생성됩니다.

- 그 후 **Working Directory에서 파일 A를 수정하여 B라는 상태로 변경**하였고 이를 commit하게 되면
> master는 현재 branch의 최신상태를 가르켜야되기 때문에 B의 해쉬값을 가지며 HEAD 또한 master의 위치를 따라갑니다. 

- 이때 ***git branch APPTIVE*** 명령어를 통해 B 위치에 `APPTIVE라는 branch`를 추가로 생성하고 **Working Directory에서 B를 수정하여 C라는 상태로 변경** 후 commit한다면
> master는 C의 해쉬값을 가지고 HEAD는 master를 따라가지만, APPTIVE branch는 B의 위치에 그대로 있습니다. 여기서 ***git checkout APPTIVE*** 명령어를 통해 HEAD를 APPTIVE branch로 이동시킬 수 있으며, 그렇게 하면 Working Directory의 C는 B로 백업됩니다.

- 이 상태에서 **Working Directory의 B를 수정하여 D로 변경** 후 commit한다면
> APPTIVE branch는 D로 변경되고 HEAD는 APPTIVE를 가르키고 있었기 때문에 똑같이 APPTIVE의 위치를 따라갑니다. 

- branch가 필요없어지면 ***git branch -d <branch 이름>*** 명령어를 통해 삭제할 수 있습니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

> **`git clone`은 다른 개발자들이 깃허브에 업로드한 파일들을 내 local에 복제하는 명령어**이며
>>깃허브 홈페이지에서 복제하고 싶은 개발자의 파일의 주소를 복사하고 local에서 복제하고자하는 폴더에서 터미널을 실행하거나 cd명령어를 통해 해당폴더로 이동 후 git clone <복사한 주소>를 입력하면 간단하게 파일을 복사할 수 있습니다.

> **`git init`은 프로젝트의 버전관리를 위해 깃이 추적할 데이터 변동사항을 가질 폴더를 local에서 선언하는 것**으로
>>git clone처럼 선언하고자 하는 하는 폴더로 이동하여 git init을 실행하는 것만으로 해당 폴더의 변동사항들을 깃이 추적할 수 있습니다.

> **`origin`은 remote 저장소의 단축이름**으로
>>저장소를 clone하면 단축이름이 자동으로 origin이라고 등록됩니다. remote 저장소를 추가하는 방법은 git remote add <단축이름> <저장소 URL> 명령어를 사용하면 됩니다. 

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

> reset에는 soft, mixed, hard 3가지 타입이 있는데, `git reset --<옵션> <커밋 ID>` 명령어를 통해 사용할 수 있습니다.

-  `--soft`는 stage area와 working directory는 건들지 않고, repository에 있는 커밋ID 이후의 저장된 내용을 모두 삭제하고 HEAD가 커밋ID를 가르키게 합니다.

-  `--mixed`는 working directory는 건들지 않고, repository에 있는 커밋ID 이후의 저장된 내용을 모두 삭제하고 HEAD가 커밋ID를 가르키게 하면서 해당 내용을 stage area에 적용합니다.

-  `--hard`는 repository에 있는 커밋ID 이후의 저장된 내용을 모두 삭제하고 HEAD가 커밋ID를 가르키게 하면서 해당 내용을 stage area와 working directory에 적용합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- `Pull Request`는 다른 개발자들과 협업하기 위해 **코드를 Github와 같은 코드저장소에 업로드하기위해 병합을 신청**한다는 개념입니다.
> Pull Requset시 전달사항 및 변경사항을 함께 기록할 수 있으며, 주로 업로드 권한이 없는 개발자가 코드 병합을 원하거나, 다른 개발자들이 아직 개발을 진행중일때 사용하기도 하지만 안전한 병합을 위해서는 Pull Request를 생활화하는 것이 좋습니다.

- `Merge`는 Pull Request를 통해 작업한 내용을 보내게 되면, 다른 팀원이 원본 저장소에서 PR내용을 확인한 후 **코드를 합치는 행위**입니다.

> 만약 merge를 진행하게되면 PR내용은 닫혀서 사라지게 되고 원본 저장소에는 바뀐 내용이 반영되어 합쳐집니다. 해당 내용이 다른 코드에 영향을 미치지 않고, 원본 저장소에 반영해도 되겠다는 판단이 들면 Merge를 진행하고, 문제가 있다고 판단될 시에는 이를 거절할 수도 있습니다.

-  **Fast-Forward Merge**는 가장 간단한 병합 방식으로, `master branch의 포인터를 새로운 커밋으로 이동시키는 방식`입니다. branch를 생성한 후에 'master' 브랜치에 변경 사항이 없고, 생성된 branch에서만 작업을 한 경우 사용합니다.
​

- **Three-Way Merge**는 두 branch가 각각 다른 곳에서 분기한 후에 각각 다르게 발전한 경우 사용하는 방식으로, `각 branch들의 최신 커밋과 이들의 공통 조상 한 개를 사용하여 병합`합니다. 단순히 branch 포인터를 최신 커밋으로 옮기는 게 아니라, 3-way Merge 의 결과를 별도의 커밋으로 만들고 해당 브랜치가 그 커밋을 가리키도록 진행합니다. 이러한 과정을 통해 병합 커밋은 두 branch를 병합한 결과를 나타내며, 두 조상을 가지게 됩니다.


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

> rebase는 merge처럼 **코드를 합칠때 사용**하는 것으로
- `merge`는 사용이 쉽고 안전하지만 커밋히스토리가 지저분할 수 있는 반면
- `rebase`는 사용이 어렵고 잘 모르고 사용하면 위험할 수 있지만 커밋히스토리가 깔끔합니다.

> 같은 조상을 가지지만 나뉘어진 branch **A**와 **B**가 있을때, **A** branch로 이동해서 `git rebase B` 명령어를 통해 **B**를 rebase하면 `Patch`라는 곳에 **A**와 **B**의 차이를 임시저장하게 되고, 새로운 base가 될 **B**에 이 Patch들이 적용됩니다. 

> 이렇듯 **Three-way Merge**를 사용했을때는 커밋히스토리가 두 조상을 가졌지만, **rebase**를 사용하면 하나의 조상을 갖는 커밋히스토리를 얻을 수 있습니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- `git stash`는 **파일의 변경 내용을 일시적으로 기록해두는 영역**입니다.

아직 commit하기 이전의 작업을 진행 중인데 더 우선순위가 높은 작업을 진행해야 할때 자주 사용하는 명령어로, git stash로 임시 저장을 하여 급한 작업을 진행 후 다시 원래 작업을 진행할 수 있습니다.
> 이때, stash는 `변경 내용`만을 저장하기 때문에 신규 파일의 경우에 stage area에 add를 통해 저장되어있지 않았다면 변경 내용을 저장할 수 없다는 단점이 있습니다.

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

> 

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
