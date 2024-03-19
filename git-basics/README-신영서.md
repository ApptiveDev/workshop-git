# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.  

> * git = 소스 코드 버전 관리 시스템 입니다 
>   * 버전 관리 = 내가 원하는 시점의 작업물로 이동할 수 있다는 것을 의미합니다 
>   * 로컬 컴퓨터에서 실행되며 저장할 수 있는 공간이 있다면 어디에나 저장 할 수 있습니다 (로컬 컴퓨터, USB, 클라우드 서버, 인터넷 등)  
>
> * github = 깃으로 관리하는 프로젝트를 온라인 상에 올려둘 수 있는 사이트 입니다 
>   * 시간, 공간의 제약이 없습니다 

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

> #### Working Directory
> * 현재 작업하고 있는 영역. 즉, 작업을 하고 있는 프로젝트 디렉토리
> * untrackted 상태 : 파일이 Git에 의해서 그 변동사항들이 추적되지 않고 있는 상태
> 
> #### Git Add
> * 작업 디렉토리(working directory) 상의 변경 내용을 스테이징 영역(staging area)에 추가하기 위해서 사용하는 Git 명령어
> * staging 영역 - 커밋할 준비가 된 변경 내용이 Git 저장소에 기록되기 전에 대기하는 장소 
> * trackted 상태
> * git add 명령어를 많이 실행해도 Git 저장소의 변경 이력에는 어떤 영향도 주지 않음
> * 장점 : 작업 디렉토리에 있는 변경 내용을 한 번에 몽땅 기록하지 않고, 조금씩 나누어서 기록할 수 있다
> 
> #### Git Commit
> * 의미있는 변경 작업들을 깃(저장소)에 기록하는 동작
> * 스냅샷 방식 - 새롭게 변경된 부분만 추출해서 저장
> * HEAD 포인터 -  최종적인 커밋 작업의 위치
>
> #### Git Push
> * 원격 저장소(remote repository)에 코드 변경분을 업로드하기 위해서 사용하는 Git 명령어
> * 새로운 branch 최초 push 사용법  
>    ``` git
>    git push --set-upstream <저장소명> <브렌치명> 
>    ```




## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

> ### branch  
> 여러 개발자들이 각자 독립적인 작업 영역(저장소) 안에서 마음대로 소스코드를 변경 가능하도록 함  
> 필요에 의해 만들어지는 각각의 브랜치는 다른 브랜치의 영향을 받지 않음  
> ``` 
>#생성
> git branch <브랜치 이름>
>
>#이동
>git checkout <브랜치 이름>
>
>#로컬 브랜치 삭제 (다른 브랜치로 이동 후)
>git branch -d <로컬 브랜치 이름> 
>
>#원격 브랜치 삭제
>git push <원격 저장소 이름> -d <원격 브랜치 이름>
>```
>   >Checkout  
>   >독립된 작업 공간인 브랜치를 자유롭게 이동할 수 있다.  
>   >``` 
>   >git checkout <브랜치 이름> 
>   >```
>  
>   >Head  
>   >현재 사용 중인 브랜치의 선두 부분을 나타내는 이름  
> 
>   >Merge  
>   >여러 개의 브랜치를 하나로 모을 수 있음
>   >```
>   >git merge <합칠 브랜치 이름>
>   >``` 


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

> #### git clone
> - 내 컴퓨터에 없는 Git 저장소를 복사해오는 명령어
>   ```
>   git clone <원격 저장소 url>
>   ```
> - 프로젝트에 대한 모든 데이터와 히스토리 가져옴
> - 원격 저장소의 기본 브랜치만 확인할 수 있음
> #### git init
> - 내 컴퓨터의 현재 디렉토리를 Git 저장소로 초기화하는 명령어
>   ``` 
>   git init 
>   ```
> - 현재 디렉토리에 .git이라는 숨김 파일이 생성되고 Git의 내부 db가 생성

> #### origin
> - 원격 저장소(URL)의 단축 이름이다
> - 저장소를 Clone하면 단축 이름이 자동으로 origin이라고 등록된다
> - 존재 이유 - add,commit,push,pull을 통해 remote repository와 협업을 할 떄 remote repository의 URL을 일일이 입력하는 대신 별칭(alias)를 사용하는 것
> 
## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

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
> commit 만으로도 변경사항을 저장하고 버전관리가 가능한데 staging 영역이 있는 이유가 궁금합니다