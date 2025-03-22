# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git - local에서 프로젝트의 작업 내용을 기록하고, 이전상태로 되돌리는 등의 역할을 한다.
github - git저장소를 온라인에서 관리하도록 하여 협업을 용이하게 해준다. 즉 remote 저장소 역할을 한다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : 현재 작업중인 파일이 있는 공간, 코드작성 및 수정을 하는 공간이다.
- Git Add : git add 파일 , 커밋을 하기전에 어떤 파일을 변경사항에 포함할지 정하는 단계이다. git add를 통해 staging Area에 파일을 올린다.
- Git Commit : git commit -m "커밋내용" , staging Area에 올라와있는 변경사항을 locale에서 확정하는 단계이다.
- Git Push : git push origin 브랜치 , locale 레포에 있는 변경사항을 remote 저장소로 올린다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

-branch를 생성하고 이동하는 명령어 : git checkout -b 새로운-브랜치명
-HEAD : 현재 작업 중인 브랜치를 가리키는 포인터이다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git clone : 이미 존재하는 원격 리포지토리를 로컬에 복제할 때 사용한다. 원격 저장소를 복제하여 폴더가 자동으로 생성되고, 해당 폴더에서 바로 Git이 활성화된다.
- git init : 완전히 새로운 Git 리포지토리를 로컬에서 처음부터 생성할 때 사용한다. 원격 저장소는 따로 설정되지 않아, 필요할 시 수동으로 추가해야한다.

- origin : 기본적으로 원격 저장소를 가리키는 별칭이다. git clone을 하면 자동으로 설정되지만, git init을 사용한 경우 수동으로 설정해야한다. (git remote add origin <원격_저장소_URL> 명령어 이용용)


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- git reset --soft : 최근 커밋을 취소하고, 변경 사항을 Staging Area로 유지한다. 즉 커밋만 되돌리고, git add 한 상태는 유지하는 것이다.
- git reset --mixed : 최근 커밋을 취소하고, 변경 사항을 Staging Area에서도 삭제한다. 즉, git add한 것도 취소되지만 파일 자체는 working directory에 남아있다.
- git reset --hard : 최근 커밋을 취소하고, Staging Area와 Working Directory의 변경 사항도 모두 삭제한다. 즉 수정내용이 전부 완전히 삭제된다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
- Pull Request : 브랜치에서 작업한 변경 사항을 메인 브랜치에 Merge하기 전에 검토 요청을 보내는 과정이다.
- Merge 
    - 다른 브랜치에서 작업한 내용을 현재 브랜치로 합치는 과정이다.
    - 브랜치가 한 방향으로만 진행된 경우, 새로운 Merge 커밋을 생성하지않고 단순히 최신 커밋으로 이동하는데, 이를 Fast-Forward Merge라고한다. 이는 충돌이 발생할 확률이 거의없지만 기록유지는 힘들다.
    - 브랜치가 서로 다른 커밋을 포함하고 있을 때 하는 Merge 방식으로 3-Way Merge가 있다. 독립적으로 진행된 변경 사항을 통합해야 하므로 충돌이 일어날 수 있고, 작업기록을 명확히 남긴다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
- Git Rebase
    -브랜치를 다른 브랜치의 최신 상태로 변경하는 작업이다.
    -git merge를 이용해 병합할때 ,병합커밋으로 인해 복잡할 수 있는 기록을 rebase를 이용하여 커밋을 깔끔하게 관리한다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
- 현재 변경 사항을 Stash에 저장하고, working directory는 수정전으로 돌아간다.
- pull을 통해 최신 코드를 불러오고 stash에 저장해두었던 코드를 불러와 이전 변경 사항을 복원시킨다.

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
