### SCP  
  
  : Secure CoPy 
  - `ssh` 원격 접속 프로토콜을 기반으로 한 파일 송수신 프로토콜  
  - 리눅스 기반 운영체제에서 사용   
  
### Local -> Remote  
$ scp {옵션} [파일명] [원격id]@[원격IP]:[받는 디렉토리 위치]  
$ scp test.txt root@192.168.200.129:/home/download  
  
  
### Remote -> Local  
$ scp {옵션} [원격id]@[원격IP]:[파일명] [받는 loacal 디렉토리 위치]  
$ scp root@192.168.200.129:/home/download/test.txt /tmp  
