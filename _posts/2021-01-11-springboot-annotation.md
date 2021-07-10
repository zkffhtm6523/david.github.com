---
title: Annotation 정리
author: David
date: 2021-01-11 23:10:29 +0900
categories: [SpringBoot, Annotation]
math: true
viewer: true
tags: [Annotation, SpringBoot]
image:
  src: /blog-assets/title/Tool_Wide_Img/Spring-Framework.jpg?raw=true
  alt: SpringBoot
---

# @Component
> 사용법에 맞게 Annotation을 세분화하는 것이 중요
통합적으로 사용할 수 있으나, 통합적인 만큼 추후에 업데이트 되는 기능들에 제한적일 수 있음

# @RestController
>Controller 중 View에 응답하지 않고 JSON으로 결과를 반환하는 Controller
@RestController 안의 Method들은 자동적으로 @ResponseBody가 자동적으로 붙는다

# @Controller(Controller > Component)
> Component를 사용해도 무방?하다
Controller을 사용함으로써 각 Method에 @RequestMapping(value = "/form", method=RequestMethod.GET)

# @Service(Service > Component)
> Service 클래스에서 사용하는 것, 현재 추가적인 기능을 제공해주는 것이 없어서 명시적으로 Component와 차이점을 못느낄 수 있으나, 추가적인 Exception 등 기능을 업데이트 해줄 수 있으니 Service를 사용하자

# @Repository(Dao > Component)
> Component를 사용해도 기능은 돌아간다.
unchecked exception들을 Spring의 DataAccessException으로 처리할 수 있는 장점

# @Inject == @Autowired
> 유사함


