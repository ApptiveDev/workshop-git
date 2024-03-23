# Git 기초

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
### Git
    Git은 소스 코드 버전 관리 시스템이다. 
    Local repository의 모든 변경사항을 기록하여 파일의 버전 관리를 용이하게 해준다.
### GitHub
    GitHub은 Git 소프트웨어를 지원하는 클라우드 기반 호스팅 서비스이다. 
    Remote repository 기능을 제공해주는 서비스이다. 
    여러 사람과 공유하고 협업할 수 있다.


## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
### Working Directory (Working Tree)
    현재 작업하고 있는 영역을 말한다.
### Staging Area
    Repository에 commit하기 전에 commit을 준비하는 위치를 말한다.
### Repository
    Working directory의 변경 이력들이 저장되어 있는 영역으로 commit들이 모여있는 저장소이다.
### Local Repo(HEAD)
    내 컴퓨터의 저장소, 즉 개인 전용 저장소를 말한다.
### Remote Repo(MASTER)
    원격 온라인 서버상의 저장소로 여러 사람이 함께 공유할 수 있다.
### Git 동작 방식
1. Git Add
    - 변경된 내용을 Staging area에 추가하는데 사용된다.
2. Git Commit
    - Staging area에 추가된 변경 사항을 저장한다.
3. Git Push
    - Local repository 내용을 Remote repository로 업로드 하는 데 사용된다.
4. Git Merge
    - 다른 branch에서 변경 사항을 결합하는 데 사용된다. 
5. Git Fetch
    - Remote repository에서 변경 사항을 가져오지만 Local branch에 자동으로 병합하지 않는다.
6. Git Pull
    - Git Fetch와 Git Merge의 조합으로 Remote repository에서 변경 사항을 가져와 현재 branch에 자동으로 병합한다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
### Branch
    Branch는 동일한 소스 코드에서 다른 작업을 동시다발적으로 할 수 있게 해주는 기능을 말한다.
    코드 전체를 복사하고 난 후, 원래 코드와는 상관없이 독립적으로 개발할 수 있다.
### HEAD
    HEAD란 해당 branch의 마지막 commit, 즉 현재 사용중인 branch의 선두 부분을 나타내는 이름을 뜻한다. 
    HEAD를 이동하면 사용하는 branch가 변경된다.
### git checkout
    git checkout 명령어는 branch 간 전환하거나 파일을 이전 상태로 복원하는 명령어이다.
### Branch 관련 Git 명령어
    // Branch 생성
    $ git branch <새로운_브랜치_이름>

    // Branch 삭제
    $ git branch -d <삭제할_브랜치_이름>

    // Branch 이동
    $ git checkout <이동할_브랜치_이름>

    // 새로운 branch 생성 후 이동
    $ git checkout -b <새로운_브랜치_이름>


## clone, init, origin
### git init과 git clone
#### 공통점
    리포지토리를 로컬에 생성하는 방법이다.
#### 차이점
1. git init
    - 기존의 Local directory를 Git 저장소로 변환한다.
    - 이미 있는 directory를 Git으로 관리하기 시작할 때 사용한다.
2. git clone
    - Remote repository부터 프로젝트를 가져온다.
    - 이미 존재하는 Git 저장소를 복제해 local로 가져온다.
    - 보통 다른 사람이나 팀의 프로젝트에 기여하기 위해 사용한다.
### origin
    origin은 Remote repository의 이름이다.
#### 설정방법
    // 자동으로 origin으로 설정
    $ git clone <원격_저장소_URL>

    // 수동으로 origin으로 설정
    $ git remote add origin <원격_저장소_URL>


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
### reset의 type
    1. soft
    2. mixed
    3. hard
<table style="text-align:center">
  <tr>
    <th></th>
    <th style="text-align:center">soft</th>
    <th style="text-align:center">mixed</th>
    <th style="text-align:center">hard</th>
  </tr>
  <tr>
    <td>HEAD</td>
    <td colspan="3">지정한 commit으로 이동한다.</td>
  </tr>
  <tr>
    <td>HEAD가 가리키는 Branch</td>
    <td colspan="3">HEAD와 같이 움직인다.</td>
  </tr>
  <tr>
    <td>Staging area</td>
    <td>변화 X</td>
    <td>지정한 commit과 동일 내용</td>
    <td>지정한 commit과 동일 내용</td>
  </tr>
  <tr>
    <td>Working directory</td>
    <td>변화 X</td>
    <td>변화 X</td>
    <td>지정한 commit과 동일 내용</td>
  </tr>
  <tr>
    <td>주 용도</td>
    <td>branch 이동하기</td>
    <td>Staging area에서 빼기</td>
    <td>commit 되돌리기</td>
  </tr>
</table>



## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
### pull request
    협력자에게 branch 병합을 요청하는 메시지를 보내는 것을 말한다.
### merge
    서로 다른 branch를 하나의 branch로 합치는 과정으로 브랜치의 작업 내용을 병합하는 것을 말한다.
### merge type
1. Fast-foward Merge
    - 분기한 branch의 commit 히스토리가 기존 branch의 commit 히스토리를 포함하고 있는 경우 사용된다.
    - Merge commit이 따로 만들어지지 않고 HEAD의 위치만 이동한다.
2. 3-Way Merge
    - 각 branch에 새 commit이 하나 이상 있는 경우 사용된다.
    - 두 branch의 코드를 합쳐서 새로운 commit을 자동 생성한다

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
### rebase
    Branch의 시작점을 다른 commit으로 옮겨주는 행위이다.
    Branch 수가 많은 경우, git log를 간단하게 해주기 위해서 rebase 명령어를 사용해 merge 한다.
### rebase 명령어를 사용하여 merge 하는 방법
    // 새로운 branch의 시작점을 main branch의 최근 commit으로 변경
    $ git switch <새로운_브랜치>
    $ git rebase main

    // Fast-forward merge 진행
    $ git switch main
    $ git merge <새로운_브랜치>

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png) 
### stash 
    stash는 변경사항을 일시적으로 저장하는 기능이다.
    아직 commit하기에 이른 경우나 다른 branch로 checkout 할 때 변경사항을 유지하고 싶을 때 사용한다.
### stash 명령어
    // 현재 Working directory의 변경 사항을 일시적으로 저장 + Working directory를 깨끗한 상태로 변경
    $ git stash
    
    // 변경 사항을 특정 이름으로 저장
    $ git stash save <이름>

    // 가장 최근의 변경 사항을 가져와 Working directory에 적용 + 변경 사항을 stack에서 제거
    $ git stash pop [인덱스_번호]

    // stash를 적용하고 stash가 적용된 상태 유지 + 임시 저장 공간에 그대로 유지
    $ git stash apply

    // n번째 stash 가져와 적용
    $ git stash apply stash@{n}

    // 현재 stash 목록 확인
    $ git stash list
    
    // n번째 stash 제거
    $ git stash drop stash@{n}

    // 모든 stash 제거
    $ git stash clear
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

