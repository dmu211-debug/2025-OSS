# 오픈소스소프트웨어(OSS) 원격 수업 04~06 정리

## 04. 깃 설치와 실행

### Git 사이트
- 공식 홈페이지: https://git-scm.com/
- Git 오픈소스 저장소: https://github.com/git/git

---

### CLI 인터페이스

#### 리눅스 기본 명령어
- pwd : 현재 디렉토리 표시
- ls -al : 디렉토리의 모든 파일 상세 리스트

#### Git 기본 명령어
- git --version : 깃 버전 확인
- git config --list : 깃 설정 확인
- git --help : 도움말 확인

---

## 05. 깃 설정과 저장소 생성
### 깃 설정 명령 구조

git config --설정범위 설정변수 설정값

### 설정 범위
- --system : 모든 사용자에게 적용
- --global : 현재 사용자에게만 적용
- --local : 현재 저장소에만 적용

---

### Git 사용자 정보 설정 (예시)
- --git config --global user.name ai7dnn
- --git config --global user.email ai7dnn@gmail.com
- --git config --global init.defaultBranch main
---

### 전역 설정 파일
- --global 옵션 사용 시 `.gitconfig` 파일에 저장  
  (Windows 기준: C:\Users\사용자명\.gitconfig)

---

### 주요 설정 명령
- git config --global core.editor notepad
- git config --get core.editor
- git config --global --edit
- git config --global -e
---

### 줄바꿈(EOL) 설정

플랫폼마다 줄 끝 처리 방식이 다르기 때문에 설정 필요

- Windows : CRLF  
- macOS/Linux : LF

#### 설정 명령
- git config --global core.autocrlf true (Windows 권장)
- git config --global core.autocrlf input (Mac/Linux 권장)
- git config --get core.autocrlf
---

### 줄바꿈 안전 설정(safecrlf)
줄바꿈 충돌 경고 방지 여부 설정

- git config --global core.safecrlf false
- git config --get core.safecrlf
---

### 주요 6가지 기본 설정 (예시)
- git config --global user.name "ai7dnn"
- git config --global user.email "ai7dnn@gmail.com"
- git config --global core.autocrlf true
- git config --global core.safecrlf false
- git config --global core.editor "code --wait"
- git config --global init.defaultBranch main
---

## Git 저장소 생성

### git init
- 현재 디렉토리를 Git 저장소로 만들 때 사용
- git init
### 하위 폴더를 생성하며 저장소 초기화
- git init basic
### Git 저장소 구조
- Git 저장소에는 **.git 폴더**가 반드시 존재
- 모든 버전 기록이 저장되는 핵심 폴더
- .git 삭제 시 버전관리 기능 상실

---

### Git 저장소 생성 명령 예시
- git init basic
- cd basic
- ls -al
---

## 06. 비주얼 스튜디오 코드와 리눅스 명령

## Visual Studio Code

- Microsoft가 개발한 오픈소스 에디터
- Electron 기반
- Windows / macOS / Linux 모두 지원
- JavaScript, TypeScript, Node.js 기본 지원
- 다양한 확장 기능 제공 (VSCode Marketplace)
- 버전 관리(Git) 기능도 지원

### VSCode 설치 버전
1. User Installer  
   - 현재 사용자만 설치 가능
   - 사용자 폴더에 설치됨

2. System Installer (권장)  
   - PC의 모든 사용자가 사용 가능  
   - 설치 위치: C:\Program Files\Microsoft VS Code

---

## 리눅스 명령 정리

### 폴더 관련 명령
- pwd 현재 폴더 표시
- cd 폴더 이동
- -mkdir dname 새 폴더 생성
- ls 파일 목록 표시
- ls -l 상세 정보
- ls -a 숨김 파일 포함
- ls -al 상세 + 숨김 파일 모두 표시
---

### 파일 관련 명령
- touch fname 빈 파일 생성
- echo 문자열 문자열 출력
- echo 'print()' 특수문자 포함 문자열 출력
- cat fname 파일 내용 출력
- cp a b 파일 a를 b로 복사
- mv f1 f2 파일 이름 변경

---

### 파일 및 폴더 삭제
- rm fname 파일 삭제
- rm -rf dname 폴더 및 내부 파일 강제 삭제
옵션
- -f : 강제 삭제
- -r : 폴더 내부 전체 삭제

---

### ls 명령 종류
- ls -l 상세 목록
- ls -a 숨김 파일 표시
- ls -t 최근 생성 순 정렬
- ls -rt 오래된 순 정렬
- ls -f 파일 종류 표시 ('/'=폴더, '*'=실행파일, '@'=링크)
---

### cat 명령 조합
- cat file1
- cat file1 file2
- cat file1 file2 | more (페이지 단위 출력)
- cat file1 file2 | head (앞 10줄)
- cat file1 file2 | tail (마지막 10줄)
---

### Redirection(리다이렉션)
파일 내용을 새로 저장 (덮어쓰기)

기존 내용 뒤에 추가
< 파일의 내용을 입력으로 사용


예시
- echo aaa > a.txt
- cat file1 file2 > file3
- echo bbb >> a.txt
- cat file4 >> file3
---

### Git 저장소 삭제
rm -rf .git
- .git 삭제 시 해당 폴더는 더 이상 Git 저장소가 아님
