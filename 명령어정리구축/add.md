 ### :octocat: git add  명령어  
  
명령어는 다음 변경(commit)을 기록할 때까지 변경분을 모아놓기 위해서 사용합니다.  
따라서, git commit 명령어를 통해 명시적으로 기록을 남기기 전까지는 아무리 git add 명령어를 많이 실행해도 Git 저장소의 변경 이력에는 어떤 영향도 주지 않습니다.

첫번째, 작업 디렉토리의 변경 내용의 일부만 스테이징 영역에 넘기고 싶을 때는 수정한 파일이나 디렉토리의 경로를 인자로 넘깁니다.  
* $ git add <파일/디렉토리 경로>  
  
두번째, 현재 디렉토리의 모든 변경 내용을 스테이징 영역으로 넘기고 싶을 땐 .을 인자로 넘김니다.  
* $ git add .  
세번째, 작업 디렉토리 내의 모든 변경 내용을 몽땅 스테이징 영역으로 넘기고 싶을 때는, -A 옵션을 사용합니다.  
* $ git add -A  
  
git add -A는 작업 디렉토리 상에 어디에 위치하든 항상 동일하게 모든 변경 내용을 스테이징으로 넘깁니다
반면에 git add .는 명령어를 실행한 디렉토리 이하에서 발생한 변경 내용만 포함하며, 해당 디렉토리 기준으로 상위 디렉토리의 변경 내용을 포함하지 않습니다. 
  
각 변경 사항을 터미널에서 직접 눈으로 하나씩 확인하면서 스테이징 영역으로 넘기거나 또는 제외할 수가 있습니다.
*  $ git add -p
---
  
### :octocat: git log 명령어  
  
  
 모든 브랜치들을 보고 싶을 때  
$ git log --oneline --graph --decorate --all  
 --oneline : 현재 커밋을 한 줄로 요약해서 보여준다  
 --graph : 커밋 옆에 브랜치의 흐름을 그래프로 보여준다  
 --decorate : 원래는 --decorate=short 옵션을 의미한다. 브랜치와 태그 등의 참조를 간결히 표시한다  
 --all : all 옵션이 없을 경우 HEAD와 관계 없는 옵션은 보여주지 않는다  
  
$ git log --patch  
$ git log --p  
 파일의 수정된 내용도 함께 확인할 수 있다  
  
$ git log --oneline  
 간단히 커멧 해시와 제목만 보고 싶을 때  
  
$ git log --oneline --reverse  
 오래된 커밋부터 보고 싶을 때  
  
$ git log --oneline -n5  
 내 브랜치의 최신 커밋을 5개만 보고 싶을 때  
  
$ git log --pretty=oneline  
 --pretty 옵션 사용하면 원하는 대로 git log를 foramtting할 수 있다  
 --pretty=oneline처럼 oneline을 이용하면 전체 해쉬코드가 출력된다  
  


$ git log --oneline -3  
 최근 커밋 중 3개만 간단하게 볼 수 있다  
  

$ git log HEAD  
 HEAD는 내가 보고 있는 커밋을 가르킨다  
 git log 와 동일한 내용을 보여준다  
  
$ git log HEAD~1  
  
$ git log HEAD~2  
 HEAD에서 두번째 떨어진 부모부터 보여준다  
  
  
---
  
  
### :octocat:show 명령어  
  
 $ git show  
* git show는 가장 최신 commit의 정보를 출력합니다.  
   
$ git show HEAD^  
* HEAD^는 가장 최신 commit의 이전 commit을 가리킵니다.  
  
$ git show HEAD^^  
* ^표시 한 개면 한 개전 두 개면 두 개전, 갯수로 얼마나 이전 값인지 알수 있음.  
  
$ git show HEAD~3^^  
* ~표시와 ^표시 혼합 사용도 가능하다.  
* 아래는 5개 전입니다.  
  
  
---
  
  
### :octocat:clone 명령어  
  GitHub repository에 있는 내용을 내 로컬(컴퓨터)에 ‘복제’하는 명령어다.  
  즉, repository에 있는 파일을 내 로컬의 특정 디렉토리로 가져올 수 있다.  
    
### :octocat:push 명령어, pull명령어  
  push: 원격저장소 올리기  
  - 작업한 내용을 공개하고 싶을 때에 원격 저장소에 업로드(push)  
  - 깃허브를 저장할 수 있는 권한이 있어야 함. 자신이 oner, 나를 협업자로 등록을 해야함.  
  
  pull: 원격 저장소에서 지역 저장소로 내리기  
  - 물론 원격 저장소에서 다른 사람이 작업한 파일을 가져 올 수 있음 (pull)  
  -* git pull <원격 저장소 명> <branch 명>  
    
    
    
### :octocat:fetch/merge 명령어  
  * fetch 명령어: 로컬디렉토리로 변경한 내용을 가져오지 않고 변경한 내역들만 확인.  
  - 원격저장소에 있는 변경사항들을 로컬저장소에 가져오기 전에 변경내용을 확인하고 싶은경우에 사용하는 명령어 입니다.  
    
  단 fetch 는 원격 저장소에 변경사항이 있는지 확인만 하고, 변경된 데이터를 로컬 Git에 실제로 가져오지는 않습니다.    
    
### :octocat:branch  
  브랜치(Branch) 장점  
  : 하나의 큰 작업 흐름의 단위인 브랜치로 작업  
  * 작업의 기록을 중간 중간에 남기게 되므로  
  * 문제가 발생했을 경우 원인이 되는 작업을 찾아내거나  
  * 그에 따른 대책을 세우기 쉬워짐.  
     
   *분기 사용  
- 저장소에서 다른 브랜치에는 영향 없이 
- * 새로운 기능을 개발하거나  
- * 버그를 수정하거나   
- *새로운 아이디를 안전하게 실험 가능  
  

#####기본 브랜치 (default branch)  
 -이름 기본이 main  
  * 저장소가 생성될 때 자동으로 생성되는  base 브랜치  
   -예전에는 master  
 -기본 설정으로 수정  
 * $ git config --global init.defaultBranch main  
 - 전역 확인  
 * $ git config --global init.defaultBranch  
 * $ git config --global --get init.defaultBranch   
- 지역 확인  
 * git config init.defaultBranch  
 * git config --get init.faultBranch  
  
$ git branch    
-저장소 목록 보기  
$ git branch -a  
- 저장소 목록 보기, 원격 포함 전체 목록  
  
$ git branch <new-branch>  
 -저장소 생성만  
$ git checkout -b <new-branch>  
 - 저장소 생성하고 이동  
$ git switch -c <new-branch>  
 - 저장소 생성하고 이동  
   
 $git branch -d  
 - 저장소 삭제  
---
### :octocat:checkout 명령어   
  checkout 명령어    
 : 브랜치를 변경하고 해당 파일을 워킹 디렉토리로 복사한다.  
 $ git checkout master  
  * 브랜치 이동  
 
 
   
---
### :octocat:switch 명령어  
 octocat:switch 명령어  
: 변경한 내용을 취소하고 이전 브랜치로 돌아갈 수 있습니다  
---
### :octocat:fast for ward  merge 명령어  
  
---
### :octocat:3-way merge   
  
---
### :octocat:rebase 명령어
