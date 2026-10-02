# Git 기초

## Git != Github

Git과 Github는 같은 것이 아니다.

**Git**은 내 컴퓨터의 파일 변경 이력을 관리하는 **버전 관리 도구**이고,  
**Github**는 Git으로 관리하는 프로젝트를 인터넷에 저장하고 다른 사람과 공유할 수 있게 해주는 **원격 저장소 서비스**이다.

즉,

- **Local**: 내 컴퓨터에 있는 Git Repository
- **Remote**: Github와 같이 인터넷에 존재하는 Repository

라고 생각할 수 있다.

Git만 사용해서 내 컴퓨터 안에서 버전을 관리할 수도 있지만, Github를 사용하면 다른 사람과 코드를 공유하거나 협업하기 편해진다.

예를 들어 내 컴퓨터에서 코드를 수정하고 commit한 뒤,

```bash
git push
```

를 사용하면 Github와 같은 Remote Repository에 변경 내용을 업로드할 수 있다.

---

## Git Workflow

Git에서 파일은 크게 다음 과정을 거쳐 관리된다.

**Working Directory → Staging Area → Local Repository → Remote Repository**

### Working Directory

현재 실제로 파일을 작성하거나 수정하고 있는 공간이다.

예를 들어 `index.html`을 수정하면 아직 Git에 저장된 것은 아니고 Working Directory에 변경 사항이 존재하는 상태이다.

변경 상태는 다음 명령어로 확인할 수 있다.

```bash
git status
```

---

### Git Add

```bash
git add 파일명
```

또는

```bash
git add .
```

을 사용한다.

Working Directory에서 수정한 파일을 **Staging Area**에 올리는 명령어이다.

Staging Area는 다음 commit에 포함할 파일을 미리 선택해두는 공간이라고 이해했다.

예를 들어 여러 파일을 수정했더라도 특정 파일만 `git add`하면 해당 파일만 다음 commit에 포함시킬 수 있다.

---

### Git Commit

```bash
git commit -m "메시지"
```

Staging Area에 올라온 변경사항을 하나의 버전으로 저장한다.

commit에는 고유한 ID가 생성되기 때문에 이전 상태를 확인하거나 돌아갈 수 있다.

예를 들어

```bash
git commit -m "로그인 기능 추가"
```

와 같이 해당 commit에서 무엇을 변경했는지 알아볼 수 있는 메시지를 함께 작성한다.

commit 기록은 다음 명령어로 볼 수 있다.

```bash
git log
```

---

### Git Push

```bash
git push
```

Local Repository에 저장한 commit을 Github와 같은 **Remote Repository로 전송하는 명령어**이다.

즉,

```text
파일 수정
↓
git add
↓
git commit
↓
git push
```

순서로 작업한다고 이해했다.

---

## Branch, HEAD

### Branch

Branch는 프로젝트의 작업 흐름을 나누기 위한 기능이다.

예를 들어 현재 정상적으로 동작하는 `main` 브랜치를 유지하면서 새로운 로그인 기능을 개발하고 싶다면,

```bash
git branch feature/login
```

처럼 새로운 브랜치를 만들 수 있다.

새로운 기능을 별도의 브랜치에서 개발하면 기존 코드에 영향을 덜 주면서 작업할 수 있다.

현재 존재하는 브랜치는

```bash
git branch
```

로 확인할 수 있다.

브랜치를 삭제하려면

```bash
git branch -d 브랜치명
```

을 사용한다.

---

### HEAD

HEAD는 **현재 내가 작업하고 있는 위치를 가리키는 포인터**이다.

일반적으로 현재 사용 중인 브랜치의 최신 commit을 가리킨다.

예를 들어

```text
main → commit A → commit B
                    ↑
                   HEAD
```

라면 현재 `main` 브랜치의 `commit B`에서 작업하고 있다는 의미이다.

---

### git checkout

기존에는 브랜치를 이동할 때 다음 명령어를 많이 사용했다.

```bash
git checkout 브랜치명
```

예를 들어

```bash
git checkout main
```

을 실행하면 main 브랜치로 이동한다.

새로운 브랜치를 만들면서 이동할 수도 있다.

```bash
git checkout -b feature/login
```

최근에는 역할을 좀 더 명확하게 하기 위해 브랜치 이동에는

```bash
git switch
```

도 많이 사용한다.

```bash
git switch main
```

새 브랜치를 만들면서 이동하려면

