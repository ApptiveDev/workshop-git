# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git: 소스 코드 및 파일 관리 시스템으로
    git을 이용하여 파일의 변화를 저장 및 추적이 가능하며 원하는 시점으로 되돌리거나 타인과 공유하는 것이 가능하다.

github: 작업물을 온라인으로 저장하고 공유하는 공간.

로컬 컴퓨터에서 git을 이용하여 작업하고 저장하여 github에 공유하고 이를 통해 github에서 협업하는 것이 가능하다.

## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  

Working Directory는 현재 내 작업물(소스코드)을 이야기 하며
이를 Git add를 통해 원하는 파일을 선택하고 staging area에 두며
이를 다시 git commit을 통해 로컬 컴퓨터의 저장소(Rocal repository)에 커밋메세지와 함께 저장.
로컬 레포지토리에 있는 변경사항을 git push를 통해 원격 저장소(remote repository)에 전송하고 git hub를 통해 공유된다.

git pull은 git fetch와 git merge를 병합한 과정으로
fetch를 통해 원격저장소에 있는 변경사항을 로컬로 가져오고 merge를 통해 로컬에 병합시킨다.

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
branch: 프로젝트의 특정 작업이나 기능을 독립적으로 분리하여 개발하기 위한 개념
        각 브랜치는 프로젝트의 특정 상태를 나타내며, 독립적으로 변경되고 관리된다.

commit: 소스 코드의 변경 사항

Head: 현재 작업중인 브랜치의 가장 최근 커밋, 즉 현재 작업중인 커밋

Git Checkout: 특정 브랜치로 이동할 때 사용되는 명령어로 "git checkout git-test-file"명령어 사용 시 git-test-file브랜치로 이동.

git branch: 새로운 브랜치를 생성할 때 사용합니다.
"git branch git-test-file" 명령어를 사용하여 git-test-file라는 새로운 브랜치를 생성

git checkout -b new-branch: 새로운 브랜치 생성 후 해당 브랜치로 이동

git branch -d: 브랜치 삭제. 예시로 git branch -d git-test-file로 git-test-file삭제 


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

git clone: 이미 존재하는 원격 저장소의 내용을 복제하여 로컬에 새로운 디렉토리를 생성.
             즉, 원격 저장소의 모든 내용을 가져와 로컬에 복사
             
             사용법 : git clone <원격 저장소 URL>

git init: 현재 디렉토리나 새로운 디렉토리에 새로운 Git 저장소를 초기화
          (아무런 내용도 없는 새로운 저장소를 생성) 
          이후에 파일을 추가하고 커밋할 수 있다.

          사용법 : git init
          
origin: 원격 저장소의 이름으로 git clone을 통해 원격 저장소 복제시,
        origin이라는 이름으로 원격 저장소 생성

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  


Soft Reset:
    Soft reset은 커밋을 되돌리고 인덱스(Staging Area)에 있는 변경 사항을 유지
    
    가장 최신의 커밋을 취소하고, 그 변경 사항을 다시 스테이징 영역에 추가 
    실제로 작업 트리의 파일은 변경되지 않음

    사용법: git reset --soft HEAD~1

Mixed Reset:
    Mixed reset은 커밋을 되돌리고 인덱스(Staging Area)에 있는 변경 사항을 취소
    
    최신 커밋을 취소하고, 그 변경 사항을 스테이징 영역에서 제거
    작업 트리의 파일은 변경 내용이 그대로 유지

    
    사용법: git reset HEAD~1

Hard Reset:
    Hard reset은 커밋을 되돌리고 작업 트리와 인덱스에 있는 변경 사항을 모두 삭제
    
    최신 커밋을 취소하고, 그 변경 사항을 스테이징 영역과 작업 트리에서 모두 제거
    
    이 명령어를 사용하면 작업 트리에 있는 모든 변경 사항이 사라지므로 주의 필요
    
    사용법: git reset --hard HEAD~1

간단히 나타내어 상술한 워킹 디렉토리(1)-인덱스(2)-로컬 리포지토리(3) 관계에서
soft는 3->2, mixed는 3->1, hrad는 3->0

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  

Pull Request: 다른 사용자가 작성한 저장소에서 변경 사항을 병합하기 위한 요청

Merge : Merge는 두 개 이상의 다른 브랜치의 변경 사항을 하나의 master branch에 통합하는 작업.
        master브랜치에서 분기해 나가는 지점(commit)을 base라 함
 -Fast Forward Merge: 병합 과정에서 새로운 commit을 생성하지 않고 이전 변경사항을
                   참조하여 쌓아 나가는 것
 -3-Way Merge: base와 그곳에서 뻗은 두 brach, 총 세 커밋을 비교하여 변경사항을 병합
              

## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  

Rebase : base를 재설정한다는 의미로, 
        하나의 브랜치가 다른 브랜치에서 파생되서 나온 경우, 다른 브랜치에서 진행된 커밋을 가져와서 base를 재설정하는 것

        rebase를 사용하면 브랜치의 커밋 히스토리를 깔끔하게 유지할 수 있고, 불필요한 머지 커밋을 방지하고 선형적인 히스토리를 유지할 수 있다

        적용 순서:

        1. 현재 브랜치에서 베이스로 지정한 브랜치(대상 브랜치)의 최신 커밋을     
          가져옵니다.
        
        2. 현재 브랜치에서 베이스로 지정한 브랜치까지의 커밋을 임시로 저장합니다.
        
        3. 베이스로 지정한 브랜치의 최신 커밋을 가져와 현재 브랜치의 마지막     
           커밋으로 합칩니다.
        
        4. 임시로 저장한 커밋을 다시 현재 브랜치 위에 적용하여 완료합니다.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  

git stash: 현재 작업 디렉토리의 변경 사항을 임시로 저장

        변경 사항을 stash에 저장하기: git stash save "임시로 저장할 메시지"

        stash 목록 확인하기: git stash list

        stash에서 변경 사항을 적용하기: git stash apply stash@{n}

        stash에서 변경 사항을 적용하고 해당 stash 제거하기: it stash pop stash@{n}

        특정 stash 삭제하기: git stash drop stash@{n}

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

Fast-Forward와 3-Way Merge의 이해가 맞는지 잘 모르겠습니다.