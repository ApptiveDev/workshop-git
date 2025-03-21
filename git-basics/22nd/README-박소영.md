# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

<span style = "color:gray">git은 local 저장소를 사용하기 때문에 다른 사람이 접근할 수 없다.<br>
github는 git을 기반으로 하는 remote 저장소이므로 다른 사람들이 공유하고 접근할 수 있다.</span>

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

working directory는 git이 관리하는 프로젝트의 실제 파일이 위치하는 곳이다.<br>
staging area는 commit을 수행하기 전에 변경사항을 일시적으로 저장하는 영역이다.<br>
working area에서 파일을 수정하고 이를 git에게 알리기 위해 git add를 사용하여 staging area에 추가한다.<br>
staging area의 변경 사항을 local repo에 영구적으로 저장하기 위해 git commit 명령어를 사용한다.<br>
local repo의 변경사항을 remote repo로 업로드 하기 위해 git push를 사용하여 변경 사항을 공유한다.<br>
반대로 remote repo의 변경사항을 local repo로 가져 오기 위해서는 git pull을 사용한다

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

commit을 branch가 가리키고 HEAD는 branch를 가리킨다.<br>
commit을 하면 HEAD가 가리키는 branch가 최신 commit으로 이동한다.<br>
git checkout <브랜치명>을 하면 해당 branch로 HEAD가 이동한다.<br>
git branch -b <브랜치명>을 사용하면 branch가 생성되고 git branch -d <브랜치명>을 사용하면 해당 branch가 삭제된다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

원하는 directory에서 git init을 사용하면 그 안에 빈 git 리포지토리를 만든다<br>
git clone <url> 을 사용하면 현재 directory의 안에 url에 해당하는 리포지토리를 복제한다.<br>
origin은 현재 git에서 작업하는 local repo와 연결된 remote repo의 주소를 가리키는 단축이름으로 git 리포지토리를 복제할 때 자동으로 생성된다.<br>
새로운 remote repo를 추가하려면 git remote add origin <추가할 remote repo 주소>를 사용하면 된다.<br>
기존에 origin이 존재하는데 새로 추가하고 싶으면 git remote remove origin을 사용하여 기존 origin을 삭제하고 추가하면 된다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

soft에서 HEAD는 첫번째 commit을 가리킨다. 하지만 staging area와 working directory는 기존의 commit 상태로 유지된다.<br>
mixed는 soft 유형에서 staging area도 함께 첫 번째 commit의 상태로 변경된다.<br>
hard는 mixed 유형에서 working directory도 첫 번째 commit의 상태로 변경된다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

프로젝트 리포지토리에서 fork를 눌러 자신의 리포지토리로 가져온 후 로컬 리포지토리에서 clone한다.<br>
내용 수정 후 자신의 리포지토리에 수정 브랜치를 push한다. 그 후 pull request 버튼을 누르고 메세지 작성후 보낸다.<br>
프로젝트 리포지토리 관리자는 pr의 변경 내용을 확인 후 merge한다.<br>
fast-forward : 메인 branch에 변경 사항이 없다면 head가 병합하려는 branch의 마지막 commit으로 이동한다.<br>
3-way merge : 메인 branch에 변경 사항이 있다면 병합하려는 branch와의 공통 commit을 찾아 병합하고 새로운 commit을 생성하여 두 개의 branch와 연결한다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

rebase는 branch가 갈라질 때 메인 branch의 마지막 commit을 조상으로 하는 새로운 commit들을 생성하여 병합하려는 branch의 변경사항들을 차례대로 적용하는 것이다.<br>
commit history를 시간 순서대로 남길 수 있어서 과거 commit history를 수정하기 좋다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

현재 작업하던 브랜치가 아닌 다른 브랜치에서 작업해야 할 때 git stash를 사용하여 변경 내용을 로컬 저장소에 임시로 저장할 수 있다.<br>
git stash list를 통해 저장된 내용을 볼 수 있고 git stash apply를 통해 치워둔 마지막 항목을 불러올 수 있다. 끝에 번호를 적으면 항목 지정이 가능하다.

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
