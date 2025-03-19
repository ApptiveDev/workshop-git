# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

Git과 GitHub는 같은 의미가 아니며, **Local(로컬)과 Remote(원격)** 개념과 관련이 있습니다.  

- **Git**: 분산형 버전 관리 시스템(DVCS)으로, **로컬(Local)에서 코드의 변경 이력을 추적하고 버전 관리를 할 수 있도록 해주는 도구**입니다. 개발자는 Git을 사용하여 변경 사항을 커밋하고, 브랜치를 생성하여 독립적인 개발을 진행하며, 필요에 따라 이전 버전으로 롤백할 수 있습니다. Git은 네트워크 없이도 사용할 수 있으며, 개발자의 **로컬 저장소(Local Repository)** 에 코드가 저장됩니다.  

- **GitHub**: Git을 기반으로 하는 **원격(Remote) 저장소 서비스**로, 로컬에서 관리하던 Git 저장소를 인터넷을 통해 **다른 사람과 공유하거나 협업할 수 있도록 지원하는 플랫폼**입니다. GitHub를 활용하면 원격 저장소(Remote Repository)에 코드를 푸시(Push)하여 백업할 수 있고, 팀원들과 Pull Request(PR) 및 코드 리뷰를 통해 협업할 수 있습니다.  

### **Git과 GitHub의 관계 (Local & Remote 연관)**
1. **Git은 로컬(Local)에서 코드 버전 관리를 담당하고**, GitHub는 원격(Remote)에서 저장소를 호스팅하여 협업할 수 있도록 돕습니다.  
2. 로컬에서 `git add` → `git commit`을 수행하여 변경 사항을 기록한 후, `git push`를 사용하여 원격 저장소(GitHub)로 업로드합니다.  
3. 반대로, 팀원이 업데이트한 코드가 원격 저장소에 있다면, `git pull`을 사용하여 로컬 저장소로 가져올 수 있습니다.  

즉, **Git은 버전 관리를 위한 도구이고, GitHub는 Git 저장소를 호스팅하는 원격 서비스**입니다. Git을 이용해 로컬에서 작업하고, GitHub를 통해 협업하는 방식으로 활용됩니다. 😊



## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

### **Git 동작 과정 설명 (다이어그램 기반)**  

Git은 코드의 변경 사항을 추적하고 버전 관리를 수행하는 도구입니다. 다이어그램을 기반으로 각 개념을 설명하겠습니다.  

---

### **1. Working Directory (작업 디렉토리)**  
- 현재 작업 중인 디렉토리로, 프로젝트의 소스 코드 파일들이 위치하는 곳입니다.  
- 새로운 파일을 생성하거나, 기존 파일을 수정하는 등 모든 변경 사항은 **Working Directory에서 발생**합니다.  
- Git의 버전 관리에 포함되지 않은 상태이며, 추적되지 않은(Untracked) 상태일 수 있습니다.  

---

### **2. Git Add (스테이징 영역에 추가)**  
- `git add` 명령어를 사용하면 **Working Directory에서 변경된 파일을 Staging Area로 이동**시킵니다.  
- 변경 사항을 커밋하기 전에 확인하고 준비하는 과정으로, 아직 Git의 최종 버전에 기록되지 않은 상태입니다.  
- 예제:  
  ```bash
  git add 파일명  # 특정 파일 추가
  git add .        # 모든 변경 사항 추가
  ```

---

### **3. Staging Area (스테이징 영역, 인덱스)**  
- Git이 커밋할 파일을 임시로 저장하는 공간입니다.  
- `git add`를 수행한 후 파일이 저장되며, 이후 `git commit`을 통해 로컬 저장소에 기록됩니다.  
- 여러 개의 파일을 수정한 후, 원하는 파일만 선택하여 커밋할 수 있습니다.  

---

### **4. Git Commit (로컬 저장소에 기록)**  
- `git commit`을 수행하면 **Staging Area의 변경 사항이 Local Repository에 저장**됩니다.  
- 커밋은 특정 시점의 프로젝트 상태를 기록하는 스냅샷과 같으며, 이후 원격 저장소에 업로드할 수 있습니다.  
- 예제:  
  ```bash
  git commit -m "변경 사항 설명"
  ```

---

### **5. Local Repo (HEAD) (로컬 저장소, HEAD 포인터)**  
- `git commit`을 수행하면 변경 사항이 Local Repository에 저장됩니다.  
- **HEAD는 현재 작업 중인 브랜치의 최신 커밋을 가리키는 포인터**입니다.  
- 이 상태에서는 아직 원격 저장소에 업로드되지 않았으며, 다른 사람과 공유할 수 없습니다.  

---

### **6. Git Push (원격 저장소로 업로드)**  
- `git push`를 사용하면 **Local Repository의 변경 사항을 Remote Repository(GitHub, GitLab 등)로 업로드**할 수 있습니다.  
- 원격 저장소에 있는 팀원들이 내 변경 사항을 확인할 수 있도록 공유하는 과정입니다.  
- 예제:  
  ```bash
  git push origin main  # main 브랜치에 업로드
  ```

---

### **7. Remote Repo (MASTER) (원격 저장소)**  
- GitHub, GitLab, Bitbucket 등의 서비스에 저장되는 **원격 저장소**입니다.  
- 여러 개발자가 협업할 때 변경 사항을 공유하는 공간입니다.  
- 원격 저장소에 있는 코드를 내려받거나(`git pull`), 최신 내용을 가져올 수 있습니다(`git fetch`).  

---

