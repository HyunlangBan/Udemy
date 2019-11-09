### Binary Search Trees
---
- Array와 Linked Lists는 각 operation들 마다 다른 복잡도를 가지고 있다. 하지만 Binary search tree는 insert, search, remove 모두를 더 빠르게 처리할 수 있다. --> **O(logN)** time complexity!
- 예를들어 페이스북에서 각각의 유저들이 다른 방식으로 이용하기 때문에(사진 포스팅하기, 친구 검색하기 등등) 이러한 pradictable running time이 중요하다.


### Trees
- root node: 모든 다른 노드들은 루트 노드를 통해 접근할 수 있다.
- edges: 노드들을 연결
- 루트 노드에서 다른 노드들까지 오직 하나의 경로만 존재해야한다. 만약 여러갈래의 길이 있다면 그것은 트리가 아니다.
- parent node: 바로 연결된 노드들 중에서 상위 노드
- child node: 바로 연결된 노드들 중에서 하위 노드
- leaf node: children nodes가 없는 노드

### Binary Search Trees
- 모든 노드들은 최대 2개의 자식들이 존재: left, right
- left child: 부모보다 작은 값
- right node: 부모보다 큰 값

***Why is it good?***: 우리가 찾아야 하는 데이터 중 절반을 제거하고 모든 결정이 이루어지기 때문 --> 
**O(logN)** time complexity

- Height of a tree: 트리가 가지고 있는 층의 갯수
  - layer h: 2^(h-1) nodes를 가지고 있음
- 보통, O(logN)이 참이라면 균형 트리이고 거짓이라면 불균형 트리이다. 이 말은 즉슨, 비대칭인 것은 문제가 된다는 것!
- Height of the tree *h*: 루트 노드에서 가장 깊은 노드까지의 경로의 길이
  - **h = log(n)** 이 최소
  - 만약 불균형 트리라면 h=log(n)은 유효하지 않고 operation running time도 logarithmic하지 않다.



### 정리
- BST는 data structure이다.
- key값들을 sorted된 상태로 유지
- Each comparison allows the operations to skip over half of the tree: each lookup/insertion/deletion takes time proportional to the logarithm of the number of items stored in the tree  
- unsorted array에서 값을 찾을때 O(N)이 걸리는 것 보단 훨씬 낫지만 hash table을 사용할때보다는 느리다.

<br>

### Search & Insertion & Deletion
---
#### Insertion
- 삽입하려는 수가 루트 노드보다 작으면 왼쪽, 크면 오른쪽으로 이동한다. 이렇게 노드를 이동하면서 과정을 계속 반복한다.
#### Serach
- 찾으려는 수가 루트 노드보다 작으면 왼쪽, 크면 오른쪽으로 이동한다. 이렇게 노드를 이동하면서 과정을 계속 반복한다.
  - Unsorted array에서는 모든 수들을 다 찾아봐야 하지만 BST에서는 절반만 찾으면 된다.  O(N) <--> O(logn)
  - 최소값 찾기: 루트 노드로부터 가장 왼쪽으로 이동한 노드
  - 최댓값 찾기: 루트 노드로부터 가장 오른쪽으로 이동한 노드
#### Delete
- 3가지의 경우가 존재
  - 삭제하려고 하는 노드가 leaf node일때
    - 가장 간단한 방법. 그냥 그 노드를 Null값으로 바꾸어버린다.
    - Fine the item itself(O(logN)) + Deletion(O(1)) = O(logN)
  - 삭제하려는 노드가 single child를 가지고 있을때
    - reference를 변경한다: 부모의 포인터가 garndchild를 바로 가르키도록 설정
    - Find(O(logN)) + update reference(O(N)) = O(logN)
  - 삭제하려는 노드가 2개의 자식 노드를 가지고 있을때
    - Two options: 왼쪽 서브트리에서 가장 큰 값(predecessor)을 찾거나 오른쪽 서브트리에서 가장 작은 값(successor)을 찾는다.
    - 만약 루트 노드를 predecessor를 이용하여 삭제하려고 한다면
      1. left subtree에서 가장 큰 값을 찾는다.(가장 오른쪽 노드 - leaf node라고 가정)
      2. 해당 노드와 루트 노드를 교체한다.
      3. 루트 노드가 predecessor 위치로 이동하였으면 그 값을 Null값으로 바꾼다.
    - 루트 노드를 sucessor를 이용하여 삭제하고자 한다면
      1. right subtree에서 가장 작은 값을 찾는다.(가장 왼쪽 노드 - right child를 가지고 있다고 가정)
      2. 루트 노드와 successor를 교체한다.
      3. successor 위치에 right child가 있으므로 루트 노드와 해당 child를 포인터를 통해 연결한다.
    - 여기서도 find와 deletion이 이루어지므로 복잡도는 O(logN)
    
  

  
