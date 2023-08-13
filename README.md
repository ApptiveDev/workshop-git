# 3️⃣️ 협업 중 문제상황

로컬의 공동 브랜치에서 작업한 후 커밋을 한 상황을 가정해봅시다. 이대로 원격 브랜치에 올라가선 안 되므로 자신의 브랜치로 가져와 다시 커밋을 해야 합니다. 실수로 커밋이 잘못된 `step-3-A-shared` 브랜치가 준비되어 있습니다. 여기서 자신의 브랜치로 해당 커밋을 가져가보세요.

## 📜️ 진행 (로컬)

1. 스터디원은 `step-3-A` 브랜치에서 자신의 브랜치(`step-3-A-<이름>`)을 하나 생성합니다. (`git branch`)
2. 스터디원은 `step-3-A-shared` 브랜치의 커밋을 없애고 자신의 브랜치로 가져갑니다.

## ✅ 자가확인
  - [ ] `step-3-A-shared`에 `playground/실수 파일.txt`이 존재하지 않는다.
  - [ ] `step-3-A-<이름>`에 `playground/실수 파일.txt`가 존재한다.

## 💻 커맨드
> 연습을 위해 주석은 최소한만 달아주세요.
```bash
git checkout step-3-A
git branch step-3-A-<이름>

# 공동 브랜치에 실수로 쌓인 커밋 확인
git checkout step-3-A-shared
git log --oneline --graph     # git graph 익스텐션으로 확인하길 추천

git reset HEAD~1
git stash
git checkout step-3-A-<이름>
git stash pop

git add .
git commit -m "커밋 메시지"
```

## 🚨️ 문제상황

- **A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)**
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. commit을 합치고자 하는 경우 (interactive rebase, squash)
- D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- E. 충돌 미리 해결하기 (rebase)
- F. 개발 중간에 PR을 올리는 경우 (branch)
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)

## 실습 코드

### A. 실수로 공동 브랜치에 commit한 경우

- 이 경우, 아직 push하지 않았다면 로컬에서 문제를 해결할 수 있다.

##### 잘못된 commit이 있는 브랜치로 이동하기

- (내 브랜치에서 잘못되었으면 하지 않아도된다. 하지만 실습의 경우에는 스터디 리더가 잘못된 커밋을 shared 브랜치에 날리기 때문에 이를 고려한 과정)
  `git checkout step-3-A-shared`

##### commit을 되돌리기: 현재 브랜치의 마지막 커밋을 취소합니다.

- 커밋은 취소되고, 해당 커밋에 있던 변경 사항은 스테이징 영역(stage)에서 작업 디렉토리(working directory)로 이동
- git reset의 기본 동작은 --mixed 이다(생략 가능).

`git reset --mixed HEAD~`

##### 변경 내용을 임시로 저장하기: 변경 내용을 임시로 저장하려면 git stash 명령을 사용합니다.

`git stash`

##### 원하는 브랜치(내 브랜치)로 이동 후 임시로 저장한 변경 내용 적용하기:

`git checkout step-3-A-nstgic3`
`git stash pop`