### **8. Git Fetch (원격 저장소의 변경 사항을 가져오기)**  
- `git fetch`는 **원격 저장소(Remote)에서 최신 변경 사항을 가져오지만, 자동으로 병합하지 않습니다.**  
- 로컬 저장소에 영향을 주지 않으며, 단순히 최신 정보를 가져오는 역할을 합니다.  
- 이후 `git merge`를 사용해 원격 변경 사항을 로컬에 반영할 수 있습니다.  
- 예제:  
  ```bash
  git fetch origin
  ```

---

### **9. Git Merge (브랜치 병합)**  
- `git merge`는 **다른 브랜치에서 가져온 변경 사항을 현재 브랜치에 병합**하는 명령어입니다.  
- 일반적으로 `git fetch` 후 변경 사항을 로컬 브랜치에 적용할 때 사용됩니다.  
- 예제:  
  ```bash
  git merge origin/main
  ```

---

### **10. Git Pull (원격 저장소의 변경 사항을 로컬에 반영)**  
- `git pull`은 `git fetch` + `git merge`를 합친 명령어입니다.  
- **원격 저장소(Remote)의 최신 변경 사항을 가져오고(Local), 자동으로 병합(Merge)합니다.**  
- 팀원들의 코드 변경 사항을 받아올 때 사용됩니다.  
- 예제:  
  ```bash
  git pull origin main
  ```

---

### **정리**  
1. **Working Directory**: 실제 작업하는 공간 (파일 추가/수정/삭제 가능)  
2. **Git Add**: 변경된 파일을 **Staging Area(스테이징 영역)** 에 추가  
3. **Staging Area**: 커밋할 파일을 준비하는 공간  
4. **Git Commit**: 변경 사항을 **Local Repository(로컬 저장소)** 에 기록  
5. **Git Push**: 로컬 변경 사항을 **Remote Repository(원격 저장소)** 로 업로드  
6. **Git Fetch**: 원격 저장소의 최신 변경 사항을 가져옴 (병합하지 않음)  
7. **Git Merge**: 다른 브랜치 또는 원격 저장소의 변경 사항을 현재 브랜치에 병합  
8. **Git Pull**: 원격 저장소에서 변경 사항을 가져오고 자동으로 병합  

---

이제 Git의 흐름을 정리하면 다음과 같습니다.  
1️⃣ **파일을 수정/추가 (Working Directory)**  
2️⃣ `git add` → 스테이징 영역에 추가  
3️⃣ `git commit` → 로컬 저장소에 기록  
4️⃣ `git push` → 원격 저장소로 업로드  
5️⃣ 다른 팀원의 변경 사항을 반영하려면 `git pull`  

위 내용을 바탕으로 추가 설명이 필요하거나 궁금한 점이 있다면 알려주세요! 😊



## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

### **Git의 기본 단위: Commit과 Branch**  

Git은 **Commit(커밋)**과 **Branch(브랜치)** 개념을 기반으로 동작합니다.  
- **Commit**: 코드의 변경 사항을 저장하는 스냅샷으로, 특정 시점의 프로젝트 상태를 기록합니다.  
- **Branch**: 독립적인 작업을 수행할 수 있도록 만든 **분기(branch)** 입니다.  

---

## **1. Branch (브랜치)란?**  
브랜치는 **커밋의 흐름을 나누어 독립적인 작업을 진행할 수 있도록 돕는 기능**입니다.  
- 여러 개발자가 동시에 작업할 수 있도록 분리된 작업 공간을 제공합니다.  
- 기본적으로 Git은 `master`(또는 `main`) 브랜치를 생성하며, 새로운 브랜치를 만들어 병렬 작업이 가능합니다.  

💡 **브랜치를 사용하면 여러 기능을 동시에 개발하고, 이후 병합(merge)할 수 있습니다.**  

---

## **2. HEAD란?**  
`HEAD`는 **현재 작업 중인 브랜치를 가리키는 포인터**입니다.  
- 항상 최신 커밋을 가리키며, 브랜치를 이동하면 HEAD도 함께 이동합니다.  
- 현재 작업 중인 브랜치가 어디인지 알려주는 역할을 합니다.  
- 위 다이어그램에서는 `FEATURE BRANCH`에 `HEAD`가 위치해 있습니다.  

---

## **3. 브랜치 관련 Git 명령어**  

### 🔹 **(1) 브랜치 확인**
```bash
git branch      # 현재 브랜치 목록 확인
git branch -a   # 로컬 + 원격 저장소 브랜치 확인
```

### 🔹 **(2) 새로운 브랜치 생성**
```bash
git branch feature-branch  # feature-branch라는 새 브랜치 생성
```

### 🔹 **(3) 브랜치 이동 (checkout)**
```bash
git checkout feature-branch  # feature-branch로 이동
```
- `checkout`을 사용하면 다른 브랜치로 이동할 수 있으며, HEAD도 해당 브랜치를 가리키게 됩니다.

💡 **Git 2.23 이후 버전에서는 `git switch`를 사용할 수도 있습니다.**
```bash
git switch feature-branch
```

### 🔹 **(4) 브랜치 생성과 동시에 이동**
```bash
git checkout -b feature-branch  # 새 브랜치를 만들고 바로 이동
```
또는  
```bash
git switch -c feature-branch
```

### 🔹 **(5) 브랜치 병합 (merge)**
```bash
git checkout main         # 메인 브랜치로 이동
git merge feature-branch  # feature-branch를 main에 병합
```

### 🔹 **(6) 브랜치 삭제**
```bash
git branch -d feature-branch  # 병합된 브랜치 삭제 (안전한 삭제)
git branch -D feature-branch  # 병합되지 않은 브랜치 강제 삭제
```

---

