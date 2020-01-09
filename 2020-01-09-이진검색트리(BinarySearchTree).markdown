---
layout: post
title: 이진 트리 (Binary Tree) 와 이진 검색 트리 (Binary Search Tree)
date: 2020-01-05 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [트리 (Tree),이진 트리 (Binary Tree),이진 검색 트리 (Binary Search Tree), 자료구조론] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72056423-eb188480-330f-11ea-9525-f5ea89f5b4cd.jpeg"/>





####이진트리 (Binary Tree)

- 노드가 왼쪽 자식과 오른쪽 자식을 갖는 트리
- 노드 최대 Branch가 2인 트리



####이진 검색 트리 (Binary Search Tree)

- 어떤 노드 N을 기준으로 왼쪽 서브 트리 노드의 모든 키 값은 노드 N의 키 값보다 작음
- 오른쪽 서비 트리 노드의 키 값은 노드 N의 키 값보다 큼
- 같은 키 값을 갖는 노드는 없음



####이진 검색 트리의 시간 복잡도

- 트리의 높이 (Depth) 를 h라고 표기한다면 O(h)

- n개의 노드를 가진다면, $h = log_2{n}$ 에 가깝기 때문에 시간 복잡도는 $O(log_2{n})$

  > 빅오 표기법 : 밑이 2인 $log{n}$
  >
  > 한번 실행시, 50%의 실행할 수도 있는 명령을 제거
  >
  > 즉, 50%의 실행시간을 단축

####장/단점

- 장점

  >중위 순회를 하면 키 값의 오름차순으로 노드를 얻을 수 있음
  >
  >구조가 단순함
  >
  >이진 검색과 비슷한 방식으로 검색이 가능
  >
  >노드의 삽입이 쉬움

- 단점

  > 평균 복잡도은 $O(log_2{n})$이지만 이는 트리가 균형잡혀 있는 경우의 평균 시간복잡도
  >
  > 최악의 경우는 링크드 리스트등과 동일한 성능을 보여줌 ( $O(n)$)



#####Python

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None


class NodeMgmt:
    def __init__(self, head):
        self.head = head

    def insert(self, value):
        self.current_node = self.head
        while True:
            if value < self.current_node.value:
                if self.current_node.left != None:
                    self.current_node = self.current_node.left
                else:
                    self.current_node.left = Node(value)
                    break
            else:
                if self.current_node.right != None:
                    self.current_node = self.current_node.right
                else:
                    self.current_node.right = Node(value)
                    break

    def search(self, value):
        self.current_node = self.head
        while self.current_node:
            if self.current_node.value == value:
                return True
            elif value < self.current_node.value:
                self.current_node = self.current_node.left
            else:
                self.current_node = self.current_node.right
        return False


""" 예시 """
head = Node(1)
BST = NodeMgmt(head)
BST.insert(2)
BST.insert(3)
BST.insert(0)
BST.insert(4)
BST.insert(8)

print(BST.search(-1))
print(BST.search(0))
```



이미지 출처 : https://www.educative.io/edpresso/how-to-check-if-a-binary-tree-is-a-binary-search-tree