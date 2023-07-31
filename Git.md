
# Git

: 버전관리 도구. 리눅스토발즈가 개발.

- 빠른속도
- 단순한 구조
- 비선형적 개발(병렬적 개발)
- 완벽한 분산
- Linux 커널과 같은 대규모 프로젝트에 유용

# 형상관리

SCM(Software Configuration Management)

형상) 와이어프레임, 스토리보드, 프로토타입, 플로우차트, 소스코드 등의 모든 산출물

계속 변화하는 sw 형상을 '변경점' 기준으로 관리해야함

ex) SVN, CVS, Git, Mercurial, BitKeeper, ClearCase...

# CVCS(Centralized Version Control System)

: 중앙집중형 버전관리

- 관리 쉬움
- 원격서버로 부터 작업할 파일을 직접 수정
- 네트워크 연결 없을 시 작업 불가
- 원격서버의 소스코드 손실 시 복구할 방법 X
- ex) CVS, SVN

# DVCS(Distributed Version Control System)

: 분산집중형 버전관리

- 원격서버에서, 로컬저장소로 복사해오기 가능
- 네트워크 끊겨도 작업 가능
- 개인적 빌드 확인 가능
- 원격 서버의 소스코드 손실해도 복구 가능
- ex) Git, Mercurial

---

# Git 설치