## **4. Git에서 브랜치를 활용하는 기본적인 흐름**
1️⃣ `git branch feature-branch` → 새로운 브랜치 생성  
2️⃣ `git checkout feature-branch` → 브랜치 이동  
3️⃣ `git add . && git commit -m "작업 완료"` → 변경 사항 커밋  
4️⃣ `git checkout main` → 메인 브랜치로 이동  
5️⃣ `git merge feature-branch` → 브랜치를 병합  
6️⃣ `git branch -d feature-branch` → 병합된 브랜치 삭제  

---

## **5. 추가적으로 알아두면 좋은 개념**
🔹 `git rebase` → 브랜치를 최신 커밋으로 정리할 때 사용  
🔹 `git stash` → 변경 사항을 임시로 저장하고 브랜치를 이동할 때 사용  
🔹 `git cherry-pick` → 특정 커밋만 선택하여 적용할 때 사용  

---

### **결론**
- `HEAD`는 현재 작업 중인 브랜치를 가리킵니다.  
- `git checkout` 또는 `git switch`를 사용하면 브랜치를 변경할 수 있습니다.  
- 브랜치를 활용하면 독립적인 작업이 가능하며, 병합(merge)을 통해 코드 변경 사항을 반영할 수 있습니다.  

🚀 **Git 브랜치를 활용하면 여러 기능을 동시에 개발하고 안전하게 관리할 수 있습니다!**  
추가 질문이 있다면 알려주세요. 😊



## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## **Git 리포지토리 생성 방법: `git clone` vs `git init`**  

Git에서 로컬에 리포지토리를 생성하는 방법에는 **`git clone`**과 **`git init`** 두 가지가 있습니다.  
이 두 가지 방법의 차이점과 함께, 원격 저장소를 의미하는 `origin`의 개념과 설정 방법도 설명하겠습니다.  

---

## **1. `git clone` vs `git init` 차이점**  

| 명령어 | 사용 목적 | 원격 저장소 연결 여부 | 기본 사용 예시 |
|--------|------------|----------------|----------------|
| `git clone` | **기존 원격 저장소를 로컬로 복제** | O (자동으로 `origin` 설정됨) | `git clone <repository-url>` |
| `git init` | **새로운 로컬 저장소 생성** | X (별도로 원격 저장소 연결 필요) | `git init` |

### **✅ `git clone`**
- **기존 원격 저장소(GitHub, GitLab 등)를 로컬에 복사**하는 명령어입니다.
- 원격 저장소가 있는 경우 사용하며, 자동으로 `origin`이라는 원격 저장소가 설정됩니다.
- 기본적으로 원격 저장소의 모든 내용(파일, 커밋, 브랜치 등)이 복사됩니다.

#### **🛠 사용 예시**
```bash
git clone https://github.com/user/repository.git
```
- 위 명령어를 실행하면 `repository` 폴더가 생성되고, 해당 저장소의 코드가 로컬로 복제됩니다.
- `git remote -v`를 실행하면 `origin`이 자동으로 설정된 것을 확인할 수 있습니다.

---

### **✅ `git init`**
- **새로운 로컬 저장소를 생성**할 때 사용합니다.
- 기존의 원격 저장소가 없는 프로젝트에서 처음으로 Git을 사용하려 할 때 유용합니다.
- 원격 저장소(`origin`)와 연결되지 않으므로, 원격 저장소를 따로 설정해야 합니다.

#### **🛠 사용 예시**
```bash
mkdir my_project
cd my_project
git init
```
- 위 명령어를 실행하면 `.git` 폴더가 생성되며, Git으로 버전 관리를 시작할 수 있습니다.

---

## **2. `origin`이란?**
- `origin`은 **로컬 저장소에서 기본적으로 가리키는 원격 저장소의 이름**입니다.
- `git clone`을 하면 자동으로 `origin`이 설정됩니다.
- `git init`을 한 경우에는 원격 저장소가 없으므로, `origin`을 직접 설정해야 합니다.

---

## **3. `origin` 설정 방법**

### **✅ `git clone`을 사용한 경우**
- `git clone`을 하면 `origin`이 자동으로 설정됩니다.
- 확인 방법:
  ```bash
  git remote -v
  ```
  예제 출력:
  ```
  origin  https://github.com/user/repository.git (fetch)
  origin  https://github.com/user/repository.git (push)
  ```

---

### **✅ `git init`을 사용한 경우 (`origin` 직접 설정)**
- `git init`으로 생성한 로컬 저장소에 원격 저장소를 추가하려면 다음과 같이 설정합니다.

#### **🛠 원격 저장소 추가하기**
```bash
git remote add origin https://github.com/user/repository.git
```
- 이제 `git push origin main` 등의 명령어를 사용할 수 있습니다.
- `git remote -v`로 `origin`이 정상적으로 추가되었는지 확인할 수 있습니다.

#### **🛠 원격 저장소 변경하기**
```bash
git remote set-url origin https://github.com/newuser/newrepository.git
```

#### **🛠 원격 저장소 삭제**
```bash
git remote remove origin
```

---

## **4. 실전 예제: `git init` + 원격 저장소 연결**
1️⃣ **새 프로젝트를 생성하고 Git을 초기화**
```bash
mkdir new_project
cd new_project
git init
```

2️⃣ **파일 추가 및 첫 커밋**
```bash
echo "# New Project" > README.md
git add .
git commit -m "Initial commit"
```

3️⃣ **GitHub 원격 저장소 추가 (`origin` 설정)**
```bash
git remote add origin https://github.com/user/new_project.git
```

4️⃣ **로컬 커밋을 원격 저장소에 푸시**
```bash
git push -u origin main
```

---

