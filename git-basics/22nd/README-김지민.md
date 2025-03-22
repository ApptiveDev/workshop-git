# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  

Git은 버전관리 소프트웨어이다. 로컬 저장소의 모든 변겅사항을 기록하여 파일의 버전 관리를 한다. 

반면 Github는 Git 을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스로, Git 은 로컬 저장소에서만 작동하기 때문에 다른 개발자와 작업을 공유하고 협업하기 어렵지만 Github를 사용해 로컬 저장소의 코드를 원격 저장소에 업로드 하고 공유하며 협업할 수 있다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  

- **Working Directory** 

    working directory 는 작업폴더로, 데이터를 불러오거나 외부로 저장하는 작업을 수행하는 기본 폴더이다. 실제 작업파일이 있는 곳이다.

- **Staging Area**

    스테이징 영역은 데이터가 변환되기 전에 윈시/처리되지 않은 데이터가 있는 영역을 말한다.

- **Local Repo**

    내 컴퓨터에 저장된 Git 저장소. 변경사항을 내 컴퓨터에서만 관리 가능하다.

- **Remote Repo**

    GitHub 등의 클라우드 서버에 있는 Git 저장소.
    여러명이 협업할 수 있도록 온라인에 저장된다.

- **Git Add**

    git add 는 작업 디렉토리 상의 변경 내용을 스테이징 영역에 추가하기 위해 사용하는 명령어이다. 커밋을 하기 전에 어떤 변경사항을 저장할지 선택한다.
    git add 를 하면 변경된 파일이 스테이징 영역으로 올라간다(커밋 대기 상태)

- **Git Commit**

    git commit 은 파일 및 폴더의 추가/변경 사항을 로컬 저장소에 기록하는 것이다.
    파일(폴더)의 버전에 변화가 발생했다는 것이고, 특정 작업이 완결된 상태로 바뀌었다는 것을 의미한다. 변경 내역에 대한 설명으로 커밋 메세지도 포함한다.

- **Git Push**

    로컬 저장소에 저장된 커밋한 작업 내용을 원격 저장소에 업로드 하기 위한 명령어.



## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  

- **Branch**

    Git 에서 독립적으로 개발을 진행할 수 있도록 만들어주는 분기 역할을 함. main 과 분리된 상태에서 새로운 작업을 할 수 있는 작업 공간이다. 커밋을 가리키는 포인터 역할을 한다.
    생성 및 삭제가 가능하다.
    
     생성 : `git branch <브랜치이름>`

     삭제 : `git branch -d <브랜치이름>`

- **Head**

    모든 브랜치에는 head 값이 존재하는데, 해당 브랜치의 마지막 커밋의 상태를 가리킨다.
    (특정 브랜치의 마지막 커밋에 대한 포인터)


git checkout 명령어는 브랜치 간 전환 또는 현재 작업중인 파일들을 복원할 때 사용한다.
- 브랜치 이동 : `git checkout <브랜치이름>`
- 특정 커밋으로 이동 : `git checkout <commit id>`
- 작업 디렉토리에서 변경 내용 되돌리기 : `git checkout -- <FILE NAME>`



## clone, init, origin
Gir 저장소를 만드는 방법은 크게 두 가지가 존재한다.

1. 아직 버전 관리를 하지 않은 로컬 디렉토리 하나를 선택해서 Git 저장소를 적용함.
    -프로젝트의 디렉토리로 이동한 후 git bash here 기능을 이용해 아래의 명령을 실행
    `git init`

2. 기존의 저장소를 Clone 함.
    -다른 프로젝트에 참여하거나 Git 저장소를 복사하고 싶을 때 git clone 명령어를 사용해서 프로젝트 히스토리를 전부 받아온다.
    `git clone <colne 하고자 하는 레포의 url>`


- **Origin**

    origin 은 대표적으로 사용되는 원격 저장소의 별칭을 의미함.

    1. 별칭 등록
        `git remote add {별칭} {원격지 주소}`

    2. 별칭 변경
        `git remote rename {변경전} {변경후}`

    3. 별칭 삭제
        `git remote rm {별칭}`



## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)
git reset 은 HEAD 의 위치를 현재의 커밋에서 과거의 커밋으로, 미래의 커밋으로 이동시킬 수 있는 커맨드이다.

reset에는 3가지 타입이 있습니다.  

1. soft
    soft 옵션을 쓰면 HEAD가 특정 커밋을 새롭게 가리키게 된다.
    대신 현재 작업중인 working directory 와 staging area 는 아무런 영향을 받지 않음

2. mixed
    역시 HEAD 가 특정 커밋을 가리키게 되고 staging area도 해당 커밋의 모습과 동일하게 변함. working directory는 아무런 영향을 받지 않음.

3. hard
    HEAD 가 특정 커밋을 가리키게 되고,
    staging area 와 현재 작업중인 working directoty 모두 해당 커밋의 모습과 동일하게 변함.


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  

- **Pull Request**

    pull request 란 다른 사용자가 작성한 저장소에서 변경사항을 병합(merge) 하기 위한 요청을 의미한다.

- **Merge**

    Merge 는 합병이라는 뜻으로 서로다른 브랜치를 병합해서 작업한 내용을 합치는 것을 의미한다.

    1. Fast-Forward Merge
        현재 브랜치의 HEAD가 대상 브랜치의 HEAD 까지로 옮기는 merge
        `git switch <현재 브랜치>`
        `git merge <대상 브랜치>`
        
        중간에 변경이 없을 때만 동작함.

    2. 3-Way Merge
        대부분의 협업에서 발생하게 되는 merge 방식
        두 브랜치가 동일 선상이 아닐때 발생함

        두 브랜치가 분할되는 기점에서 공통조상을 찾고 두 브랜치 커밋과 공통조상의 커밋, 총 3개의 커밋이 관여하게 됨.


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
### Git rebase란?
`git rebase` 는 두개의 공통 base 를 가진 branch에서 한 branch 의 base 를 다른 branch의 최신 커밋으로 branch의 base를 옮기는 작업이다.

**장점**
1. 공유 branch의 최신 변경사항을 즉각 반영할 수 있다.
2. rebase 는 커밋 이력을 남기지 않으므로 commit history 가 깔끔해진다.


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
stash를 이용해 작업중에 갑작스럽게 다른 작업을 진행해야 할 때, 작업중인 사항을 잠시 치워둘 수 있다.

코드를 다른곳에 보관한 후에 내가 원하는 branch 에 적용할 수 있다.

- git stash 로 변경사항들을 stash 공간으로 이동.
    `git stach`
- stash 한 변경사항 다시 적용 및 삭제
    `git stach pop`
- stash 한 마지막 항목 적용(삭제)
    `git stash apply(drop)`
- 새 브랜치 생성하여 pop
    `git stash branch <브랜치명>`


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
