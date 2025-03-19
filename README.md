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
1. 이 리포지토리를 로컬에 clone 합니다.
```bash
# 적당한 폴더 생성 및 이동 (linux의 경우 ~/repositories 추천)
mkdir ~/repositories
cd ~/repositories 

# 현재 리포의 우측 상단에서 git clone URL 복사 후 붙여넣기
git clone <workshop-git github URL>

# 클론된 폴더로 이동
cd workshop-git
```
2. 이 브랜치(`step-1`)에서 본인의 브랜치를 만듭니다.
   - 브랜치명은 `step-1-<이름>`으로 생성
```bash
# step-1 브랜치로 이동
git checkout step-1

# 본인 브랜치 생성 및 이동
git checkout -b step-1-<이름> 
```
3. `/git-basics/README.md`를 복사하고, 빈 항목들을 조사해 채워넣습니다.
   - 복사한 파일명은 `/git-basics/<기수>/REAMDE-<이름>.md`로 변경
        - ex) `git-basics/22rd/README-WONSEOK.md`
   - 채우면서 최소 3개의 커밋 쌓기
```bash
# <기수> 폴더 생성하기 (없다면)
# 1은 뒤에 st, 2는 nd, 3은 rd로 붙이기 (ex - 21st, 22nd, 23rd, 24th, ...)
mkdir git-basics/<기수>

# /git-basics/README.md 복사
cp git-basics/README.md git-basics/<기수>/README-<이름>.md

# (README-<이름>.md를 채우면서)
git add .
git commit -m "<커밋 메시지>"
```

4. 본인 브랜치를 push하고 `step-1` 브랜치로 Pull Request를 올립니다.
```bash
# 브랜치를 처음 push하는 경우 원격 브랜치 등록
# 현재 브랜치를 origin의 step-1-<이름> 브랜치와 연동한다.
# step-1-<이름> 대신 다른 브랜치명을 사용하면 해당 원격 브랜치와 연결됨.
git push --set-upstream origin step-1-<이름>
# 첫 push 이후에는 git push만 사용하면 됨
git push
```

## ➕️ 추가 목표
이제 Markdown 문서를 작성할 수 있게 되었으니, 본인의 Github 프로필을 꾸며봅시다. 아래 참고 블로그나 잘 꾸며진 프로필을 보면서 본인의 프로필을 만들어보세요. 연습을 위해 로컬 git에서 작업하시기 바랍니다.
- **참고**: [(노션) 깃허브 프로필 꾸미기!](https://80000coding.oopy.io/865f4b2a-5198-49e8-a173-0f893a4fed45)  
