## Queues
* **FIFO** (first in, first out)
* Enqueue & Dequeue

### Implementation(s)
* Array
* Doubly linked list
* Ring buffer
* Two stacks

### Array
* Array as storage
* Enqueue is simply an append(), almost always O(1)
* Dequeue is a removeFirst(), always O(n)

| Operations       | Best Case | Worst case |
| ---------------- | --------- | ---------- |
| enqueue          | O(1)      | O(1)       |
| dequeue          | O(n)      | O(n)       |
| Space complexity | O(n)      | O(n)       |

### Doubly linked list
* Doubly linked list as storage
* Enqueue is simply an append(), always O(1)
* Dequeue is a removeFirst, always O(1)

| Operations       | Best Case | Worst case |
| ---------------- | --------- | ---------- |
| enqueue          | O(1)      | O(1)       |
| dequeue          | O(1)      | O(1)       |
| Space complexity | O(n)      | O(n)       |

* Dequeuing and Enqueuing are always O(1)
* Extra storage for next and previous references
* Enqueuing requires relatively expensive dynamic allocation

### Ring buffer
* [Example implementation](https://github.com/raywenderlich/swift-algorithm-club/blob/master/Ring%20Buffer/RingBuffer.swift)
* Read and Write pointers
* Fixed size array storage

| Operations       | Best Case | Worst case |
| ---------------- | --------- | ---------- |
| enqueue          | O(1)      | O(1)       |
| dequeue          | O(1)      | O(1)       |
| Space complexity | O(n)      | O(n)       |

* Same time complexity as linked list implementation
* Has fixed size, and enqueuing fails when full
* Has much better space complexity when compared to linked list implementation

### Double stack
* Enqueuing goes into the right stack
* Dequeuing **reverses** the right stack and places it into the left stack
* Enqueue is simply append in right stack, always O(1)
* Dequeuing is a little bit more complex:
  * First, it checks if the **left** stack is empty
  * If not, pops left stack's last element
  * If empty, sets `leftStack = rightStack.reversed()` and cleans the right stack. Then, pops left stack's last element
  * Reversing is O(n), but it does not happen much often (since you first empty out the left array)
  * The overall complexity is still [amortized](https://en.wikipedia.org/wiki/Amortized_analysis) O(1)

> In computer science, amortized analysis is a method for analyzing a given algorithm's complexity, or how much of a resource, especially time or memory, it takes to execute. The motivation for amortized analysis is that looking at the worst-case run time per operation, rather than per algorithm, can be too pessimistic.


| Operations       | Best Case | Worst case |
| ---------------- | --------- | ---------- |
| enqueue          | O(1)      | O(1)       |
| dequeue          | O(1)      | O(1)       |
| Space complexity | O(n)      | O(n)       |

* Dequeuing is O(1) instead of the *Array*'s O(n)
* Does not have the fixed size constraint like *Ring Buffer*
* Unlike *Linked List*, it does not have to mantain references to nodes, and as the elements are next to each other in memory blocks, some elements will be loaded on cache on first access, which reduces the access time.
