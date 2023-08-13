노션 링크 첨부
https://www.notion.so/Git_Hub-Study-09e13a1415214a4f9523a1e63071b7cd

### **1️⃣️ Git 기초**

🎯 스터디 목표

- git과 github의 차이점
- git이 동작하는 과정
- git 기본 명령어

## 📌 Git이란?

```kotlin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
```

---

 🔖 **Git**

개인 컴퓨터에서 돌아가는  `분산 버전 관리 시스템`이다.

> **“버전 관리 시스템”**
> 
> - 파일 변화를 시간에 따라 기록했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다
> 
> **“분산 버전 관리 시스템”.** 
> 
> - 저장소 자체를 히스토리와 더불어 전부 복제한다.

🔖 **Github** 

Github는 Git 소프트웨어를 지원하는 **일종의 클라우드 서비스**이다.

> 🤔  단순히 고양이 클라우드 서비스인 줄 알았는데 분산 처리 구조와 협업에서 병합 문제를 해결할 수 있는 도구로 깃허브가 필수인 이유를 알게 되었다.
> 

[➕ Git에서 병합 충돌을 해결하는 방법](https://docs.github.com/ko/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github)

📍 Git은 병렬 개발이 가능하다. 👉 `branch`

## 📌 **Git 동작흐름**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0a7c3af7-4db2-4864-827b-443f9a368543/Untitled.png)

```kotlin
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
```

 📒 **Working Directory** 

작업할 파일이 있는 디렉토리이다. ****

- untracked - 정보가 아직 없고 트래킹하지 않은,
- tracked - (수정된/수정된)

 📒 **Staging Area** 

 ****커밋(Commit)을 수행할 파일들이 올라가는 영역이다.

- 고유한 해시코드 , 작성시간, 작성자의 정보를 가진다.

 📒 **Local repository**

개발자는 로컬 저장소에서 작업한다. 로컬저장소는 개발자 개인의 작업 공간이다.

 📒**Remote repository**

원격저장소는 인터넷 상의 서버에 위치한 Git 저장소이다. 여러 개발자가 협업을 위해서 사용하고, 코드의 변경사항을 받아올 수 있다.

### ⌨️ 명령어 설명

- ✍️ `git add 명령어`
    
    작업 디렉토리상의 변경내역을 스테이징 영역에 추가하기 위해 사용하는 명령어이다. 
    
    ```bash
    git add
    
    git add *
    
    git add . (모든 파일을 포함해서)
    
    git add *.css (css파일들만)
    ```
    
    > 다음 변경을 기록할 때까지 변경분을 모아놓는 작업으로 `git commist`명령어를 통해 명시적으로 기록을 남기기 전까지는 Git 저장소의 변경 이록에 아무런 영향을 줄 수 없다.
    > 

- ✍️ `git status 명령어`
    
    작업 디렉토리(working directory)와 스테이징 영역(staging area)의 상태를 확인하기 위해서 사용하는 명령어이다.
    
    ```bash
    git status 
    ```
    
    > **Changes to be committed**
    > 
    > 
    >  이 영역은 스테이징 영역에 넘어가 있는 변경 내용을 보여줍니다.
    > 
    > **Changes not staged for commit**
    > 
    > 이 영역은 아직 워킹 디렉토리에 있는 변경 내용을 보여줍니다.
    > 
    > **Untracked files**
    > 
    > 이 영역도 아직 워킹 디렉토리에 있는 아직 한 번도 해당 Git 저장소가 관리한 적이 없는 새로운 파일을 보여줍니다.
    > 

## 📌 **Branch, HEAD**

```kotlin
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
```

---

📒 **Commit**

코드의 변경 사항을 저장하는 작은 단위이다.

🧾 Commit 메시지

- 변경사항을 간결하고 명확하게 설명해야한다.

```bash
git commit -m "Commit message"
//커밋 메시지를 지정하는 옵션입니다. 커밋 메시지는 해당 커밋의 변경 사항을 간결하게 설명하는 역할을 합니다. 메시지는 반드시 작성되어야 한다. 

git commit -a -m "Commit message"
//-a: 변경된 모든 파일을 자동으로 스테이징하고 커밋하는 옵션입니다. 이 옵션을 사용하면 git add 명령을 사용하여 파일을 스테이징할 필요 없이 수정된 파일들이 자동으로 커밋됩니다. 하지만 새로 생성된 파일은 스테이징되지 않으므로 주의해야 합니다.

git commit --amend
//--amend: 이전 커밋을 수정할 때 사용하는 옵션입니다. 만약 이전 커밋의 메시지를 수정하거나 변경 사항을 추가하려면 이 옵션을 사용합니다. 이 경우, 변경 사항을 스테이징하고 --amend 옵션을 사용하여 커밋을 수정합니다.

git commit --amend -m "New commit message"
//--amend -m "New commit message": 이전 커밋의 메시지를 수정할 때, 새로운 커밋 메시지를 지정하는 옵션입니다.

```

📒 **Branch**

Branch는 코드 변경 사항을 분리하여 관리하는 방법입니다.

- 기본적으로 'main' 또는 'master'라는 기본 브랜치가 있으며, 새로운 브랜치를 만들 수 있습니다.

```bash
//새로운 브랜치 생성
git branch <branch-name>

//브랜치 삭제
git branch -d <branch-name>

//브랜치 이동
git checkout <branch-name>

//브랜치 생성 후 이동
git checkout -b <new-branch-name>
```

📒 **HEAD**

현재 작업 중인 Commit을 가리키는 포인터이고, 현재 체크아웃된 브랜치의 가장 최신 커밋을 가리킨다. 

[더 알아보기](https://charles098.tistory.com/24)

## 📌 **clone, init, origin**

```kotlin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
```

---

📒 **`git clone`과 `git init`의 차이점과 이용 방법**

- **`git init`**
    - 새로운 디렉토리를 Git 리포지토리로 초기화하는 명령어입니다. 이 방법은 기존 프로젝트를 버전 관리하려는 경우에 유용합니다. 초기화 후에는 **`git add`**, **`git commit`** 등의 명령어를 사용하여 변경 사항을 관리할 수 있습니다.
    
- **`git clone`**
    - 원격 저장소에서 전체 리포지토리를 복제하여 로컬 환경에 가져오는 명령어입니다. 다른 사람이나 팀과의 협업이나 기존 프로젝트의 포크(Fork)를 생성할 때 주로 사용됩니다.

📒 **`origin`이란 키워드와 설정 방법**

- **`origin`**
    
    리모트(원격) 저장소의 닉네임으로, 원격 저장소의 URL을 가리킵니다. 기본적으로 Git에서 원격 저장소를 참조할 때 사용되는 이름입니다.
    
    **`origin`** 설정 방법
    
    - **`origin`**을 설정하려면 **`git remote add`** 명령을 사용합니다. 이 명령을 통해 원격 저장소의 URL과 **`origin`**이라는 이름을 연결합니다.
    
    ```
    git remote add origin <repository-url>
    ```
    
    이후에는 **`git push`**, **`git pull`**, **`git fetch`** 등의 명령을 사용하여 원격 저장소와의 데이터 교환을 할 때 **`origin`**을 사용합니다. **`origin`**은 원격 저장소의 URL과 닉네임을 편리하게 관리하도록 도와줍니다.
    

[더 알아보기](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EB%A6%AC%EB%AA%A8%ED%8A%B8-%EC%A0%80%EC%9E%A5%EC%86%8C)

> ➕ **`git clone`** 명령어를 실행하면, 원격 저장소의 URL을 **`origin`**이라는 이름으로 자동으로 설정해줍니다. 이렇게 함으로써 나중에 원격 저장소와의 상호작용 시 간편하게 사용할 수 있습니다.
> 

## 📌 **reset**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/49b458e8-7f71-4ab8-a1a9-2a6dd6a0e9e0/Untitled.png)

```markdown
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
```

---

**`reset`** 명령은 커밋을 조작하거나 작업 디렉토리의 상태를 변경하는 데 사용되는 중요한 명령어입니다.

| HEAD | 마지막 커밋 스냅샷, 다음 커밋의 부모 커밋 |
| --- | --- |
| Index | 다음에 커밋할 스냅샷
git commit 명령을 실행하면 Index는 새 커밋으로 변환된다. |
| 워킹 디렉토리 | 샌드박스 |

📒 **Mixed Reset (`git reset [--mixed] <commit>`)**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c3f6abe1-b581-4759-940b-710f8c9bccb7/Untitled.png)

```bash
git reset <commit>
```

- 가리키는 대상을 가장 최근의 `커밋` 으로 되돌리는 것은 같다. 그러고 나서 ***Staging Area*** 를 비우기까지 한다. `git commit` 명령도 되돌리고 `git add` 명령까지 되돌리는 것이다.

📒 **Soft Reset (`git reset --soft <commit>`)** 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/097ef8bb-24ca-4641-a404-712e2d71b71a/Untitled.png)

