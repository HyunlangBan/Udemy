### Insert at the Beginning
---
실습코드
```python
class Node(object):

  def __init__(self, data):
      self.data = data
      self.nextNode = None
  
class LinkedList(object):
  
  def __init__(self):
      self.head = Node(None)
      self.size = 0
      
  # O(1) !!!!!!
  def insertStart(self, data):

      self.size += 1
      newNode = Node(data)
      
      if not self.head:
          self.head = newNode
      else:
          newNode.nextNode = self.head
          self.head = newNode
          
 
 # O(1)
 def size1(self):           #size는 python 기본 메소드 이므로 쓰지 않도록 주의
      return self.size
      
  
 # O(N) not good!!!!!
 def size2(self):
 
    size = 0
    actualNode = self.head
    
    while actualNode is not None:
        size += 1
        actualNode = actualNode.nextNode
 return size
 ```
 
#### 헷갈리는 부분
- Node의 초기 형태는 head와 pointer(nextNode)이다. 
- 객체를 생성할때는 `__init__`(생성자)의 매개변수를 꼭 전달해주어야 한다.
- linkedList의 초기 형태는 `self.head = None` 이라고 써있는데 linked List도 Node로 이루어져있을텐데(마지막 노드의 next가 None이어야 끝나니까) 왜 nextNode는 지정해주지 않는 것일까? head, nextNode 모두 None이라면 `self.head = Node(None)`이 더 맞는것 같다.
- size는 생성되는 LinkedList 마다 다르므로 `self.size`
- size1 메소드는 객체마다 사이즈가 저장되고 있으므로 간단하게 호출할수 있지만, size2에서는 `size`라는 변수로 메소드 안에서 크기를 직접 계산한다. 왜 `self.size`가 아닌지 약간 헷갈렸는데, 이것은 LinkedList의 크기가 아니고 메소드 내에서만 사용되는 `size`이기 때문이다.

<br>

### Insert at the End, Traverse
---
실습코드

```python
#class LinkedList

# O(N) - Linear time complexity
def insertEnd(self, data):

    self.size += 1
    newNode = Node(data)
    actualNode = self.head
    
    while actualNode.nextNode is not None:
        actualNode = actualNode.nextNode
        
    actualNode.nextNode = newNode

def traverseList(self):
    actualNode = self.head
    
    while actualNode is not None:
        print("%d " % actualNode.data)
        actualNode = actualNode.nextNode
```

<br>

### Remove
---
```python
#class LinkedList

def remove(self, data):

    if self.head is None:
        return
    
    self.size -= 1
    
    currentNode = self.head
    previousNode = None
    
    while currentNode.data != data:
        previousNode = currentNode       # previousNode는 currentNode의 이전 노드를 계속 추적
        currentNode = currentNode.nextNode
    
    if previousNode is None:  # It means currentNode is the head.
        self.head = currentNode.nextNode
    else:
        previousNode.nextNode = currentNode.nextNode
 ```
