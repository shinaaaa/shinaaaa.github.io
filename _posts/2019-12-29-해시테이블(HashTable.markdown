---
layout: post
title: 해시 테이블 (Hash Table)
date: 2019-12-29 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [해시 테이블 (Hash Table), 자료구조론] # add tag
---

![img](https://user-images.githubusercontent.com/37543606/71552581-1ca56c00-2a43-11ea-9cc0-7562a1268784.png)



#### 해시 테이블 (Hash Table)

- 키 값을 연산에 의해 직접 접근 가능한 데이터 구조

  > Key를 통해 바로 데이터를 받아올 수 있으므로, 속도가 획기적으로 빨라짐
  >
  > 보통 배열로 미리 Hash Table 사이즈 만큼 생성 후에 사용
  >
  > 예시 ) 파이쎤 딕셔너리 (Dictionary) 타입  --> Key를 가지고 바로 데이터(Value)를 꺼냄

  

#### 주요 용도

- 검색이 많이 필요한 경우
- 저장, 삭제, 읽기가 빈번한 경우
- 캐시 구현시 (중복 확인이 쉬움)



#### 장/단점

- 장점

  > 데이터 저장/읽기 속도가 빠름 (검색 속도가 빠름)
  >
  > 키에 대한 데이터가 있는지 확인이 쉬움 (중복 검사가 용이)

- 단점

  > 상대적으로 많은 저장공간이 필요
  >
  > 여러 키에 해당하는 주소가 동일할 경우 충록을 해결하기 위한 뱔도의의 자료구조가 필요

  

#### 해시 (Hash)

- 임의 값을 고정 길이로 변환하는 것



#### 해싱 함수 (Hashing Function)

- Key에 대해 산술 연산을 이용해 데이터 위치를 찾을 수 있는 함수



#### 해시 값 (Hash Value), 해시 주소 (Hash Address)

- Key를 해싱 함수로 연산해서, 해시 값을 알아내고, 이를 통해 해시 테이블에서 해당 Key에 대한 데이터 위치를 일관성있게 찾음



#### 슬롯 (Slot)

- 한 개의 데이터를 저장할 수 있는 공간
- 저장할 데이터에 대해 Key를 추출할 수 있는 별도 함수도 존재할 수 있음



출처 : https://open4tech.com/array-vs-linked-list-vs-hash-table/