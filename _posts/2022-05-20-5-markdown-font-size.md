---
published: true
layout: post
title: Markdown font size
description: Markdown font size code
image:
categories: [markdown tips]
tags: [github, git_blog, githubio, markdown, md, post, markdown tips]
---

This is default size.<br>

<font size = 4> \<font size = 4> </font>

** '\\' 는 코드에 쓰이는 것들이 문자로 쓰이게 해줌.


<font color='red'> \<font color = 'red'> </font> <br>

<font size = 4, color = 'Yellow'> size = 4, color = 'Yellow'</font> <br>

<font face = '돋움'> face = '돋움 적용됨' </font> <br>
<font face = '궁서'> face = '궁서 적용됨' </font> <br>
<font face = 'serif'> face = 'serif 적용됨' </font> <br>
<font face = 'Helvetica'> face = 'Helvetica 적용됨' </font> <br>


<br>


<p><font size = 4; color = 'Orange'; face = 'serif'> p_tag)) font_tag)) size = 4; color = 'Orange'; face = 'serif' </font></p> <br>



<font face = 'Nanum Gothic'>Nanum Gothic</font> <br>


<span style = 'font-family : 굴림'>굴림 적용됨</span> <br>
<span style = 'font-family : 바탕'>바탕 적용됨</span> <br>
<span style = 'font-family : serif'>serif 적용됨</span> <br>
<span style = 'font-family : sans-serif'>sans-serif</span> <br>
<span style = 'font-family : FANTASY'>FANTASY 적용됨, 소문자 가능</span> <br>
<span style = 'font-family : cursive'>cursive 적용됨</span> <br>
<span style = 'font-family : monospace'>monospace 적용됨</span> <br>
<span style = 'font-family : verdana'>verdana 적용됨</span> <br>

<span style = 'font-family : Nanum Gothic;'>Nanum Gothic</span> <br>
<span style = 'font-family : Hanna;'>Hanna</span> <br>
<span style = 'font-family : Jeju Gothic'>Jeju Gothic</span> <br>
<span style = 'font-family : 새굴림'>새굴림</span> <br>
<span style = 'font-family : Arial'>Arial 적용됨</span> <br>

<span style = 'font-family : 나눔스퀘어'>나눔스퀘어??????</span> <br>

<br>

<br>

[참고1 font coloring도 font 태그로 가능](https://klahan.tistory.com/59) <br>
[참고2 굵기, 캡션, 줄간격..., 폰트도 존재](https://ojji.wayful.com/2015/03/HTML-How-to--Set-FONT-Size-Color-Weight-Family-Variant-Line-Height-ect.html) <br>
[참고3 폰트 여럿 span 태그 방식 외에 새로운 폰트 정의하고 싶을 때 사용하는 @font-face](https://unikys.tistory.com/275) <br>
[참고4 폰트 정의하기, woff는 웹폰트, ttf는 true type](https://moo-you.tistory.com/294) <br>
<br>

>> font-family는 해당 폰트가 사용자의 웹에 있다면 우선순위로 사용하게끔 폰트 나열한 것
<br>
<br>

@font-face {
    font-family: '나눔스퀘어';
    src: url('fonts/NANUMSQUARE_ACR.TTF') format('truetype');
} p {
    font-family: 나눔스퀘어;
    }

blabla<br>



[참고2.5 font의 weight](https://mygumi.tistory.com/205)