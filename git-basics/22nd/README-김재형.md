# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

>* git은 local storage에서 동작
>    * 다른 개발자와 작업물을 공유하는 것은 어렵다. 
>* github는 웹 상의 remote stroage에 작업물을 저장
>    * 다른 개발자와 작업물을 공유하기 편해진다.

[참고자료](https://yeongjaekong.tistory.com/4)

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

>* Working Directory: 현재 작업을 하고 있는 디렉토리 
>    * 이 디렉토리 안 모든 파일은 tracked(프로젝트 디렉토리에 존재하는 경우)/untracked(이 프로젝트 디렉토리에 없는 경우)로 나뉨
>   * tracked는 또 수정/커밋 유무에 따라 상태가 변화
* Git Add: working directory의 변경 사항을 staging area에 추가(add)하는 것
    * 절대/상대 경로를 사용하여 파일,디렉토리를 추가할 수 있다.
* staging area: git add를 통해 추가된 파일/디렉토리의 영역 
* Git Commit: git add를 통해 staging area로 올린 작업물들을 commit하여 local repository에 변경사항을 반영
* local repository: git commit을 통해 변경이 확정되면 변경사항을 반영하고 버전을 매긴다.
* Git push: git commit을 통해 변경사항을 반영한 작업물들을 remote storage에 저장되어있는 작업물들도 변경사항이 반영되도록 하는 작업
* Git pull: 다른 개발자가 github의 remote storage에 변경사항을 반영하였고 나의 local storage에는 변경사항이 반영되지 않은 경우, git pull을 사용하여 나의 local storage를 최신 버전으로 업데이트가 가능
 
[참고자료1](https://iseunghan.tistory.com/322)
[참고자료2](https://anerim.tistory.com/203)

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

>* git의 HEAD와 branch는 포인터 
* HEAD는 branch를 통해 직접적으로 commit을 가리키고 있음
    * commit을 할 때마다 가장 최근 commit을 가리키러 HEAD가 가리키고 있는 branch가 이동한다. 
* branch를 새로 생성하면, 이 branch는 마찬가지로 HEAD가 가리키고 있는 commit을 가리킨다. 

[참고자료](https://charles098.tistory.com/24)

### branch관련 명령어
```
// Branch 생성
$ git branch <새로운_브랜치_이름>

// Branch 삭제
$ git branch -d <삭제할_브랜치_이름>

// Branch 이동, HEAD가 이동할 branch를 가리킨다.
$ git checkout <이동할_브랜치_이름>

// 새로운 branch 생성 후 이동
$ git checkout -b <새로운_브랜치_이름>
```

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

> * git init: local에 git이 관리하는 빈 저장소를 새로 만드는 명렁어
>    * 새로운 프로젝트를 시작하기 전에 이 명령어를 사용하면 git이 해당 디렉토리를 관리해준다.
> * git clone: github의 remote repository를 그대로 복제하여 local에 해당 프로젝트 디렉토리를 만드는 방식이다.

>* origin: remote repository의 주소를 키워드로 만들어서 대신 사용하는 것
>   * remote repository의 주소를 일일이 기억하고 입력하는 것이 불편하기 때문

```
// 새로운 origin 설정
$ git remote add origin 'remote repositroy 주소'
```

[참고자료](https://velog.io/@yejine2/git-%EC%A0%80%EC%9E%A5%EC%86%8C-%EC%83%9D%EC%84%B1-init-clone-%EB%B0%A9%EB%B2%95)



## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

> * git reset은 soft,mixed,hard가 존재
* git reset --soft : 되돌아갈 commit의 hash값을 적으면 HEAD가 가리키는 branch가 가리키는 commit이 사용자가 되돌아가려고 하는 commit을 가리킴 (commit 취소)
* git reset --mixed : soft 작업에서 staging area까지 비우는 작업을 수행 (commit 취소, add 취소)
* git reset -- hard : mixed작업에서 이번엔 working directory에서 변경했던 데이터까지 되돌림 
    * 로컬에 저장된 데이터까지 롤백 
    * commit을 한 적이 없는 변경사항은 모두 덮어써져 복구가 되지 않음에 주의.

[참고자료](https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Reset-%EB%AA%85%ED%99%95%ED%9E%88-%EC%95%8C%EA%B3%A0-%EA%B0%80%EA%B8%B0)

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

> * pull request(pr): branch를 새로 생성하고 checkout을 통해 HEAD가 가리키는 branch를 바꾼 후 수정한 작업물을 push하는 경우에 가능
>    * pr을 생성하게되면 main branch와 변경사항을 비교할 수 있으며, 변경을 확정하고 싶으면 merge, 아니라면 pr을 종료시킬 수 있다. 

> * Fast-forward: 기준 branch에는 신규 commit이 없고 새로운 branch에만 commit이 존재하는 경우, 새로운 branch를 그냥 main branch로 보고 병합해버리는 방식
> * 3-way merge: 두 branch가 신규 commit이 1회 이상 있는 경우 merge를 진행하는 경우에 발생. 두 branch의 코드를 합쳐서 새로운 commit 생성하여 merge


## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

> * rebase: branch의 시작점을 다른 commit으로 옮겨주는 것 
>    * 앞서 살펴본 merge방식을 branch의 시작점을 바꿈으로써 개발자가 제어 가능


## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

> * git stash: 수정한 파일, add한 파일들을 스택에 저장해두는 명령어
>    * 하던 작업을 멈추고 다른 branch로 이동이 필요한 경우 stash를 이용하여 하던거 까지 저장 가능


## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- 브랜치관리전략에 대표적으로 Github Flow, Git Flow가 있습니다. 두 방식에서는 리포지토리를 어떻게 관리할까요?
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
