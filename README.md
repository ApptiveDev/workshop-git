# 3️⃣️ 협업 중 문제상황
 한 파일을 수정하는 데에 많은 커밋을 만들어 오히려 히스토리를 번잡하게 만드는 경우입니다. 이 브랜치에 있는 합칠커밋들 4개를 하나의 커밋으로 합쳐봅니다.

## 📜️ 진행
- 스터디원은 `step-3-C` 브랜치로부터 자신의 브랜치를 생성하고 push합니다.
- 합칠커밋 1, 2, 3, 4를 하나의 커밋으로 합칩니다.
- 합친 커밋의 이름을 `dev.txt 파일 생성`으로 변경합니다.
- 변경된 브랜치를 다시 push 해봅니다.
- 성공적으로 push한 후 자신의 원격 브랜치를 삭제합니다.

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- **C. commit을 합치고자 하는 경우 (interactive rebase, squash)**
- D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- E. 충돌 미리 해결하기 (rebase)
- F. 개발 중간에 PR을 올리는 경우 (branch)
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)