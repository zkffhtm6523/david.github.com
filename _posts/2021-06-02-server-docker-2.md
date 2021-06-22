---
title:  "Docker"
author: David
date:   2021-06-22 23:10:29 +0900
categories: [Server, Docker]
math: true
viewer: true
tags: [Server, Docker]
image:
  src: /blog-assets/title/Tool_Wide_Img/Docker.png?raw=true
  alt: Docker
---

# Docker 명령어 정리

```shell
# docker 이미지 목록
docker images

# docker 이미지 삭제
docker rmi python:latest # 파이썬 최근 이미지 삭제

# docker 프로세스 목록
docker ps

# docker container 삭제(기동중 or 중지 모두)

# 삭제
docker rm "container ID"

# 강제 삭제
docker rm -f "container ID"

# docker container 시동(최근에 사용한 것이 없으면 dockerhub에서 가져옴)
docker run -it python:3.8.5 # -it 옵션을 통해서 파이썬 콘솔 즉시 진입

# docker container 중지
docker stop "container ID"

# docker container 접속 -> 구동되고 있지만 접속은 되어 있지 않을 때
docker attach "container ID"

# docker container 중지 없이 나가기
Ctrl+p -> Ctrl+q

# docker 외부에서 docker container 내부 명령어 실행
# /bin/bash로 실행되는 것이기에 echo 명령어가 먹는다
docker exec dff2 echo "hello"

# docker container 변경 내역 확인
docker diff "container ID"
```
