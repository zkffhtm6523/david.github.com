---
title:  "Async"
author: David
date:   2021-07-06 23:10:29 +0900
categories: [SpringBoot, Http]
math: true
viewer: true
tags: [Async, SpringBoot]
image:
  src: /blog-assets/title/Tool_Wide_Img/Spring-Framework.jpg?raw=true
  alt: Docker
---

# Java -> @Async 비동기 서비스

```java
// @EnableAsync로 비동기 기능 활성화
// 비동기를 원하는 메소드는 public이어야 한다.
```

### @Configuration
```java
@Configuration
@EnableAsync
public class AsyncConfig extends AsyncConfigurerSupport {

    
    public Executor getAsyncExecutor() {
        // ThreadPoolTaskExecutor로 비동기로 호출하는 Thread 대한 설정을 한다
        ThreadPoolTaskExecutor executor = new ThreadPoolTaskExecutor();
        // corePoolSize: 기본적으로 실행을 대기하고 있는 Thread의 갯수
        executor.setCorePoolSize(2);
        // MaxPoolSise: 동시 동작하는, 최대 Thread 갯수
        executor.setMaxPoolSize(10);
        //QueueCapacity : MaxPoolSize를 초과하는 요청이 Thread 생성 요청시 해당 내용을 Queue에 저장하게 되고, 사용할수 있는 Thread 여유 자리가 발생하면 하나씩 꺼내져서 동작하게 된다.
        executor.setQueueCapacity(500);
        //ThreadNamePrefix: spring이 생성하는 쓰레드의 접두사를 지정한다.
        executor.setThreadNamePrefix("hanumoka-async-");
        executor.initialize();
        return executor;
    }
}
```

### @Async를 적용한 Service
```java
@Service
public class AsyncService {

    private static final Logger logger = LoggerFactory.getLogger(AsyncService.class);

    //비동기로 동작하는 메소드
    
    public void onAsync() {
        try {
            Thread.sleep(5000);
            logger.info("onAsync");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    //동기로 동작하는 메소드
    public void onSync() {
        try {
            Thread.sleep(5000);
            logger.info("onSync");
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

### @Async Return Type
1. void
2. CompletableFuture
3. ListenableFuture
4. Future


### @Async 참조 링크
1. [Return Type](https://opentutorials.org/module/782/6083)
2. [Configuration 설정](https://www.hanumoka.net/2020/07/02/springBoot-20200702-sringboot-async-service/)
3. [Simple & Configuration](http://dveamer.github.io/java/SpringAsync.html)