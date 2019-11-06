### Linked List - Basics
---

node1 -> node2 -> node3 -> NULL (**last node is NULL**)

#### A single node:

- Data, Reference
Data: integer, double, or custom object
Refernece: next node

#### Linked List - Features:

- Simple and common data structure.
- Used to implement several other common data types: stacks, queues
- Do not allowed random access to data --> getItem(int index) (X)
- Basic operations such as optaining the last node of list, finding a node that contains a given data, locating the place where a new node should be inserted -- require sequential scanning of most or all of the list elements.


#### Advantages:

- Dynamic structures ( arrays are not!)
- Allocate the needed memory in run-time
- Very efficient if we want to manipulate the first elements
- Can store items with different sizes: an array assumes every element to be exactly the same
- It's easier for a linked list to grow organically <---> arrays

#### Disadvnatage:

- Waste memory because of the references
- Nodes in a linked list must be read in order form the beginnings(sequential access) <--> array random access
- Difficulties arise in linked lists when it comes to reverse traversing --> solution: double linked lists
   - Easier to read but memory is wasted in allocating spaces for a back pointer <--> array: memory freindly
   


<br><br>
### Linked Lists Operations - Insert, Remove
---
- Inserting items **at the beginning** of the linked list: O(1) time complexity

  ex)

  linkedList.insertAtStart(10)
  
  linkedList.insertAtStart(4)
  
  linkedList.insertAtStart(-5)
  

  -5 --> 4 --> 10 --> NULL

  We just have to set the pointer to point to the next node

  **계속 강조하는 것: Array는 첫번째에 insert를 하게되면 reconstruct를 해야하기 때문에 O(N)이 되지만, Linked List는 첫번째에 삽입하고 포인터만 지정해주면 되므로 O(1)**

  맨 마지막에 insert할때는 array, 맨 앞에 insert할때는 Linked list가 효율적!


- Inserting items **at the end** of the linked list: we have to traverse the whole linked list to find the last node

  - How do we find the last node? We know the last node is pointing to a NULL
  - We have to update the references when we get there --> O(N) time complexity
  
  ex)

  linkedList.insertAtEnd(25):
  
  12 -> 4 -> 123 -> -7 -> 10 -> [25] -> NULL
  
  **Updating the references again taeks O(1) BUT we have to traverse the list itself and that what takes O(N) // O(1) + O(N) = O(N)**


- Remove item **at the beginning** of the linked list: Do not have to search the item, just update the reference accordingly --> O(1) time complexity
- Remove item **at the end** of the linked list: Have to search for the given item which may take lot of time if the item is at the end --> O(N) time complexity



### Doubly Linked Lists
- Problem with liked lists: Cannot go from back to front because the references are in the opposite directions.
   - SOLUTION: doubley linked list
   - Can get from everywhere to everywhere BUT it is not memeory friendly, we have to store lots of references. BUT there is no need to track the previous node during traversal!
   
   
### Linked List versus Arrays
#### Search
- Array List: **Index**를 알고 있을 때는 random access가 가능하므로 매우 효율적이다 --> O(1)
             하지만 index를 모를때는 array를 돌아야 할수도 있으므로 O(N)d이다.
- Linked List: 항상 List 전체를 확인해야 하므로 O(N)이다.

**ArryaList** is better for search operation.


#### Deletion
- **Linked list** is better for this operation.
   - wWhy? Linked list basically operates with pointers: removal only requires change in the pointer location which can be done very fast.
   
#### Memory Management
- Array: do not need any extra memory --> memory friendly
- LinkedLists: need extra memory for references/pointers

**Array** are better.


|                      | Linked List | Arrays|
|:--------------------:|:-----------:|:-----:|
|  Search              | O(N)        | O(1)  |
|  Insert at the start | O(1)        | O(N)  |
|  Insert at the end   | O(N)        | O(1)  |
|  Waste space         | O(N)        | 0     |
