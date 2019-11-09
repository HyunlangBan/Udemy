### Stack Implementation
```python
class Stack(object):

    def __init__(self):
        self.stack = []
    
    def isEmpty(self):
        return self.stack == [] # Stack이 비었으면 True, 안비었으면 False

    def push(self, data):
        self.stack.append(data)

    def pop(self):
        data = self.stack[-1]
        del self.stack[-1]
        return data
    
    def peek(self):
        return self.stack[-1]

    def sizeStack(self):
        return len(self.stack)
```

<br>


### Queue Implementation
```python
class Queue(object):

    def __init__(self):
        self.queue = []

    def isEmpty(self):
        return self.queue == []

    def enqueue(self, data):
        self.queue.append(data)

    def dequeue(self):
        data = self.queue[0]
        del self.queue[0]
        return data

    def peek(self):
        return self.queue[0]

    def sizeQueue(self):
        return len(self.queue)
```
