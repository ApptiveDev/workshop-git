# 3️⃣️ 협업 중 문제상황
 한 파일을 수정하는 데에 많은 커밋을 만들어 오히려 히스토리를 번잡하게 만드는 경우입니다. 이 브랜치에 있는 합칠커밋들 4개를 하나의 커밋으로 합쳐봅니다.

## 📜️ 진행 (로컬)
- 스터디원은 `step-3-C` 브랜치로부터 자신의 브랜치를 생성합니다.
- 합칠커밋 1, 2, 3, 4를 하나의 커밋으로 합칩니다.
- 합친 커밋의 이름을 `dev.txt 파일 생성`으로 변경합니다.

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

## 실습 코드

### C. commit을 합치고자 하는 경우 (interactive rebase, squash)

- 커밋을 합치는 과정은 코드의 히스토리를 깔끔하게 만들거나, 작은 변경 사항들을 하나의 의미 있는 커밋으로 묶는 데 유용하다.
- interactive rebase를 사용하면, 선택한 범위의 커밋을 다시 정렬하거나 편집하거나 합칠 수 있게된다.
- 자주 쓰이는 방식이니 꼭 익혀두도록 하자!

##### interactive rebase 시작하기

- 합치고 싶은 커밋의 범위를 선택해야 한다.
- 예를 들어, 마지막 3개의 커밋을 하나로 합치는 예시를 들어본다.

`git rebase -i HEAD~3`

##### 커밋 합치기 (squash):

- 합치고 싶은 커밋 앞의 단어를 pick에서 squash로 변경한다.
- 변경된 커밋이 이전 커밋과 합쳐집니다.

```
pick f392171 First change
pick a1d2e3f Second change
-> squash a1d2e3f Second change
squash 123456 Third change
```

##### 커밋 메시지 편집

- 커밋의 메시지를 편집할 수 있는 새 창이 열리는데 적절하게 메세지를 편집한다.

##### rebase 완료

편집이 끝나면 편집기를 닫고, 다음 명령으로 rebase를 완료한다.

`git rebase --continue`

##### 원격 저장소에 반영 (스터디에서는 진행하지 않음)

- 만약 이 변경 사항을 원격 저장소에도 반영하고 싶다면, 강제로 push해야 할 수 있다.

`git push origin <branch-name> --force-with-lease`

공동 브랜치에서는 실수한 커밋이 취소되고, 본인 브랜치에서는 해당 커밋이 유지가 된다.
