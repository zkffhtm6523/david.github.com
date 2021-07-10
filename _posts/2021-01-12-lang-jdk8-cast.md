---
title:  Java_형변환
author: David
date:   2021-01-12 23:10:29 +0900
categories: [Programming, Java]
math: true
viewer: true
tags: [Java]
image:
  src: /blog-assets/title/Tool_Wide_Img/java_image.webp?raw=true
  alt: Java
---

# 1. 묵시적 형변환
> 자동 형변환이라고도 하며
별도의 설정 없이 작은 데이터 타입 -> 큰 데이터타입으로 변환시에 사용됨

![images](https://media.vlpt.us/images/zkffhtm6523/post/529c3771-197a-4eba-b63b-923095fde5f2/image.png)

> int가 4바이트, double가 8바이트
int의 값은 데이터 손실 없이 자동으로 형변환할 수 있다

**아래의 값을 출력하면**

![images](https://media.vlpt.us/images/zkffhtm6523/post/0b5579d0-a91f-43e2-8dad-a153f4435c60/image.png)

# 2. 명시적 형변환
> 강제 형변환이라고도 하며 형변환 타입을 명시해줌으로써

> **큰 데이터타입 -> 작은 데이터 타입**
으로 변환 시에 사용할 수 있음

![images](https://media.vlpt.us/images/zkffhtm6523/post/1401a370-1c55-4026-88b8-a05d7042c4b8/image.png)

> 명시적 형변환은 데이터의 크기에 상관 없이 사용할 수 있다. 하지만 큰 데이터타입 -> 작은 데이터 타입의 경우를 살펴보자.

![images](https://media.vlpt.us/images/zkffhtm6523/post/368359c9-a33c-4453-93cf-c39c87fb646c/image.png)

> double e의 변수에는 11.5라는 값을 담아줬다. (int)e라는 명시적 형변환을 통해서 소수점이 날라간 11이라는 값이 f에 저장되고 출력되었다.

**즉, 큰 데이터 타입에서 작은 데이터 타입으로 형변환이 일어나는 경우 자료의 손실이 일어날 수 있다.**

# 3. 최근 추세
> 개발자로서 프로젝트 진행 시, 묵시적 형변환을 통한 에러가 빈번하게 일어난다고 한다. 가독성 및 에러 방지 차원에서 형변환 시 형변환 타입을 명시해주는 습관을 길러야겠다!
