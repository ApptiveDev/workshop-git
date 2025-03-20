# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

git을 통해 local에 저장, version 관리에 이용

github를 이용해 git이 local에 저장하는 데이터를 remote에 업로드, 온라인으로 공유, 협업을 지원

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

Working Directory : 일반적으로 local의 실제 파일을 작업, 수정하는 공간

Git Add : 변경된 파일을 Staging Area에 올리기. git이 추적할 변경 사항을 지정

Git Commit : Staging Area에 추가된 변경 사항을 Local Repo에 저장. 새로운 version 추가

Git Push : local에 저장된 commit된 변경 사항을 github에 업로드

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

commit : 개발과정에서 변경된 내용을 기록하는 version의 단위

branch : 파생된 독립적인 개발 라인

head : 현재 위치한 commit 또는 branch를 가리키는 pointer

    # 새로운 브랜치 생성 (feature 브랜치)
    git branch feature-branch  

    # 브랜치 목록 확인
    git branch  

    # 현재 HEAD가 가리키는 커밋 확인
    git log --oneline --decorate

    # 특정 커밋으로 이동 (Detached HEAD 상태)
    git checkout <커밋 해시값>

    # 특정 브랜치로 이동 (Checkout)
    git checkout feature-branch  

    # 다시 원래 브랜치로 돌아오기
    git checkout main
 

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git clone : remote Repo에서 local로 복사

    #복사
    git clone <url>

git init : 새로운 git 저정장소 생성

    # 현재 디렉토리를 Git 저장소로 만들기
    git init

    # 원격 저장소(origin) 연결
    git remote add origin <url>

    # 변경 사항을 원격 저장소로 푸시
    git push -u origin main

origin : remote Repo의 기본 이름

    # 확인
    git remote -v

    # 설정
    git remote add origin <url>

    # 삭제
    git remote remove origin

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

    # 최근 commit만 취소
    git reset --soft

    # 최근 commit 취소, staging area 비움
    git reset --mixed

    # local 포함, 모든 변경 사항 삭제. 이전 commit의 version으로 되돌림
    git reset --hard

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

PR : github에서 코드 리뷰, 병합을 요청하는 기능

Merge : 한 branch의 변경 사항을 다른 branch에 반영하는 과정. PR 승인 후 진행행

Fast-Forward : 새로운 branch에서 변경 사항만 추가된 경우, Git이 단순히 commit을 이동시키는 방식

    # Fast-Forward 병합 실행
    git merge feature

3-Way Merge : Git이 각 branch의 변경 사항을 비교하여 새로운 Merge Commit을 생성.
main과 feature가 서로 다른 변경 사항을 포함하고 있으면 3-Way Merge가 발생

    # 3-Way Merge 실행
    git merge --no-ff feature

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

한 브랜치의 변경 사항을 다른 branch의 최신 commit 위로 재배치.
branch의 commit을 정리하고 히스토리를 깔끔하게 유지. 기존 commit 히스토리를 보존하고자 한다면 사용에 유의

    # feature 브랜치를 main 브랜치의 최신 상태로 업데이트
    git checkout feature  
    git rebase main  


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

작업 변경 사항을 add, commit 없이 임시저장.

    # 임시 저장
    git stash

    # 최근 저장 불러오기
    git stash pop

    # 목록 보기
    git stash list

    # 지정 불러오기
    git stash apply stash@{0}

    # 지정 삭제
    git stash drop stash@{0}

    # 전체 삭제
    git stash clear

    # 메모 달아 저장하기
    git stash save "메모"

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
