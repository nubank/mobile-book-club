## Stacks
* **LIFO** (last in, first out)
* Push & Pop

### Implementation
* Array as storage
* Push is simply an append()
* Pop is simply a popLast()
* Both are amortized O(1): array has to realloc memory when it is full (for push only), and this is a O(n) operation.

### Why not collection
* Stack's purpose is to limit the way we access the elements. Being a collection opens the access to *subscripts* and *iterators*.
* Altough it is not implemented in the book, we considered Stacks as Sequences and made a quick implementation.

### Bonus
* ExpressibleByArrayLiteral
	* Requires an init that receives as argument an Array
	* In Swift standard library, there are protocols for the other primitive type (e.g.: `ExpressibleByIntegerLiteral`)
