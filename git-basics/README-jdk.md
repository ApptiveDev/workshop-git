# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

Git은 버전 관리 시스템으로 local repository와 remote repository라는 두 개의 저장소를 갖고 있습니다.
로컬 저장소는 자신의 작업 컴퓨터에 저장하는 저장소이고, 원격 저장소는 네트워크에 연결된 서버에 저장하는 저장소입니다.
GitHub는 git으로 관리하는 프로젝트를 올려둘 수 있는 사이트입니다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working Directory : 현재 작업 공간
Git Add : 작업한 내용을 임시 저장소에 담는 행위
Git Commit : local repository에 저장하는 행위
Git Push : local repository에 저장된 변경 사항을 remote repository에 보내는 행위
Git pull : remote repository에 저장된 정보를 받아오는 행위

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

Master branch는 프로젝트의 메인 진행 줄기입니다.
Feature branch는 개개인이 들고와서 수정하는 줄기입니다.
HEAD는 Feature branch 중 가장 최신 버전입니다.
git checkout은 프로젝트 기록의 특정 시점으로 이동하는 명령어입니다.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git init은 새로운 git 저장소를 만드는 명령어이고, git clone은 remote repository를 local repository로 복제하는 명령어
origin은 remote repository를 통제하기 위한 대명사입니다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

1. git reset -soft : commit된 파일을 초기화하고 staging area로 돌려놓는 명령어
2. git reset -mixed : commit된 파일을 초기화하고 staging area도 초기화하는 명령어
3. git reset -hard : commit된 파일과 staging area뿐만 아니라 working directory까지 초기화하는 명령어

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request : Feature branch를 Master branch에 합병하는 것을 요청
Merge : 합병

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

rebase : branch의 분기점을 변경하는 행위
특정 브랜치 A에서 다른 브랜치 B를 파서 작업 중이었는데 A 브랜치에 다른 사람이 추가로 commit을 올리면 B 브랜치를 merge 하려고 할 때, conflict가 발생하므로
분기점을 변경하여 원활하게 merge될 수 있도록 도와줍니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

A 브랜치에서 작업 중에 B 브랜치를 통한 작업을 해야하는 상황에서 stash를 이용하면 기존에 작업 중이던 변경 사항을 잠시 치워두고 B 브랜치에서 작업을 마친 후에 stash 공간에서 다시 가져올 수 있습니다.

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
merge의 두 타입에 대해 이해가 잘 되지 않습니다.