---
published: true
layout: post
title: github branch 초기설정? 외 
description: github branch
image:
categories: [github logs]
tags: [github, git_blog, githubio, git, git_organization]
---

[github 협업 명령어 총정리](https://velog.io/@tami/git-hub-%EB%A1%9C-pull-request-%ED%95%98%EB%8A%94-%EB%B2%95) <br>

# 1. 시작 전 (완전 처음일 때)에 충돌방지를 위해 각자의 branch를 생성 해줍니다. <br>

코드로 하는 브랜치 생성 방법은 다음과 같습니다. <br>
VS Code의 터미널에서
```
git branch 브랜치네임   # 브랜치 생성
git checkout 브랜치네임 # 브랜치로 이동
```
을 입력하여 생성하거나... github의 repo 페이지에서 생성이 가능하다면 거기서 생성... 후 이동 <br>
<br>

> 가능하길래 가져왔습니다.<br>
branch 바꾸는 박스를 눌러서 (find or create a branch가 적혀있는) 입력박스에 원하는 브랜치 네임을 입력 후 아래 생긴 create 버튼을 누름으로써 새로운 브랜치를 생성한다. <br>
[참고](https://redcow77.tistory.com/438) <br>
<br>

+ 코드로 브랜치 생성 후에는 아래의 코드를 통해 초기 설정(?)이 필요합니다.
```
git push --set-upstream origin 브랜치네임
# 참고로 이 코드는 해당 브랜치로 checkout한 상태가 아니어도 되더랍니다.
```

# 2. 작업 시작 전에는 무조건 pull을 해서 최신 소스를 불러와야한다.
코드로는
```
git pull
```
<br>
버튼방식으로는<br>
VS Code의 소스제어 탭의 ...에서 버튼으로 pull할 수 있음. <br>
<br>

해당 작업을 하지않으면 작업간 충돌이 발생할 수 있다.

* 작업 시작 전에 pull 뿐만 아니라 main브랜치와 merge도 해야 하는 것 같다. <br>
<br>

내 브랜치인 상태에서 (이미 <git checkout 브랜치> 를 한 상태에서)
```
git merge main
```
을 입력함으로써 main의 내용을 불러오도록 한다. <br>

* merge는 내가 병합을 시켜주고자 하는 브랜치B에서(<git checkout 브랜치B>인 상태에서) <git merge 병합하고자 하는 내용이 있는 브랜치A>를 하면 됨.
<br>


[git default remote, branch 설정](https://blog.leocat.kr/notes/2016/01/21/git-config-default-remote-branch) <br>
<br>

### --- 이상 git branch 생성 후 초기 설정 ---