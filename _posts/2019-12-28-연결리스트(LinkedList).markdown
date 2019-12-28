---
layout: post
title: 연결리스트(LinkedList)
date: 2019-12-28 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [연결리스트(LinkedList), 자료구조론] # add tag
---

<img src='https://user-images.githubusercontent.com/37543606/71540345-7f87fc00-298c-11ea-8719-4f42c6a5f469.jpg'/>



#### 연결리스트(LinkedList)

- 데이터를 순서대로 나열한 자료구조
- 떨어진 곳에 존재하는 데이터를 화살표로 연결해서 관리하는 구조



##### 노드(Node)

- 각각의 데이터와 다음 노드를 가리키는 포인터를 가지고 있음

  >  머리 노드(Head Node) : 맨 앞에 있는 노드
  >
  >  꼬리 노드(Tail Node) : 맨 뒤에 있는 노드
  >
  >  이전 노드(Predecessor Node) : 하나의 노드 바로 앞에 있는 노드
  >
  >  다음 노드(Successor Node) : 바로 뒤에 있는 노드



##### 포인터(Pointer)

- 각 노드 안에, 다음이나 이전의 노드와 연결 정보를 가지고 있는 공간



###### Java

```java
import java.util.*;

public class ExLinkedList {
  public static void main(String[] args) {

    /* LinkedList 선언 */
    LinkedList<String> linkedlist = new LinkedList<String>();

    /* LinkedList에 값을 저장 */
    linkedlist.add(0, "피카츄");
    linkedlist.add(1, "파이리");
    linkedlist.add(2, "이상해씨");
    linkedlist.add(3, "꼬부기");

    /* LinkedList 값 출력 */
    System.out.println("LinkedList 값 출력  : " + linkedlist);

    /* LinkedList 3번째에 값을 추가 */
    linkedlist.add(2, "망나뇽");

    /* LinkedList 값 출력 */
    System.out.println("LinkedList 값 출력  : " + linkedlist);

    /* LinkedList 1번째에 값을 변경 */
    linkedlist.set(1, "리자몽");
    /* LinkedList 값 출력 */
    System.out.println("LinkedList 값 출력  : " + linkedlist);
  }
}
```



###### Python

```python
class Node:
    def __init__(self, data, next=None):
        self.data = data
        self.next = next


def add(data):
    node = head
    while node.next:
        node = node.next
    node.next = Node(data)


node1 = Node(1)
head = node1
for index in range(2, 10):
    add(index)

    node = head
while node.next:
    print(node.data)
    node = node.next
print(node.data)
```

출처 : https://www.pinterest.co.kr/pin/543528248769991289/