```bash
git switch -c feature/login
```

을 사용할 수 있다.

---

## clone, init, origin

### git clone

이미 Github 등에 존재하는 Repository를 내 컴퓨터로 가져올 때 사용한다.

```bash
git clone Repository_URL
```

Repository의 파일뿐 아니라 기존 commit 기록과 Remote Repository 정보까지 같이 가져온다.

---

### git init

현재 내 컴퓨터에 존재하는 폴더를 새 Git Repository로 만들 때 사용한다.

```bash
git init
```

실행하면 해당 폴더 내부에 `.git`이라는 디렉터리가 생성되고 Git이 파일 변경 이력을 관리하기 시작한다.

정리하면,

- `git clone`: 이미 존재하는 Repository를 가져옴
- `git init`: 현재 폴더에서 새로운 Repository를 시작함

이라고 이해했다.

---

### origin

`origin`은 일반적으로 **Remote Repository의 기본 이름**이다.

예를 들어 Github Repository를 clone하면 해당 Github Repository가 자동으로 `origin`이라는 이름으로 등록된다.

현재 등록된 Remote Repository는

```bash
git remote -v
```

로 확인할 수 있다.

직접 등록하려면

```bash
git remote add origin Repository_URL
```

을 사용할 수 있다.

즉,

```bash
git push origin main
```

은

> origin이라는 Remote Repository의 main 브랜치로 commit을 push한다.

는 의미이다.

---

## reset

`git reset`은 commit이나 staging 상태를 이전 상태로 되돌릴 때 사용한다.

대표적으로 `--soft`, `--mixed`, `--hard` 세 가지가 있다.

### reset --soft

```bash
git reset --soft HEAD~1
```

commit만 취소하고 변경 내용은 **Staging Area에 남겨둔다.**

즉, commit 메시지를 잘못 작성했거나 commit을 다시 구성하고 싶을 때 사용할 수 있다.

---

### reset --mixed

```bash
git reset --mixed HEAD~1
```

commit과 staging을 취소하지만 수정한 파일 내용은 **Working Directory에 남겨둔다.**

`--mixed`는 기본 옵션이므로

```bash
git reset HEAD~1
```

이라고 작성해도 같은 동작을 한다.

---

### reset --hard

```bash
git reset --hard HEAD~1
```

commit뿐 아니라 Staging Area와 Working Directory의 변경 내용까지 되돌린다.

수정 내용 자체가 사라질 수 있기 때문에 주의해서 사용해야 한다.

정리하면 다음과 같다.

| 명령어 | Commit | Staging | 수정한 파일 |
|---|---|---|---|
| `--soft` | 취소 | 유지 | 유지 |
| `--mixed` | 취소 | 취소 | 유지 |
| `--hard` | 취소 | 취소 | 삭제 |

---

## Pull Request, Merge

### Pull Request

Pull Request(PR)는 내가 작업한 브랜치의 내용을 다른 브랜치에 반영해달라고 요청하는 기능이다.

예를 들어

```text
feature/login
↓
Pull Request
↓
main
```

과 같이 사용할 수 있다.

PR을 사용하면 바로 main 브랜치에 코드를 합치는 것이 아니라 팀원들이 코드를 확인하고 리뷰한 뒤 Merge할 수 있다.

따라서 협업 프로젝트에서 많이 사용한다.

---

### Merge

Merge는 서로 다른 브랜치의 작업 내용을 하나로 합치는 것이다.

예를 들어 현재 `main` 브랜치에서 다음 명령어를 실행하면

```bash
git merge feature/login
```

`feature/login`의 변경 내용을 main에 합친다.

---

### Fast-Forward Merge

main 브랜치에서 새로운 commit이 생기지 않은 상태에서 다른 브랜치만 앞으로 진행된 경우 사용할 수 있다.

예를 들어

```text
A --- B
      \
       C --- D
```

에서 main이 B를 가리키고 feature가 D를 가리킨다면,

Merge 후에는 단순히 main의 위치를 D까지 이동시키면 된다.

```text
A --- B --- C --- D
                  ↑
                 main
```

따라서 별도의 Merge Commit이 필요하지 않다.

---

### 3-Way Merge

두 브랜치가 각각 다른 commit을 가지게 된 경우 사용된다.

예를 들어

```text
      C --- D
     /
A --- B
     \
      E --- F
```

