# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.


## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

# git
git은 본인의 코드와 그 수정내역을 기록하고 관리하도록 돕는 버전 관리 프로그램이다 로컬에서 프로젝트의 기록을 스스로
관리할 수 있도록 해준다 git을 통해 브랜치를 생성하고 이전 브랜치로 복구, 삭제 병합이 가능하다 하지만
로컬 저장소를 사용하기 때문에 다른 개발자와 실시간으로 작업을 공유할 수 없다

# git hub
gihub는 git 저장소를 관리하는 클라우드 기반 호스팅 서비스이다 git 저장소 호스팅 서비스는 클라우드 기반으로 다른 
사람과 소스코드 공규가 가능하며 git의 기본적인 기능을 확장하여 제공한다.
github같은 클라우드에 저장하는 git을 remote git이라고 부른다.



## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

## git 동작

working directory는 작업 공간으로 아직 git에 기록될 준비가 되지 않은 파일들이 위치하는 공간
Staging Area는 대기 공간으로 Git에 기록될 준비가 된 파일들이 위치하는 공간
Logal Repository는 .git폴더이다.
Remote Repository는 원격 저장소이다 github라고 생각하면 된다.
git add를 하면 Staging Area에 올라간다. 여기서 git commit을 하면 Local Repository에 저장된다 commit만 하면
자신의 컴퓨터 자체에만 기록되고 Remote Repository에는 저장이 안된다
push를 해주면 Remote Repository에 저장이 된다.



## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

**브랜치란** 독립적으로 어떤 작업을 진행하기 위한 개념 각각의 브랜치는 다른 브랜치의 영향을 받지 않기 때문에, 여러 작업을 동시에 진행할 수 있다. 
여러명이 동식에 작업을 할 때 다른 사람의 작업에 영향을 주거나 받지 않도록, 메인 브랜치에서 자신의 작업 전용 브랜치를 만들고 각자 작업을 진행한 후 작업이 끝난 사람은 메인 브랜치에 자신의 브랜치의 변경 사항을 적용한다.
**HEAD란**  해당 브랜치의 마지막 커밋을 뜻한다.
```
git checkout -b test 는 test 브랜치를 생성후 바로 test브랜치로 이동
git checkout main은 main브랜치로 이동하고
git branch -d test를 하면 test 브랜치를 삭제한다.
```

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

**git init**을 하면 .git이라는 하위 디렉토리를 해당 디렉토리 위치에 만든다.
init은 아직 버전관리를 하지 않은 로컬 디렉토리 하나를 선택해서 Git저장소를 적용하는 방법이다
`사용법 : git init`
**git clone**이란 이미 만들어진 git 저장소를 복사하고 싶을 때 사용한다 저장소로 부터 프로젝트를 복제한다.
`사용법 : git clone <저장소 위치>`

**origin**이란 원격 저장소의 이름을 뜻한다.
`git remote add origin <주소>`


## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## git reset
**git reset**은 과거의 commit으로 돌아가고 이후의 커밋은 삭제하는 명령어 이다.
`git reset-hard : 해당 커밋ID의 상태로 이동하고, Working Directory와 index영역 모두 초기화`
`git reset-mixed : 해당 커밋ID의 상태로 이동하고, Index영역은 초기화되고 Working Directory는 변경되지 않음`
`gir reset-soft : 해당 커밋ID의 상태로 이동하고 Index영역과 Working Directory 모두 변경되지 않고 commit된 파일들을 staging area로 돌려놓는다.`

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

**pull request**는 저장소를 fork한 뒤, 포크한 저장소에서 변경 사항을 가지고 원래 저장소의 소유자에게 병합 해달라고 요청하는 것이다.

여기서 fork는 다른 사람의 깃허브 저장소에서 내 깃허브 저장소로 그대로 복제하는 기능이다. 
fork한 저장소는 원본 저장소와 연결되어 있다. 연결 되어 있다는 의미는 original repository에서 새로운 commit이 생기면 이는 그대로 forked된 repository로 반영할 수 있다. 이 때 fetch나 rebase의 과정이 필요하다.

**Merge**란 git branch를 다른 branch로 합치는 과정이다 
###Fast Forward Merge
커밋이 생기지 않고 현재 브랜치의 HEAD가 대상 브랜치의 HEAD까지로 옮기는 merge이다 
어떤 경우에 사용 할까?
예로 들자면 master vranch에서 새로운 브랜치 하나를 생성 한 후에 master branch는 더이상 커밋하지 않고, 생성된
브랜치에서만 커밋을 하는경우 merge하면 master브랜치의 Head가 새로운 브랜치 Head commit 이후로 이동된다.

###3 way merge
병합하려는 두개의 브랜치의 공통 조상을 base로 두고 base와 다른 두개를 비교하며 충돌하거나 병합 시켜준다.

![스크린샷 2023-08-13 012841](https://github.com/ApptiveDev/study-git/assets/64734115/e914759d-155a-43d8-ba54-1126b10cb266)

1. 위 사진에서 Base를 기준으로 Me와 other을 비교한다 A는 Me와 base가 같으므로 수정된 Other을 사용해서 자동으로 삭제 시켜주고 
2. B는 셋다 같으므로 B
3. C는 Me와 other,base다 다르므로 충돌
4. D는 Base와 Other이 같고 Me에서만 다르므로 병합할 때 D코드는 삭제한다

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

**rebase**란 말 그대로 재설정한다는 의미로, 하나의 브랜치가 다른 브랜치에서 파생되서 나온 경우, 다른 브랜치에서 진행된 커밋을 다시 가져와서 base를 재설정하는 것이다. 새로운 커밋을 기반으로 작업을 함으로써 파생된 브랜치는 병합시에 conflict없이 자신의 브랜치에 진행된 커밋을 반영할 수 있다.
### rebase의 장점
 커밋 히스토리가 시간순서대로 반영되어 시간순서대로 관리하거나 merge를 통해 발생하는 불필요한 병합 커밋을 제거할 때  사용하면 좋다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

### stash란
자신이 어떤 작업을 하던 중에 다른 요청이 들어와서 하던 작업이 완료되지 않앗지만 잠시 멈추고 다른 브랜치로 변경할 일이 있으면 완료되지 않은 일을 commit하기엔 껄끄러울 때 잠시 스택에 저장할 수 있도록 하는 명령어이다.
`git stash 또는 `
`git stash save를 하면 된다.`
`git stash list를 하면 stash 목록을 확인할 수 있다.`
`git stash apply를 가장 최근의 stash를 가져와 적용한다.`
`git stash apply [stash 이름] 해당 stash를 적용한다.`
`git stash drop 가장 최근의 stash를 제거한다.`
`git stash drop [stash 이름] 해당 stash를 제거한다.`

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push/pull --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
