---
title:  "WebClient"
author: David
date:   2021-06-28 23:10:29 +0900
categories: [SpringBoot, Http]
math: true
viewer: true
tags: [JDK11, SpringBoot]
image:
  src: /blog-assets/title/Tool_Wide_Img/Spring-Framework.jpg?raw=true
  alt: Docker
---

# WebClient vs RestTemplate

> - RestTemplate은 WebClient 보다 이전에 나왔다
> - RestTemplate은 동기식이며, response가 올 때까지 다음 행동으로 넘어갈 수 없다
> - RestTemplate은 곧 deprecated 될 예정


## WebClient
```java
dependencies {
        compile 'org.springframework.boot:spring-boot-starter-webflux'
        compile 'org.projectreactor:reactor-spring:1.0.1.RELEASE'
    }
```

### - WebClient Instance 생성
```java
Webclient client = WebClient.builder()
                            .baseUrl("http://localhost:8080")
                            .defaultCookie("쿠키키","쿠키값")
                            .defaultHeader(HttpHeaders.CONTENT_TYPE, MediaType.APPLICATION_JSON_VALUE)
                            .build();
```

### - Request 요청하기
```java
// 1.일단 HTTP 메소드를 정해야한다.
WebClient.UriSpec<WebClient.RequestBodySpec> req = client.post();

// 2.두번째로 uri API를 제공해야한다. String 포맷 혹은 java.net.URL 포맷으로 넘긴다.
WebClient.RequestBodySpec uri = client
                                .post()
                                .uri("/search");

// 3.필요하다면 Request에 body, content-type,length, cookie, header 등을 포함할 수 있다.
WebClient.RequestHeadersSpec<?> req2 = client.post()
                                             .uri("/search")
                                             .body(BodyInserters.fromObejct("data"));
```

### - Response 응답하기
> 1. exchange :  ClientResponse를 상태값 그리고 헤더와 함께 가져온다.
> 2. retrive : body를 가져온다

```java
String response = req.exchange().block().bodyToMono(String.class).block();

String response2 = req2.retrieve().bodyToMono(String.class).block();
```