- [https://git-scm.com](https://git-scm.com/) [로컬]
- [https://github.com](https://github.com/) [원격]
- [https://github.com/trending](https://github.com/trending) 에서 제일 인기있는 repo 확인가능 ***
- [https://about.gitlab.com](https://about.gitlab.com/) [깃랩]
- 깃랩은 private저장소도 무료

# Git 사용

- CLI : (Command Line Interface)'Git Bash'프로그램에서 명령어 입력

# Git 구성

![https://user-images.githubusercontent.com/67628725/197425206-c2b76d8d-d045-4f63-979d-8eaa159e4557.png](https://user-images.githubusercontent.com/67628725/197425206-c2b76d8d-d045-4f63-979d-8eaa159e4557.png)

- 작업디렉토리(Working Directory) : git에서 관리 o 추적 x
- 스테이징영역(Staging Area) : git에서 변경점 추적 o, commit준비영역, 작업한 내용물의 임시저장영역
- 로컬저장소(Local Repository) : commit이 영구적으로 저장되는 영역
- 원격저장소(Remote Repository) :

- 클론(Clone) : 원격저장소 -> 로컬저장소로 코드 가져오기
- 커밋(Commit) : git에서 가장 의미있는 '변경의 단위', (변경점을 local저장소에 저장하는 행위.)
- 풀(Pull) : 원격저장소에 있는 다른 개발자의 commit을 받아옴 (최신 업데이트)
- 푸시(Push) : 로컬저장소에 있는 내 commit을 원격저장소로 업데이트 함

# Git 기본플로우

1. 원격저장소의 소스코드 -> 로컬저장소로 다운로드 [clone]
2. 작업디렉토리에서 작업, 소스코드 수정
3. 작업한 내용 '스테이지 영역'에 추가 [add]
4. 의미있는 변경점이 쌓이면 커밋 [commit]
5. 로컬저장소에 영구적으로 저장
6. 원격저장소에 업데이트된 다른 개발자의 커밋 받아옴 [pull]
7. 최신업데이트 해서 충돌을 없앤 후,
8. 로컬저장소에 저장된 내 commit을 원격저장소에 반영함 [push]

---

# Git 기본 환경설정

### git정보등록)

$ git config --global user.name "이름" : 이름 등록

$ git config --global user.email "이메일주소" : 이메일 등록

$ git config --global core.editor vim : 기본에디터(vim) 설정

$ git config --global --list : git기본 등록정보 확인 => 모든 정보는 [.gitconfig] 파일에 저장됨. 즉 이를 수정함으로써 설정내용 수정 가능

$ vi ~/.gitconfig

### 저장소생성하는 두가지 방법)

1. clone 하기
2. 로컬저장소 생성 -> 초기화(git init) -> 원격저장소 연결(git remote add)

### 워킹디렉토리 생성)

$ mkdir {디렉토리명} : 워킹디렉토리 생성

$ git init : ***'.git'*** 폴더 생성 + master기본브랜치 생성

{.git 폴더 내부 ls-al 명령어 친 후 구조 사진.jpg} 

=> 변경되는 파일을 추적/관리할 수 있게 하는 파일워킹디렉토리의 두가지 파일상태)

 1. Untracked : 변경사항은 있으나, 한번도 staging area에 포함되지 않아 git에 의해 관리되지 않은 파일

 2. Tracked : staging area에 한번 이상 포함되어 git에 의해 관리되는 파일

### 원격저장소와 연결)

$ git remote add {원격저장소 별칭} {원격저장소 주소} : 원격-로컬 연결 (저장소 별칭 ex_default, origin)

$ git remote -v : 로컬에 연결된 원격저장소 주소 확인 => fetch랑 push 브랜치 두개 생기던데 뭐임????  

or  

$ git clone {원격저장소 주소}  : 원격저장소 로컬로 다운로드 (기본 master 브랜치)  
 - 이미 존재하는 '.git' 폴더까지 다운로드 하는 것이므로, 별도의 초기화 필요치 않음
 - 

---  

  

# Git 명령어 정리

$ git --version 버전 확인

$ clear 명령창 clean

### 파일작성)

$ vi {파일명} : 파일 열기ESC버튼 + wq입력 후 enter : 파일 저장후 닫기 (w:저장, q:닫기)

$ ~/ : 루트 디렉토리 의미

$ mkdir {파일명} : 폴더 생성

$ cd {디렉토리경로} : 해당 경로로 이동

### git확인)

$ git status : 현재 폴더 내, 파일의 상태(브랜치, 커밋, 스테이징 등) 확인

$ git log : 커밋의 히스토리 확인  
      - down 키보드 누르면 -> 로그 히스토리 쭈욱 확인 가능  
      `<히스토리 구성>  
      - commit: 커밋id => SHA1 해시알고리즘으로 커밋id만듦  
      - Author: 작성자  
      - Date: 커밋날짜  `
  
      `<git log 옵션>  
      --help		: 해당 명령어의 매뉴얼 페이지 생성  
      -u 			: git diff + log => 커밋히스토리와 함께 각 커밋에서의 코드 변경내용을 보여줌  
      -u {commit ID}	: 입력한 {commit ID}의 내용 + 코드변경내용  
      		= $ git show {commit ID}와 같은 명령어
      -{숫자n}		: 최신 n개만큼의 커밋내용 표출  
      --name-only		: 커밋히스토리의 '변경된 파일명'까지 보게됨
      --oneline		: 커밋을 간결하게 한줄로만 표시  
      --reverse  : 오래된 커밋순으로 표시  
        
      -- all  : 모든 branch의 커밋확인  
      -- graph  : 브랜치를 그래프 그림으로 표현  `

### git동작)

 * 변경점 = 코드의 변경사항을 의미

$ git add {파일명} : 스테이징 영역에 변경점 올림  
 *경고발생warning: in the working copy of 'test.java', LF will be replaced by CRLF the next time Git touches it  
 - 위같은 에러가 뜬다면, 다음 명령어로 에러를 무시할 수 있음
 - $ git config --global core.safecrlf false

$ git commit :스테이징(add)된 변경사항들을 commit  
 - git commit할 시, editor창이 뜨는데, 커밋메시지를 입력하는 곳이다.
 - 'i' 누른 후 입력 후 저장. (#주석처리 된 줄은 메시지로 안들어감)  

$ git commit -m "{커밋메시지}" : 커밋메시지와 함께 바로 commit

$ git diff : '워킹 디렉토리'에서, 변경사항(코드) 확인.  
  - 보기 힘들기 때문에 간단한 변경 or 변경점 적은 경우에만 사용
  - 변경점이 스테이징 되어있지 않더라도, 이전에 한번 staging영역에 올라온 파일은 git에 의해 관리되기 때문에 확인 가능

#### commit 되돌리기1 - 복구 X)  
$ git commit --amend  
 - 마지막 반영한 최신 '커밋메시지'를 변경하고 싶을 때
 - 최신 커밋에 추가할 변경점이 있을 때  
 - -> 최신 커밋 수정가능한 에디터 실행됨
 - 되돌린 커밋은 절대 복구할 수 없음 !!! ***  

#### commit 되돌리기2 - 복구 O, roll-back)  
$ git revert {마지막에 반영한 commit ID}  
 - 변경 취소 & 반영한 커밋 되돌리기 가능  
 - 커밋히스토리를 유지하며, 내용만 롤백  
 - 즉, commit을 취소한 내용의 commit이 하나 추가로 더 생김  
 - 되돌린 커밋은 새로운 파일로 저장되어 코드 원복이 가능함  

### git 원격 저장소에 반영)  

$ git push {원격저장소 별칭} {현재로컬브랜치}: 원격 저장소에 commit 반영(push)- {저장소 별칭} : 

$ git remote -v 실행 시, 제일 처음에 뜨는 이름 origin [https://gitlab.com/ys26/TEST.git](https://gitlab.com/ys26/TEST.git) (fetch) 에서 origin. ???? origin 이 뭐 가리키더라 ??(위에서 설정한 원격저장소 주소의 별칭임)  
 - {현재 브랜치} : 로컬 디렉토리에서 현재 있는 브랜치 (git bash 에 괄호치고 써 있음)
 - 이후 창 뜨면 아이디/비번 누르고 들어가기
 - (git 업데이트 이후, 토큰 발급한 후 사용해야함)


$ git pull {원격저장소 별칭} {현재로컬브랜치} : 원격 -> 로컬로 다른 개발자가 반영한 commit 가져오기 (로컬에 머지)  
 - 가져온 commit + merge commit 까지 중복 발생 ***
 - ?? 머지 커밋 없애려면 어떻게 해야함 ??

---

### git 브랜치)
- 본래 소스코드로 부터 분기한 '독립적인' 작업 공간  
- 최신 commit을 가리키는 일종의 `포인터`
- 매우 가벼움
- 

$ git branch : 현재 작업중인 브랜치 확인  
 - 기본 master 브랜치
 - 초기 git init 후, commit이 없는 채로 git branch실행 시, 아무것도 뜨지 않음. (커밋이 없어 브랜치=포인터가 가리키는 게 없기 때문)
 - commit 이 없다 = 브랜치(포인터)가 가리킬 것이 없다 = 브랜치가 없다 = 최초 commit이 있어야 브랜치가 가리킬 수 있다.
 - 브랜치 포인터)
   - HEAD : 현재 (로컬)브랜치를 가리키는 일종의 포인터 (마지막 commit에 대한 스냅샷)
   - ex) `HEAD -> master(브랜치) -> commit1(최신커밋)`  형태로 가리키고있음
   - 새로운 commit은 바로 이전 commit을 가리키는 형태로 linked 됨
 - `<git branch 옵션>  
   -v  : 각 브랜치가 가리키는 최신 commit 보여줌  
     <형태>  
     {브랜치명} {최신 commit ID} {최신 commit 메시지} on {해당 commit이 있는 브랜치(머지된 브랜치)}`

$ git branch {생성할 브랜치명} : 새로운 브랜치 생성 (자동이동 X)  
 - 브랜치 새로 생성 = 현재기준 브랜치의 최신 commit을 가리키는 포인터를 또 새로 하나 더 만듦
 - ???? 처음 branch 생성하면 가리키는 commit이 없음? 기존 분기한 브랜치 기준으로 commit 가리키는 거 아님 ??  
 
   

$ git checkout {이동할 브랜치명} : 브랜치 이동  
 - HEAD 포인터가 가리키는 포인터가 바뀜
 - 각 브랜치마다 각자의 최신 commit 옆에 초록색 괄호()로 브랜치 표시됨 (해당 브랜치의 history에 지난 commit이 포함되어있다면)
 - 각 브랜치는, 포인터가 가리키는 각자의 최신 commit까지밖에 기억못함.
 - `<git checkout 옵션>
   -b  : 브랜치 생성&이동 동시에`

$ git branch -d {삭제할 브랜치명} : 브랜치 삭제  
 - 해당 브랜치가 가리키는 commit까지 삭제되는 것이 아닌,
 - 해당 브랜치의 포인터만 삭제됨  
 - ?? 그럼 그 commit 다른데 반영안하고 그냥 삭제하면 남은 commit은 어떻게됨?? 가비지 콜렉터 등이 처리해줌? 


### 브랜치 병합 Merge)  
$ git merge {합쳐질 브랜치명} : 브랜치를 병합
 - 기준이 되는 (main)브랜치로 먼저 이동(checkout) 후 merge한다.***
 - 그 이후 합쳐질 (issue)브랜치를 병합한다.
 - 머지 커밋이 발생
 - 로그에 Fast-forward 라고 뜸

##### Fast-forward Merge)
 - (main)브랜치(포인터)의 위치만, 단순히 (합쳐질 브랜치의) 최신 commit으로 이동시키는 방식

##### 3-way Merge)  
 - 두 브랜치가 각각 서로 겹치지 않는 커밋을 2개 이상 갖고 있을 때
 - 아래 3개의 commit을 모두 고려해 merge 진행
    1. 두 브랜치의 공통커밋 중 가장 최신 commit  
    2. A 브랜치의 최신 commit   
    3. B 브랜치의 최신 commit  
 - 새로운 merge commit이 각각 2) A의최신 커밋, 3) B의최신 커밋을 둘다 가리키는 형태로 생성됨.  
 - 그 후 생성된 최신 merge commit을 현재 브랜치 포인터가 다시 가리키는 형태의 머지방식  
 - ??? 그럼, 2) 3)의 commit 내용을 섞을 때 날짜기준으로 사이사이에 섞여 들어가지 않고 링크된 순서대로 A쭉- 다끝나고 B쭉- 나옴?????  
  

