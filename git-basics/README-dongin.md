# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
**Git**
- 버전 관리 시스템.
- 하나의 프로젝트에 여러 사람이 작업할 때 작업의 히스토리(변경 사항)를 관리할 수 있게 해주는 도구이다.
**Github**
- Git을 사용하여 관리되는 프로젝트를 올려두고, 협업을 쉽게 할 수 있도록 도움을 주는 웹 기반 플랫폼.
- 프로젝트의 버전을 관리하기 때문에 협업할 때 편리하다.
**Repository**
- Local Repository는 자신의 컴퓨터에 있는 저장소를 의미하고, Remote Repository는 인터넷 상에 위치한 저장소를 의미한다.
- 보통, Local 저장소에서 Git을 통해 프로젝트를 작업한 후, Remote 저장소(Github)에 올려 다른 팀원들과 공유하는 방식으로 협업을 진행한다.
> 이렇게, Git과 Github를 통해 코드의 변경 사항을 확인하고, 다양한 개발자와 원할한 작업이 가능하다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
**Working Directory**
- 사용자가 실제로 작업하고 있는 로컬 파일 시스템의 디렉토리.
- 개발자가 코드를 수정, 생성하는 곳.
**git add**
-  Working Directory에서 변경된 파일들을 임시저장공간(Staging Area)로 이동시키는 명령어.
- Git이 추적해야 할 변경 사항을 선택하는 과정으로, 사용자는 commit할 파일들을 고를 수 있다.
**git commit**
- Staging Area에 있는 변경 사항들을 Local Repository에 영구적으로 저장하는 명령어.
- 각 commit은 해당 프로젝트의 버전을 나타내며, 커밋 메시지를 통해 해당 변경 사항에 대한 설명을 추가할 수 있다.
**git push**
- Local Repository의 commit을 Remote Repository (ex. Github)에 업로드하는 명령어.
- 코드의 최신 버전을 팀원들과 공유, 백업하는 데 사용된다.
**git fetch**
- Remote Repository의 최신 변경 사항을 Local로 가져오는 명령어.
- 원격 저장소의 최신 상태를 확인하고 싶을 때 사용한다. git fetch 후, git merge나 git rebase를 사용해서 원격 변경 사항을 현재 작업 브랜치에 반영할 수 있다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
**branch**
- - 개발의 주 흐름에서 벗어나, 독립적으로 어떤 작업을 진행하기 위한 기능.
- 프로젝트의 한 부분에서 다른 부분으로 작업 범위를 옮길 수 있게 도와준다.
- 생성 : git branch <생성할 branch 이름>
- 삭제 : git branch -d <삭제할 branch 이름>
- 이동 : git checkout <이동할 branch 이름>
**HEAD**
-  현재 작업 중인 branch의 가장 최신 커밋.
- Git이 어느 시점의 코드를 바탕으로 작업하고 있는지를 의미한다. 즉, 프로젝트의 현재 '상태'를 나타내는 포인터이다.
**git checkout**
- 특정 branch로 전환하거나, 과거의 어떤 시점(버전)으로 작업 디렉토리의 상태를 되돌리는 명령어.
- 이전 버전의 파일을 복구하거나, 다른 버전 간의 차이를 비교할 수 있게 한다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
**git clone**
- 기존에 존재하는 Git 저장소 (Repository)를 Local 컴퓨터로 복사해오는 명령어.
- Remote 저장소의 모든 데이터(코드, branch, 버전 기록 등)를 포함하여 복제한다. 
**git init**
- 새로운 Git 저장소를 만드는 명령어.
- Git이 작업 디렉토리를 Git 저장소로 초기화하고, 코드의 버전 관리를 시작할 수 있다. 새로운 저장소를 만들고, 프로젝트의 최초 버전을 관리하기 시작할 때 사용.
**origin**
- 원격 저장소 (Remote Repository)를 나타내는 가장 일반적인 별칭.
- 프로젝트 초기에 `push, pull, fetch` 등의 명령어 사용 시, 원격 저장소를 지칭하는 별칭의 역할을 한다.
- 설정 방법
    1. 원격 저장소 연결하기
    2. 원격 저장소 확인하기
        - 현재 로컬과 연결된 모든 원격 저장소와 그들의 URL이 출력됨
    3. 원격 저장소 별칭 변경, 제거
```
# 원격 저장소를 새로 연결
git remote add <별칭> <원격 저장소 주소>

# 연결된 원격 저장소 확인
git remote -v

# 별칭 변경
git remote rename <기존 별칭> <새 별칭>

# 원격 저장소 연결 제거
git remote remove <별칭>
```

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
**git reset**
- 주로 잘못된 commit을 취소하거나, 변경할 때 사용하는 명령어.
- 3가지 옵션을 통해 commit의 상태를 조절할 수 있다.
1. `--soft`
    - 지정한 커밋으로 돌아간다. Staging Area(임시저장공간)의 상태는 유지한다.
    - 커밋만 취소하고, 변경된 파일들을 다시 커밋할 때 사용
    - 즉, 가장 최근에 커밋된 내용이 사라지고, 변경 사항이 Staging Area에 남아 있어서 다시 커밋할 수 있다.
