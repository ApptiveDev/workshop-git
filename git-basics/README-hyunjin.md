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


⸰ Branch : 커밋사이를 가볍게 이동할 수 있는 포인터이다. 기본적으로 Git은 master 브랜치를 만든다. 처음 커밋하면 이 master 브랜치가 생성된 커밋을 가리킨다. 이후 커밋을 만들면 master 브랜치는 자동으로 가장 마지막 커밋을 가리킨다. git branch <브랜치이름> 명령어를 통해서 생성가능하다.

⸰ HEAD : 현재 작업하는 로컬 브랜치를 가리킨다.

⸰ Git checkout : 다른 브랜치로 이동할 수 있는 명령어이다. 즉 HEAD가 가리키는 브랜치를 옮긴다.

⸰ 출처 : https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80


## clone, init, origin

⸰ Git init : 빈 git 저장소를 만들거나 기존 저장소를 다시 초기화하는 명령어이다.

⸰ Git clone : git clone <url> 과 같이 사용하며, url에 해당하는 저장소를 복제해 새 directory로 가져오는 명령어이다.

⸰ Origin : 대표적으로 사용되는 원격 저장소의 별칭을 의미한다. 

별칭이란? - 로컬 저장소를 원격 저장소에 등록하기 위해서는 (git push) git 호스팅사 서버의 URL이 필요하다. github나 gitlab같은 호스팅사로 이용할 경우, 이 연결 URL은 프로토콜과 호스팅사 도메인으로 이루어진다. 즉 URL 주소가 길어진다. 그렇기 때문에 이 URL을 간략하게 특정 문자로 지정하는 것을 별칭이라고 한다. (별칭은 중복사용 불가능하다.)
별칭은 git remote <별칭> <URL>로 지정하고 git remote rename <변경전> <변경후>로 바꿀수있다. 삭제는 git remote rm <별칭>으로 한다

⸰ 출처 : https://yoongrammer.tistory.com/21 , https://m.blog.naver.com/rinjyu/222180087428

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  

⸰ Reset : 총 3단계에 걸쳐서 이루어진다. (git reset 명령어)

1. HEAD 이동 : reset 명령이 하는 첫 번째 일은 HEAD 브랜치를 이동시키는 것이다. checkout 명령처럼 HEAD가 가리키는 브랜치를 바꾸지는 않는다. HEAD는 계속 현재 브랜치를 가리키고 있고, 현재 브랜치가 가리키는 커밋을 바꾼다. (--soft 옵션을 주면 여기까지 진행.)

2. Index(staging area) 업데이트 : Index를 현재 HEAD가 가리키는 스냅샷으로 업데이트 한다. 즉 git commit과 git add명령을 되돌리는 것이다.(--mixed 옵션을 주면 여기까지 진행. default는 --mixed 옵션)

3. Working directory 업데이트 : working directory까지 업데이트 한다. 다시 말해 working directory파일을 강제로 덮어쓴다. 이 단계는 되돌리기가 불가능하기 떄문에 위험하다. (--hard 옵션을 주면 여기까지 진행)

⸰ 출처 : https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Reset-%EB%AA%85%ED%99%95%ED%9E%88-%EC%95%8C%EA%B3%A0-%EA%B0%80%EA%B8%B0

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  

⸰ Pull Request : Pull Request는 사용자가 원격 저장소에 Push하여 새로운 사항이 적용됐을 경우, 다른 사용자에게 push된 상황을 알리는 것을 말한다. 이를 줄여서 PR이라고도 한다.Pull request를 보내 놓으면 여러 동료들에게 리뷰를 받을 수 있고, 내가 올린 코드에 동료가 병합하여 진행할 수도 있다.

⸰ Merge : 말 그대로 병합. git branch를 다른 branch로 합치는 과정이다.

1. Fast Forward Merge : 가장 기본적인 Merge이다. 현재 branch의 HEAD가 대상 branch의 HEAD까지로 옮기는 Merge이다. git switch <현재 branch>와 git merge <대상 branch> 명령어로 사용가능하다.

2. 3-way Merge : 동시간대에 두명 이상이 commit을 하면 Fast Forward Merge가 불가능하기 때문에, 내 branch commit과 다른 branch commit을 병합해서 새로운 커밋을 생성하는 방법이다.

⸰ 출처: https://ittrue.tistory.com/93 , https://kotlinworld.com/277 , https://wonyong-jang.github.io/git/2021/02/05/Github-Merge.html


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  

⸰ Rebase : 두 branch를 합치는 방법으로, Merge와는 다르게 이름 그대로 branch의 공통 조상이 되는 base를 다른 branch의 commit 지점으로 바꾸는 것이다. 

기본 전략 - 먼저 Rebase 하려는 브랜치 커밋들의 변경사항을 Patch라는 것으로 만든 다음에 임시저장소에 저장해 둔다. 그리고 이를 master 브랜치에 하나씩 적용시켜 새로운 커밋을 만든다. (git checkout feature, git rebase master, git checkout master, git merge feature를 이용한다.)

* Rebase를 위처럼 두 브랜치를 병합하는데 사용할 수도 있지만, 단일 브랜치 내에서 rebase를 사용하여 커밋 히스토리를 정리할 수도 있다.
즉, rebase를 이용하면 작업 도중 커밋 히스토리를 수정해야 하는 상황에서 유용하게 사용할 수 있다.

⸰출처 : https://wonyong-jang.github.io/git/2021/02/05/Github-Rebase.html


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  

⸰ Stash : stash(git stash 명령어)는 작업중인 변경사항을 일시적으로 저장하고 branch전환, 또는 코드 commit 시점을 유연하게 다룰 수 있게 해준다.
변경사항을 commit하기에 이른 경우, 임시저장, 다른 branch로 체크아웃할때 변경사항을 유지하고 싶은 경우에 사용한다.

* git stash(git stash save) - 현재 작업 중인 변경 사항을 일시적으로 저장하고, 작업 디렉토리를 깨끗한 상태로 만든다. 이 때, 저장한 변경 사항은 스택에 쌓이게 된다.

* git stash pop(git stash pop <index 번호>) - 스택에 쌓인 가장 최근의 변경 사항을 불러와 작업 디렉토리에 적용된다. 이 때, 스택에서 해당 변경 사항은 제거됨.

* git stash apply - stash를 적용한 후에도 stash가 적용되어 있는 상태를 유지한다. 임시 저장공간에서 삭제되지 않는다. 이에 대해 추가 작업을 수행하려면 다시 git stash 명령어를 실행해야 함.
만약 branch마다 적용을 하고싶다면 git stash apply를 활용하면 된다.

* git stash list - 현재 stash들의 목록을 확인할 수 있다.

⸰ 출처 : https://velog.io/@fkszm3/Git-stash-%EB%9E%80-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%A0%EA%B9%8C


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