## **5. 정리**
| 명령어 | 설명 |
|--------|------------|
| `git clone <url>` | 원격 저장소를 로컬에 복제 (자동으로 `origin` 설정) |
| `git init` | 새로운 로컬 저장소 생성 (원격 저장소 미연결) |
| `git remote add origin <url>` | 원격 저장소를 `origin`으로 추가 |
| `git remote -v` | 현재 설정된 원격 저장소 확인 |
| `git remote set-url origin <new-url>` | `origin`의 URL 변경 |
| `git remote remove origin` | 원격 저장소 `origin` 삭제 |

**🚀 `git clone`은 기존 원격 저장소를 복제할 때, `git init`은 새로운 프로젝트를 Git으로 관리할 때 사용됩니다.**  
추가 질문이 있다면 알려주세요! 😊



## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## **Git `reset`의 3가지 타입: `soft`, `mixed`, `hard`**  

Git의 `reset` 명령어는 특정 커밋으로 되돌아갈 때 사용됩니다.  
이때 **되돌아가는 방식**에 따라 **`--soft`, `--mixed`, `--hard`** 세 가지 옵션이 있습니다.  

---

## **1. `git reset --soft`**  
- **HEAD만 이동**, Staging Area(= Index)와 Working Directory는 그대로 유지  
- 되돌아간 커밋 이후의 변경 사항이 **Staging Area에 남아 있음**  
- `git commit --amend` 또는 추가적인 수정 후 다시 커밋할 때 유용  

### **🛠 사용 예시**
```bash
git reset --soft HEAD~1
```
- 마지막 커밋을 되돌리지만, 변경된 파일들은 여전히 **Staging Area**에 있음  
- 다시 `git commit`을 하면 기존 커밋을 수정할 수 있음  

---

## **2. `git reset --mixed` (기본값)**  
- **HEAD와 Staging Area(Index)만 이동**, Working Directory는 유지  
- 즉, 되돌아간 커밋 이후의 변경 사항이 **Unstaged 상태(Working Directory)로 이동**  
- 기본 옵션이므로 `--mixed`를 생략하면 자동으로 적용됨  
- 수정한 내용을 다시 Staging하고 싶다면 `git add .`를 실행해야 함  

### **🛠 사용 예시**
```bash
git reset --mixed HEAD~1
```
- 마지막 커밋을 되돌리지만, 변경된 파일들은 **Staging Area에서 빠지고(unstaged)**, **Working Directory에는 남아 있음**  

---

## **3. `git reset --hard`**  
- **HEAD, Staging Area(Index), Working Directory 모두 되돌림**  
- 되돌아간 커밋 이후의 변경 사항이 **완전히 삭제됨** (복구 불가!)  
- 정말 되돌리고 싶은 경우에만 신중하게 사용  

### **🛠 사용 예시**
```bash
git reset --hard HEAD~1
```
- 마지막 커밋을 완전히 삭제하고, 변경 사항도 모두 사라짐  
- 복구가 불가능하므로 **사용에 주의해야 함!**  

---

## **📌 `reset` 3가지 옵션 비교**  

| 옵션 | HEAD 이동 | Staging Area 영향 | Working Directory 영향 | 되돌린 후 변경 사항 |
|------|-----------|------------------|----------------------|----------------|
| `--soft` | ✅ 이동 | ❌ 유지 | ❌ 유지 | **Staged 상태 유지 (commit만 취소됨)** |
| `--mixed` | ✅ 이동 | ✅ 초기화 | ❌ 유지 | **Unstaged 상태로 이동** |
| `--hard` | ✅ 이동 | ✅ 초기화 | ✅ 초기화 | **모든 변경 사항 삭제 (복구 불가)** |

---

## **🎯 실전 예제: `reset`을 활용한 커밋 취소**  
```bash
git reset --soft HEAD~1   # 마지막 커밋 취소 (Staged 상태 유지)
git reset --mixed HEAD~1  # 마지막 커밋 취소 (Unstaged 상태로 이동)
git reset --hard HEAD~1   # 마지막 커밋 및 변경 사항 완전히 삭제
```

---

## **🔹 추가 정보: `reset` 사용 시 주의할 점**
1. **`--hard` 옵션은 되돌릴 수 없으므로 신중하게 사용해야 합니다!**  
   - 실수로 실행했을 경우, `git reflog`를 통해 이전 상태를 확인하고 복구할 수 있음  

2. **공유된 원격 저장소에서는 `reset` 대신 `revert` 사용을 고려**  
   - `reset`은 과거 커밋을 변경하기 때문에 협업 시 충돌이 발생할 가능성이 있음  
   - `git revert`를 사용하면 **이전 커밋을 되돌리는 새 커밋을 생성**하여 이력을 유지할 수 있음  

---

## **🔹 `git reset`과 `git revert` 차이점**
| 명령어 | 원격 저장소에서 사용 가능? | 기존 커밋 유지 여부 | 사용 목적 |
|--------|--------------------|--------------|------------|
| `git reset` | ❌ (공유된 브랜치에서는 사용 지양) | ❌ (커밋 삭제됨) | 특정 커밋 이후 변경 사항 제거 |
| `git revert` | ✅ (안전하게 사용 가능) | ✅ (이력을 유지하며 취소) | 특정 커밋을 취소하는 새로운 커밋 생성 |

---

### **🚀 결론**
- `git reset --soft` → **최근 커밋을 취소하고, Staging Area 유지**  
- `git reset --mixed` → **최근 커밋을 취소하고, 변경 사항을 Unstaged 상태로 이동**  
- `git reset --hard` → **모든 변경 사항을 완전히 삭제 (주의!)**  

🔥 **원격 저장소와 협업할 때는 `reset`보다 `revert`를 고려하세요!**  
추가 질문이 있다면 알려주세요 😊



## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

# **Pull Request와 Merge**  