처럼 서로 다른 방향으로 개발이 진행되었다면 단순히 포인터를 이동할 수 없다.

이 경우 Git은

- 두 브랜치가 갈라지기 전 commit
- 현재 브랜치의 commit
- Merge할 브랜치의 commit

세 가지를 비교해서 새로운 **Merge Commit**을 생성한다.

```text
      C --- D
     /       \
A --- B       M
     \       /
      E --- F
```

이것을 3-Way Merge라고 한다.

---

## rebase

rebase는 한 브랜치의 시작점을 다른 브랜치의 최신 commit 뒤로 옮기는 기능이다.

예를 들어

```text
      C --- D feature
     /
A --- B --- E --- F main
```

에서 feature 브랜치에서

```bash
git rebase main
```

을 실행하면 다음과 같이 변경된다.

```text
A --- B --- E --- F --- C' --- D'
```

feature 브랜치가 최신 main을 기준으로 다시 이어지는 형태가 된다.

Merge와 목적은 비슷하지만 commit 기록을 한 줄로 깔끔하게 만들 수 있다는 장점이 있다.

하지만 rebase는 기존 commit의 기반을 변경하면서 **새로운 commit을 생성하는 방식**이기 때문에 이미 다른 사람과 공유한 commit에 함부로 사용하는 것은 주의해야 한다.

---

## stash

`git stash`는 아직 commit하지 않은 수정사항을 임시로 보관하는 기능이다.

예를 들어 현재 기능을 개발하다가 갑자기 다른 브랜치로 이동해서 오류를 수정해야 하는 상황이 있을 수 있다.

하지만 현재 수정 내용이 완료되지 않아 commit하기 애매하다면

```bash
git stash
```

를 실행한다.

그러면 현재 변경사항을 임시로 저장하고 Working Directory를 깨끗한 상태로 만들 수 있다.

저장한 stash 목록은

```bash
git stash list
```

로 확인할 수 있다.

다시 변경사항을 적용하려면

```bash
git stash apply
```

를 사용할 수 있다.

가장 최근 stash를 적용하면서 stash 목록에서도 제거하려면

```bash
git stash pop
```

을 사용한다.

---

# Advanced

## Github Flow와 Git Flow

### Github Flow

Github Flow는 비교적 간단한 브랜치 전략이다.

기본적으로 `main` 브랜치를 중심으로 작업한다.

```text
main
 ├─ feature/login
 ├─ feature/signup
 └─ fix/error
```

새로운 기능을 개발할 때 브랜치를 만들고 작업이 끝나면 Pull Request를 생성한다.

코드 리뷰 후 main에 Merge하고 작업 브랜치는 삭제한다.

구조가 간단하기 때문에 지속적으로 기능을 배포하는 웹 서비스 등에 적합하다.

---

### Git Flow

Git Flow는 여러 종류의 브랜치를 사용하는 방식이다.

대표적으로

```text
main
develop
feature/*
release/*
hotfix/*
```

등을 사용한다.

`main`에는 실제 배포 가능한 코드가 있고, `develop`에서 다음 버전 개발을 진행한다.

새로운 기능은 `feature` 브랜치에서 작업하고 배포 준비 단계에서는 `release`, 긴급 수정은 `hotfix` 브랜치를 사용한다.

Github Flow보다 복잡하지만 배포 버전을 명확하게 관리해야 하는 프로젝트에서 사용할 수 있다.

---

## git rebase --interactive

```bash
git rebase -i HEAD~3
```

과 같이 사용한다.

최근 commit들을 직접 수정하거나 정리할 수 있는 기능이다.

예를 들어

- commit 순서 변경
- 여러 commit 합치기
- commit 메시지 수정
- 필요 없는 commit 제거

등을 할 수 있다.

여러 개의 작은 commit을 정리해서 PR을 올리고 싶을 때 유용할 수 있다.

---

## branch의 upstream

upstream은 Local Branch가 어떤 Remote Branch를 추적할지 연결해놓은 정보이다.

새로운 브랜치를 처음 push하면

```bash
git push --set-upstream origin feature/login
```

또는

```bash
git push -u origin feature/login
```

을 사용할 수 있다.

한 번 upstream을 설정하면 이후에는

```bash
git push
```

만 입력해도 연결된 Remote Branch로 push할 수 있다.

---

## Fork

Fork는 다른 사람의 Repository를 **내 Github 계정에 복사하는 기능**이다.

