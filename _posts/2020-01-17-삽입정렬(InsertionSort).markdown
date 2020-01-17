---
layout: post
title: 삽입정렬(InsertionSort)
date: 2020-01-17 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [삽입정렬(InsertionSort), 알고리즘 (Algorithm)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72411589-96ad5300-37ae-11ea-8cc6-d14109dc4e87.gif" />



삽입 정렬 (Insertion Sort)

- 선택한 요소를 알맞은 위치에 삽입하는 정렬
- 가장 작은 값을 선택하여 정렬하는 선택 정렬과 달리 선택된 값을 정렬



##### Python

```python
import random


def ExInsertionSort(data):
    for index in range(len(data) - 1):
        for index2 in range(index+1, 0, -1):
            if data[index2] < data[index2-1]:
                data[index2], data[index2-1] = data[index2-1], data[index2]
            else:
                break
    return data


data_list = random.sample(range(100), 50)
print(data_list)

insertion_sort = ExInsertionSort(data_list)
print(insertion_sort)
```



이미지 출처 : https://gfycat.com/ru/densebaggyibis