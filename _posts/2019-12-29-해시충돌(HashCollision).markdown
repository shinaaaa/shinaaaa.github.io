---
layout: post
title: 해시 충돌 (Hash Collision)
date: 2019-12-30 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [해시 충돌 (Hash Collision), 자료구조론] # add tag
---

<img src ="https://user-images.githubusercontent.com/37543606/71568098-c817f480-2b07-11ea-8e36-b6eccbc52d83.jpg"/>



#### 해시 충돌 (Collision)

- 저장할 버킷이 중복되는 현상
- 해시 함수를 가능하면 해시 값이 치우치지 않도록 고르게 분포된 값을 만들어야함



#### 개방 해싱 (Open Hashing) 

- 주소 밖에 새로운 공간을 할당하여 문제 해결

- 체인법 (Chaining)

  > 같은 해시 값을 갖는 데이터를 쇠사슬 (Chain) 모양으로 연결 리스트에서 연결하는 방법
  >
  > 해시 테이블 저장공간 외의 공간을 활용하는 기법
  >
  > 충돌이 일러나면, 리크드 리스트라는 자료 구조를 사용해서, 링크드 리스트로 데이터를 추가하여 뒤에 연결 저장하는 기법



#### 패쇄 해싱 (Close Hashing)

- 해시 테이블 저장공간에서 충돌 문제를 해결하는 기법

- 저장공간 활용도를 높이기 위한 기법

- 오픈 주소법 (Open Addressing)

  - 선형 탐사 (Linear Probling)

    > 충돌이 일어나면, 해당 Hash Address의 다음 Address부터 맨 처음 나오는 빈공간에 저장하는 기법

  - 제곱 탐사 (Quadratic Probing)

    > 선형 탐사와 유사하며 고정폭을 제곱 수로 증가는 기법

  - 이중 해싱 (Double Hashing)

    > 2개의 해시 함수를 사용하여 충돌 발생시 다른 해시 함수를 사용하는 기법

  - 재해싱 (Rehashing)

    > 해시 테이블 크기를 늘려 테이블 크기에 맞게 다시 테이블에 해싱하는 기법



##### Python (ChinHash)

```python
hash_table = list([0 for i in range(8)])

def get_key(data):
    return hash(data)

def hash_function(key):
    return key % 8

def save_data(data, value):
    index_key = get_key(data)
    hash_address = hash_function(index_key)
    if hash_table[hash_address] != 0:
        for index in range(len(hash_table[hash_address])):
            if hash_table[hash_address][index][0] == index_key:
                hash_table[hash_address][index][1] = value
                return
        hash_table[hash_address].append([index_key, value])
    else:
        hash_table[hash_address] = [[index_key, value]]
    
def read_data(data):
    index_key = get_key(data)
    hash_address = hash_function(index_key)

    if hash_table[hash_address] != 0:
        for index in range(len(hash_table[hash_address])):
            if hash_table[hash_address][index][0] == index_key:
                return hash_table[hash_address][index][1]
        return None
    else:
        return None
```

 

##### Python (Linear Probing)

```python
hash_table = list([0 for i in range(8)])


def get_key(data):
    return hash(data)


def hash_function(key):
    return key % 8


def save_data(data, value):
    index_key = get_key(data)
    hash_address = hash_function(index_key)
    if hash_table[hash_address] != 0:
        for index in range(hash_address, len(hash_table)):
            if hash_table[index] == 0:
                hash_table[index] = [index_key, value]
                return
            elif hash_table[index][0] == index_key:
                hash_table[index][1] = value
                return
    else:
        hash_table[hash_address] = [index_key, value]


def read_data(data):
    index_key = get_key(data)
    hash_address = hash_function(index_key)

    if hash_table[hash_address] != 0:
        for index in range(hash_address, len(hash_table)):
            if hash_table[index] == 0:
                return None
            elif hash_table[index][0] == index_key:
                return hash_table[index][1]
    else:
        return None

```





이미지 출처 : https://present5.com/the-good-the-bad-and-the-ugly-network/