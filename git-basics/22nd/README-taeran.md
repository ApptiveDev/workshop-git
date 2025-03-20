# Git 기초
Git 알아보기_김태란(개발)

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
Git : **local** 에서의 모든 변경사항을 기록하는(버전관리를 하는) **소프트웨어**   
Github : 클라우스 서버를 통해 **local의 코드 -> remote** 로 업로드하고 공유할 수 있도록 하는 **서비스**

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
Working Directory : 내가 현재 작업하고 있는 디렉토리 (위치)   

**Git Add** : add를 해줘야만 **commit의 대상**으로 들어간다 (== Staging Area에 올라감)    
ㄴ Git이 해당 파일의 버전관리를 시작함    
ㄴ git restore --staged ${filename} 을 해주면 Staging Area에서 제거 가능     
ㄴ add를 사용하면 어느 부분을 커밋할지 구체적으로 조정이 가능하다             

**Git Commit** : commit을 해줘야만 **git에 저장**을 할 수 있다 (== Local Repo에 올라감)    
ㄴ commit은 git log가 남음. add 한 것들에 스탬프를 찍는 과정.     

**Git Push** : 내가 commit 한 것들을 원격 저장소에 저장함 (== Remote Repo에 올라감)   
ㄴ 하기 전에 원격 저장소와 연결이 되어 있어야 함    

**Git Pull** : remote -> local 로 코드를 가져옴 & 더 최신 코드라면 merge 까지 진행   

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
*"HEAD와 branch는 포인터이다"*   

HEAD : 레포에서의 현재 사용자 위치(checkout을 하면 HEAD가 바뀜)      
branch : 일종의 타임라인으로, 각 branch는 독립된 context를 가진다. (-> 다른 브랜치에 영향 x)   

git branch {브랜치명} : 새로운 브랜치 생성 가능(HEAD가 이를 가리키게 됨)  
git checkout {브랜치명} : HEAD를 움직여서 다른 브랜치로 전환 가능  



## clone, init, origin
#### git clone과 git init의 차이점, 이용방법  
git init : .git이라는 하위 폴더를 생성해 해당 폴더를 git으로 관리할 수 있게 해줌.   
git clone : remote로부터 프로젝트를 local에 복제함.  
ㄴ git clone {깃허브 코드 주소}.git  

#### origin이란 키워드는 무엇인지, 어떻게 설정하는지  
origin : 현재 git에서 작업하는 local과 연결된 **remote의 주소**를 가리킴.   
git remote : origin 생성   
git remote remove origin : origin 삭제 

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
#### reset의 3가지 타입
1. git reset --soft   
ㄴ HEAD가 특정 커밋을 새롭게 가리킴 (working directory OR staging area 영향 x)
2. git reset --mixed   
ㄴ HEAD가 특정 커밋을 새롭게 가리킴 (staging area도 해당 커밋의 모습과 동일하게 변함)
3. git reset --hard (주의 요망)   
ㄴ HEAD가 특정 커밋을 새롭게 가리킴 (working directory & staging area 모두 변함)

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
#### Pull Request
협업을 할 때, push를 한 뒤에 변경사항을 기록하고 pull request를 요청한다.   

#### Merge
팀원의 PR(Pull Request) 내용을 확인한 후, 다른 코드에 영향을 미치지 않고 remote 저장소에 반영해도 된다면, 그때 merge를 진행한다. (-> 원본 저장소에 바뀐 내용이 반영되어 합쳐진다)   

##### Merge_Fast-Forward
현재 브랜치의 HEAD가 대상 브랜치의 HEAD로 옮겨지는 merge    
```git switch [현재 브랜치]```    
```git merge [대상 브랜치]```   
But, 중간에 다른 커밋이 있다면 Conflict 발생 -> 동작 x   

##### Merge_3-way Merge
merge 할 때 두 브랜치가 동일 선상에 없을 때, **공통 조상**으로 merge 진행   
```git checkout master```   
```git merge {브랜치명}```   
공통조상 (Base)를 기준으로, merge의 결과로 채택한 후   
두 브랜치가 다른 변화를 발생시켰다면 이를 충돌로 판단하고 해결해야 merge 가능   

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

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
