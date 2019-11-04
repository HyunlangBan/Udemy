## Arrays

### Arrays:
- Collection of elements / values
- index가 있다 -> index를 통한 random access가 가능하다.
- 같은 data type만 저장이 가능하다.
- 1차원부터 다차원까지 다양한 차원이 가능하다.
- Dynamic array: array의 사이즈는 다이나믹하게 변한다.
- Application: lookup tables / hashtables, heaps


### Multidimenshional arrays:
- numbers[row index][column index]

### Advantages:
- index를 사용하면 매우 빠르게 데이터에 접근이 가능하다. --> O(1)
   + linked list로 하면 맨 마지막까지 찾아야할때 O(N)
- 구현, 사용이 쉽고 매우 빠르다.
- 계속해서 아이템을 추가하고 인덱스를 지닌 아이템들을 원할때 array를 사용

### Disadvantages:
- Compile time에 Array의 사이즈를 알아야한다. --> It is not so dynamic data structure.
- Array가 꽉 차면 더 큰 array를 만들어야 하는데 그러려면 기존의 것을 하나하나 카피 한 후 붙여넣기 해야한다.
  => O(N) operation
 다른 데이터 타입끼리는 저장이 불가능
 
 ### Arrays operation: add
 Array가 꽉차기 전까지 값을 추가할 수 있다.
 
Value | Index
------|-------
34    | 0
12    | 1
120   | 2
-5    | 3
|     | 4
|     | 5
|     | 6
|     | 7

낮은 인덱스부터 순차적으로 채웠을 때: very fast O(1) operation

이미 있는 인덱스에 새로운 값을 삽입할때: insert(23,1) #index1에 23을 삽입

Value | Index
------|-------
34    | 0
23    | 1
12    | 2
120   | 3
-5    | 4
|     | 5
|     | 6
|     | 7

새로 삽입한 다음의 값들을 모두 한칸씩 뒤로 이동시켜야한다. --> O(N) time complexity

### Arrays operation: remove
add와 동일하게 마지막 item을 삭제하면 매우 간단하다 --> O(1) time complexity
하지만, 기존의 index에 있던 값을 삭제하면 그 밑의 값들을 모두 위로 한칸씩 이동시켜야 하므로 복잡해진다 --> O(N) time complexity

remove(1)

Value | Index
------|-------
34    | 0
|      | 1
12    | 2
120   | 3
-5    | 4
|     | 5
|     | 6
|     | 7


**결론: array는 가장 끝의 인덱스의 값을 더하거나 삭제할 때는 매우 효율적이고 빠르지만 중간 인덱스의 값을 건드릴때는 다시 값들을 이동시켜야하므로 그다지 좋은 방법은 아니다.**

### Arrays in Python:
Python doesn't have a native array data structure but it has a list which is more general and can be used as multi-dimensional array as well.

```python
numbers = [10,20,300,40.5,50]
# 원래 array는 같은 데이터 타입만 가능하지만 python은 문자열, 실수, 자연수 모두 가능하다.

# random indexing --> O(1) get items if we know the index
# print(numbers[4])

# numbers[1] = 'Adam' --> [10, 'Adam', 300, 40.5, 50] --> Array 설명처럼 추가 한 값 뒤의 값들이 한칸 밀리는 줄 알았는데 그냥 대체된다. native array가 아니라서 그런가보다.

#O(N) search running time --> index를 모르면 linear time complexity
maximum = numbers[0]
for num in numbers:
    if num > maximum:
        maximum = num
        
print(maximum)
```
