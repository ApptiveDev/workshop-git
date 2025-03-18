# 1️⃣️ Git 기초
![git-basics](https://digitalvarys.com/wp-content/uploads/2019/06/Git-Basics-and-Beginners-Guide-1.png)  
Git과 Github 사용의 첫 단계입니다. 

## 🎯️ 목표
- [ ] git의 동작 과정 이해
- [ ] rebase와 reset 이해
- [ ] Github 저장소 clone 하기
- [ ] 브랜치를 만들고 커밋 쌓기
- [ ] Pull Request와 Merge
- [ ] Markdown 문서 작성

## 📜️ 진행
0. 본인의 OS 환경에 적합한 Git bash를 설치합니다. APPTIVE Git 워크샵은 bash를 활용해 진행됩니다. [설치파일 다운로드 링크](https://git-scm.com/downloads)
1. 설치 후, 본 리포지토리를 로컬에 clone 합니다. 바탕화면 우클릭 후, 추가옵션 > Open Git bash here 선택 (Window 11 기준). bash 콘솔창에 아래 명령어 입력.
```bash
# 적당한 폴더 생성 및 이동 (linux의 경우 ~/repositories 추천)
mkdir repositories
cd repositories 

# 현재 리포의 우측 상단에서 git clone URL 복사 후 붙여넣기
git clone https://github.com/ApptiveDev/workshop-git.git

# 클론된 폴더로 이동
cd study-git
```
2. 이 브랜치(`step-1`)에서 본인의 브랜치를 만듭니다.
    - 브랜치명은 `step-1-<이름>`으로 생성
```bash
# step-1 브랜치로 이동
git checkout step-1

# 본인 브랜치 생성 및 이동
git checkout -b step-1-이름
```
3. `/git-basics/README.md`를 복사하고, 빈 항목들을 조사해 채워넣습니다.
    - 복사한 파일명은 `/git-basics/REAMDE-<이름>.md`로 설정합니다.
      - ex) README-kimgiyun.md
    - 해당 파일을 메모장, VSCode 등으로 연 뒤 내용을 조사해 채우면서, 최소 3개의 commit을 쌓아봅시다.
```bash
# /git-basics/README.md 복사
cp git-basics/README.md git-basics/22nd/README-이름.md

# (README-<이름>.md를 꾸준히 채우면서)
git add .
git commit -m "<커밋 메시지>"
```

4. 본인 브랜치를 APPTIVE 원격 저장소로 push한 뒤, `step-1` 브랜치로 Pull Request를 올립니다.
```bash
# 브랜치를 처음 push하는 경우 원격 브랜치 등록
# 현재 브랜치를 origin의 step-1-<이름> 브랜치와 연동한다.
# step-1-<이름> 대신 다른 브랜치명을 사용하면 해당 원격 브랜치와 연결됨.
git push --set-upstream origin step-1-이름
# 첫 push 이후에는 git push만 사용하면 됨
git push
```
