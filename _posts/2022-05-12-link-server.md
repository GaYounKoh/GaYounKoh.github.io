---
layout: post
title: 서버연결
description: tutorial
image:
categories: [tutorial]
tags: [server, linux, terminal, github, git_blog, githubio, markdown, md, post, guri]
---

# [서버 - git 연결 과정]
1. 확장에서 ssh 검색해서 설치 (파란색,,,)
2. 좌측 아래 초록색 버튼 클릭
3. Connect to SSH 클릭
4. Linux 선택
5. continue (해당 pc에서 처음 켤 때만 선택)
6. 서버 비번 입력
7. Open Folder (/project 혹은 /project/kelly 선택)
8. 비번입력
~~9. 서버에 git 전용 폴더 생성 (에러방지 위해 전용폴더 이름은 영어로)~~ 이렇게 하면 폴더 안에 repo 폴더 또 생성됨
10. 연결할 repo 새로 생성
11. ctrl+` 해서 터미널 열고 
12. cd / ........ ~~생성한 전용폴더로 경로 변경~~ 내 폴더로 경로 변경
13. 명령어 [git clone 클론한 레포 주소]
14. 명령어 [git init] ;;;(.git 폴더 (숨겨져있음) 생성하는 코드, 클론 하면 자동 생김.)

## [.git 폴더 보이게 설정하기] <br>
1. ctrl + shift + p 해서 명령팔레트 열어서 settings 검색해서 preferrence open user settings 들어가기
2. 검색창에 exclude 검색
3. exclude 배너에서 .git 찾아서 삭제 (포함하겠단 의미)

### clone한 repo 폴더 위치 맘껏 이동해도 됨.