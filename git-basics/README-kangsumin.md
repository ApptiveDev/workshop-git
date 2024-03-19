# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

### Git
- 소스코드를 효과적으로 관리하기 위해 개발된 분산형 버전 관리 시스템이다.
  
- Git에서는 소스 코드가 변경된 이력을 쉽게 확인할 수 있고, 특정 시점에 저장된 버전과 비교하거나 특정 시점으로 되돌아갈 수도 있다.
  
- 컴퓨터의 변경사항을 추적하고 여려 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위해 사용한다.

- Git은 Remote Repository(원격 저장소)와 Local Repository(로컬 저장소) 두 종류의 저장소를 제공한다.

  - **Remote Repository(원격 저장소)**: 파일이 원격 저장소 전용 서버에서 관리되며 여러 사람과 함께 공유하기 위한 저장소이다.
  
  - **Local Repository(로컬 저장소)**: 내 PC에 파일이 저장되는 개인 전용 저장소이다.

- 평소에는 내 PC의 로컬 저장소에서 작업하다가 소스를 공개하고 싶을 때 원격 저장소에 업로드 할 수 있다.
- 또한 원격 저장소에서 다른 사람이 작업한 파일을 로컬 저장소로 가져올 수도 있다.

### GitHub 
- 클라우드 방식으로 관리되는 버전 관리 시스템(VCS)으로 **원격저장소를 제공** 한다.
  
- Git에 원격 저장소 호스팅을 지원하는 웹 서비스이며 GitHub를 통해 Git에 저장된 파일 버전을 웹 상의 저장소에 업로드 하여 다른 이들과 공유할 수 있다.
  
- 개발자들간의 협업이 가능한 서비스이다.

### 정리
- Git은 소스 코드의 버전 관리를 위한 도구이고, GitHub은 Git 저장소를 호스팅하고 프로젝트 관리를 위한 서비스이다.

-  Git을 사용하여 로컬에서 작업한 변경 사항을 추적하고 관리하고, GitHub을 사용하여 프로젝트를 온라인으로 공유하고 협업할 수 있다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
- Working Directory
- Git Add
- Git Commit
- Git Push
  
## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
git clone:
git init:
origin:

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
reset:

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
Pull Request:
Merge:

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
rebase:

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.
git stash:

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
