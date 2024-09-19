# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

`Git` 은 버전관리 소프트웨어다. 로컬 저장소(내 컴퓨터)의 모든 변경사항을 기록하여 파일의 버전관리가 용이하다.
`Github` 는 Git을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스다. Git은 로컬 저장소에서 작동하기에 다른 개발자와 협업하기 어렵다. 이 때 Github를 사용하여 리모트 저장소(원격 저장소)에 로컬 저장소의 코드를 업로드하고 공유할 수 있다. 

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- `Working directory` : 이력관리 대상 파일들이 위치하는 영역, 작업된 파일이나 코드가 저장되는 공간
- `Staging area` : commit 할 대상 파일들이 위치하는 영역
- `Local repo` : 내 컴퓨터 안에 있는 저장소
- `Remote repo` : 서버에 있는 원격 저장소
- `Git Add` : Working directory 내에 수정사항이 있는 파일들을 Staging area에 올린다.
- `Git Commit` : 이력 저장
- `Git Push` : Local repo 의 변경 사항을 Remote repo로 업로드한다.
- `Git Pull` : Remote repo의 내용을 Local repo로 복원한다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

### git reset 옵션
- 공통 : 커밋 취소
1. --soft : staging 상태 유지 (git add 상태)
2. --mixed : staging 취소, local 변경 상태 취소
3. --hard : staging 취소, local 변경 상태 취소

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

### Pull Request
- 한 분기의 변경 내용 집합을 다른 분기에 병합하라는 제안
- 변경 내용을 기본 코드베이스에 통합하기 전에 제안된 변경 내용 집합을 검토하고 논의할 수 있다.
- 원본 콘텐츠와 대상 브랜치간의 차이점을 표시한다.

### Merge
- merge는 한 분기 (동일 저장소 또는 fork한 저장소)에서 변경 내용을 가져와서 다른 분기로 적용한다.
- PR 또는 명령줄을 통해 발생한다.

![image](https://github.com/user-attachments/assets/dff857c3-dd8a-4722-8bdd-6856d9031f9e)
![image-1](https://github.com/user-attachments/assets/682e983f-e719-4a24-9913-7c121cee27bf)
- `fast-forward` : 가장 기본적인 merge, 기준이 되는 브랜치에는 신규 커밋이 존재하지 않고 다른 브랜치에만 커밋이 존재할 때 브랜치 병합을 하는 경우
	- 새로운 커밋이 생기지 않고 HEAD의 위치만 변한다.

![image-2](https://github.com/user-attachments/assets/37c76559-af6d-400c-93dc-84da12ccb472)
![image-3](https://github.com/user-attachments/assets/536e45ab-4d4f-4548-9d55-632793d47115)
- `3-way merge`: 두 브랜치 보두 base에서 commit을 진행해서 분기해 나간 상태가 되었을 때
	- 새로운 commit이 생성된다.
	- merge 명령은 base를 기준으로 변경사항이 있는 파일들을 merge commit에 반영한다. 만약 두 commit 모두에서 변경 사항이 발생한 파일에 대해서는 충돌이 발생하며 해당 파일의 충돌을 해결 한 후 commit 하면 된다.

참고 : https://wikidocs.net/153693



## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

`git rebase`를 통해 브랜치의 base를 조정할 수 있다.
- 여러 개의 브랜치를 생성하여 작업한 후 main 또는 master 브랜치에 병합하는 방법 중 작업 종류가 유사한 브랜치끼리 한 줄기로 표시되도록 정리하는 방법
- rebase 과정에서 branch 간 내용을 자동으로 merge 한다. 만약 자동으로 merge를 할 수 없다면, 충돌 메시지를 발생시키고 이 때는 수동으로 코드를 정리해야 한다.
- 일을 병렬로 동시에 진행해도 rebase를 하고 나면 모든 작업이 차례대로 수행된 것 처럼 보인다. 리모트 브랜치에 커밋을 깔끔하게 적용하고 싶을 때 유용하다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

`stush` 는 안전하게 저장하다. 라는 사전적 의미를 가지고 있다. 작업 내용을 별도의 공간에 임시 저장, 추출 할 수 있다.

만약 내가 어떤 작업을 하던 중 아직 완료가 되지 않아 commit을 하지 못하는 상황에서 pull이 필요할 때 사용한다. 

- git stush 명령은 modified 파일에 대해서만 적용된다. 만약 새로 추가한 파일도 임시 저장하고 싶다면 `-u` 옵션을 사용하면 된다.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지. 
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
