## Data Structure

>Data structure: to store data in an **efficient** way.
>
>We often have the intuition --> if we want to make an algorithm fast, we have to optimize it.
>
>Data structures make sure the running time will better.

올바른 데이터 구조를 통해 효율적으로 데이터를 저장하면 처리 속도를 향상시킬 수 있다.
<br>
<br>


>* Dijkstra algorithm
>
>Without a proper data structure (heap / priority queue) the running time would be quadratic // O(N^2)
>
>Priority queue approach makes sure the running time will be far better // O(N*logN)

한 예로 Dijkstra algorithm에서 적절한 데이터 구조냐 아니냐에 따라서 처리 속도가 확연하게 달라질 수 있다.

데이터의 수가 많아질 수록 차이가 더 선명해짐
<br>
<br>

>* Abstract data type
>
>We just define what methods / funcitons the data structure will have, so we define the basic behavior.
>
>IMPORTANT: it is just the model, ADT does no sepecify the concrete implmentation or programming language.
>
>For example: stack -> push() pop() peek()

ADT는 특정한 데이터 구조를 위한 모델일 뿐이다. 우리는 ADT로 이 데이터 구조가 가지고 있을 method/function들이 어떤 것들이 있는지를 정의할 수 있다.

만약에 데이터 구조가 stack이라면 우리는 push(), pop(), peek()를 사용할 수 있음을 안다.

([실제 자료를 내부적으로 어떻게 저장하고 처리하는지에 대한 것은 따지지 않고, 이 자료형을 이용할 때의 기능만 이야기하는 것](https://juff.tistory.com/entry/ADTAbstract-Data-Type))


>* Data Structure
> The concrete implementation, the actual representation of the data
> The aim is to be able to store and retrieve data in an efficient manner
> What we want: to be able to insert / find items in O(1) time complexity and to be able to retreive items in O(1) as well
> For example: arrays, linked lists, binary trees...

Date Structure는 데이터의 실제 표현이며 구체적 구현이다.

---


Abstract Data Types | Data Structure
--------------------|-----------------
Stack               | array, linked list
Queue               | array, linked list
Priority queue      | heap
Dictionary/hashmap  | array

ADT and Data Structure are **not independent**rom each other.

ADT are the specification and every ADT have an underlying data structure that's going to implement the behavior that has been specified in the ADT.
