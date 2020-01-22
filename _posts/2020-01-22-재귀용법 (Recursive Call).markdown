---
layout: post
title: 재귀용법 (Recursive Call)
date: 2020-01-22 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [재귀용법 (Recursive Call), 알고리즘 (Algorithm)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72888927-e7462280-3d51-11ea-9f19-b06b51c52d90.gif"/>





#### 재귀 용법 (Recursive Call)

- 함수 안에서 동일한 함수를 호출하는 형태
- 어떤 사건이 자기 자신을 포함하고 다시 자기 자신을 사용하여 정의될 때



##### Java

```java
import java.util.Scanner;

public class ExRecursiveCall {
  public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    int num = scan.nextInt();

    for (int i = 0; i < num; i++) {
      System.out.println(Factorial(i));
    }
  }

  public static int Factorial(int num) {
    if (num > 1) {
      return num * Factorial(num - 1);
    } else {
      return num;
    }
  }
}
```



##### Python

```python
def factorial(num):
    if num > 1:
        return num * factorial(num-1)
    else:
        return num


data = int(input())

for num in range(data):
    print(factorial(num))
```



이미지 출처 : https://giphy.com/gifs/homer-simpson-the-simpsons-3ov9jQX2Ow4bM5xxuM