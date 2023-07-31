# 3️⃣️ 협업 중 문제상황
 
## 📜️ 진행
- 아래 문제상황을 하나씩 보면서 해결 방법을 고민해봅니다.
- 스터디원은 문제상황을 해결해보고, 이후 스터디장은 해결방법을 알려줍니다.
- 스터디장은 어떤 명령어를 써야할지 알려주고, 스터디원은 직접 따라합니다.

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. 개발 중간에 PR을 올리는 경우 (branch, rebase)
- D. commit을 합치고자 하는 경우 (interactive rebase, squash)
- E. commit을 쪼개려는 경우 (interactive rebase, reset mixed)
- F. 충돌 미리 해결하기 (rebase)
- G. 특정 커밋으로 Rebase (tag)
- H. 실수로 reset --hard 후 push까지 한 경우 (reflog)
  - git rebase -i -> git push -f
  - git reset --hard -> git push -f
- I. 부모 브랜치, 자식 브랜치 모두 PR을 올려야 하는 경우