## **1. Pull Request(PR)란?**  
- Pull Request(이하 PR)는 **GitHub, GitLab, Bitbucket 등에서 코드 변경 사항을 병합하기 전 리뷰를 요청하는 기능**  
- `feature` 브랜치에서 작업한 내용을 `main` 또는 `develop` 브랜치로 합칠 때 사용  
- PR을 통해 팀원들이 변경 사항을 검토하고, 코드 리뷰 후 승인되면 병합(Merge)  

### **🔹 Pull Request 과정**
1. `feature-branch`에서 새로운 기능을 개발  
2. 원격 저장소(Remote Repo)로 `git push`  
3. GitHub(GitLab 등)에서 `main` 브랜치로 PR 생성  
4. 팀원들이 코드 리뷰 후 승인 (필요하면 수정)  
5. PR을 `Merge`하여 변경 사항을 반영  

---

## **2. Merge란?**  
- Git에서 **두 개 이상의 브랜치를 하나로 합치는 과정**  
- PR이 승인되면 `merge`를 수행하여 `feature` 브랜치의 변경 사항을 `main` 브랜치에 반영  
- Merge는 방식에 따라 **Fast-Forward Merge**와 **3-Way Merge**로 나뉨  

---

## **3. Merge의 두 가지 타입**  

### **🔹 (1) Fast-Forward Merge**  
- 새로운 브랜치에서 작업한 후, `main` 브랜치에 다른 변경 사항이 없는 경우  
- 브랜치의 HEAD가 단순히 앞으로 이동하는 방식  
- 커밋 그래프가 직선 형태로 유지됨  

### **🛠 Fast-Forward Merge 예제**
```bash
# feature 브랜치 생성 후 작업
git checkout -b feature-branch
# 작업 후 커밋
git add .
git commit -m "Add new feature"
# main 브랜치로 체크아웃
git checkout main
# Fast-Forward Merge 실행
git merge feature-branch
```

### **✅ Fast-Forward Merge의 특징**
- **장점**: 커밋 기록이 깔끔하고 단순  
- **단점**: 브랜치가 독립적으로 존재하지 않으므로, 이력이 명확하지 않을 수 있음  

---

### **🔹 (2) 3-Way Merge**  
- `main` 브랜치가 변경된 후, `feature` 브랜치를 Merge하려고 하면 Fast-Forward가 불가능  
- Git이 **공통 조상(Common Ancestor) 커밋을 기준으로 세 개의 커밋을 비교하여 병합**  
- 새로운 병합 커밋(Merge Commit)이 생성됨  

### **🛠 3-Way Merge 예제**
```bash
# main 브랜치에서 변경 사항이 생김
git checkout main
git pull origin main
# feature 브랜치에서 작업 후 main으로 병합
git checkout feature-branch
git merge main
# main 브랜치로 돌아가서 병합 수행
git checkout main
git merge feature-branch
```

### **✅ 3-Way Merge의 특징**
- **장점**: Merge 커밋이 남아 있어 변경 이력을 명확하게 확인 가능  
- **단점**: 불필요한 Merge Commit이 많아질 수 있음  

---

## **4. Merge vs. Rebase**
- `git rebase`는 **브랜치를 병합하는 또 다른 방식**  
- 기존 커밋을 재배열하여 깔끔한 히스토리를 유지  
- Merge와 비교하면 `git rebase`는 **브랜치 커밋을 새롭게 쌓는 방식**, Merge는 **Merge Commit을 생성**  

### **🛠 Rebase 예제**
```bash
git checkout feature-branch
git rebase main
```

### **✅ Merge vs. Rebase 비교**
| 방식 | 히스토리 유지 | 새로운 Merge Commit 생성 | 협업 추천 여부 |
|------|------------|-----------------|------------|
| `merge` | O | O (3-Way Merge) / X (Fast-Forward) | O |
| `rebase` | X (커밋이 새롭게 정렬됨) | X | X (협업 시 주의 필요) |

---

## **🎯 결론**
1. **PR(Pull Request)**는 협업에서 변경 사항을 병합하기 전에 코드 리뷰를 거치는 과정  
2. **Merge**는 브랜치를 하나로 합치는 과정이며, **Fast-Forward Merge**와 **3-Way Merge**가 있음  
3. **Fast-Forward Merge**는 브랜치 HEAD가 단순 이동하는 방식으로 **히스토리가 깔끔**  
4. **3-Way Merge**는 공통 조상을 기준으로 **Merge Commit이 생성**되며, **히스토리 보존**  
5. **Rebase**는 커밋을 다시 정렬하여 히스토리를 깔끔하게 하지만 협업 시 주의 필요  

🔹 **협업 시에는 PR을 활용하여 코드 리뷰 후 Merge하는 것이 베스트!**  
추가 질문이 있다면 알려주세요 😊



## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

# **Rebase란?**  

## **1. Rebase란 무엇인가?**  
`git rebase`는 브랜치의 기반(Base) 커밋을 변경하여 **커밋 히스토리를 다시 정렬하는 Git 명령어**입니다.  
즉, 특정 브랜치에서의 변경 사항을 다른 브랜치의 최신 커밋 위에 다시 적용하는 방식입니다.  

**💡 간단히 말하면?**  
👉 **"현재 브랜치가 마치 최신 브랜치에서 시작된 것처럼 보이게 만든다!"**  

---

## **2. Rebase의 동작 방식**  

### **🔹 Rebase 전 (기존 구조)**
```bash
A---B---C (main)
     \
      D---E---F (feature)
```
- `feature` 브랜치는 `main`에서 분기되어 독립적으로 진행됨  

