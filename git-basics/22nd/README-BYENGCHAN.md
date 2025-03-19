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

- Branch: 특정 커밋을 가리키는 포인터
- HEAD: 현재 작업 중인 브랜치를 가리키는 포인터
  - 일반적으로 현재 체크아웃된 브랜치를 나타냄

```cmd
git branch <생성할 브랜치명>
```

- 브랜치 생성
- 브랜치명에는 공백이 들어가면 안된다.

- 브랜치 전환

```cmd
git switch <전환할 브랜치명>
Git 2.23 이후 추천방식
git checkout <전환할 브랜치명>
```

- 브랜치 전환

```cmd
git checkout -c <브랜치명>
```

- 브랜치 생성 후 바로 이동

```cmd
git branch -d <브랜치명>
강제삭제
git branch -D 브랜치이름
```

- 병합이 완료된 브랜치 삭제
- 병합이 완료되지 않으면 -D 사용

## clone, init, origin

git 저장소 생성 방법에는 `git init` 방식과 `git clone` 방식이 있다

| 명령어      | `git clone`                                    | `git init`                  |
| ----------- | ---------------------------------------------- | --------------------------- |
| 용도        | 기존 원격 저장소를 복제                        | 새로운 로컬 레포지토리 생성 |
| 동작방식    | 원격 저장소의 전체 데이터를 가져와 로컬에 복사 | 빈 Git 저장소를 생성        |
| origin 설정 | 자동으로 origin 설정                           | 원격 저장소 없음(수동)      |

### origin 이란?

- 원격 저장소의 기본 이름
- `git clone`을 사용하면 자동으로 origin 설정
- `git init`을 사용하면 직접 origin 설정

## reset

### 1. `--soft`

- HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리킨다.
- 현재 작업 중인 working directory, stagin area는 영향 받지 않음 X

### 2. `--mixed`

- HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리킨다.
- staging area도 해당 커밋의 모습과 동일하게 변한다.
- working directory는 영향 받지 않는다 X

### 3. `--hard`

- HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리킨다.
- staging area , working directory 모두 해당 커밋의 모습과 동일하게 변함.

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

```

```
