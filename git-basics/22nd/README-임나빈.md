# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
Git은 버전 관리 시스템이고 local에서 파일을 추적하고 관리합니다. Github는 Git을 기반으로 한 웹 호스팅 서비스로 remote repository를 관리할 수 있는 플랫폼이며 협업을 위해 공유하는 공간입니다

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)
- **Working Directory** : 실제 파일을 편집하는 작업 공간입니다. `git status`를 통해 변경된 파일을 확인합니다.
- **Git Add** : `git add` 명령어를 통해 변경사항을 Staging Area에 추가합니다. 
    - `git add [filename]` : 특정 파일을 추가  
    - `git add .` : 모든 변경사항을 추가
- **Staging Area** : 커밋할 파일이 임시로 저장되는 공간입니다
- **Local Repo** : 로컬 저장소이며 커밋된 모든 기록이 저장됩니다
- **Remote Repo** : 원격 저장소이며 `git fetch`로 Remote Repo의 변경사항을 Local Repo로 가져옵니다(merge는 X), `git pull`은 변경사항을 가져온 후 자동 병합합니다 (merge + fetch)

- **Git Commit** : `git commit` 명령어를 통해 Local Repo에 변경사항이 저장됩니다. 
    - `git commit -m "commit message"`
- **Git Push** : `git push` 명령어를 통해 Local Repo의 변경사항을 Remote Repo로 업로드 합니다 
    - `git push origin [branch_name]`

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- **Branch** : 코드 변경 사항을 독립적으로 작업할 수 있도록 하는 기능. 서로 독립적으로 작업하면서 나중에 merge 할 수 있습니다.
    - `git branch [branch_name]` : 브랜치 생성
    - `git branch -d [branch_name]` : 브랜치 삭제
    - `git checkout [branch-name]` : 브랜치 이동
- **HEAD** : 현재 작업 중인 브랜치의 현재 위치를 가리킵니다. Head는 특정 커밋을 가리키고, 커밋을 업데이트 하거나 이동하면 움직입니다.
    - `git checkout [commit-id]` : HEAD 이동
- **git checkout** : 브랜치 변경, 파일 복원 등에 사용합니다
    - `git checkout feature-branch`
    - `git checkout [filename]`
    - `git checkout [commit_id]`


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- **git clone** : 원격 저장소의 전체 내용을 로컬로 복제하는 명령어. clone을 사용하면 원격 저장소의 모든 커밋 기록, 브랜치, 태그 등이 로컬 저장소에 복사됩니다.
    - `git clone [repository-url]`
- **git init** : 새로운 로컬 저장소를 생성하는 명령어.
    - `git init`
- **origin** : 원격 저장소를 나타냅니다. origin은 URL을 가리키며 로컬 저장소와 원격 저장소를 연결할 수 있습니다
    - `git remote add origin [repository_url]` : 원격 저장소 설정
    - `git remote -v` : 원격 저장소 확인

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
- **git reset** : 작업 중인 커밋을 되돌리는 명령어
    - `git reset -- soft [commit_id]` : HEAD 포인터를 이동시켜 지정된 커밋으로 되돌리지만, Working Directory와 Staging Area는 그대로 두고, 해당 커밋 이후의 변경 사항은 그대로 Staging 상태로 남겨둡니다

    - `git reset --mixed [commit_id]` : HEAD 포인터는 지정된 커밋으로 이동하고 변경사항은 Working Directory에는 
    남아있으나 Staging Area에서만 제거됩니다 (기본 옵션)
    - `git reset --hard [commit_id]` : HEAD 포인터를 지정된 커밋으로 이동시키고 Working Directory와 Staging Area 모두를 해당 커밋 상태로 되돌립니다 (이전 변경 사항이 모두 삭제됨)

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
- **Pull Request** : 한 브랜치에서 다른 브랜치로 변경 사항을 병합하고자 할 때 리뷰를 요청하는 과정. PR을 통해 팀원들이 코드 변경을 리뷰하고 문제를 수정하거나 논의할 수 있습니다

    1. 브랜치에서 작업을 완료하고 커밋 push
    2. pr을 생성하여 리뷰 요청

    3. 변경 사항을 리뷰하고 피드백 제공
    4. 리뷰가 완료되면 변경사항 merge

- **Merge** : 두 개의 브랜치를 하나로 합치는 기능. PR을 통해 이루어 지며 Git에서 자동으로 병합을 시도하고 충돌이 있을 경우 수동으로 해결해야합니다.

    - Fast-Forward Merge : HEAD 포인터를 이동시켜 병합하는 방식으로 병합 커밋이 생성되지 않습니다
        - `git checkout main`
        - `git merge feature-branch`

    - 3-Way Merge : 두 브랜치가 서로 다른 변경 사항을 포함하고 있을 때 발생합니다.

        1. 두 브랜치가 갈라지기 전의 마지막 공통 커밋을 찾는다
        2. 브랜치 A 변경사항 확인
        3. 브랜치 B 변경사항 
        4. 병합이 완료되면 Git이 병합 커밋 생성

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
한 브랜치의 변경 사항을 다른 브랜치의 맨 위로 적용하는 방법. 
- `git checkout featchure-branch`
- `git rebase main`

    1. feature-branch에 있는 커밋들이 main 브랜치의 최신 커밋 뒤에 재적용됨 (병합 커밋 생성X)
    2. 충돌이 발생할 경우 해결 후 `git rebase --coninue`를 실행하여 계속 진행
- 병합 커밋 없이 커밋 히스토리를 관리할 때 유용합니다

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
현재 작업 중인 변경 사항을 임시로 저장하고 Working Directory를 깨끗하게 되돌리는 기능. 다른 브랜치로 이동하거나 작업을 잠시 중단해야 할 때 사용됩니다.
- `git stash`
- `git stash list` : 저장한 목록 보기
- `git stash pop` : 가장 최근 stash 복원

- `git stash apply stash@{idx}` : 특정 stash 복원
- `git stash drop stash@{idx}` : 특정 stash 삭제
- `git stash clear` : 모든 stash 삭제


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