### **🔹 Rebase 후 (main 브랜치 기준으로 재배치)**
```bash
A---B---C (main)
         \
          D'--E'--F' (feature)
```
- `feature` 브랜치의 모든 커밋(D, E, F)이 `main`의 최신 커밋(C) 위로 다시 적용됨  
- 즉, **D, E, F 커밋이 새롭게 만들어진 것처럼 보이게 됨**  

---

## **3. Rebase 사용 방법**  

### **(1) 기본적인 Rebase 명령어**  
```bash
git checkout feature
git rebase main
```
- `feature` 브랜치를 `main` 브랜치의 최신 상태로 재배열  
- `feature` 브랜치에서의 변경 사항이 `main`의 최신 커밋 뒤에 다시 적용됨  

### **(2) Rebase 충돌 해결 방법**
- Rebase 도중 충돌이 발생하면 Git이 경고 메시지를 표시하고 Rebase가 중단됨  
- 충돌을 해결한 후 다음 명령어를 실행하면 Rebase가 계속 진행됨  
```bash
git add .
git rebase --continue
```
- 만약 Rebase를 취소하고 싶다면?
```bash
git rebase --abort
```

---

## **4. Rebase가 유용한 경우**  

### ✅ **1) 히스토리를 깔끔하게 유지하고 싶을 때**  
- `git merge`를 사용하면 **Merge Commit**이 남게 되어 불필요한 커밋이 많아질 수 있음  
- `git rebase`는 **브랜치를 직선 형태로 정리**하여 **히스토리를 단순하고 깔끔하게 유지**  

### ✅ **2) 여러 개발자가 협업하는 프로젝트에서 최신 변경 사항을 반영하고 싶을 때**  
- `main` 브랜치에서 새로운 변경 사항이 생겼다면, `feature` 브랜치를 최신 상태로 업데이트  
- `git pull --rebase`를 사용하면, 최신 변경 사항을 적용하면서 불필요한 Merge Commit 없이 유지 가능  

```bash
git pull --rebase origin main
```

### ✅ **3) Feature 브랜치를 최신 상태로 유지하고 싶을 때**  
- 여러 명이 공동 작업하는 경우, `git merge main`을 수행하면 불필요한 Merge Commit이 생성됨  
- `git rebase main`을 하면 `main` 브랜치의 최신 변경 사항을 반영하면서도 **커밋 히스토리를 깨끗하게 유지**  

---

## **5. Merge vs. Rebase 차이점**  

| 비교 항목 | Merge | Rebase |
|-----------|---------|---------|
| **커밋 히스토리** | Merge Commit이 생성됨 | 직선형 히스토리를 유지 |
| **사용 목적** | 협업 시 변경 사항을 명확히 남길 때 | 히스토리를 깔끔하게 정리할 때 |
| **충돌 처리** | Merge 시점에 한 번에 처리 | 각 커밋마다 개별적으로 충돌 해결 필요 |
| **커밋 순서 유지** | 유지됨 | 변경될 수 있음 |

---

## **6. Rebase 사용 시 주의할 점**  

⚠ **🚨 이미 Push한 커밋을 Rebase하지 말 것! 🚨**  
- **Rebase는 커밋을 새롭게 생성하는 것과 동일**하므로, 이미 원격 저장소(Remote Repository)에 Push한 후에 Rebase하면 문제가 발생할 수 있음  
- 다른 사람이 같은 브랜치를 사용 중이라면 **충돌 위험**이 있음  
- **해결 방법:** `git push --force`를 사용할 수 있지만, 이는 협업 프로젝트에서는 권장되지 않음  

```bash
git push --force  # 강제로 Push (주의!)
```

### **🔹 안전한 Rebase 사용 방법**
- `git rebase`는 **로컬에서 작업 중인 브랜치**에서만 사용  
- 이미 원격에 Push한 경우에는 `merge`를 사용하는 것이 더 안전함  

---

## **🎯 결론: 언제 Rebase를 사용할까?**  

✅ **Rebase를 사용하면 좋은 경우**  
- 커밋 히스토리를 깨끗하게 정리하고 싶을 때  
- 개인 작업을 정리하여 `main`에 반영하기 전에 깔끔한 히스토리 유지  
- `main` 브랜치의 최신 상태를 `feature` 브랜치에 반영할 때  

❌ **Rebase를 피해야 하는 경우**  
- 원격 저장소에 Push한 후 다른 사람이 같은 브랜치를 사용할 가능성이 있을 때  
- 협업 중인 브랜치에서 Rebase 후 `--force push`를 해야 하는 상황  

---

## **📌 요약**  
1. `git rebase`는 브랜치의 기반(Base) 커밋을 변경하여 **커밋 히스토리를 깔끔하게 유지**하는 Git 명령어  
2. `git merge`와 달리 **불필요한 Merge Commit 없이 직선형 히스토리를 유지**  
3. `git pull --rebase`를 사용하면 최신 변경 사항을 반영하면서도 히스토리를 깨끗하게 유지 가능  
4. 하지만, **이미 Push된 커밋을 Rebase하면 충돌 위험이 커지므로 주의해야 함**  
5. 협업 중이라면 `merge`를, 개인 브랜치 정리에는 `rebase`를 추천!  

💡 **협업 시에는 Merge, 개인 브랜치 정리에는 Rebase를 활용하면 최적의 Git 관리 가능!** 🚀



## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

# **Git Stash 활용 방법**  

## **1. Git Stash란?**  
`git stash`는 **현재 작업 중인 변경 사항을 임시로 저장**하고, 작업 디렉터리를 깨끗한 상태로 만들 수 있는 Git 명령어입니다.  
즉, **작업을 중단하고 다른 브랜치로 전환해야 할 때 유용하게 사용**됩니다.  

