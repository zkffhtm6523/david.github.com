---
title:  "Linux Curl"
author: David
date: 2021-07-12 23:10:29 +0900
categories: [Linux, 명령어]
math: true
viewer: true
tags: [curl, linux, ubuntu]
image:
  src: /blog-assets/title/Tool_Wide_Img/ubuntu_logo.jpg?raw=true
  alt: Docker
---

# 리눅스 CURL : 웹 요청 명령어

>- CURL은 command line 기반의 웹 요청 도구 
>- Unix, Linux, Windows 등의 주요 OS에서 구동 가능
>- HTTP / HTTPS / FTP / LDAP / SCP / TELNET / SMTP / POP3 등 핵심 프로코콜을 지원
>- download & upload 모두 가능
> 

```shell
# curl 명령어
curl [options] <url> 
```

|short|long|설명|
|:------:|:------:|:---:|
|-k|--insecure          |https 사이트를 SSL certificate 검증없이 연결한다.|
|-l|--head              |HTTP header 만 보여주고 content 는 표시하지 않는다|
|-D|--dump-header <file>|<file> 에 HTTP header 를 기록한다.	|
|-L|--location          |서버에서 HTTP 301 이나 HTTP 302 응답이 왔을 경우 redirection URL 로 따라간다. --max-redirs 뒤에 숫자로 redirection 을 몇 번 따라갈지 지정할 수 있다.기본 값은 50이다|
|-d|--data              |HTTP Post data|
|-v|--verbose           |동작하면서 자세한 옵션을 출력한다.|
|-J|--remote-header-name|어떤 웹서비스는 파일 다운로드시 Content-Disposition Header 를 파싱해야 정확한 파일이름을 알 수 있을 경우가 있다. -J 옵션을 주면 헤더에 있는 파일 이름으로 저장한다.|
|-o|--output File       |	curl 은 remote 에서 받아온 데이타를 기본적으로는 콘솔에 출력한다. -o 옵션 뒤에 FILE 을 적어주면 해당 FILE 로 저장한다. (download 시 유용)|
|-O|--remote-name       |file 저장시 remote 의 file 이름으로 저장한다. -o 옵션보다 편리하다.|
|-s|--slient            |정숙 모드. 진행 내역이나 메시지등을 출력하지 않는다. -o 옵션으로 remote data 도 /dev/null 로 보내면 결과물도 출력되지 않는다|