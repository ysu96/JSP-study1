Install JAVA in window10
=========================
### 1. 자바 개발 도구 JDK 설치
  * www.oracle.com

### 2. 환경변수 설정
  * 제어판 - 시스템 및 보안 - 시스템 - 고급 시스템 설정
  * 환경 변수 - 시스템 변수 새로만들기
  * 변수 이름 : JAVA_HOME, 변수 값 : C:\Program Files\Java\jdk-15.0.1 (jdk 설치경로)
  * Path 환경변수 편집 - 새로 만들기
  * %JAVA_HOME%\bin; 추가
  
### 3. 설치 확인
  * javac -version
    * 오류 시 JAVA_HOME, Path 환경 변수 다시 수정
    

Install Intellij
=========================
### https://www.jetbrains.com/idea/download/#section=windows
