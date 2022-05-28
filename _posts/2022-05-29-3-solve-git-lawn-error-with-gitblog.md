---
published: true
layout: post
title: git blog와 잔디밭 에러 (원인 파악 끝)
description: git blog와 잔디밭 에러
image:
categories: [github]
tags: [github, git_blog, githubio, lawn, error]
---

[1. github 잔디가 심어지지 않아요!](https://pongsoyun.tistory.com/122) <br>
[2. git 잔디가 안심기는 이유](https://kimmy100b.github.io/git/2020/08/14/git/) <br>
[3. github 잔디심기 오류 해결하기](https://txegg.tistory.com/107) <br>
<br>

[1-1. git branch 생성하기](https://for-it-study.tistory.com/53) <br>
<br>

일단 나의 경우 gh-pages라는 이름의 브랜치만 있고 master가 없어서 그걸 생성해주도록 해보자. <br>
==> 결국 해결이 안됐다. <br>
<br>

# [2.]에서 이유 확인...
독립형 저장소가 아니라 <span style = 'color : red'>***fork***</span>로 이뤄져있다면 <u>잔디밭에 연동이 안된다.</u>
전에 김수에게 들었었는데 또 까먹음...
아마 내가 놓친 두 번 중 한 번은 이거 때문에 방심하고 놓쳤던 게 아니었을까하는 생각이....