```bash
git reset --soft <commit>
```

- 이 리셋은 **`-mixed`**와 유사하지만, 변경 사항을 스테이징 영역에 남겨둡니다. 이전 커밋으로 되돌아가기 위해 사용됩니다.
- 선택한 커밋으로 돌아가고, 해당 커밋 이후의 변경 사항을 스테이징 영역에 남겨둡니다.

📒 **Hard Reset (`git reset --hard <commit>`)**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3521e3be-79cb-40cb-b568-56b4b6450e21/Untitled.png)

```bash
git reset --hard <commit>
```

- `reset` 명령을 통해 `git add` 와 `git commit` 명령으로 생성한 마지막 커밋을 되돌린다. 그리고 **워킹 디렉토리의 내용까지도 되돌린다.**
- 변경 사항이 모두 제거되고, 선택한 커밋의 상태로 작업 디렉토리와 스테이징 영역이 강제로 덮어씌워집니다.
- 주의: 이 모드는 변경 사항을 완전히 삭제하므로 조심해서 사용해야 합니다.

## 📌 **Pull Request, Merge**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/afa84c89-23f6-4e84-9603-4a7aea7a279b/Untitled.png)

```kotlin
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
```

---

📒 **Pull Request (풀 리퀘스트)**

Pull Request는 코드 변경 사항을 다른 브랜치에 병합하도록 요청하는 기능입니다.

