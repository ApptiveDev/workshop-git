## Git 과 Github의 차이

### Git

- 버전 관리 소프트웨어

프로젝트의 수정한 코드가 동작하지 않을 때 버전을 롤백 할 수 있음

로컬 저장소의 모든 변경사항을 기록하여 파일의 버전관리

### Github

- Git을 사용하는 프로젝트를 지원하는 **웹 호스팅 서비스**이다.

Git은 **로컬(local)** 저장소에서 작동하여 다른 개발자와 작업을 공유하고 협업하기 어렵다.

Github은 웹 상에서 클라우드 서버(**원격(remote)** 서버)를 통해 **로컬(local)** 저장소의 코드를 업로드하고 공유할 수 있다.

다른 사람들과 작업물 공유 및 사용할 수 있다.

## Git Workflow

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F7XB0f%2FbtsdlqFq3Il%2FVKOMdP7p5a1ziN9EhAFeE0%2Fimg.png" width= 50%>

### Git 파일의 상태

Git은 파일을 크게 `Commited`, `Modified`, `Staged`의 세 가지 상태로 관리함

| 상태     | 설명                                                |
| -------- | --------------------------------------------------- |
| Commited | 데이터가 로컬 저장소에 안전하게 저장됨              |
| Modified | 수정한 파일을 아직 로컬 저장소에 커밋하지 않은 상태 |
| Staged   | 수정한 파일을 곧 commit 할 것이라고 표시한 상태     |

Git Directory(Repostiry)는 현재 작업하는 디렉터리에서 파일을 가져와 **Working Directory**를 만듭니다.

1. Working Directory에서 파일을 수정
2. 수정한 파일을 git add 로 Staging Area에 올림
3. Staging Area에 있는 파일들을 git commit으로 Repository에 영구적으로 저장

### add / commit / push 의 차이

| 명령어       | 설명                                                       |
| ------------ | ---------------------------------------------------------- |
| `git add`    | 다음 변경을 기록할 때 까지 변경 내용을 모아놓기 위해 사용  |
| `git commit` | 변경 내용을 로컬 repositry에 기록(내 컴퓨터의 로컬 저장소) |
| `git push`   | 변경 내용을 원격 repositry에 기록 (github)                 |

`git add` 명령어를 통해 Staging Area로 변경 내용의 일부 혹은 전부를 이동시킨다.

`git status` 명령어를 통해 현재 Working Directory와 Staging Area의 상태를 확인할 수 있다.

Staging Area에 들어간 변경 내용을 `git commit`으로 로컬 저장소에 기록한다.

`git push`로 원격 저장소에 업데이트 할 수 있다.

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

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
