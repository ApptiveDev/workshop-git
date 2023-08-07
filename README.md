# 3️⃣️ 협업 중 문제상황
 
## 📜️ 진행
- 아래 문제상황을 하나씩 보면서 해결 방법을 고민해봅니다.
- 스터디원은 문제상황을 해결해보고, 이후 스터디장은 해결방법을 알려줍니다.
- 스터디장은 어떤 명령어를 써야할지 알려주고, 스터디원은 직접 따라합니다.

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
  - git rebase -i -> git push -f
  - git reset --hard -> git push -f
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우