### 충돌 Conflict)  
 - 변경점이 충돌하는 상태  
 - 같은 파일 내의 같은 부분이 각각 변경점commit으로 남은 후, 이를 원격에 반영할 때 발생  
 - 어떤 변경사항을 적용할지 수정하는것이 conflict 해결을 의미  
 - 해결은 아래 두가지 방법으로 가능  
  1) 직접 충돌난 파일 열어 수정 후 해결  
     - >>>>  ======   <<<<< 등의 표현으로 각 브랜치 안의 내용 표시  (해당 기호 지워도됨)  
  2)  $ git mergetool  
     - `vimdiff`, 등 머지툴 사용해서 해결  
     - 3-way 방식 반영해 위에 3개의 비교창이 뜸 (A내용 / 공통내용 / B내용)  
     - 하단의 워킹디렉토리 창에서 직접 수정  
  - 충돌 해결 후, add, commit 부터 다시 해야됨 (커밋메시지 자동작성됨)  

---  
### 태그 Tag)  
- 특정 시점의 소스코드 정보를 기록하기 위함  
- 의미있는 시점의 commit을 태깅한 것  
- ex) rc: release candidate : 배포 예비버전  

 ##### Lightweight 태그)  
 $ git tag {태그명}  
  - 태그명(버전명)만 남기는 태그  

 ##### Annotated 태그)  
 $ git tag -a {태그명} -m {태그메시지}  
 $ git tag -a {태그명} `{기준시점의 커밋ID}` -m {커밋메시지}
  - 태그명(버전명) 외 여러 정보(작성자의 이름, 이메일, 생성날짜, 태그메시지)를 함께 저장한 태그
  - {기준시점의 커밋ID} 옵션 포함하면, 특정 시점의 commit에 태그할 수 있음 (ID는 $git log로 확인 )


 $ git show {태그명}  
  - {태그명} 에 저장된 정보 출력 & 확인
  - `<옵션>
    -ref : 전체 태그의 hash값 확인 가능  `  
    


