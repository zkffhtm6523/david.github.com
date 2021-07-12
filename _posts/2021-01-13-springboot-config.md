---
title: "XML 설정 파일 정리"
author: David
date: 2021-01-13 23:10:29 +0900
categories: [SpringBoot, XML]
math: true
viewer: true
tags: [XML, SpringBoot]
image:
  src: /blog-assets/title/Tool_Wide_Img/Spring-Framework.jpg?raw=true
  alt: SpringBoot
---

## 프로젝트 구조
![images](https://media.vlpt.us/images/zkffhtm6523/post/e0b2bd9c-bc1d-45d5-a751-ae2bfd3e9e12/image.png)

## 1. servlet-contex.xml

| servlet-contex.xml |
| - |
| <center>WEB Application 에서 client 요청을 받기 위한 설정 <center>|
| <center> JSP와 관련있는 객체(bean) 설정 - controller, MultipartResolver, Interceptor(로그인 등) <center> |
| <center> 어노테이션 ```<annotation-driven/>``` </center>|
| <center> URL 관련 설정 </center>|

> servlet에서 보듯이 요청과 관련된 객체를 정의

>url과 관련된 controller나, @(어노테이션), ViewResolver, Interceptor, MultipartResolver 등의 설정

![images](https://images.velog.io/images/zkffhtm6523/post/1e6f10f5-06d5-49d8-8d73-9319377b4578/image.png)

```
DispatcherServlet Context: defines this servlet's request-processing infrastructure
```

위와 같은 주석이 있는데, **DispatcherServlet과 관련된 설정**을 해야함을 알 수 있습니다.

## 2. root-contex.xml
| root-contex.xml |
| - |
| <center> JSP와 관련없는 객체(bean)을 설정합니다.(service, repository) <center>|
| <center>  비지니스 로직을 위한 설정을 합니다. <center> |
| <center> 외부 jar 파일등으로 사용하는 클래스는 `<bean>`태그를 이용하여 작성합니다. </center>|
| <center> URL 관련 설정 </center>|
  
>따라서 **Service, Repository(DAO), DB**등 비즈니스 로직과 관련된 설정
 servlet-context.xml 과는 반대로 view와 관련되지 않은 객체를 정의
  
![](https://images.velog.io/images/zkffhtm6523/post/39a725c0-f4aa-4e5a-8a2b-d6000fe528ab/image.png)
  
(출처: https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html#mvc)
  
## 3. web.xml
  
>설정을 위한 설정파일입니다.
즉, **최초로 WAS가 최초로 구동될 때, 각종 설정을 정의**해줍니다.
여러 xml파일을 인식하도록 각 파일을 가리켜 줍니다.