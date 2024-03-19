# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git : 로컬 저장소의 모든 변경사항을 기록하여 파일 버전관리
git hub : git을 사용하는 웹 호스팅 서비스
로컬 저장소의 코드를 업로드하고, 공유 할 수 있음

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working directory : 로컬 저장소에 접근할 수 있으며, 실제로 파일을 생성하고 수정하는 공간, 현재 작업중인 공간

Staging area : 곧 commit할 파일에 대한 정보를 저장하는 곳

local repository : 내 컴퓨터 안에 있는 저장소, 네트워크 필요 X

remote repository : 원격 서버에 있는 저장소, 네트워크 필요(github, gitlab...)

Git add : 작업 위치(Working directory 이하 WD)폴도에 작업한 파일이 있을 경우, add를 통해서 staging Area로 옮길 수 있음

Git commit : staging area에 저장되어있는 변경 사항들을 로컬저장소에 등록

Git push : 원격 저장소에 commit된 파일들을 모두 업로드

Git pull : 원격 리포지토리에서 로컬로 변경 내용을 가져와 병합

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

commit : 의미있는 변경 작업들을 저장소에 기록하는 동작

branch : 여러 개발자들이 동시에 작업을 할 수 있게 만들어주는 기능
각자 독립적인 작업 영역(저장소)안에서 코드 변경 가능

Head : 모든 브랜치에는 HEAD값이 존재하는데, 해당 브랜치의 마지막 커밋을 뜻함

git checkout : 코드저장소(repository)에서 특정 브랜치로 전환하는 작업


Git branch 주요 명령어
git branch [-l](-l생략 가능) : 로컬 branch 정보를 보여줌
git branch -v : 로컬 branch의 정보를 마지막 커밋 내역과 함께 보여줌
git branch -r : remote repo의 branch 정보를 보여줌
git branch -a : 로컬/리모트 저장소의 모든 branch 정보 보여줌
git branch (이름) : 로컬에 새로운 branch 생성
생성과 동시에 해당 branch로 이동하려면 -b 사용
git branch -d (branch이름) : branch 삭제


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git init : .git이라는 하위 폴더를 생성, git으로 관리할 수 있게 해주는 명령어

git clone : 저장소로부터 프로젝트를 복제하는 것
bare repository를 생성하거나, 저장소에 있는 project를 내 pc에 설치할때 사용
사용법 : git clone {프로토콜} {프로젝트 주소}.git

origin : 대표적으로 사용되는 원격 저장소의 별칭, 특정 원격 저장소를 식별하는 이름

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

git reset : Head의 위치를 현재 커밋에서 과거나 미래로 이동시키는 커맨드
soft : head가 특정 커밋(과거, 미래)을 새롭게 가르키게됨
mixed : soft처럼 새롭게 가리키지만, staging area도 해당 커밋의 모습과 동일하게 변하게 됨
hard : 마찬가지로, working directory도 해당 커밋의 모습과 동일하게 변하게 됨

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull request : 다른 사용자가 작성한 저장소에서 변경 사항을 병합하기 위한 요청
줄여서 PR이라고 함
Merge : 여러 브랜치를 master 브랜치에 병합하는 것
fast-forward : master브랜치에서 분기해 나가는 지점(commit), 즉 두 브랜치가 공통으로 가지고 있는 commit을 base라 함
fast-forward관계에 있는 브랜치를 관계에서 git merge명령을 입력하면 새로운 commit이 생기지 않는다
뒤에 쳐진 브랜치의 참조 개체가 앞서있는 브랜치가 가리키는 개체를 참조하도록 이동하는 것
3-way merge : 두 브랜치 모두 base에 위치하고 있지 않을 시, 두 브랜치가 분리된 commit을 참조할 때 git merge명령을 실행하면 새로운 commit이 생성된다. 이것을 3-way merge라 부른다

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

Rebase : base를 재설정한다는 의미로, 하나의 브랜치가 다른 브랜치에서 파생되서 나온 경우, 다른 브랜치에서 진행된 커밋을 가져와서 base를 재설정하는 것

내가 작업하던 브랜치에 main 내용이 필요해서 적용시키고 싶을때 쓰면 좋음

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

Git stash : 변경사항을 일시적으로 저장하는 기능으로, 나중에 다시 사용가능

명령어 : 
git stash / git stash save
git stash pop {index} : 스택에 쌓은 가장 최근의 변경사항을 불러와 디렉토리에 적용하고, 해당 변경사항은 스택에서 제거됨
git stash apply : 적용해도 스택에서 사라지지 않음
git stash list : 목록확인


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