1. 개발자는 자신의 변경 사항이 포함된 브랜치에서 작업을 완료하고 커밋합니다.
2. 원격 저장소에 해당 브랜치를 푸시합니다.
3. 해당 브랜치에서 GitHub, GitLab, Bitbucket 등의 웹 기반 플랫폼에서 Pull Request를 생성합니다.
4. 다른 팀원들은 Pull Request를 검토하고 논의할 수 있습니다. 변경 사항이 품질과 표준을 준수하는지 확인합니다.
5. 리뷰가 완료되면 Pull Request를 병합(Merge)할 수 있습니다.

📒 **Merge (병합)** 

Merge는 두 개의 다른 브랜치의 변경 사항을 하나의 브랜치에 통합하는 작업입니다. 주로 Pull Request를 통해 수행되며, 두 가지 주요 Merge 타입이 있습니다.

🗒️ **Fast-Forward Merge**

- Fast-Forward Merge는 히스토리 분기가 없을 때 사용됩니다. 즉, 브랜치가 포인터처럼 일렬로 나열되어 있는 상황입니다.
- 변경 사항을 통합하기 위해 기준 브랜치(주로 **`main`** 또는 **`master`**)를 병합하려는 브랜치의 최신 커밋으로 이동시킵니다.
- 이로써 변경 사항이 기준 브랜치에 빠르게 통합됩니다

🗒️  **3-Way Merge (3-way 병합)**

- 3-Way Merge는 두 브랜치가 서로 다른 변경 사항을 가지고 있을 때 사용됩니다.
- 기준 브랜치, 통합하려는 브랜치, 그리고 공통 조상 커밋을 비교하여 변경 사항을 통합합니다.
- Git은 변경 사항을 가능한 한 자동으로 병합하고, 충돌(conflict)이 발생하면 사용자에게 해당하는 부분을 해결하도록 안내합니다.

## 📌 **rebase**

```kotlin
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.
```

---

📒 **rebase**

Git에서 브랜치의 커밋 히스토리를 다시 구성하거나 변경하는 작업을 의미합니다. 주로 브랜치를 다른 브랜치에 더 적절하게 통합하거나 더 선형적인 히스토리를 유지하기 위해 사용됩니다.

✅ **Rebase의 기본 작동 방식**

1. 현재 브랜치에서 다른 브랜치의 변경 사항을 가져옵니다.
2. 현재 브랜치의 커밋 히스토리를 다른 브랜치의 커밋 히스토리 위로 이동시킵니다.
3. 충돌이 발생하면 충돌을 해결하고 계속 진행합니다.
4. 브랜치의 히스토리가 재정렬되고, 변경 사항이 적용됩니다.

✅ **Rebase가 유용한 상황**

