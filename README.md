# 3️⃣️ 협업 중 문제상황
 로컬의 공동 브랜치에서 작업한 후 커밋을 한 상황을 가정해봅시다. 이대로 원격 브랜치에 올라가선 안 되므로 자신의 브랜치로 가져와 다시 커밋을 해야 합니다.

## 📜️ 진행 (로컬)
1. 현재 브랜치 `step-3-A`에서 `/playground` 폴더에 텍스트 파일 하나를 만들고 커밋합니다.
2. 이 커밋을 지우고 본인 브랜치로 가져갑니다.

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