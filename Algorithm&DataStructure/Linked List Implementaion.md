### Insert

실습코드
```python
class Node(object):

  def __init__(self, data):
      self.data = data
      self.nextNode = None
  
class LinkedList(object):
  
  def __init__(self):
      self.head = None
      self.size = 0
      
  # O(1) !!!!!!
  def insertStart(self):
      
      newNode = Node(self, data)
      self.size += 1
      newNode = Node(data)
      
      if not self.head:
          self.head = newNode
      else:
          newNode.nextNode = self.head
          self.head = newNode
          
 
 # O(1)
 def size(self):
      return self.size
      
  
 # O(N) not good!!!!!
 def size2(self):
    self.size = 0 -----> size = 0
    actualNode = Node(data) ----> (X)
    actualNode = self.head
    
    while actualNode is not None:
        self.size += 1
        actualNode = actualNode.nextNode
return self.size-----> size
   
