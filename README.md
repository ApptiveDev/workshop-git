# 3️⃣️ 협업 중 문제상황
개발 도중 변경 내역이 생각보다 많아 도중에 PR을 먼저 올리려고 합니다. 이 경우 PR을 올린 브랜치에서 자식 브랜치를 따서 작업을 계속해야 합니다. 
 
## 📜️ 진행
- 스터디원은 `step-3-F` 브랜치로부터 자신의 브랜치를 하나 만듭니다.
- 스터디원은 `./playground`에 간단한 파일을 하나 만들고 `step-3-F`에 PR 합니다.
- 스터디원은 해당 브랜치에서 또 다시 브랜치를 따서 파일을 하나 더 만들고 PR을 새로 올립니다.
  - 어떤 브랜치에 PR 요청을 해야 할까요?
- 스터디원은 PR 들을 순서대로 merge 해봅니다.
- 스터디원은 merge 이후 해당 브랜치들을 삭제합니다.

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. commit을 합치고자 하는 경우 (interactive rebase, squash)
- D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- E. 충돌 미리 해결하기 (rebase)
- **F. 개발 중간에 PR을 올리는 경우 (branch)**
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)