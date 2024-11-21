# github 기초

## github 용도
1. 내 소스코드를 저장 (버전관리)
2. 소스코드 공유
3. 협업하는 공간

# github 사용법
## 1. Repository 생성 : Public or Private
### ...or create a new repository on the command line
```
    echo "# github" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin git@github.com:20eung/github.git
    git push -u origin main
```

### ...or push an existing repository from the command line
```
    git remote add origin git@github.com:20eung/github.git
    git branch -M main
    git push -u origin main
```   

---
# github 설치 및 설정
## 1. git download, 설치

    https://git-scm.com/downloads

## 2. git bash 실행 (환경설정)
```
    git config --global user.name "20eung"            <-- 사용자 영문 이름
    git config --global user.email "20eung@gmail.com" <-- 깃허브 가입시 쓴 이메일
    git config --list                                 <-- 설정이 잘 들어갔나 확인
```
## 3. token 인증 방법 (1)

### GitHub 계정에 SSH 키 추가

### 1. SSH 키 생성

이메일 주소는 GitHub 계정에 연결된 이메일 입력
생성된 SSH 키는 기본적으로 ~/.ssh/id_rsa 와 같은 경로에 저장됨

```
ssh-keygen -t rsa -b 4096 -C "20eung@gmail.com"
```


### 2. SSH 에이전트 시작

```
eval "$(ssh-agent -s)"
```

### 3. SSH 키 추가

```
ssh-add ~/.ssh/id_rsa
```

### 4. SSH 공개 키 복사

출력된 공개키를 클립보드에 복사

```
cat ~/.ssh/id_rsa.pub
```

### 5. GitHub에 SSH 키 추가

#### 1. GitHub에 로그인

#### 2. 우측 상단의 프로필 사진을 클릭한 후 Settings로 이동

#### 3. 좌측 사이드바에서 SSH and GPG keys를 선택

#### 4. New SSH key 버튼을 클릭하고, 제목을 입력한 후 앞에서 복사한 공개 키를 붙여넣기

#### 5. Add SSH key 버튼을 클릭하여 SSH 키를 추가


## 3. token 인증 방법 (2)

#### 1. github 접속, 로그인
https://github.com

#### 2. 우측 상단 사용자 계정 아이콘 눌러 Settings 클릭

#### 3. 좌측 하단 Developer settings 클릭

#### 4. 좌측 메뉴 Personal access tokens 클릭

#### 5. 우측 메뉴 Generate new toke 클릭

#### 6. Note, Expiration 설정 후 Select scopes에서 repo 체크

#### 7. 맨 아래 Generate token 클릭

#### 8. 복사 (반드시!)

#### 9. 로컬 컴퓨터 git 설정에 등록
```
    git config --global user.password '복사한 토큰 붙여넣기'
```

#### 10. 만약 git@github.com: Permission denied (publickey). 에러가 발생한다면
* GitHub 우측 상단 사용자 계정 아이콘 눌러 Settings 클릭
* SSH and GPG key 눌러 SSH keys 의 [ New SSH key] 클릭
* 로컬 컴퓨터의 .ssh/id_rsa.pub 파일 내용을 복사하여 붙여넣기
* 로컬 컴퓨터에서 상태가 정상인지 테스트
```
$ ssh -T git@github.com
Hi 20eung! You've successfully authenticated, but GitHub does not provide shell access.
```

#### 11. 만약 id_rsa.pub 가 없다면 생성하자
```
$ ssh-keygen -t rsa
```

## 4. GitHub 연결 테스트

```
ssh -T git@github.com
```

## 5. GitHub 리포지토리 클론

```
git clone git@github.com:20eung/repository.git
```

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

## 5. 로컬 파일을 수정하고나서 할 일

    $ git add .
    $ git commit -m "second commit"   <-- 히스토리를 만든다. -m은 메시지(message) 의미
    # git push origin master          <-- github repository에 업로드
    
## 6. github 웹사이트 새로고침

---
# 깃허브 협업 방법
## <마스터 계정>
### 1. 신규 프로젝트 생성 - github repository
### 2. VS Code에서 파일 생성, 업로드
## <신입 계정>
### 3. github > Code > ssh download url 복사
### 4. 터미널(cmd창)에서
    C:> git clone 붙여넣기 freshman  <-- 신입 폴더이름
    C:> cd freshman
    C:> code .
### 5. VS Code에서 소스코드 수정
### 6. 터미널 열어서
    $ git add .
    $ git commit -m "freshman first commit"
    $ git checkout -b 'freshman'   <-- 신입 계정을 위한 새로운 공간 생성
    $ git push origin freshman     <-- 신입 계정을 위한 공간에 업로드
    
### 7. github 페이지 새로고침
    freshman had recent pushes less than a minute ago    <-- 메시지 확인
    Compare & pull request         <-- 버튼 클릭

---
### VS Code 소스코드 자동정렬 익스텐션
#### 1. VS Code Extentions > Prettier 다운받아 설치
#### 2. VS Code 소스코드창에서 마우스 오른버튼 눌러 Format Document 클릭
---
출처: 코딩알려주는누나 https://www.youtube.com/watch?v=lelVripbt2M
깃, 깃허브 한번에 이해시켜드리고 포트폴리오 올리는 법까지 알려드림. 15분안에 당신은 Github 전문가가 됩니다
