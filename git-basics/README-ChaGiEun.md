# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
<br/><br/>
- local Repository : 개발자의 컴퓨터에서 작업되는 프로젝트 저장공간
- remote Repository : 클라우드 서비스(ex)GitHub)를 통해 인터넷 서버에 저장된 공간
<br/>
*Git*은 주로 **로컬 컴퓨터**에서 작업할 때 사용됩니다.
사용자는 로컬 컴퓨터에서 Git을 사용하여 프로젝트의 변경 사항을 추적하고 관리할 수 있습니다.
Git을 사용하면 로컬 저장소를 생성하고, 변경 사항을 커밋하고, 브랜치를 만들고 병합하는 등의 작업을 수행할 수 있습니다.
<br/>
*GitHub*은 **리모트 저장소**를 제공하여 여러 사용자가 소스 코드를 공유하고 협업할 수 있습니다.
사용자는 GitHub을 사용하여 리모트 저장소를 만들고, 다른 사용자와의 협업을 위해 변경 사항을 푸시하고 풀 리퀘스트를 만들 수 있습니다.




## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
<br/><br/>
- **Working Directory**<br/>
    - 사용자의 작업 공간으로써, 로컬 저장소에 접근할 수 있으며 실제 파일을 수정하거나 생성하는 공간입니다.
    - 현재 작업 중인 소스코드들을 담고 있으며, 운영체제도 워킹 디렉토리 내부의 파일들만 접근하거나 수정할 수 있습니다.
    - 작업 폴더에서 .git 디렉토리를 제외한 나머지 부분입니다.
- **Git Add**<br/>
    - commit의 전단계입니다.
    - commit을 하고자 하는 파일들은 commit하기 전에 add를 해줘야 commit 할 수 있습니다.
- **Git Commit**<br/>
    - git에 저장하는 단계입니다.
    - commit을 해주면 commit을 한 곳으로 언제든지 다시 돌아올 수 있기때문에 코드의 추가, 삭제가 자유로워집니다.
- **Git Push**<br/>
    - git push를 하게되면 로컬 저장소에 있는 변경 이력이 원격 저장소에도 반영됩니다.


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
<br/><br/>
- commit은 Git 저장소(원격 저장소)에 우리의 디렉토리(로컬 저장소)에 있는 모든 파일에 대한 스냅삿을 기록하는 것입니다.
- branch는 그저 commit 노드를 참조하는 것입니다. 
- HEAD란 현재 checkout된 브랜치의 마지막 commit에 대한 포인터입니다.
- git checkout은 branch 혹은 commit을 전환하거나, 내용을 되돌리는 기능을 합니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
<br/><br/>
- **git init과 git clone의 차이**
    - git init : 빈 git 저장소를 만들거나 기존 저장소를 다시 초기화하는 명령어
    - git clone : git clone에 해당하는 저장소를 복제해 새 디렉터리로 가져오는 명령어<br/>
-> git init은 프로젝트 자체를 처음부터 시작하는것이고, git clone은 프로젝트 내에 중간 투입이 가능하며 clone 시 inti을 다시 해줄 필요가 없습니다.
- **이용방법**
    - git init
    - git clone
- **origin**
    - remote 저장소를 가리키는 별칭입니다.
    - 새로운 프로젝트를 clone할 때 : git clone <원격 저장소 URL> <디렉토리 이름>
    - 기존 저장소에 새로운 원격 저장소를 추가할 때 : git remote add origin <원격 저장소 URL>

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
<br/><br/>
git reset은 HEAD의 위치를 현재 커밋에서
1. 과거의 커밋으로 이동시킬 수도 있고
2. 미래의 커밋으로 이동시킬 수도 있습니다.

- **--soft--**
    HEAD가 특정 커밋을 새롭게 가리키게 됩니다. 대신 현재 작업 중인 working directory와 staging area는 아무런 영향을 받지 않습니다.
- **--mixed--**
    HEAD가 특정 커밋을 새롭게 가리키게 됩니다. 그리고 staging area도 해당 커밋의 모습과 동일하게 변합니다. 하지만 현재 작업 중인 working directory는 아무런 영향을 받지 않습니다.
- **--hard--** 
    HEAD가 특정 커밋을 새롭게 가리키게 됩니다. 그리고 staging area와 현재 작업중인 working directory도 해당 커밋의 모습과 동일하게 변합니다.

*staging Area : 커밋을 하기 위해 $git add 명령어로 추가한 파일들이 모여있는 공간<br/>
**working directory** --$git add--> **staging area** -- $git commit --> **repository**


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
<br/><br/>
- Pull Request : '코드를 수정했는데 당신도 코드를 수정했다면 제 수정한 내용도 적용시켜 주세요'라는 의미입니다.
- Merge : git branch를 다른 branch로 합치는 과정을 merge라 합니다. merge의 기본 단위는 브랜치이며, git merge 명령어로는 커밋 단위로 합치기가 불가능합니다.
    - Fast-Forward : 현재 브랜치의 HEAD가 대상 브랜치의 HEAD까지로 옮기는 merge입니다. 대신 중간에 변경이 없을 때만 동작합니다. 
    - 3-Way Merge : 두 브랜치가 동일 선상이 아닐 때 3-way Merge가 발생합니다. 서로 다른 브랜치에 공통되는 base branch를 기점으로 충돌을 최소화 시키는 방법입니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
<br/><br/>
두개의 공통 Base를 가진 Branch에서 한 Branch의 Base를 다른 Branch의 최신 커밋으로 branch의 base를 옮기는 작업입니다. 용어 그대로 베이스를 다시 설정하는 작업입니다.<br/>
Git에서 한 브랜치에서 다른 브랜치로 합치는 방법은 Merge와 Rebase입니다. Merge와 Rebase의 실행결과는 같지만 커밋 히스토리가 달라집니다. Merge는 쉽고 안전하지만 커밋 히스토리가 지저분할 수 있는 반면, Rebase는 잘 모르고 사용할 경우 위험할 수 있어 까다롭지만 커밋히스토리를 깔끔하게 관리할 수 있습니다.
<br/>
공유 branch에 대한 최신 commit을 반영하면서 작업을 해야할 때 git rebase를 사용한다면 작업 branch에서 항상 최신 변경사항을 적용한 commit을 유지할 수 있습니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

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