💡 **한마디로?**  
👉 **"현재 작업 내용을 임시 저장해 두고, 나중에 다시 복구하는 기능!"**  

---

## **2. Git Stash 기본 사용법**  

### **🔹 Stash 저장하기**  
```bash
git stash
```
- **현재 변경된 파일과 Staging Area의 변경 사항을 모두 저장**  
- 저장 후에는 `git status`를 확인하면, **작업 디렉터리가 깨끗한 상태**가 됨  

💡 **Stash 저장과 동시에 메시지 추가하기**  
```bash
git stash save "임시 저장 메시지"
```
- 여러 개의 Stash를 저장할 경우 구분하기 쉽게 메시지를 추가할 수 있음  

---

## **3. Stash 목록 확인 및 복원**  

### **🔹 Stash 목록 확인**  
```bash
git stash list
```
- 현재 저장된 Stash 목록을 확인 가능  
- 예제 출력:
  ```
  stash@{0}: WIP on feature-branch: 123abc 작업 내용1
  stash@{1}: WIP on main: 456def 작업 내용2
  ```
- `stash@{0}`이 가장 최근에 저장된 Stash  

### **🔹 Stash 적용 (복원하기)**  
```bash
git stash apply
```
- 가장 최근에 저장된 Stash를 적용하지만, **Stash는 삭제되지 않음**  
- 만약 특정 Stash를 적용하려면?
  ```bash
  git stash apply stash@{1}
  ```

### **🔹 Stash 적용 후 삭제까지 하기 (pop)**  
```bash
git stash pop
```
- Stash를 적용한 후, **적용된 Stash는 자동으로 삭제됨**  

---

## **4. 특정 Stash 삭제 및 전체 삭제**  

### **🔹 특정 Stash 삭제**  
```bash
git stash drop stash@{0}
```
- `stash@{0}` Stash만 삭제  

### **🔹 모든 Stash 삭제**  
```bash
git stash clear
```
- **모든 Stash를 한 번에 삭제**  

---

## **5. Stash에 특정 파일만 저장하기**  

### **🔹 Untracked 파일 제외하고 Stash 저장**  
```bash
git stash -u
```
- **Tracked 파일만 저장 (Untracked 파일은 제외)**  

### **🔹 Untracked & Ignored 파일까지 Stash 저장**  
```bash
git stash -a
```
- **모든 파일(Untracked, Ignored 포함)을 Stash에 저장**  

---

## **6. Stash를 활용하는 실전 시나리오**  

### ✅ **1) 작업 도중 급하게 다른 브랜치로 이동해야 할 때**  
```bash
git stash
git checkout main
git pull origin main
git checkout feature-branch
git stash pop
```
- 변경 사항을 임시로 저장 후, `main` 브랜치 업데이트 후 다시 원래 브랜치에서 작업 재개  

### ✅ **2) 여러 개의 Stash를 관리하며 특정 시점의 변경 사항 적용**  
```bash
git stash list
git stash apply stash@{2}
```
- 특정 Stash(`stash@{2}`)만 적용 가능  

### ✅ **3) 특정 파일만 Stash에서 복구하고 싶을 때**  
```bash
git checkout stash@{0} -- file.txt
```
- `stash@{0}`에서 `file.txt`만 복구  

---

## **7. Git Stash vs. Git Commit 비교**  

| 기능 | Git Stash | Git Commit |
|------|----------|------------|
| 목적 | 임시 저장 | 영구 저장 |
| 적용 대상 | 현재 작업 디렉터리 변경 사항 | 모든 변경 사항 |
| 히스토리 유지 | 유지되지 않음 (stash list에서만 조회 가능) | 유지됨 (Git Log에서 조회 가능) |
| 브랜치 전환 가능 여부 | 가능 | 불가능 (Commit 후에만 가능) |
| 삭제 가능 여부 | 가능 (`git stash drop`, `git stash clear`) | 가능 (`git reset`, `git revert`) |

💡 **Stash는 임시 저장 용도로만 사용하고, 장기적인 변경 사항은 Commit을 활용하는 것이 좋음!**  

---

## **🎯 결론: 언제 Git Stash를 사용할까?**  

✅ **Git Stash를 사용하면 좋은 경우**  
- **작업 중인데 급하게 브랜치를 변경해야 할 때**  
- **Commit하기 애매한 작업 내용을 임시로 저장하고 싶을 때**  
- **다른 작업을 먼저 해야 할 때 현재 진행 중인 변경 사항을 임시로 보관**  
- **Untracked 파일까지 포함해 임시 저장하고 싶을 때 (`git stash -u` or `git stash -a`)**  

❌ **Git Stash를 피해야 하는 경우**  
- 장기적으로 변경 사항을 저장하려면 **Commit을 사용하는 것이 더 적절함**  
- 협업 중이라면 Stash보다는 **Branch를 활용하여 명확한 기록을 남기는 것이 좋음**  

---

## **📌 요약**  
1. `git stash`는 **작업 중인 변경 사항을 임시로 저장하고, 나중에 다시 불러올 수 있는 Git 명령어**  
2. `git stash list`로 Stash 목록을 확인하고, `git stash apply` 또는 `git stash pop`으로 복원 가능  
3. `git stash drop stash@{n}`으로 특정 Stash 삭제, `git stash clear`로 모든 Stash 삭제 가능  
4. `git stash -u`는 Untracked 파일 포함, `git stash -a`는 Ignored 파일까지 포함 가능  
5. Stash는 **임시 저장 용도로만 사용**하고, 변경 사항을 확정할 때는 Commit을 활용하는 것이 좋음  

🚀 **Git Stash를 적절히 활용하면, 작업 흐름을 유지하면서도 유연하게 브랜치를 전환할 수 있음!**



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