2. `--mixed`
    - 기본옵션으로, 지정한 커밋으로 돌아가면서 Staging Area의 변경 사항도 취소한다. 작업 디렉토리의 파일 내용은 그대로 유지된다.
    - 커밋을 취소하고, 변경 사항을 수정한 후, 다시 Staging 하고 싶을 때 사용
    - 즉, 지정한 커밋으로 되돌리는 동시에, Stage에 올라가 있던 변경 사항들이 작업 디렉토리에 남게 되어 수정 후 다시 Staging 가능하다.
3. `--hard`
    - 지정한 커밋으로 돌아가고, Staging Area 및 작업 디렉토리의 변경 사항 모두를 취소한다.
    - 잘못된 커밋을 완전히 취소하고, 이전 상태로 완벽하게 돌아가고 싶을 때 사용
    - 즉, 작업 디렉토리의 내용까지 완전히 되돌린다. 다시 되돌릴 수 없으므로, 사용에 주의해야 한다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
**pull request**
- 코드 변경 사항을 검토/논의 후, 메인 프로젝트에 병합하기 위한 요청.
- 소스코드에 대한 변경 사항을 다른 사람들과 공유하고, 리뷰 받고자 할 때 사용하는 Github의 기능이다.
- 사용 과정
    1. 자신의 Local에서 작업을 진행한 후, 변경 사항을 Github에 push한다.
    2. Github에서 메인 프로젝트 저장소로 pull request를 생성한다.
    3. 팀원/프로젝트 관리자가 이 pull request를 리뷰하고, 피드백을 제공한다.
    4. 모든 리뷰와 변경 요청이 완료되면, 메인 저장소의 관리자가 pull request를 merge하여 변경 사항을 프로젝트에 반영한다.
**merge**
- 두 가지 branch의 변경 사항을 하나로 합치는 과정
- 개발 과정에서 branch를 활용하여 기능 개발, 버그 수정 등을 진행한 수, 이를 다시 메인 코드라인에 병합해야 할 때 사용한다.
1. `fast-forward`
- 현재 branch의 HEAD가 병합하려는 branch의 히스토리에 이미 포함되어 있을 때, 단순히 현재 branch의 HEAD를 최신 commit으로 옮기는 방식
- 별도의 commit이 생성되지 않는다.
![B1991810-9A2D-4C9B-A9AB-6134A6A0753E.jpg](https://prod-files-secure.s3.us-west-2.amazonaws.com/94628612-4999-4a9e-bd19-428a991f4eb4/07bf5db2-2482-457e-abea-7fff29726106/B1991810-9A2D-4C9B-A9AB-6134A6A0753E.jpg)
 2. `3-way-merge`
- 두 branch의 기점부터 diverge(갈라진) 지전까지 고려하여 병합하는 방식
- 병합된 새로운 commit이 생성되고, 이 commit은 두 branch의 각 최신 commit을 부모로 가진다.
![3F39365F-3CF4-419A-A822-76A79D49FAAB.jpg](https://prod-files-secure.s3.us-west-2.amazonaws.com/94628612-4999-4a9e-bd19-428a991f4eb4/b6a46e40-3024-4127-a4da-aa10af653a31/3F39365F-3CF4-419A-A822-76A79D49FAAB.jpg)

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
**rebase**
- 한 branch의 변경 사항을 다른 branch로 가져와서 두 branch의 공용 기저(base)를 다시 설정하는 과정
- 즉, 기저 재설정을 의미하고, 복잡한 commit 히스토리를 깨끗하게 유지할 수 있는 방법이다.
- 장점
    - 공유하는 branch의 최신 변경 사항을 즉각 반영
    - commit 이력을 하나의 직선으로 관리 가능 (깔끔한 프로젝트 히스토리)
- 사용 시점
    - 자신의 작업 branch에 다른 branch의 최신 변경 사항을 반영하고 싶을 때
    - 병합 충동이 예상되는 상황에서 branch 충돌을 미리 해결하고 싶을 때
    - 단, 다른 사람과 공유하는 branch에서는 조심해서 사용
![1928B19D-B305-4D8D-92C2-30615BFDEA56.jpg](https://prod-files-secure.s3.us-west-2.amazonaws.com/94628612-4999-4a9e-bd19-428a991f4eb4/d8d9204a-5380-463b-bf7e-c7b7df15b75a/1928B19D-B305-4D8D-92C2-30615BFDEA56.jpg)

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
**git stash**
- 아직 마무리하지 않은 작업을 스택에 임시로 저장하는 명령어
- 다른 작업을 수행한 후, 저장했던 변경 사항을 다시 적용할 수 있다.
- 수정한 파일만 저장한다 (Modified이지만 Tracked인 파일, Staged 파일 등)
- 활용 방법
    - 작업 중 급하게 다른 branch로 이동해야 하는 상황에서, 현재 branch의 변경 사항이 아직 commit할 준비가 안 되었을 때
    - 실험적인 변경을 해보고 싶지만, 현재 작업 내용을 잃고 싶지 않을 때
```
# 현재 작업 중인 변경 사항을 임시 저장
git stash

# 가장 최근에 stash된 변경 사항을 다시 적용
git stash pop

# stash된 변경 사항을 적용하지만, stash 목록에서 제거 하지 않음
git stash apply

# 현재까지의 stash 목록을 보여줌
git stash list

# 모든 stash를 제거
git stash clear
```

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

> [git 연습 사이트 공유](https://learngitbranching.js.org/?locale=ko, "git 연습 사이트")

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