1. **브랜치 통합**: 다른 브랜치에서 작업한 변경 사항을 현재 브랜치에 더 효율적으로 통합하고 싶을 때 사용됩니다. **`merge`** 대신 **`rebase`**를 사용하여 더 선형적인 히스토리를 유지할 수 있습니다.
2. **커밋 히스토리 정리**: 커밋 히스토리를 깔끔하게 유지하기 위해 사용됩니다. 커밋 메시지를 수정하거나 불필요한 중간 커밋을 합치는 등의 작업을 수행할 수 있습니다.
3. **충돌 해결**: 충돌이 발생할 경우, **`rebase`**를 통해 충돌을 더 명확하게 보면서 해결할 수 있습니다.
4. **Upstream 변경 통합**: 원격 저장소의 변경 사항을 받아오거나 업스트림 변경을 반영할 때 사용됩니다. 기존 커밋 히스토리 위로 변경 사항을 적용할 수 있습니다.

> ⚠️ 주의할 점
 **`rebase`**를 남들과 함께 작업하고 있는 브랜치에서 사용할 때, 히스토리가 변하기 때문에 주의해서 사용해야 한다.
> 

## 📌 **stash**

```kotlin
git stash를 활용하는 방법에 대해 적어주세요.
```

---

📒 **stash** 

Stash 명령을 사용하면 워킹 디렉토리에서 수정한 파일들만 저장한다. Stash는 Modified이면서 Tracked 상태인 파일과 Staging Area에 있는 파일들을 보관해두는 장소다. 

아직 끝내지 않은 수정사항을 스택에 잠시 저장했다가 나중에 다시 적용할 수 있다(브랜치가 달라져도 말이다).

**✅ git stash 활용 방법**

**1. 변경 사항 저장:**

```bash
git stash
```

이 명령을 실행하면 스테이징 영역에 있는 변경 사항과 작업 디렉토리의 변경 사항이 모두 저장됩니다. 작업 디렉토리는 이전 커밋 상태로 되돌아가며, 변경 사항은 일시적으로 스태시(stash) 스택에 저장됩니다.

**2. 스태시 리스트 확인:**

```bash
git stash list
```

이 명령을 실행하면 스태시 스택에 저장된 스태시들의 리스트를 확인할 수 있습니다.

**3. 스태시 적용:**

```bash
git stash apply
```

가장 최근에 저장한 스태시를 현재 브랜치에 적용합니다. 스태시는 스택에 남아있으므로 나중에도 다시 적용할 수 있습니다.

➕ Git은 Stash를 적용할 때 Staged 상태였던 파일을 자동으로 다시 Staged 상태로 만들어 주지 않는다. 그래서 `git stash apply` 명령을 실행할 때 `--index` 옵션을 주어 Staged 상태까지 적용한다. 그래야 원래 작업하던 상태로 돌아올 수 있다.

**4. 특정 스태시 적용:**

```bash
git stash apply stash@{n}
```

특정 스태시를 적용할 때는 위와 같이 스태시 인덱스(**`stash @{n}`**)를 명시합니다.

**5. 스태시 적용 및 제거:**

```bash
git stash pop
```

가장 최근에 저장한 스태시를 적용하고, 스태시 스택에서 제거합니다.

**6. 스태시 제거:**

```bash
git stash drop stash@{n}
```

`apply` 옵션은 단순히 Stash를 적용하는 것뿐이다. Stash는 여전히 스택에 남아 있다. `git stash drop` 명령을 사용하여 해당 Stash를 제거한다.

특정 스태시를 제거할 때는 위와 같이 스태시 인덱스(**`stash@{n}`**)를 명시합니다.

**7. 모든 스태시 제거:**

```bash
git stash clear
```

스태시 스택에 있는 모든 스태시를 제거합니다.

> **`git stash`**를 활용하면 현재 작업 중인 변경 사항을 임시로 저장하고 나중에 다시 적용할 수 있어 편리합니다. 이를 통해 다른 브랜치로 이동하거나 작업을 정리하는 동안 변경 사항을 보존하면서 유연하게 작업할 수 있습니다.
> 

[더 알아보기](https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Stashing%EA%B3%BC-Cleaning)

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push/pull --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 `parent/child-1`, `parent/child-2`는 가질 수 있지만 `parent`, `parent/child`는 가질 수 없다. 무슨 이유 때문인지. 
- 리포지토리의 두 타입인 bare, non-bare

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push/pull --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 `parent/child-1`, `parent/child-2`는 가질 수 있지만 `parent`, `parent/child`는 가질 수 없다. 무슨 이유 때문인지. 
- 리포지토리의 두 타입인 bare, non-bare

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.