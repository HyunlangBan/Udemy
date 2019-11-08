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
 
 
 ### Heap Memory
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
