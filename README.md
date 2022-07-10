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

출처: 코딩알려주는누나 https://www.youtube.com/watch?v=lelVripbt2M
깃, 깃허브 한번에 이해시켜드리고 포트폴리오 올리는 법까지 알려드림. 15분안에 당신은 Github 전문가가 됩니다
