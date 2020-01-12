---
layout: post
title: 버블 정렬 (Bubble Sort)
date: 2020-01-12 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [버블 정렬 (Bubble Sort), 알고리즘 (Algorithm)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72214951-c4489100-354f-11ea-8499-bd0fe496217d.gif" />



#### 정렬

- 어떤 데이터들이 주어졌을 때 이를 정해진 순서대로 나열하는 것

  > 내부 정렬 : 정렬할 모든 데이터를 하나의 배열에 저장할 수 있는 경우에 사용하는 알고리즘
  >
  > 외부 정렬 : 정렬할 데이터가 너무 많아서 하나의 배열을 저장할 수 없는 경우에 사용하는 알고리즘



#### 버블 정렬 (Bubble Sort)

- 액체 안에 공기 방울이 위로 올라오는 모습에서 착안

- 이웃한 두 요소의 대소 관계를 비교하여 앞에 있는 데이터가 뒤에 있는 데이터보다 크면, 자리를 바꿈

- 요소의 개수가 n개인 배열에서 n-1회 비교, 교환을 하고 나면 가장 작은 요소가 맨 처음으로 이동

- 비교,교환 작업을 패스하소함

  > 수행하는 패스가 n 회가 아니고 n-1회인 이유는 n-1회 작업을 하면 마지막 요소는 이미 끝에 놓이기 때문



##### Python

```python
import random


def bubbleSort(data):
    for index in range(len(data) - 1):
        swap = False
        for index2 in range(len(data) - index - 1):
            if data[index2] > data[index2 + 1]:
                data[index2], data[index2 + 1] = data[index2 + 1], data[index2]
                swap = True

        if swap == False:
            break
    return data


data_list = random.sample(range(100), 50)
print(bubbleSort(data_list))
```



이미지 출처 : https://medium.com/@peterlin5301997/bubble-sort-5a66156c942e