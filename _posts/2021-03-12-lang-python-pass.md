---
title: '[Python] Pass, Continue, Break'
author: David
date: 2021-03-12 23:10:29 +0900
categories: [Programming, Python]
math: true
viewer: true
tags: [Python]
image:
  src: /blog-assets/title/Tool_Wide_Img/Python.jpg?raw=true
  alt: Python
---

## - pass, continue, break 차이점

- **pass :** 실행할 코드가 없는 것으로 다음 행동을 계속해서 진행합니다.
- **continue :** 바로 다음 순번의 loop를 수행합니다.
- **break :** 반복문을 멈추고 loop 밖으로 나가도록합니다.

## 1. pass 예시
```python
## 실행
for i in range(10):
    if i % 2 == 0:
        pass
        print(i)    
    else:
        print(i)
print("Done")

## 결과
0
1
2
3
4
5
6
7
8
9
Done
```

## 2. continue 예시
```python
## 실행
for i in range(10):
    if i % 2 == 0:
        continue
        print(i)    
    print(i)
print("Done")

## 예시
1
3
5
7
9
Done
```

## 3. break 예시
```python
## 실행
for i in range(10):
    if i % 2 == 0:
        break
        print(i)    
    else:
        print(i)
print("Done")

## 예시
Done
```
