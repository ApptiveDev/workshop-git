# 3️⃣️ 협업 중 문제상황
 커밋에 너무 많은 내용이 들어가 있으면 히스토리를 관리하기 힘들어 집니다. 해당 커밋이 문제를 일으킨 경우 reset이나 revert를 해야 하는데, 전체를 되돌리면 불필요한 부분까지 되돌려지기 때문입니다. 이곳에 있는 커밋 1개를 2개로 쪼개보세요.
## 📜️ 진행 (로컬)
- 스터디원은 '쪼갤커밋'을 되돌립니다.
- 스터디원은 다음 2개로 다시 커밋합니다.
  - 커밋 1: dev1.txt 만 담습니다.
  - 커밋 2: dev2.txt 만 담습니다.

## 🚨️ 문제상황
- A. 실수로 공동 브랜치에 commit한 경우 (reset, stash, pop)
- B. 실수로 공동 브랜치에 commit하고 push까지 한 경우 (cherry-pick, revert)
- C. commit을 합치고자 하는 경우 (interactive rebase, squash)
- **D. commit을 쪼개려는 경우 (interactive rebase, reset mixed)**
- E. 충돌 미리 해결하기 (rebase)
- F. 개발 중간에 PR을 올리는 경우 (branch)
- G. 중간에 올린 PR에 변경 요청이 들어온 경우 (rebase)
- H. 중간에 올린 PR을 Squash Merge 할 경우 (interactive rebase)
- I. 실수로 reset --hard 후 push까지 한 경우 (reflog)
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)