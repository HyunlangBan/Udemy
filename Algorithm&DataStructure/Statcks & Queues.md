### Stack
---
- Abstract data type
- Basic operations: pop(), push(), peek() --> O(1)
- **LIFO** structure: last in first out
- In most high level languages, a stack can be easily implemented either with arrays or linked lists.
- A number of programming languages are stack-oriented, meaning they define most basic operations(adding, printing) as taking their arguments from the stack, and placing any return values back on the stack.


#### Aplications
- In stack-oriented programming languages
- Graph algorithms: depth-first search 
- Finding Euler-cycles in a graph
- Finding stronly coneected components in a graph

<br>

 ### Stack(call stack)
 - 메모리의 특별한 영역(in the RAM)
 - Call Stakc은 컴퓨터 프로그램의 active subrountines/메소드/함수들에 대한 정보를 저장하는 abstract 데이터 타입이다.
 - 보통 detail은 숨겨져 있고 high-level 프로그래밍 언어에서 자동적으로 관리된다.
 - 각 함수에서 만들어진 일시적 변수들을 저장한다. 매번 함수가 새 변수를 선언할 때마다 stack안으로 push된다.
 - stack에서 popped out되면 저장되었던 정보는 영구적으로 사라진다.
 - Local variables: stack에 있고 함수가 return되면 사라진다.
 - Stack memory는 한정적이다.
 
 <br>
 
 ### Heap Memory
 ---
 - 자동으로 관리되지 않는다.
 - A large region of memory
 - C: malloc() and calloc() funcion
 - Java: refrence 타입들과 objects가 heap에 있다.
 - 이 메모리는 자동으로 관리되지 않으므로 사용하지 않는 정보는 삭제해주어야 한다. --> 그렇지 않으면 memory leak! 
 - Slower because of the pointers
 
 <br>
 
 ### 정리
 ---
 Stack Memory | Heap Memory
:------------:|:-----------:|
Limited in size|no size limits
fast access|slow access
local variables|objects
spaces is managed effieciently by CPU|memroy may be fragmented
variables cannot be resized | variables can be resized


<br>

### Stack and recursion
---
- Recursive methods를 사용하는 것이 편리할 때: DFS, Factorial, traversing a binary search tree, linked list에서 item 검색 등
- 모든 recursive 알고리즘들은 stack을 이용하는 간단한 메소드로 변형될 수 있다.
- **우리가 recursion을 사용한다면, OS는 어쨌든 stack을 사용할 것이다.**

#### Factorial
```c++
public void factorial(int n) {
    if(n == 0)   # Base Case -- 종료 포인트
        return 1;
    
    return n*factorial(n-1);       # Recursive Case
```

- Recursive 함수 호출들은 base case가 될때까지 stack안으로 push된다.
- 만약 너무 많은 함수를 호출하여 push되었다면 stack은 꽉 차서 더이상의 공간이 남지 않을 수도 있다 --> **stack overflow!!**

```
return 1
2*factorial(1)  ==> 2*1
3*factorial(2)  ==> 3*2*1
4*factorial(3)  ==> 4*3*2*1
factorial(4)    ==  4*3*2*1
```

<br>

### Queue
---
- An abstract data type
- Basic operations: enqueue() and dequeue(), peek()
- FIFO structure: Fisrt in first out
- It can be implemented with dynamic arrays as well as with linked lists
- Important when implementing BFS algorithm for graph

#### Enqueue
Queue의 끝에 새 값들을 추가한다.

#### Dequeue
Queue의 맨 앞부터 삭제한다.

#### Peek
값을 삭제하지 않고 Queue의 맨 앞의 값만 가져온다.

### Applications
- When a resource is shared with several consumers (threads): store them in a queue --> ex) CPU scheduling
- 데이터가 두 프로세스간에서 동시에 전달되지 않을때(asynchronously)  --> ex) IO buffers
- Operational research applications or atochastic models relies heavily on queues.
- 운영체제가 관련된 한 queue는 매우 중요하다. 안드로이드에서는 실행되어야하는 프로세스들을 추적하기위해 queue들을 유지한다. Queue에 저장된 프로세스들은 FIFO방식으로 처리된다.

**Stack&Queue: The fundamental building block for most of the operating systems**
