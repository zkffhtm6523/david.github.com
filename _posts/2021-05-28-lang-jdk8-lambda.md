---
title:  "JDK8_Lambda"
author: David
date:   2021-05-28 23:10:29 +0900
categories: [Programming, Java]
math: true
viewer: true
tags: [jdk8]
image:
  src: /blog-assets/title/Tool_Wide_Img/java_image.webp?raw=true
  alt: Java
---

> 람다 표현식은 한 번 이든 여러 번이든 나중에 실행할 수 있게 전달하는 코드 블록이다.

# 람다 표현식 문법
```java
(String) first, String Second) -> {
    int difference = first.length() < second.length();
    if(difference < 0) return -1;
    else if(difference > 0) return 1;
    else return 0;
}
```


