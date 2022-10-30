# Git


# Git
:  버전관리 도구. 리눅스토발즈가 개발.
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
 ex) CVS, SVN

# DVCS(Distributed Version Control System)
 : 분산집중형 버전관리 
 - 원격서버에서, 로컬저장소로 복사해오기 가능
 - 네트워크 끊겨도 작업 가능 
 - 개인적 빌드 확인 가능 
 - 원격 서버의 소스코드 손실해도 복구 가능   
 ex) Git, Mercurial

# Git 설치
 - https://git-scm.com [로컬]
 - https://github.com [원격]
 * https://github.com/trending 에서 제일 인기있는 repo 확인가능 ***
 - https://about.gitlab.com [깃랩] 
 * 깃랩은 private저장소도 무료 

# Git 사용 
 * CLI : (Command Line Interface)  
 'Git Bash'프로그램에서 명령어 입력
 
# Git 구성 
![다운로드](https://user-images.githubusercontent.com/67628725/197425206-c2b76d8d-d045-4f63-979d-8eaa159e4557.png)  

 *작업디렉토리(Working Directory)	: git에서 관리 o 추적 x  
 *스테이징영역(Staging Area)		: git에서 변경점 추적 o, commit준비영역, 작업한 내용물의 임시저장영역  
 *로컬저장소(Local Repository)	: commit이 영구적으로 저장되는 영역   
 *원격저장소(Remote Repository)	:  
 *클론(Clone)			: 원격저장소 -> 로컬저장소로 코드 가져오기   
 *커밋(Commit)			: git에서 가장 의미있는 '변경의 단위', (변경점을 local저장소에 저장하는 행위.)   
 *풀(Pull)				: 원격저장소에 있는 다른 개발자의 commit을 받아옴 (최신 업데이트)  
 *푸시(Push)			: 로컬저장소에 있는 내 commit을 원격저장소로 업데이트 함   

# Git 기본플로우
 1. 원격저장소의 소스코드 -> 로컬저장소로 다운로드 [clone]
 2. 작업디렉토리에서 작업, 소스코드 수정
 3. 작업한 내용 '스테이지 영역'에 추가 [add]
 4. 의미있는 변경점이 쌓이면 커밋 [commit]
 5. 로컬저장소에 영구적으로 저장 
 6. 원격저장소에 업데이트된 다른 개발자의 커밋 받아옴 [pull]
 7. 최신업데이트 해서 충돌을 없앤 후, 
 8. 로컬저장소에 저장된 내 commit을 원격저장소에 반영함 [push]
 


# Git 기본 환경설정  
git정보등록)  
 $ git config --global user.name "이름"	chl: 이름 등록  
 $ git config --global user.email "이메일주소"	: 이메일 등록  
 $ git config --global core.editor vim		: 기본에디터(vim) 설정  
 $ git config --global --list			: git기본 등록정보 확인   
 => 모든 정보는 [.gitconfig] 파일에 저장됨. 즉 이를 수정함으로써 설정내용 수정 가능   
 $ vi ~/.gitconfig  
 
 
저장소생성하는 두가지 방법)  
1. clone 하기    
2. 로컬저장소 생성 -> 초기화(git init) -> 원격저장소 연결(git remote add)  
  
워킹디렉토리 생성)  
 $ mkdir {디렉토리명}				: 워킹디렉토리 생성  
 $ git init				: '.git' 폴더 생성 + master기본브랜치 생성  
{.git 폴더 내부 ls-al 명령어 친 후 구조 사진.jpg}				=> 변경되는 파일을 추적/관리할 수 있게 하는 파일  
				워킹디렉토리의 두가지 파일상태)  
    1. Untracked 				: 변경사항은 있으나, 한번도 staging area에 포함되지 않아 git에 의해 관리되지 않은 파일  
    2. Tracked				: staging area에 한번 이상 포함되어 git에 의해 관리되는 파일  
      
원격저장소와 연결)  
 $ git remote add {저장소 별칭} {저장소 주소}				: 원격-로컬 연결 (저장소 별칭 ex_default, origin)  
 $ git remote -v				: 로컬에 연결된 원격저장소 주소 확인 => fetch랑 push 브랜치 두개 생기던데 뭐임????  
 
  
