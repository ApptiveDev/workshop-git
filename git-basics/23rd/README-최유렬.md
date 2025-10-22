# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.


git은 분산 버전 관리 시스템이고, github는 원격 레포지토리 호스팅 서비스이다. 개발자가 local repo에서 작업한 이력을 git을 통해 관리할 수 있으며, 관리한 내역을 remote repo(github 등)로 업로드해 공유할 수 있다. 다른 개발자들은 업로드된 remote repo를 복제해 local repo에서 작업할 수 있다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : git이 파일을 추적하는 작업 공간
- Staging Area : 커밋할 변경 사항들을 모아두는 임시 공간
- Local Repo : 내 컴퓨터에 있는 버전 이력 저장소
- Remote Repo : 원격 서버에서 공유되는 공용 버전 이력 저장소 (예: github)

- `git add` : 커밋할 변경사항을 Staging Area로 추가
- `git commit` : 선택한 변경사항을 Local Repo에 기록
- `git push` : Local Repo에 기록된 변경이력을 Remote Repo로 업로드
- `git pull` : Remote Repo의 변경이력을 가져와 내 Working Directory에 병합 시도


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- Commit: 변경 사항을 기록하는 Git의 기본 단위로 각 commit은 고유한 해시값을 가집니다.
- Branch: 독립적으로 개발을 진행할 수 있는 작업 공간으로, 여러 브랜치를 만들어 병렬 작업이 가능합니다. 보통 기본 작업 파일을 살려두고 나머지 기능이나 수정사항을 점검한 후 적용하기 위해 사용합니다.
- HEAD: 현재 체크아웃(작업 중)된 브랜치를 가리키는 포인터로, HEAD가 가리키는 브랜치가 변경됩니다. (HEAD = 현재 작업중인 branch)
- git checkout [브랜치명]: 특정 브랜치로 이동하거나, 특정 커밋을 체크아웃할 때 사용합니다.
    - git checkout -b [새로운 브랜치명] : 새 브랜치를 생성하고 해당 브랜치로 이동
- git switch [브랜치명] : 특정 브랜치로 이동합니다.
    - git switch -c [새로운 브랜치명]: 새 브랜치를 생성하고 해당 브랜치로 이동합니다.
- git branch [새로운 브랜치명]: 새로운 브랜치를 생성하지만, 현재 브랜치를 변경하지 않습니다.
- git branch -d [브랜치명]: 로컬 브랜치를 삭제합니다.
- git push origin --delete [브랜치명]: 원격 브랜치를 삭제합니다.

### 사용 예시 
```bash
git switch -c new_branch  # new_branch를 만들고 해당 브랜치로 이동
# 변경사항을 만들었다고 가정
git add .
git commit -m "new branch commit"
git switch main
git merge new_branch      # main 브랜치에 merge
git branch -d new_branch  # 필요 없으면 삭제
```

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git init : 로컬 저장소에 새로운 Git repository를 생성합니다. GitHub와는 따로 연동해줘야합니다.
- git clone : 원격 저장소에 있는 기존의 repository를 복제하여 로컬로 가져옵니다. 원격 저장소와 자동으로 연동됩니다.
- origin : git clone시 자동으로 생성되는 remote 저장소의 별칭(alias)
    - 만약 따로 연동해줘야 할 경우..
    - `git remote add origin '저장소 주소'`
    - `git push -u origin main`

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- `git reset --soft [커밋ID]` : 지정한 커밋으로 HEAD만 이동하고, 변경 사항은 Staging Area(=index)에 유지됩니다. 
    - 최근 커밋을 수정할 때 유용
- `git reset --mixed [커밋ID]` : 지정한 커밋으로 HEAD와 Staging Area를 이동하지만, Working Directory는 그대로 유지됩니다. 커밋은 취소되지만 파일 변경 사항은 남아있어 다시 커밋할 수 있습니다.
    - git reset의 기본값
- `git reset --hard [커밋ID]` : 지정한 커밋으로 HEAD, Staging Area, Working Directory를 모두 이동시켜 변경 사항을 완전히 삭제합니다.
    - 실행하면 되돌리기 어려움

- 공유된 브랜치에 대해 reset을 사용하면 커밋이 꼬일 수 있으므로 주의해야 함
    - 대안: git revert 명령어 사용 (되돌린 것에 대한 커밋이 생성됨)


## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request : GitHub, GitLab 등에서 사용하는 기능으로, 브랜치 병합을 요청하는 과정입니다. 협업을 하며 수정사항을 병합할지 검토한 후 진행할 수 있습니다.
    - Fork: repo에 대한 읽기 권한이 없을 경우, repo를 복제해 수정한 다음 pull request
    - Branch 생성 : 새 branch에서 변경사항을 커밋하고, merge 요청
- Merge : 한 브랜치의 변경 사항을 다른 브랜치에 적용하는 과정입니다. `git merge [브랜치명]` 명령어로 수행됩니다.



1) Fast-Forward Merge : 대상 브랜치가 병합하려는 브랜치의 최신 커밋을 그대로 따라갈 수 있을 때 발생합니다. 별도의 병합 커밋 없이 브랜치의 HEAD가 이동합니다.
    - 브랜치가 선형으로 병합
2) 3-Way Merge : 두 브랜치가 서로 다른 변경 사항을 가질 때 발생하며, 공통 조상(ancestor)을 기준으로 병합합니다. 새로운 병합 커밋이 생성됩니다.
    - 브랜치가 다이아몬드 모양으로 병합

### main 브랜치에서 sub 브랜치를 병합
```bash
git switch main  # 메인 브랜치로 이동
git merge sub    # sub 브랜치를 병합
```

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase : 브랜치의 변경 사항을 다른 브랜치의 최신 상태 위로 이동시키는 명령어입니다. git merge와 달리 병합 커밋 없이 깔끔한 커밋 히스토리를 유지할 수 있습니다.

<활용방법>
1) 협업 중 최신 코드 반영
2) 불필요한 Merge Commit 방지 : 병합 커밋 없이 정리된 커밋 히스토리를 유지할 수 있습니다.
3) 커밋 순서 정리 및 수정 : git rebase -i HEAD~n을 사용하면 특정 개수의 커밋을 수정, 삭제, 합치기 할 수 있습니다.

### sub 브랜치를 main 브랜치로 rebase
```bash
git switch sub  # sub branch로 이동
git rebase main # main branch로 rebase
```

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- git stash : 작업 중인 변경 사항을 임시로 저장하고, 작업 디렉토리를 깨끗한 상태로 되돌리는 기능입니다.

<활용방법>
1) 커밋하지 않고도 다른 브랜치로 이동하거나, 코드를 테스트할 때 유용합니다.
2) 변경 사항 임시 저장 : Staging Area와 Working Directory의 변경 사항이 stash로 이동하고, 작업 디렉토리는 깨끗한 상태가 됩니다.
3) 임시 저장한 변경 사항 적용 : 가장 최근에 저장한 변경 사항을 다시 적용하고, stash 목록에서 제거합니다.
4) 저장된 목록 확인 : 여러 개의 stash를 저장할 수 있으며, 목록을 확인할 수 있습니다.
5) 특정 stash 적용 : stash@{n}에 해당하는 특정 stash를 적용하지만 목록에서 제거하지 않습니다.
6) 특정 stash 삭제
7) 모든 stash 삭제

### 사용 예
```bash
git stash save "임시 변경사항"
# git switch, checkout 등 작업 수행
git stash list
git stash pop
```

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
- Github는 수많은 양의 레포지토리들을 어떻게 감당할까
