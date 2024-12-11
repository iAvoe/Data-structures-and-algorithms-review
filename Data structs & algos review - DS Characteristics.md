# Data structures and algorithms review

## Data structure characteristics

| Types\Characteristics  | Support Rand-Access | Type of Sorting/Ordering             | Type of Searching           | Best Searching Strategy (Time cplx)   | Requires "new" to Resize |
|------------------------|---------------------|--------------------------------------|-----------------------------|---------------------------------------|--------------------------|
| Arrays                 | Yes                 | None                                 | None                        | O(N): Linear search                   | Yes (fixed size)         |
| Arrays (ordered)       | Yes                 | None                                 | None                        | O(log N): Binary search               | Yes (fixed size)         |
| ArrayLists             | Yes                 | Caller-defined (lambda/comparator)   | Built-in (e.g., contains()) | O(N): Linear search                   | No (dynamic resizing)    |
| ArrayLists (ordered)   | Yes                 | Caller-defined (lambda/comparator)   | Built-in (e.g., contains()) | O(log N): Binary search               | No (dynamic resizing)    |
| Linked Lists           | No                  | Caller-defined (lambda/comparator)   | Built-in (e.g., contains()) | O(N): Linear search                   | No (dynamic resizing)    |
| Linked Lists (ordered) | No                  | Caller-defined (lambda/comparator)   | Built-in (e.g., contains()) | O(N): Linear search                   | No (dynamic resizing)    |
| Stacks                 | No                  | LIFO (Last In, First Out)            | -                           | -                                     | No (dynamic resizing)    |
| Queues                 | No                  | FIFO (First In, First Out)           | -                           | -                                     | No (dynamic resizing)    |
| Binary Trees           | No                  | Caller-defined (lambda/comparator)   | Built-in (e.g., contains()) | O(log N): Binary search               | No (dynamic resizing)    |
| HashSets               | Yes                 | None (buckets used)                  | Built-in (e.g., contains()) | O(1): Find bucket, then linear search | No (dynamic resizing)    |
| Heaps                  | No                  | Min heap / Max heap (caller-defined) | Built-in (e.g., contains()) | O(log N): Heap-like binary search     | No (dynamic resizing)    |

## Time complexity to add and remove

| Types\Characteristics  | Time Complexity to Add an Item                           | Time Complexity to Remove an Item          |
|------------------------|----------------------------------------------------------|--------------------------------------------|
| Arrays                 | O(1): Adding to empty slot; O(N): copying or resizing    | O(N): Find item and shift elements         |
| ArrayLists             | O(1): Add to the end; O(N): shifting for resizing        | O(N): Find item and shift elements         |
| Linked Lists           | O(1): Add to the end; O(1): Update links                 | O(1): Update links after removal           |
| Linked Lists (ordered) | O(1): Find item; O(N): shifting elements after insertion | O(1): Update links after removal           |
| Stacks                 | O(1): Add to the top                                     | O(1): Removing always takes constant time  |
| Queues                 | O(1): Add to the end                                     | O(1): Removing always takes constant time  |
| Binary Trees           | O(log N): Find item; O(1): re-link parent/child          | O(log N): Find item & re-link parent/child |
| HashSets               | O(1): Hash and add to the bucket                         | O(1): Find and remove from the bucket      |
| Heaps                  | O(log N): Reconfigure heap after adding                  | O(log N): Reconfigure heap after removing  |

## Advantages and use cases

| Types\Characteristics   | Advantages                                           | Use case                                           |
|-------------------------|------------------------------------------------------|----------------------------------------------------|
| Arrays                  | Fast random access, simple implementation            | Anywhere when a fixed size is enough               |
| ArrayLists              | Dynamic size & fast random access                    | Anywhere when a fixed size isn't enough            |
| Linked Lists            | Efficient insertion and deletion in O(1)             | Anywhere when resizing is frequent                 |
| Stacks                  | Efficient push, pop in O(1)                          | Editing softwares' "restorable history of actions" |
| Queues                  | Efficient enqueue, dequeue in O(1)                   | Task scheduling, printing                          |
| Binary Trees            | Efficient search, insertion, deletion                | File systems, huffman coding                       |
| HashSets                | Fast lookup times in O(1)                            | Checking element exists in a large pool of data    |
| Heaps                   | Efficient insertion and extraction of the min/max    | Sorting and Shortest path algorithms               |