원본 Repository에 직접 push할 권한이 없어도 Fork한 Repository에서는 자유롭게 수정할 수 있다.

예를 들어 오픈소스 프로젝트에 기여할 때

```text
원본 Repository
↓ Fork
내 Repository
↓ Clone
내 컴퓨터
```

형태로 작업할 수 있다.

수정 후 원본 Repository에 Pull Request를 보내 변경 사항을 반영해달라고 요청할 수 있다.

---

## git fetch와 git pull

### git fetch

Remote Repository의 최신 변경 내용을 가져오지만 현재 내 브랜치에는 바로 합치지 않는다.

```bash
git fetch
```

즉, Remote에서 어떤 변경이 있었는지 먼저 확인할 수 있다.

### git pull

Remote Repository의 변경 내용을 가져오고 현재 브랜치에 반영한다.

일반적으로

```text
git pull ≈ git fetch + merge
```

라고 이해할 수 있다.

따라서 다른 사람의 변경 내용을 확인한 후 직접 Merge 여부를 판단하고 싶다면 `git fetch`가 유용하다.

---

## reset --hard와 push --force

### reset --hard

```bash
git reset --hard
```

Working Directory의 수정 내용까지 삭제할 수 있기 때문에 확실히 필요 없는 변경사항일 때만 사용하는 것이 좋다.

### push --force

```bash
git push --force
```

Remote Repository의 기존 Git history를 강제로 덮어쓸 수 있다.

다른 사람이 작업한 commit까지 영향을 받을 수 있기 때문에 협업 브랜치에서는 특히 주의해야 한다.

가능하다면

```bash
git push --force-with-lease
```

처럼 다른 사람의 변경사항이 있는지 확인해주는 방법을 사용하는 것이 더 안전하다.

---

## .gitignore

`.gitignore`는 Git이 추적하지 않을 파일이나 폴더를 지정하는 파일이다.

예를 들어

```text
node_modules/
.env
.DS_Store
```

처럼 작성할 수 있다.

`node_modules`처럼 다시 설치할 수 있는 파일이나 `.env`처럼 API Key, Password 등이 포함될 수 있는 파일은 Git에 올리지 않는 것이 좋다.

---

## Branch 이름의 `/`

Git의 브랜치 이름은 실제로 `.git/refs/heads/` 아래에서 경로 형태로 저장될 수 있다.

예를 들어

```text
feature/login
feature/signup
```

은 각각

```text
refs/heads/feature/login
refs/heads/feature/signup
```

과 같은 구조로 관리될 수 있다.

하지만

```text
feature/login
```

이라는 브랜치가 이미 존재하면 `login` 자체가 하나의 이름으로 사용되기 때문에

```text
feature/login/backend
```

처럼 그 아래에 다시 브랜치를 만들 수 없다.

파일 시스템에서 하나의 경로가 동시에 파일이면서 디렉터리가 될 수 없는 것과 비슷한 이유라고 이해했다.

---

## Detached HEAD

일반적으로 HEAD는 현재 브랜치를 가리킨다.

```text
HEAD → main → commit
```

하지만 특정 commit으로 직접 checkout하면

```bash
git checkout commit_ID
```

HEAD가 브랜치가 아니라 commit 자체를 가리킬 수 있다.

```text
HEAD → commit
```

이를 **Detached HEAD 상태**라고 한다.

이 상태에서도 commit을 만들 수 있지만 특정 브랜치에 연결되어 있지 않기 때문에 이후 다른 브랜치로 이동하면 해당 commit을 찾기 어려워질 수 있다.

Detached HEAD 상태에서 만든 작업을 유지하고 싶다면 새로운 브랜치를 생성하면 된다.

```bash
git switch -c new-branch
```

Detached HEAD는 과거 commit의 코드를 잠시 확인하거나 특정 버전에서 테스트할 때 사용할 수 있다.

## Questions

1. `git clone`과 Github의 `Fork`는 둘 다 Repository를 복사하는 것처럼 보이는데, 정확히 어떤 차이가 있는지 궁금했다.

2. `merge`와 `rebase`는 모두 서로 다른 브랜치의 작업 내용을 합칠 때 사용하는데, 두 방식의 차이와 각각 어떤 상황에서 사용하는지 궁금했다.

3. Github의 비공개(Private) Repository도 Fork할 수 있는지, 가능하다면 어떤 조건에서 가능한지 궁금했다.