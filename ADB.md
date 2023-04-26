### ADB  
  
  : Android Debug Bridge (안드로이드 디버그 브리지)  
  - 안드로이드 기반 기기들의 디버깅에 사용되는 프로그래밍 도구  
  
    * (안드로이드 장치의 *데몬* + USB or TCP 통신 + 호스트 PC의 서버) 형태로 연결  
    * 구글 오픈소스 SW  (Apache 라이센스)  
    * 윈도우, 리눅스, mac OS 와 호환   

$ adb root                                    // adb 권한 부여   
$ adb shell                                   // 타겟에 접속  
$ adb devices                                 // adb연결된 타겟 디바이스 표시    
$ adb push {파일명} {push할 타겟의 위치}        // 로컬 -> 타겟 파일 전송  
$ adb pull {pull할 로컬의 위치} {파일명}        // 타겟 -> 로컬 파일 전송  
