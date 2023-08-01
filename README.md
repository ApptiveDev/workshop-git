# 2️⃣️ Git 협업

![git-collaboration](https://media.licdn.com/dms/image/C4E0DAQGYq7DdDvIr6g/learning-public-crop_288_512/0/1568669538450?e=2147483647&v=beta&t=jbk5EPqUfoeQQbGBYFVVpO6_iW_0ZMskzP2qIx4MtnQ)  
앞서 학습한 git 커맨드를 이용해 간단한 계산기를 함께 만들어봅시다. 이 과정에서 작업내용을 되돌려보기도 하고, 충돌도 해결해보고, 자신의 브랜치를 최신 상태로 업데이트해보기도 합니다.

## 시나리오

### [사칙연산]

1. 팀리더가 GitHub에 'simple-calculator'라는 저장소를 생성합니다.
2. 초기 파이썬 프레임워크가 메인 브랜치에 준비되어 있으니 팀 리더는 이를 메인 브랜치에 올려놓습니다.
3. 참가자들은 각자의 기능(사칙연산)을 개발하고 이를 메인 브랜치에 합치려 합니다.

- 이때 5명 이상인 팀은 사칙연산 + 나머지 구하기를 진행합니다.

4. 나눗셈을 맡은 참가자들은 일부러 분모에 0일 경우를 고려하지 않고 코드를 작성하고 이슈를 발생시킵니다.

## 진행

1. Fork와 클론

각 참가자는 'simple-calculator' 저장소를 Fork하고, 자신의 로컬 환경으로 Clone합니다.

2. 브랜치 생성 및 작업 시작

각 참가자는 자신의 기능에 맞는 브랜치를 생성하고, 해당 브랜치에서 기능을 완성합니다.

3. 오류 코드 작성

나눗셈과 나머지를 맡은 참가자들은 일부러 오류를 고려하지 않은 코드를 작성하고 커밋합니다.

4. 커밋 및 Push

모든 참가자들은 완성된 기능 혹은 오류를 포함한 코드를 커밋하고, Fork한 저장소로 Push합니다.

5. Pull Request 생성

원본 저장소에 PR을 생성합니다. 다른 참가자들은 해당 PR을 리뷰하고 피드백을 제공합니다.

- PR 예시 형식

6. 머지 및 이슈 발생

리뷰가 완료되면 PR이 머지됩니다. 오류나 문제가 발견되면, 이슈를 생성합니다.

7. 이슈 해결

이슈를 확인한 참가자는 새로운 브랜치를 생성하여 이슈를 해결하고 커밋합니다. "Fixes #이슈번호"를 포함하여 커밋합니다.

8. PR 재생성 및 머지

오류 해결 후 원본 저장소에 다시 PR을 생성합니다. 리뷰 후 PR이 머지됩니다. 9. 이슈 확인 및 종료

해당 이슈는 "Fixes #이슈번호"를 포함한 커밋으로 인해 자동으로 닫힙니다.
참가자들은 이 과정을 통해 GitHub 협업, 이슈 관리, PR 생성 및 머지, 그리고 충돌 해결의 전체적인 과정을 경험하게 됩니다.

## 상세

### 저장소 생성(팀 리더)

```
# 저장소 생성
mkdir simple-calculator
cd simple-calculator

# git 저장소 초기화
git init

# 초기 코드 작성 (IDE로 작성하셔도 됩니다!)
echo "코드" >> calculator.py

# 깃에 추가하기
git add calculator.py

# 깃에 커밋하기
git commit -m "Initialize calculator with add function."

# GitHub에 원격 저장소 생성 후 연결 (GitHub에서 생성한 후)
# 혹은 먼저 생성후에 clone
git remote add origin [GitHub 저장소 URL]
git push -u origin master

```

### 기능 구현 (4명)

```
# 저장소 클론
git clone [GitHub 저장소 URL]
# 디렉토리 이동
cd simple-calculator

# 브랜치 생성 및 이동
# 브랜치 생성전략 참조
git checkout -b feature-[구현할 기능명]

# 코드 작성 (IDE로 작성하셔도 됩니다!)
echo "코드" >> calculator.py


# 커밋 및 Push
git add calculator.py
git commit -m "Feature [구현한 기능명]"
git push origin [자신의 브랜치명]

# GitHub에서 PR 생성
# PR 명명 전략 참조
```

### 코드 리뷰 및 merge (팀 리더 or 코드리뷰어)

팀 리더는 GitHub에서 개발자 A와 B의 PR을 확인하고 리뷰합니다.

오류가 존재한다면 PR에서 이를 comment로 남깁니다.

### 이슈 생성 (팀 리더 or 코드리뷰어)

GitHub의 'Issues' 탭에서 새로운 이슈 생성:

제목 예시: "나눗셈 기능 구현에서 분모 0으로 나누는 문제 발생"
내용: "0으로 나누었을 시에는 오류 메세지가 출력되도록 변경 요청 드립니다."

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
