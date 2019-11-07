### Doubly Linked List
NULL <- Node1 <=> Node2 <=> Node3 <=> Node4 -> NULL
- We can access the head and tail.
- A single node contains **data**(integer, double or custom object), reference pointing to the **next node** and pointing to the **previous node** in the linked list

<br>

#### Single Linked Lsit
We found the item we want to get rid of --> it takes O(N)
- WHY? We need the previous on in the refernece update.

삭제할 노드가 주어져 있다고 가정하면,
Single linked list에서는 previous node가 node를 찾을때까지 리스트를 탐색해야하므로 O(N)

<br>

하지만, Double linked list에서는 바로 이전 노드에 접근할 수 있으므로 **O(1)** running time


<br>

#### Advantages of double linked lists
- Can be traversed both directions: forward and backward
- the remove operation is more effiecient if the node is given
   - for linked lists we need the previous node as well to find it. Usually we need to traverse the whole list
- To remove a node from singly linked list -> we need the node + predecessor
- To remove a node from doubly linked list -> we need the node
