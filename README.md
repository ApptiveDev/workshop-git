# 2️⃣️ Git 협업

![git-collaboration](https://media.licdn.com/dms/image/C4E0DAQGYq7DdDvIr6g/learning-public-crop_288_512/0/1568669538450?e=2147483647&v=beta&t=jbk5EPqUfoeQQbGBYFVVpO6_iW_0ZMskzP2qIx4MtnQ)  
앞서 학습한 git 커맨드를 이용해 간단한 계산기를 함께 만들어봅시다. 이 과정에서 작업내용을 되돌려보기도 하고, 충돌도 해결해보고, 자신의 브랜치를 최신 상태로 업데이트해보기도 합니다.

## 시나리오

### [사칙연산]

1. 스터디원은 `step-2` 브랜치로부터 자신의 브랜치를 생성합니다.
2. 스터디원는 자신의 브랜치에서 맡은 기능을 개발하고 `step-2`에 Pull Request를 올립니다.
3. 실습 후 스터디장은 브랜치를 실습 이전의 상태로 복구합니다.

## 진행

### 1. 브랜치 생성 및 작업 시작

- 각 참가자는 자신의 기능에 맞는 브랜치를 생성하고, 해당 브랜치에서 기능을 완성합니다.

### 2. 커밋 및 Push

- 모든 참가자들은 완성된 기능 혹은 오류를 포함한 코드를 커밋하고, Push 합니다.

### 3. Pull Request 생성

- `step-2`로 PR을 생성하고, 다른 참가자들은 해당 PR을 리뷰하고 피드백을 제공합니다.

### 4. 머지

- 리뷰가 완료되면 PR이 머지됩니다. 오류나 문제가 발견되면, 이슈를 생성합니다.


## 상세

### 기능 구현 (4명)
```
# 저장소 클론
git clone [GitHub 저장소 URL]
# 디렉토리 이동
cd simple-calculator

# 브랜치 생성 및 이동
git checkout -b feature-[구현할 기능명]

# 커밋 및 Push
git add calculator.py
git commit -m "Feature [구현한 기능명]"
git push origin [자신의 브랜치명]

# GitHub에서 PR 생성
# PR 명명 전략 참조
```

### 코드 리뷰 및 merge

스터디장은 GitHub에서 개발자 A와 B의 PR을 확인하고 리뷰합니다.

오류가 존재한다면 PR에서 이를 comment로 남깁니다.

### 이슈 생성

GitHub의 'Issues' 탭에서 새로운 이슈 생성:

**제목 예시**: "나눗셈 기능 구현에서 분모 0으로 나누는 문제 발생"  
**내용 예시**: "0으로 나누었을 시에는 오류 메세지가 출력되도록 변경 요청 드립니다."

### 이슈 해결

```
# 오류가 발생한 브랜치로 이동
git checkout [브랜치명]

# 코드 수정 (IDE로 작성하셔도 됩니다!)
echo "코드" >> calculator.py

# 커밋 및 Push
git add calculator.py
git commit -m "Fix 나눗셈 분모 0으로 나누는 이슈. Fixes #1"
#하고 숫자들 제목에 작성하게 된다면 이슈번호 1을 해결한다는 내용이 포함된다.
git push origin [브랜치명]
```
