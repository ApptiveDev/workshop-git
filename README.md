# 3️⃣️ 협업 중 문제상황
 이슈를 더 작은 단위로 쪼개거나, 이슈 제목을 바꾸는 등 처리중인 이슈가 변경되는 경우 브랜치 이름도 적절히 바꿔주는 것이 좋습니다. 로컬 브랜치는 쉽게 바꿀 수 있지만 원격 브랜치는 그렇지 않습니다. 한번 원격 브랜치까지 바꿔봅시다. 

## 📜️ 진행
- 스터디원은 `step-3-J`에서 자신의 브랜치를 생성한 후 push합니다.
- 스터디원은 로컬 브랜치의 이름을 변경합니다.
- 스터디원은 연결된 원격 브랜치를 삭제한 후, 변경한 이름으로 다시 push합니다.
- `git branch -vv`로 로컬, 원격 브랜치의 명이 일치함을 확인합니다.
- 확인 후 자신의 원격 브랜치를 삭제합니다.

주의) 모든 작업은 git 커맨드라인으로 해야 합니다.

## 커맨드
```bash
git checkout step-3-J
git checkout -b step-3-J-<이름>
git push -u origin step-3-J-<이름>
git branch -m <새 이름>
git branch -vv
git push --delete origin step-3-J-<이름>
git push -u origin <새 이름>
git branch -vv
```

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. commit을 합치고자 하는 경우 (interactive rebase, squash)
- D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- E. 충돌 미리 해결하기 (rebase)
- F. 개발 중간에 PR을 올리는 경우 (branch)
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- **J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)**