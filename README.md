Queue Using Dynamic Array

A generic Queue implementation in C++ built using a custom Dynamic Array as the underlying data structure.

The project demonstrates how a Queue can reuse an existing data structure instead of implementing memory management and array operations from scratch.

Overview

The clsMyQueueArr<T> class uses:

clsDynamicArray<T> _MyList;

The Queue follows the FIFO (First In, First Out) principle:

Front                         Back
  ↓                            ↓
[10] → [20] → [30] → [40]

The first element inserted is the first element removed.

Template Support

The Queue uses a C++ template:

template <class T>
class clsMyQueueArr

This allows it to work with different data types:

clsMyQueueArr<int> Numbers;
clsMyQueueArr<string> Names;
Main Operations
Push

Adds an element to the back of the Queue.

void push(T Item)
{
    _MyList.InsertAtEnd(Item);
}
Pop

Removes the first element from the Queue.

void pop()
{
    _MyList.DeleteFirstItem();
}
Front

Returns the first element:

T front()
{
    return _MyList.GetItem(0);
}
Back

Returns the last element:

T back()
{
    return _MyList.GetItem(Size() - 1);
}
Additional Operations

The class also provides:

Print() – Prints all elements.
Size() – Returns the current size.
IsEmpty() – Checks whether the Queue is empty.
GetItem() – Retrieves an element by index.
Reverse() – Reverses the Queue.
UpdateItem() – Updates an element.
InsertAfter() – Inserts an element after a specific index.
InsertAtFront() – Inserts an element at the beginning.
InsertAtBack() – Inserts an element at the end.
Clear() – Removes all elements.
Data Structure Relationship

This implementation builds on the Dynamic Array created previously:

Queue
  ↓
Dynamic Array

The Dynamic Array is responsible for:

Dynamic memory allocation
Resizing
Insertion
Deletion
Element access
Memory management

The Queue focuses on providing the Queue interface and FIFO behavior.

Complexity

Based on the current clsDynamicArray implementation:

Operation	Complexity
push()	O(n)
pop()	O(n)
front()	O(1)
back()	O(1)
Size()	O(1)
IsEmpty()	O(1)
GetItem()	O(1)
Reverse()	O(n)
UpdateItem()	O(1)
InsertAfter()	O(n)
InsertAtFront()	O(n)
InsertAtBack()	O(n)
Clear()	O(1)*

push() can be O(n) because InsertAtEnd() resizes the array every time an element is added.

pop() is O(n) because deleting the first array element requires shifting the remaining elements.

Concepts Practiced
Queue
FIFO
Dynamic Arrays
Templates
Dynamic Memory Allocation
Pointers
Array Resizing
Insertion and Deletion
Object-Oriented Programming
Code Reusability
Abstraction
Time Complexity
Learning Goal

The main goal of this implementation was to understand how a Queue can be built using a Dynamic Array and how an existing data structure can be reused to create a higher-level data structure.

This implementation also allows comparison between:

Queue using Doubly Linked List
              vs
Queue using Dynamic Array

Both provide the same Queue concept, while their underlying implementations have different performance characteristics.

Related Implementation

This Queue depends on the custom:

clsDynamicArray<T>

implementation created as part of the same Data Structures practice series.
