# 3️⃣️ 협업 중 문제상황
 팀원이 같은 부분을 수정했다면 PR 때 충돌이 일어나게 됩니다. Github에서 충돌을 해결하기는 불편하니 로컬에서 미리 충돌을 해결해봅시다.
 
## 📜️ 진행
- 스터디원은 `step-3-E` 브랜치에서 자신의 브랜치를 만듭니다.
- 스터디장은 `step-3-E`에서 `/playground/version.txt`의 버전을 높인 후 커밋, push합니다.
- 스터디원은 자신의 브랜치에서 스터디장과 다른 버전으로 높이고 커밋, push합니다.
- 스터디원은 자신의 브랜치를 `step-3-E`에 PR을 올립니다.
- 스터디원은 로컬에서 충돌을 해결하고 다시 push 후 PR을 merge합니다.
- 스터디원은 자신의 브랜치를 삭제합니다.

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. commit을 합치고자 하는 경우 (interactive rebase, squash)
- D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- **E. 충돌 미리 해결하기 (rebase)**
- F. 개발 중간에 PR을 올리는 경우 (branch)
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)