---
layout: post
title: 선택정렬(SelectionSort)
date: 2020-01-15 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [선택정렬(SelectionSort), 알고리즘 (Algorithm)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72407753-e76b7e80-37a3-11ea-8d7e-c088e51d592e.gif" />



#### 선택정렬 (Selection Sort)

- 가장 작은 요소부터 정렬
- 해당 최소값을 데이터 맨 앞에 위치한 값과 교체
- 맨 앞의 위치를 뺀 나머지 데이터를 동일한방법으로 반복



##### Java

```java
package Java;

import java.util.Random;
import java.util.ArrayList;

public class ExSelectionSort {
  public static void main(String[] args) {

    ArrayList<Integer> arrayList = new ArrayList<Integer>();
    Random rand = new Random();

    int range = 10;

    for (int i = 0; i < range; i++) {
      arrayList.add(rand.nextInt(range));
    }
    System.out.println("초기 값 : " + arrayList);

    for (int i = 0; i < arrayList.size(); i++) {
      int lowest_num = arrayList.get(i);
      int lowest_index = i;
      int num = arrayList.get(i);

      for (int j = i + 1; j < arrayList.size(); j++) {
        if (lowest_num > arrayList.get(j)) {
          lowest_num = arrayList.get(j);
          lowest_index = j;
        }
      }
      System.out.println("최소 값 : " + lowest_num);
      arrayList.set(i, lowest_num);
      arrayList.set(lowest_index, num);
      System.out.println(arrayList);
    }
    System.out.println(arrayList);
  }
}
```



##### Python

```python
import random


def ExSelectionSort(data):
    for stand in range(len(data) - 1):
        lowest = stand
        for index in range(stand + 1, len(data)):
            if data[lowest] > data[index]:
                lowest = index
        data[lowest], data[stand] = data[stand], data[lowest]
    return data


data_list = random.sample(range(100), 10)
print(data_list)

selectionSort = ExSelectionSort(data_list)
print(selectionSort)
```



이미지 출처 : https://algorithms.tutorialhorizon.com/selection-sort-java-implementation/selection-sort-gif/

