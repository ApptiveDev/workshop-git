# 3️⃣️ 협업 중 문제상황
 `git reset --hard`로 날려버린 변경내역을 원격 브랜치까지 push 해버린 경우를 가정합시다. 다시 생각해보니 필요했던 커밋이라면? 날아간 파일은 어디서도 찾을 수 없고 답이 없어 보입니다. 그러나 `git reflog`는 이렇게 휴지통 비우기까지 해버린 커밋을 다시 되돌릴 수 있습니다.

## 📜️ 진행 (로컬)
- 스터디원은 `step-3-I` 브랜치로 이동합니다.
- 커밋 2개가 준비되어 있습니다. 이 2개의 커밋을 `git reset --hard`로 삭제합니다.
- `git reflog`를 통해 삭제한 커밋 중 최신 것의 커밋 해시를 복사합니다.
- `git checkout`으로 커밋 해시를 복원합니다.
- 새로 브랜치를 만들고, 기존 자신의 브랜치에 다시 반영합니다.

## 커맨드
```bash
git checkout step-3-I

git reset --hard HEAD~2
git reflog

# 되돌리고자 하는 커밋 해시 복사
git checkout <커밋 해시>
git branch <백업 브랜치>
git checkout step-3-I
git rebase <백업 브랜치>
git branch -d <백업 브랜치>
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
- **I. 실수로 reset --hard 후 push까지 한 경우 (reflog)**
- J. 로컬, 원격 브랜치 모두 브랜치명을 변경하고자 할 경우 (push --delete, --set-upstream)