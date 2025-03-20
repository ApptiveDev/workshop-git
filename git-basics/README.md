# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

깃과 깃허브의 가장 큰 차이점은 깃이 소프트웨어이며, 깃허브가 서비스라는 점입니다. 깃은 개발자의 로컬(local) 컴퓨터에서 동작하며, 소스 코드의 버전 관리를 담당합니다. 반면, 깃허브는 깃 리포지토리를 호스팅하는 웹 서비스(remote)로, 프로젝트 협업을 위한 다양한 도구를 제공합니다.
-> GitHub는 Git 저장소를 호스팅하는 원격(remote) 저장소 서비스이다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : 사용자가 작업하는 로컬 파일들이 위치한 영역으로 업로드 전의 작업한 파일입니다.
- Git Add : Working Directory에서 변경된 파일을 Staging Area로 추가하여 커밋 대상으로 만듭니다.
- Git Commit : Staging Area의 변경 사항을 코멘트와 함께 로컬 저장소(Local Repository)에 기록합니다.
- Git Push : 로컬 저장소에서 원격 저장소(GitHub)로 변경 사항을 업로드합니다.
- Git Fetch : 원격 저장소의 최신 변경 사항을 로컬로 가져오지만, 자동으로 병합하지는 않습니다.
- Git Merge : 다른 브랜치의 변경 사항을 현재 브랜치에 합칩니다.(수정사항을 적용하거나 기능을 업데이트 하는 과정)
- Git Pull : 원격 저장소의 변경 사항을 가져와 로컬 저장소와 자동으로 병합(Merge)합니다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- Commit: 변경 사항을 기록하는 Git의 기본 단위로 각 commit은 고유한 해시값을 가집니다.
- Branch: 독립적으로 개발을 진행할 수 있는 작업 공간으로, 여러 브랜치를 만들어 병렬 작업이 가능합니다. 보통 기본 작업 파일을 살려두고 나머지 기능이나 수정사항을 점검한 후 적용하기 위해 사용합니다.
- HEAD: 현재 체크아웃(작업 중)된 브랜치를 가리키는 포인터로, HEAD가 가리키는 브랜치가 변경됩니다. (HEAD = 현재 작업중인 branch)
- git checkout [브랜치명]: 특정 브랜치로 이동하거나, 특정 커밋을 체크아웃할 때 사용합니다.
- git switch -c [새로운 브랜치명]: 새 브랜치를 생성하고 해당 브랜치로 이동합니다.
- git branch [새로운 브랜치명]: 새로운 브랜치를 생성하지만, 현재 브랜치를 변경하지 않습니다.
- git branch -d [브랜치명]: 로컬 브랜치를 삭제합니다.
- git push origin --delete [브랜치명]: 원격 브랜치를 삭제합니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git init : 로컬 저장소에 새로운 Git repository를 생성합니다. Git Hub에는 따로 연동해줘야합니다.
- git clone : 원격 저장소에 있는 기존의 repository를 복제하여 로컬로 가져옵니다. 원격 저장소와 자동으로 연동됩니다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- git reset --soft [커밋ID] : 지정한 커밋으로 HEAD만 이동하고, 변경 사항은 Staging Area(=index)에 유지됩니다. 최근 커밋을 수정할때 유용합니다.
- git reset --mixed [커밋ID] : 지정한 커밋으로 HEAD와 Staging Area를 이동하지만, Working Directory는 그대로 유지됩니다. 커밋은 취소되지만 파일 변경 사항은 남아있어 다시 커밋할 수 있습니다.
- git reset --hard [커밋ID] : 지정한 커밋으로 HEAD, Staging Area, Working Directory를 모두 이동시켜 변경 사항을 완전히 삭제합니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request : GitHub, GitLab 등에서 사용하는 기능으로, 브랜치 병합을 요청하는 과정입니다. 협업을 하며 수정사항을 병합할지 검토한 후 진행할 수 있습니다.
- Merge : 한 브랜치의 변경 사항을 다른 브랜치에 적용하는 과정입니다. git merge [브랜치명] 명령어로 수행됩니다.
1) Fast-Forward Merge : 대상 브랜치가 병합하려는 브랜치의 최신 커밋을 그대로 따라갈 수 있을 때 발생합니다. 별도의 병합 커밋 없이 브랜치의 HEAD가 이동합니다.
2) 3-Way Merge : 두 브랜치가 서로 다른 변경 사항을 가질 때 발생하며, 공통 조상(ancestor)을 기준으로 병합합니다. 새로운 병합 커밋이 생성됩니다.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.



## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.



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