---  

  
### 협업)  

- Repository 에 멤버 초대  
   - 해당 Repositories > Settings > Collaborators(Members) > E-mail 또는 id로 초대 > 권한범위 지정 > 초대전송  
- 브랜치별 권한 설정  
   - 해당 Repositories > Settings > Branches > protection rule(Protected branch) > 브랜치별 상세권한 설정  

### 브랜치 전략)    
  - 조직/개인마다 다른 브랜치 활용 방식  
  - 조직에 맞게 프로세스화 하는게 중요 (일관적, 생산적)  
  - 다음이 브랜치 기준이 될 수 있음 : feature/개발자/ 스프린트 / 사내검증 등등..  
  - GITHUB의 브랜치 항목에서  
      - Default branch : 메인브랜치    
      - Active branch : 빈번히 사용하고 있는 브랜치  
      - Stable branch : 비교적 오래되어 잘 사용되지 않는 브랜치  DB
   
  #### <브랜치 전략 소개>  
  1) GitFlow : https://nvie.com/posts/a-successful-git-branching-model  
    - 5개 브랜치 (master / develop / feature / release /hotfix)  
    - master = 고객에게 release되는 최종 브랜치  
    - develop = master로부터 분기, 기능 개발 브랜치  
    - release = develop브랜치에서 분기 => `검증/ 이슈 수정` 하는 용도 (수정 후 devlop에 병합)  
    - hotfix = master로부터 분기 (수정 후 master, develop에 모두 반영)
       
    * $ git-flow --help : gitflow 내용 도움말 확인 가능  
    * $ git flow init : gitflow 방식으로 기본 브랜치(develop & master 우선 두개만) 자동생성 + (prefix 규칙 설정) + develop 브랜치로 checkout + initial commit 자동 남김  
    * $ git flow feature start {개발할 기능명} : 'feature/{개발할기능명}' 브랜치 생성 + checkout  
    * $ git flow feature finish {개발한 기능명} : 'feature/{개발한 기능명}' 브랜치를 develop 브랜치로 (merge + checkout) & 삭제  
    * $ git flow release start {버전명} : 'release/{버전명}' 브랜치 생성 + checkout  
    * $ git flow release finish {버전명} : 'release/{버전명}' 브랜치를 master 브랜치로 merge(버전명 포함, 태그 자동생성) + develop브랜치로 merge + 'release/{버전명}' 브랜치 삭제 & develop 브랜치로 checkout  
    * $ git flow hotfix start {이슈번호} : 'hotfix/{이슈번호}' 브랜치 생성 + checkout  
    * $ git flow hotfix finish {이슈번호} : 'hotfix/{이슈번호}' 브랜치를 master 브랜치로 merge(버전명 포함, 태그 자동생성)
  3) ffffff




   
### Cherry-Pick)  
  
  : 다른 브랜치에 있는 commit을 일부만 선택해 내 브랜치에 적용할 때 사용  
$ git checkout {타겟브랜치}  
$ git cherry-pick {commit번호}  
  

