# github 기초

## github 용도
1. 내 소스코드를 저장 (버전관리)
2. 소스코드 공유
3. 협업하는 공간

# github 사용법
## 1. Repository 생성 : Public or Private
### ...or create a new repository on the command line

    echo "# github" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin git@github.com:20eung/github.git
    git push -u origin main


### ...or push an existing repository from the command line

    git remote add origin git@github.com:20eung/github.git
    git branch -M main
    git push -u origin main
    
---
# github 설치 및 설정
## 1. git download, 설치

    https://git-scm.com/downloads

## 2. git bash 실행 (환경설정)

    git config --global user.name "20eung"            <-- 사용자 영문 이름
    git config --global user.email "20eung@gmail.com" <-- 깃허브 가입시 쓴 이메일
    git config --list                                 <-- 설정이 잘 들어갔나 확인

---
# VS Code를 이용하여 컴퓨터 로컬 파일을 github에 올리기
## 1. VS Code 실행
## 2. Terminal > New Terminal 클릭
## 3. Terminal 창에 git init 부터 실행

    $ git init
    $ git add .       <-- 전체 파일 올릴 때
    $ git index.html  <-- 특정 파일만 올릴 때
    $ git status      <-- 상태 확인해볼 때
    $ git commit -m "first commit"  <-- commit 은 히스토리를 만들어주는 행위
    $ git remote add origin git@github.com:20eung/github.git  <-- github 레파지토리와 연결고리 생성
    $ git remote -v   <-- 연결고리 생성된 것 확인
    $ git push origin master        <-- github에 업로드
    
## 4. github 웹사이트 새로고침

출처: 코딩알려주는누나 https://www.youtube.com/watch?v=lelVripbt2M
깃, 깃허브 한번에 이해시켜드리고 포트폴리오 올리는 법까지 알려드림. 15분안에 당신은 Github 전문가가 됩니다
