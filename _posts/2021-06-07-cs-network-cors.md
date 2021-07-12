---
title:  "CORS & SOP"
author: David
date:   2021-06-07 22:10:29 +0900
categories: [Computer-Science, Network]
math: true
viewer: true
tags: [CORS, SOP]
image:
  src: /blog-assets/title/Tool_Wide_Img/Network.jpg?raw=true
  alt: Network
---

# CORS란?
> **CORS** : Cross-Origin Resource Sharing(교차 출처 자원 공유)  

### 1. 출처(Origin)란?
>![image](https://user-images.githubusercontent.com/66704969/121032115-efd3b780-c7e5-11eb-8ec2-f4c1c15f0293.png)
Javascript에서 **console.log(location.origin)** 입력하면 출처가 출력

### 2. SOP란?
>**SOP(Same-Origin Policy)** : 동일 출처 정책  

### 3. CORS VS SOP
> https://taggle.kr 
> https://taggle.kr/bookmark (O) 
> https://taggle.kr:443/bookmarks?page=1 (O) 
> http://taggle.kr (X) 
> https://api.taggle.kr (X) 
> https://taggle.kr:8080 (O & X)_IE만 다르게 취급함    

### 4. CORS & SOP가 나오게 된 이유
> **- SOP 등장 이유**
 : 예를 들어 이 정책이 없다는 것은? 그냥 아무나,누구나 내 도메인 서버에 와서 자원을 가져 갈 수 있는 것이다. 그렇다는건 비밀번호를 가로채는 스크립트를 만들어 자원을 쉽게 빼 갈 수 있다는 뜻이 된다.
>
> **조건 : 프로토콜, 호스트명, 포트가같아야만 자원을 주고 받을 수 있다.**

> **- CORS 등장 이유**
 웹 브라우저에서 외부 도메인 서버와 통신하기 위한 방식을 표준화한 스펙이다. 서버와 클라이언트가 정해진 해더를 통해 서로 요청이나 응답에 반응할지 결정하는 방식으로 교차 출처 자원 공유(cross-origin resource sharing)라는 이름으로 표준화가 되었다.
>
> **한마디로 Cross-Site Http Request를 가능하게 해주는 표준 규약** 
>
> 우리는 ajax를 이용한 rest api 서비스를 굉장히 많이 사용하기 때문에 꼭 same-origin policy을 부시고 CORS를 허용 해줘야한다.
>

### 5. CORS 시나리오
```java
// 두 개의 출처가 같다는 것이 헤더에 포함되어야 함
Origin == Access-Control-Allow-Origin
```

### 6. CORS 종류
>1. Preflight Request  
>2. Simple Request
>3. Credential Request


#### 6-1 Preflight Request
>![image](https://user-images.githubusercontent.com/66704969/121037855-c5d0c400-c7ea-11eb-8797-c0fba5c0b1b2.png)
![image](https://user-images.githubusercontent.com/66704969/121038144-02042480-c7eb-11eb-8341-7fbd5e6ee3e0.png)

#### 6-2 Simple Request
>![image](https://user-images.githubusercontent.com/66704969/121040010-8905cc80-c7ec-11eb-9840-20e356730d64.png)
![image](https://user-images.githubusercontent.com/66704969/121040157-a5a20480-c7ec-11eb-884e-e6c695e5887a.png)

#### 6-3 Credential Request
>![image](https://user-images.githubusercontent.com/66704969/121040258-b8b4d480-c7ec-11eb-87db-ec001e28b81f.png)
![image](https://user-images.githubusercontent.com/66704969/121040402-d4b87600-c7ec-11eb-8ede-4daff4bf314b.png)
![image](https://user-images.githubusercontent.com/66704969/121040501-e9950980-c7ec-11eb-828c-fc31b658466f.png)

### 7. 결론
> **Front 개발환경을 위해 응답 헤더에 올바른 Access-Control-Allow-Origin이 내려올 수 있도록 세팅 필요**