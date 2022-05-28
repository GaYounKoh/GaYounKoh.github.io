---
published: true
layout: post
title: 시나리오를 통해 github organization 알아보기
description: github organization
image:
categories: [github tips]
tags: [github, git_blog, githubio, git, git_organization]
---

[[git] github에서 협력하여 작업해보자 (organization)](https://coding-hwije.tistory.com/37) <br>
[위의 블로그가 참고한 듯한 블로그](https://victorydntmd.tistory.com/91) <br>

## organization이란?
: 여러 명이 같은 프로젝트를 관리하는데 사용하는 그룹계정, <br>
사람들을 서브그룹으로 나누어 관리할 수 있음. <br>


## 계정만들기
로그인 후 우측 상단 +를 눌러 organization을 만들 수 있음.

## 팀원 추가
View organization -> People 탭 -> Invite member -> 초대할 멤버의 email 입력 -> 수락

## 운영
여기에 repo를 만든다면 공동계정(organization)에 작업공간(repository)를 만든 것

## 작업에 필요한 주요 커맨드 (시나리오를 통해서)
1. 멤버 A가 최초로 작업 시작 : 기존 업로드 방식과 같음.
```bash
git init                        # git 폴더 생성
git add .                       # 모두 stage에 올림
git commit -m '커밋메세지'      # 커밋
git remote add origin 깃헙주소  # origin 만들기
git push origin master          # push

```

2. 멤버 B는 프로젝트 파일을 받아와야 함.
```bash
git clone 깃헙주소
```

현재 위치한 경로에 폴더가 생김.
이제 이 경로에서 작업 시작.

3. 멤버 B는 branch를 사용해 <span style = 'color:red'>***독립적으로***</span> 작업을 진행해야 함.
```bash
git branch 브랜치1              # 브랜치 생성
```

4. branch 작업 -> master와 merge -> push 순서로!!!
```bash
git checkout 브랜치1            # 이동
git add .
git commit -m '~~ 부분 추가'    # 브랜치 커밋

git checkout master             # master 브랜치로 이동
git merge 브랜치1               # master를 브랜치1과 합치기
git push origin master          # push
```

[지금까지의 process를 정리해보자면]
* A가 main repo를 만들고, 그 아래 branch 생성 후 그 곳에서 작업.
* B는 branch를 생성, 그 곳에서 작업.
* 작업이 끝났다면 main과 branch를 merge & git에 push

여러 명이 작업하다가 push를 함부로 하다보면 <span style = 'color:red'>***충돌***</span>이 일어나는데, <br>
> * 충돌: 같은 곳 수정하고 push했을 때 발생하는 에러 같은... <br>

혼자 작업하다가 발생하는 충돌도 끔찍한데 다같이 작업하다 발생하는 충돌이라니... 상상도 하기 싫다. <br>
branch에서 commit 해준 후 원래의 main과 합치고 push. <br>
이렇게 하면 충돌이 일어날 때 대처가 쉬울 것...이라는 작성자님의 전언. <br>

5. A와 B가 같은 소스로 작업중일 때 <br>
A가 푸시를 했다면 <br>
B는 <u>**구버전**</u>을 사용중이라 <span style = 'color:red'>***최신 소스***</span>를 받아야 함.

```bash
git checkout master             # 마스터로 이동
git pull                        # 최신 소스 가져오기

git checkout 브랜치1            # 브랜치1로 이동
git merge master                # 마스터와 합치기

# 마스터에서 최신 소스를 받고, 머지 후 깃에 올리기 
```

[5번 내용 정리] <br>
A가 git에 푸시를 한다면 B는 pull을 하고 B 자신의 branch와 merge후 작업. <br>
작업 후엔 merge, merge 후엔 push <br>

merge시 충돌이 발생할 수 있음. <br>
HEAD 영역이 현재 브랜치, 그 아래가 충돌되는 부분 <br>
(자세한 이미지는 상단에 올려둔 참고한 블로그를 통해 확인) <br>
충돌되는 부분은 상의 후 수동으로 변경하면 됨. <br>
소통이 중요하다는 작성자님의 전언... <br>
<br>
<br>

6. [브랜치2]에서 작업한 것에 대해 이전 버전으로 돌아가기 - [두 번째 링크](https://victorydntmd.tistory.com/91) 참고<br>
이전 버전으로 돌아가려는 이유는 다양할텐데 일단 작성자님은 테스트 도중 버그가 발생한 경우를 언급해주셨음. <br>
멤버 C가 버전을 local repo에서만 관리했다면 <span style = 'color:red'>***reset, revert 명령어 둘 중 하나***</span>를 사용할 수 있는데, push를 해서 git에 올라간 상황이라면 <span style = 'color:red'>***revert만***</span> 사용할 수 있음. <br>
> * 로컬레포란: git에 올리기 전 (push 전)인 vscode에서의 상태같은.... <br>
<br>

작성자님은 이미 push를 해버려서 git에 올라간 상황일 때를 예로 들어주심. <br>
commit 이력을 통해 에러가 발생하기 이전 지점을 찾아보도록 함. <br>

[commit 이력 확인 방법]
```bash
git log --online -10
```

[이전 버전으로 돌아가는 방법]
```bash
git revert 커밋번호
```

> * 커밋 메세지를 잘 작성해놔야 하는 이유: 어느 버전으로 갈지 쉽게 선택하기 위함.

이렇게 돌아가게 됐을 때 C의 브랜치에서 충돌이 발생할 수도 있는데
이 때 돌아간 버전에 없는 코드 부분은 지움으로써 <span style = 'color:red'>***이전 버전***</span>으로 돌아감.


* 이전 버전으로 돌아간 이력을 커밋메세지를 통해 남기는게 좋음.

```bash
git add .
git commit -m '~~~~버전으로 백업'
git push origin 브랜치2
```