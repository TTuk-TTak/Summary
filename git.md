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
{git의 이해.png}
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
 -----------------------------------------
 6. 원격저장소에 업데이트된 다른 개발자의 커밋 받아옴 [pull]
 7. 최신업데이트 해서 충돌을 없앤 후, 
 8. 로컬저장소에 저장된 내 commit을 원격저장소에 반영함 [push]
 


# Git 기본 환경설정 
 $ git config --global user.name "이름"	chl: 이름 등록
 $ git config --global user.email "이메일주소"	: 이메일 등록
 $ git config --global core.editor vim		: 기본에디터(vim) 설정
 $ git config --global --list			: git기본 등록정보 확인 
 => 모든 정보는 [.gitconfig] 파일에 저장됨. 즉 이를 수정함으로써 설정내용 수정 가능 
 $ vi ~/.gitconfig

# Git 명령어 정리
 $ git --version	버전 확인 
 $ clear		명령창 clean

파일작성) 
 $ vi {파일명} 				: 파일 열기 
 ESC버튼 + wq입력 후 enter			: 파일 저장후 닫기 (w:저장, q:닫기)
 $ ~/					: 루트 디렉토리 의미			
 $ mkdir	{파일명}				: 폴더 생성
 $ cd {디렉토리경로}			: 해당 경로로 이동 
 
 



