# Git 명령어 정리
 $ git --version	버전 확인   
 $ clear		명령창 clean

파일작성)   
 $ vi {파일명} 				: 파일 열기   
 ESC버튼 + wq입력 후 enter			: 파일 저장후 닫기 (w:저장, q:닫기)  
 $ ~/					: 루트 디렉토리 의미  
 $ mkdir	{파일명}				: 폴더 생성    
 $ cd {디렉토리경로}			: 해당 경로로 이동  
 
 git확인)  
  $ git status 				: 현재 폴더 내, 파일의 상태(브랜치, 커밋, 스테이징 등) 확인  
  $ git log				: 커밋의 히스토리 확인  
  								<히스토리 구성>  
          - commit 커밋id => SHA1 해시알고리즘으로 커밋id만듦  
          - Author: 작성자  
          - Date: 커밋날짜  
            
          <git log 옵션>  
          --help				: 해당 명령어의 매뉴얼 페이지 생성  
          -u 				: git diff + log => 커밋히스토리와 함께 각 커밋에서의 코드 변경내용을 보여줌  
          -u {commit ID}				: 입력한 {commit ID}의 내용 + 코드변경내용  
          				= $ git show {commit ID}와 같은 명령어
          -{숫자n}				: 최신 n개만큼의 커밋내용 표출  
          --name-only				: 커밋히스토리의 '변경된 파일명'까지 보게됨
          --oneline				: 커밋을 간결하게 한줄로만 표시  
            
 git동작)																												* 변경점 = 코드의 변경사항을 의미    
  $ git add {파일명}																				: 스테이징 영역에 변경점 올림  
  				*경고발생  
      warning: in the working copy of 'test.java', LF will be replaced by CRLF the next time Git touches it  
      위같은 에러가 뜬다면, 다음 명령어로 에러를 무시할 수 있음  
      $ git config --global core.safecrlf false  
  $ git commit																				:스테이징(add)된 변경사항들을 commit  
  				git commit할 시, editor창이 뜨는데, 커밋메시지를 입력하는 곳이다.  
      'i' 누른 후 입력 후 저장. (#주석처리 된 줄은 메시지로 안들어감)  
  $ git commit -m "{커밋메시지}"  				: 커밋메시지와 함께 바로 commit  
  $ git diff  				: '워킹 디렉토리'에서, 변경사항(코드) 확인.  
   				- 보기 힘들기 때문에 간단한 변경 or 변경점 적은 경우에만 사용  
       - 변경점이 스테이징 되어있지 않더라도, 이전에 한번 staging영역에 올라온 파일은 git에 의해 관리되기 때문에 확인 가능  
         
  commit 되돌리기1 - 복구 X)  
   $ git commit --amend   
    	- 마지막 반영한 최신 '커밋메시지'를 변경하고 싶을 때 -> 최신 커밋 수정가능한 에디터 실행됨  
        - 되돌린 커밋은 절대 복구할 수 없음 !!! ***  
  commit 되돌리기2 - 복구 O, roll-back)   
   $ git revert {마지막에 반영한 commit ID}   
   	- 변경 취소 & 반영한 커밋 되돌리기 가능  
   	- 커밋히스토리를 유지하며, 내용만 롤백    
	- 즉, commit을 취소한 내용의 commit이 하나 추가로 더 생김   
	- 되돌린 커밋은 새로운 파일로 저장되어 코드 원복이 가능함   
	
git 원격 저장소에 반영)	
   $ git push {원격저장소 별칭} {현재로컬브랜치}  
   	: 원격 저장소에 commit 반영(push)  
		- {저장소 별칭} : $ git remote -v 실행 시, 제일 처음에 뜨는 이름 
			origin  https://gitlab.com/ys26/TEST.git (fetch) 에서 origin. ???? origin 이 뭐 가리키더라 ??(위에서 설정한 원격저장소 주소의 별칭임)
		- {현재 브랜치} : 로컬 디렉토리에서 현재 있는 브랜치 (git bash 에 괄호치고 써 있음)
		- 이후 창 뜨면 아이디/비번 누르고 들어가기 


  
 
 



















