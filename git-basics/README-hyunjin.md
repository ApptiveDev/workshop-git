# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  


⸰ Git은 개인 컴퓨터에서 돌아가는 Version Control System이다. 반면에 GitHub은 Github라 불리는 회사에서 서비스하고 있는 서버에 올라간 Git이다.

⸰ 즉 개인 컴퓨터에서 사용하는 Git을 Local Git이라 부르고, Github이나 Gitlab과 같은 클라우드에 저장하는 Git을 Remote Git이라 부른다.

⸰ 출처 : https://kotlinworld.com/265

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  


⸰ Working Directory : 사용자의 작업 공간으로서, 로컬 저장소에 접근할수 있으며 실제 파일을 수정하거나 생성하는 공간이다.작업 폴더에서 .git 디렉토리를  제외한 나머지 부분. 파일들을 추적(tracked)/비추적(untracked) 상태로 구분한다.

⸰ Staging area : commit이 가능한 영역으로, commit하기 전 파일을 담아두는 상자라고 볼 수 있다.

⸰ Local repository : 본인의 컴퓨터에 저장된 로컬 버전의 프로젝트 저장소.

⸰ Remote repository : Local repo와는 반대로 내 컴퓨터가 아닌 (일반적으로 원격 서버) 버전의 프로젝트 저장소.

⸰ Working directory에 있는 작업물을 git add 명령어를 통해 staging area로 보내고, git commit 명령어를 통해서 간단한 코멘트를 남겨 라벨링 후, Local repo로 보낸다. 최종적으로 git push를 통해서 Local repo에 있는 파일을 Remote repo(github)로 보낸다.

⸰ 출처 : https://m31phy.tistory.com/146 , https://ittrue.tistory.com/94 , https://dev-jacob.tistory.com/entry/Git-Repository%EB%9E%80

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  


⸰ branch : 커밋사이를 가볍게 이동할 수 있는 포인터이다. 기본적으로 Git은 master 브랜치를 만든다. 처음 커밋하면 이 master 브랜치가 생성된 커밋을 가리킨다. 이후 커밋을 만들면 master 브랜치는 자동으로 가장 마지막 커밋을 가리킨다. git branch <브랜치이름> 명령어를 통해서 생성가능하다.

⸰ HEAD : 현재 작업하는 로컬 브랜치를 가리킨다.

⸰ git checkout : 다른 브랜치로 이동할 수 있는 명령어이다. 즉 HEAD가 가리키는 브랜치를 옮긴다.

⸰ 출처 : https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

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
