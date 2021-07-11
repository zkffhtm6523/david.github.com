---
title: <!cdata[ 사용이유
author: David
date: 2021-01-14 23:10:29 +0900
categories: [Mybatis, cdata]
math: true
viewer: true
tags: [cdata, mybatis]
image:
  src: /blog-assets/title/Tool_Wide_Img/mybatis.png?raw=true
  alt: Mybatis
---

## 1. 개념
> 특수문자, 비교연산자 등 단어나 문장을 문자열로 인식하게 함

## 2. 예시

 
```sql
//사용 전

<select id ="list" parameterType="int" resultType="board.test.testDto>

select *

from employees

where salary > 100

</select>
```
```sql
//사용 후

<select id = "list" parameterType="int" resultType="board.test.testDto>

<![CDATA[

select *

from employees

where salary > 100

]]>

</select> 

```