좋은 주제들이네요! 각각의 개념을 깊이 있게 이해하면 Git을 보다 효과적으로 활용할 수 있습니다. 간략한 설명과 함께 더 깊이 조사할 수 있는 방향을 제시해볼게요.

---

### **1. 브랜치 관리 전략: Github Flow vs. Git Flow**
- **Github Flow**  
  - `main` 브랜치에서 직접 feature 브랜치를 만들고 작업 후 PR을 통해 머지하는 방식  
  - 단순한 워크플로우, CI/CD와의 연계가 쉬움  
  - 작은 프로젝트, 빠른 배포가 필요한 경우 적합  

- **Git Flow**  
  - `develop`, `feature`, `release`, `hotfix` 등의 여러 브랜치를 활용하는 방식  
  - 배포 주기가 긴 프로젝트나 팀 단위 협업에서 적합  
  - 브랜치 간 머지 전략이 중요  

📌 **조사 포인트:**  
- Github Flow에서는 `main` 브랜치에서 직접 배포하는데, Git Flow에서는 왜 `develop` 브랜치가 필요한가?  
- 두 방식이 충돌하는 경우 어떻게 해결할까?  

---

### **2. `git rebase --interactive`란?**
- `git rebase -i HEAD~n`을 사용하면 최근 `n`개의 커밋을 수정, 병합, 삭제할 수 있음  
- `pick`, `squash`, `reword`, `edit`, `drop` 등의 옵션을 활용 가능  

📌 **조사 포인트:**  
- `squash`와 `fixup`의 차이  
- `edit`을 활용해 특정 커밋만 수정하는 방법  

---

### **3. 브랜치의 upstream이란? (`git push --set-upstream`)**
- `git push --set-upstream origin feature-branch`를 실행하면 로컬 브랜치와 원격 브랜치를 연결  
- 이후 `git push`나 `git pull`을 별도의 옵션 없이 사용 가능  

📌 **조사 포인트:**  
- `upstream`을 변경하려면? (`git branch --unset-upstream` 활용)  
- `git pull --rebase`와 함께 사용하면 어떤 이점이 있을까?  

---

### **4. Fork는 언제 유용한가?**
- `PR`은 같은 리포지토리의 브랜치뿐만 아니라 **Fork한 리포지토리**에서도 가능  
- **Fork가 유용한 경우:**  
  - 원본 프로젝트를 유지하면서 개인적으로 기능을 추가하고 싶을 때  
  - 오픈소스 프로젝트에 기여할 때  

📌 **조사 포인트:**  
- Fork 후 원본 리포지토리(`upstream`)의 변경 사항을 동기화하는 방법 (`git remote add upstream`)  
- PR을 보낼 때 내 브랜치와 원본 브랜치의 충돌을 해결하는 방법  

---

### **5. `git fetch`와 `git pull`의 차이점**
- `git fetch`: 원격 저장소의 변경 사항을 가져오지만 **로컬 브랜치에는 반영하지 않음**  
- `git pull`: `fetch + merge` (로컬 브랜치에 직접 반영됨)  

📌 **조사 포인트:**  
- `git fetch --prune` 옵션을 활용하면 어떤 장점이 있을까?  
- `git fetch`를 사용한 후 `git diff origin/main`으로 변경 사항을 확인하는 방법  

---

### **6. `reset --hard`와 `push --force`의 적절한 사용법**
- `git reset --hard HEAD~1`: 가장 최근의 커밋을 삭제하고 변경 사항도 함께 제거  
- `git push --force`: 원격 저장소의 히스토리를 강제로 덮어씀  

📌 **조사 포인트:**  
- `--force-with-lease` 옵션은 어떻게 동작하는가?  
- 협업 중에 `push --force`를 사용할 경우 생길 수 있는 문제  

---

### **7. `.gitignore` 사용법**
- 특정 파일을 Git에 추가하지 않도록 설정하는 파일  
- 패턴 예제:
  ```
  *.log        # 모든 .log 파일 무시
  /node_modules/  # 특정 폴더 무시
  !important.log  # 예외적으로 추가할 파일 지정
  ```

📌 **조사 포인트:**  
- `.gitignore`을 프로젝트 초반에 설정하지 않고 후에 적용하면 어떻게 될까?  
- `.gitignore`을 잘못 설정해서 커밋된 파일을 제거하려면? (`git rm --cached`)  

---

### **8. 브랜치 이름의 계층적 구조**
- 브랜치 이름에 `/`를 포함하면 계층 구조처럼 보이지만, 실제 Git은 폴더 개념이 아님  
- `parent/child/grandchild`와 `parent/child`를 동시에 가질 수 없는 이유:  
  - `parent/child`가 하나의 브랜치라면 `parent/child/grandchild`는 독립적인 브랜치로 인식되지 않음  

📌 **조사 포인트:**  
- Git의 브랜치 네이밍 규칙과 `refs/heads/` 내부 구조  
- Git에서 브랜치 삭제 시 주의할 점  

---

### **9. Detached HEAD란?**
- 특정 커밋을 체크아웃하면 HEAD가 브랜치가 아닌 특정 커밋을 가리키는 상태  
- Detached HEAD 상태에서 커밋을 하면 임시 브랜치가 생기지만, 브랜치를 생성하지 않으면 커밋이 사라짐  

📌 **조사 포인트:**  
- Detached HEAD에서 만든 커밋을 유지하는 방법 (`git checkout -b new-branch`)  
- `git switch -`를 활용한 빠른 브랜치 이동  

---

이 주제들에 대해 직접 실습해보거나 공식 문서를 찾아보면서 학습하면 Git을 훨씬 더 깊이 이해할 수 있을 거예요! 🚀



## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
