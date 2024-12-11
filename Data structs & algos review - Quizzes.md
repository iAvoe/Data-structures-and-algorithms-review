# Data structures and algorithms review

## Quizzes

### When applied to an array a[ ] of integers, the pseudo code:
```
Boolean sort = true
int k = 0
While sort == true and k < a.length-1
If a[k] > a[k+1] Then
sort = false
End If
k = k +1
End While
```
- Will determine if the array is arranged in ascending order

### If a[] is integers, the following pseudo code describes a strategy for:
```
int k = 0
int m = 1
While m < a.length
If a[m] < a[k] Then
k = m
End If
m = m+1
End While
```
- Determines the index of the smallest array element

### What will be the value of `x[1]` after the following code is executed?
```
int[] x = {22, 33, 44};
arrayProcess(x[1]);
...
public static void arrayProcess(int a) {
    a = a + 5;
}
```
- [x] 33; The variable is passed by value
- [ ] 38; The variable is passed by reference

### What would be the results of the following code?
```
final int SIZE = 25;
int[] array1 = new int[SIZE];
// Filling array1 with some values
int value = 0;
for (int a=0; a<=array1.length; a++) {
    value += array1[a];
}
```
- [ ] value contains the lowest value in array1
- [ ] This would cause the program to crash
- [ ] value contains the highest value in array1
- [x] value contains the sum of all the values in array1

### For `String[] str = {"abc", "def", "ghi", "jkl"};`, what would be the value of `str[2]`: 
- [ ] "def"
- [x] "ghi"
- [ ] A reference to the String "def"
- [ ] A reference to the String "ghi"

### The insertion sort works by:
- repeatedly taking the first value in the unsorted portion of the array and placing it at its proper place in the part of the array that is already sorted

### The quick sort works by:
- partitioning the unsorted portion of the array into two sublists and a pivot and recursively sorting the two sublists

### The Selection sort works by:
- repeatedly locating the smallest value in the unsorted portion of the array and moving it toward the lower end of the array

### The bubble sortworks by:
- repeatedly comparing adjacent items and swapping them so smaller values come before larger values

### The binary search algorithm:
- Cannot be used to search an array that is not sorted

### The linear search algorithm:
- Is slower than binary search, but works on unsorted arrays

### A search algorithm
- [x] Is a way to locate a specific item in a larger collection of data
- [ ] Is rarely used with arrays

### The role of the partition (array, start, end) method in quick sort is to:
- [ ] identify the position of the largest value in the part of the array that lies between start and end
- [ ] sort the segment of the array between start and end
- [ ] split the array into two sorted sublists on either side of the pivot element
- [x] None of the above. The partition method does not directly sort the array, nor focus to find the latgest value

### A search for an item X in an array starts at the lower end of the array, then looks for X by comparing array items to X in order of increasing subscript. It's a:
- Sequential search / Linear search

### A contigous segment of an array is given by specifying two subscripts, lower and upper. Which of the following expressions gives the subscript of the array element that is three quarters of the way from lower to upper?

- lower + (upper - lower) * 3/4. This 3/4 position is in respect of `array[0]` to `array[lower]`, thus adding "lower" is required

### On average, performing a sequential search on an array of N elements will require:
- N/2 comparisons

### The addition of two integers
- [ ] is a basic step if there is a fixed bound on the size of the integers
- [ ] is a basic step in algorithms that use addition to define more complex operations such as multiplication
- [ ] is always a basic step
- [x] All of the above

### What does `double[] array1 = new double[10];` do: 
- [ ] Declares array1 to be a reference to an array of double values
- [ ] Will allow valid subscripts in the range of 0-9
- [ ] Creates an instance of an array of 10 double values
- [x] All of the above

### What is the value of a:
```
int[] x = { 55, 33, 88, 22, 99, 11, 44, 66, 77 };
int a = 10;
if (x[2] > x[5]) a = 5;
else a = 8;
```
- (88 > 11) is valid, thus a==5

###  When an array is passed to a method
- [ ] It is passed just as an object
- [ ] The method has direct access to the original array
- [ ] A reference to the array is passed
- [x] All of the above.

Note: Arrays are objects in java; Arrays in Java are mutable, which allows direct access, and thus the reference is passed to method

### What do you normally use with a partially-filled array?
- [ ] An accumulator
- [ ] A class that does nothing but manage the array
- [x] An accompanying integer value that holds the number of items stored in the array (size or length)
- [ ] An accompanying parallel array

### Given that String[] str has been initialized, to get a copy of `str[0]` with all characters to upper case, use:
- [ ] str[0].toUpperCase();
- [ ] str[0].upperCase();
- [x] str.toUpperCase();
- [ ] str.uppercase();

### How many rows and how many columns are in here: `int [][] points = new int[10][20];`
- 10 rows and 20 columns 

### If numbers is a 2D array, which of the following would give the length of column r? 
- [ ] numbers.length
- [x] numbers[r].length
- [ ] numbers.length[r]
- [ ] numbers[r].length()

### Java limits the number of dimensions that an array may have to 15.
- False

### What will be the result of executing: `int[] x = {0, 1, 2, 3, 4, 5};`
- [ ] The value of x[1] will be 0, x[2] will be 0, x[3] will be 0, x[4] will be 0, x[5] will be 0, and x[6] will be 0
- [x] An array of 6 values ranging from 0-5 and referenced by the variable x will be created

### Which of the following is a correct method header for receiving a two-dimensional array as an argument?
- [ ] `public static void passArray(int intArray[2])`
- [ ] `public static void passArray(int[1][2] intArray)`
- [ ] `public static void passArray(int[] intArray)`
- [x] `public static void passArray(int intArray[][])`
- [x] `public static void passArray(int[][] intArray)`

Note: `int intArray[][]` is a C-style declaration that also works in Java, but compiler would recommend a Java native style

-----

### Lists, Linked Lists

#### The position of an item within a list is called its
- [ ] rank
- [ ] level
- [x] index
- [ ] number

#### The int indexOf(Object o) method of the List interface
- [ ] adds an object to a list and returns the index of the newly added object
- [ ] uses binary search to locate the given object, and then returns its index
- [x] searches a list for the occurrence of an object and returns its index

#### A list in which each stored element is associated with a reference to its successor is called 
- [x] a linked list
- [ ] an array list

#### To allocate storage for their elements, linked lists use
- [ ] contiguous allocation
- [x] linked allocation
- [ ] expandable allocation

Note: ArrayLists uses contiguous and expandable allocation

#### In java, the linked lists, has its first node in a list index of:
- [ ] -1
- [x] 0
- [ ] 1

#### In a linked list, the successor of a node X
- is the node that comes after X, and may not exist

#### The logic to remove the 1st node in a non-empty linked list is:
- [ ] delete the node by setting the head reference to null: `head = null;`
- [x] move the head reference one node forward: `head = head.next;`
- [ ] move the successor reference in the head node one node forward: `head.next = head.next.next;`
- [ ] set a reference `pred` to the predecessor of the node you want to remove, and set the successor of pred to the successor of the head

#### To remove a node X with index 1 or greater from a linked list:
- set a reference pred to the predecessor of the node you want to remove, and set the successor of pred to the successor of X

#### In a linked list implementation using a reference `first` to point to the first node of the list, a method `isEmpty()` can test to see if the list is empty by executing the `statement(s)`:
- `return first == null;`

#### To remove a node with a positive index k from a linked list, 
- [ ] start a reference r at the head of the list, walk r forward k steps, and then set r to null
- [ ] decrement k by 1, and then use recursion
- [x] Set the successor node in k-1 equal to the value in the successor in node k
- [ ] decrement k by 1, and set the reference to the node to be removed to null

#### A circularly linked list makes it easy to
- jump from the last node to the first

#### The tail of a list
- [ ] is a synchronized subclass of the LinkedList class
- [ ] is what you get when take a list and remove its head
- [ ] is an instance of a class that implements the ListTail interface
- [x] None of the above

-----

### Recursion

#### In many recursive operations on lists,
- [ ] some operation that does not require recursion is performed on the head element
- [ ] a recursive call is made on the tail of the list
- [ ] the base case of the recursion corresponds to the empty list
- [x] All of the above

#### In order to use recursion on linked lists
- [x] no changes to the node class are necessary
- [ ] the class that represents nodes must implement the Repeatable interface
- [ ] it is necessary to modify the class that represents nodes, by adding a reference needed to support recursion

#### When using recursion on linked lists
- [ ] the recursive method should be one of the methods specified in the List interface
- [x] the recursive method should be made private, and should be called by a public non-recursive method
- [ ] the linked list class is subclassed, and then the recursive method overrides a method of the same name in the list class
- [ ] the recursive method should not call itself outside of its base case

#### A recursive computation of the size of a list can work as follows:
- [x] if the list is empty, return zero; otherwise, recursively compute the size of the tail, add one, and return the result
- [ ] if the list is not empty, recursively compute the size of its tail, add one, and return the result
- [ ] set a local counter to zero; loop through the list, incrementing the counter by one at each element of the list; return the counter
- [ ] recursively compute the size of the tail, add one, and return the result

#### A linked list class uses a Node class with a successor reference next to represent nodes. A private recursive method `Node add(int index, E element, Node list)` takes a reference list (referring to the first in a chain of Node objects), adds a node containing the given element at the given index, and returns a reference to the first node of the resulting chain. Assume that index is nonnegative and is less or equal to the size of list. Under these circumstances, the add method should handle its non-base case (index is not 0) by:
- [ ] recursively returning the value add(index, element, list.next)
- [ ] recursively returning the value add(index-1, element, list)
- [x] setting list.next to add(index-1, element, list.next) and returning list
- [ ] setting list.next to add(index, element, list.next) and returning list

-----

### Stacks and Queues

#### A queue is a container that allows elements to be stored and removed
- in a first-in-first-out fashion

#### In a list implementation of a queue, the end of the list at which elements are added is called
- [ ] the front of the queue
- [ ] the head of the queue
- [x] the rear of the queue
- [ ] the bottom of the queue

#### The stack push operation
- [x] adds a single item to the stack
- [ ] is normally implemented through a hash set
- [ ] removes and returns an item from the stack
- [ ] returns the item at the top of the stack, but does not remove it

#### The stack empty operation
- [ ] checks to see if there is at least one item on the stack
- [ ] removes all elements from the stack
- [ ] destroys the stack and creates a new empty one in its place
- [x] None of the above

#### The stack pop operation
- [ ] removes all items currently on the stack
- [ ] removes from the stack the number of elements specified by its integer parameter
- [x] extracts one element from the stack and returns it
- [ ] does not exist: There is no such stack operation

#### The stack class provided by the Java Collections Framework
- [x] cannot be used to instantiate a stack of int, or of any primitive type
- [ ] can be used to create stacks of int
- [ ] is not efficient, so its use is not recommended
- [ ] can be used to hold values of any type

#### In an implementation of a stack based on a singly-linked list, it is most efficient to add a new item so that
- [ ] the new item has the lowest index of all items in the list
- [ ] the new item is not duplicated by any other item already in the stack
- [ ] the items in the stack stay sorted in ascending order
- [x] the new item has the highest index of all items in the list

#### Which of the following operations is not a stack operation?
- [x] remove and return the item at a specified position
- [ ] set the element at the bottom of the stack to a specified value
- [ ] remove and return an item with a specified value
- [ ] All of the above: that is, none of the above are stack operations

#### A stack based on a linked list is based on the following code
```
class Node{
    String element;
    Node next;
    Node(String el, Node n) {
        element = el;
        next = n;
    }
}
Node top = null;
```
##### The code for implementing the operation void push(String x) can be written as
- [x] `top = new Node(x, top);`
- [ ] `if (top == full) { throw new RuntimeException("Overflow"); } else { top = new Node(x, top); }`
- [ ] `top = add(Node x);`
- [ ] `top.add(x);`


#### The operation for removing an item from a queue is called
- dequeue

#### In a queue implementation that uses an array of fixed size,

- [ ] the array must be made so large that the queue will never run out of space
- [ ] the array must be created from an ArrayList object
- [x] it is necessary to use the array as a circular buffer
- [ ] the queue must implement the List interface

-----

### Binary Trees

#### A binary tree is a collection of nodes in which
- each node has at least one predecessor and at most two successors

#### The direct predecessor of a node in a binary tree is called its
- [x] child
- [ ] root
- [ ] grandparent
- [ ] parent

#### In a binary tree,
- [ ] there may be any number of nodes with no predecessor
- [ ] there must be at most one node with no predecessor
- [x] there may be at most two nodes with no predecessor

Note: the root node is one, thus at most two

#### A node in a binary tree that has no children is called
- [ ] a twig
- [x] a leaf
- [ ] a single node
- [ ] barren

#### A binary tree traversal method that visits the root first, and then recursively traverses the left and right subtrees is called
- [ ] priority order traversal
- [x] preorder traversal
- [ ] top down traversal
- [ ] postorder traversal

#### A binary tree stores items that have a natural order in such a way that at each node X, all items stored in the left subtree of X are less than the item stored at X, and all items stored in the right subtree are greater than the item stored at X. Such a binary tree is called
- [ ] a red-black tree
- [ ] an AVL tree
- [ ] a priority queue
- [x] a binary search tree

#### An empty binary tree has height
- [ ] 1
- [x] 0
- [ ] -1
- [ ] None of the above: the height of an empty binary tree is not defined.

#### A binary tree with just one node has height
- [ ] -1
- [x] 0
- [ ] 1
- [ ] None of the above

#### Deleting the root of a binary search tree when the root is a leaf, then
- the reference to the root of the tree should be set to null

#### Deleting the root of a binary search tree when the root has one child, then
- the reference to the root of the tree should be set to point to the one child

#### Deleting the root of a binary search tree when the root has two children, then
- the root node removed, then the least node in the right subtree should be deleted and used to replace the root

#### A binary tree with no root
- [ ] must have exactly two nodes
- [ ] must have only one node
- [x] must be empty

-----

### ArrayLists

#### The ArrayList class method is used to insert an item is called:
- [x] add
- [ ] insert

#### The ArrayList class method that deletes an item is called:
- [x] remove
- [ ] delete

#### The ArrayList class is in the package:
- [ ] java.lang
- [ ] java.arraylist
- [x] java.util
- [ ] java.array

#### An ArrayList automatically expands in size to accommodate the items stored in it. 
- True

#### The code `ArrayList<String>[] a = new ArrayList<String>[100];`:
- [x] will not compile
- [ ] compiles and runs correctly, but is inefficient
- [ ] compiles and runs correctly and efficiently
- [ ] compiles correctly, but causes a runtime exception when the program is executed

Note: Correct declaration is `ArrayList<String>[] a = new ArrayList[100]; // Warning: unchecked cast`

#### The declaration `ArrayList<int> aL = new ArrayList<int>();`:
- [ ] compiles and runs correctly, but is not recommended
- [x] causes a compile-time error, because int is not an Object
- [ ] allows the programmer to create an ArrayList that holds integer types
- [ ] compiles correctly, but causes an exception to be thrown at run time

#### If you try to add an item to an ArrayList whose size is equal to its capacity:
- [ ] an exception that indicates that the ArrayList is full is thrown
- [ ] The method for adding the new item returns null
- [x] a new ArrayList object with twice the capacity is created, and the elements are moved to this new ArrayList.
- [ ] The method for adding the new item returns false

#### An ArrayList is so called because:
- [ ] you can pass it as a parameter to any method that expects an array
- [x] it is implemented as a class that uses an internal array to hold the elements of the list
- [ ] you can use array subscript notation to work with the ArrayList

Note: An ArrayList cannot be passed as a parameter to a method, and you cannot use array subscript notation

#### The difference between an array and an ArrayList is
- [ ] an array keeps track of its length while an ArrayList does not track comparable information
- [x] arrays have a fixed size and cannot grow to accommodate more elements
- [ ] an ArrayList uses a LinkedList to hold its elements, an array does not

#### The `boolean contains(E element)` searches ArrayList for a given element. The efficient & correct implementation of this method:
- [ ] returns 0 if the element is not found in the list
- [ ] uses binary search to locate the element
- [ ] throws an exception if the element is not found in the list
- [x] uses sequential search to locate the element


-----

### Generics

#### One of the advantages of using generics is that:
- [x] more data type problems can be uncovered at compile-time rather than at run time
- [ ] programs that use generic code require less effort in design and development
- [ ] programs that use generics are smaller when translated to byte code
- [ ] program that use generics execute faster than programs that do not

#### The automatic conversion of a primitive type to its corresponding wrapper, when being passed as parameter to a generic class is called:
- [ ] type wrapping
- [ ] autoconversion
- [x] autoboxing
- [ ] type promotion

#### When a generic method is called,
- [ ] the compiler uses information explicitly specified by the programmer, if available; otherwise, the type defaults to Object
- [ ] the compiler determines the actual types to use for the type parameters from the context
- [x] the programmer must explicitly specify the actual types to use for the type parameters

#### Which of the following statements are true?
- [ ] You cannot instantiate an object of a generic type
- [ ] You can declare references to arrays whose elements are of a generic type
- [ ] You cannot create arrays whose elements are instances of a generic type
- [x] All of the above

#### In a generic method, a type parameter is defined:
- [x] after the method's return type, and before the method's name
- [ ] inside the parentheses, along with the method's parameter variables.
- [ ] inside the body of the method, but before any local variables are declared
- [ ] before the method's return type

Note:
```
public static <T> void printArray(T[] array) {
    for (T element : array) {
        System.out.println(element);
    }
}
```

-----

### Hashcodes, hashsets, hashmaps

#### A hashcode of an object
- [ ] is the value returned when you store the object into a HashSet collection
- [x] is useful when storing objects in HashMaps, HashSets, and Lists
- [ ] is an integer that can be used to characterize an object and help identify it
- [ ] None of the above

#### If different objects can have the same hash code, then:
- [x] some HashSet buckets may have more than one object
- [ ] the operation of searching a HashSet becomes more efficient
- [ ] the HashSet add method will throw an IllegalStateException
- [ ] None of the above

#### LinkedHashSet differs from HashSet because the LinkedHashSet:
- [x] allows elements to be retrieved in the same order as they were added
- [ ] stores objects that have the same hash code in the same bucket
- [ ] is a subclass of LinkedList
- [ ] is a subclass of TreeSet

#### A HashMap
- [ ] is a subclass of Map that implements the HashCode interface
- [x] uses hash codes to store keys
- [ ] is a subclass of HashSet that implements the Map interface

Note: HashMap relies on the `hashCode()` method of the keys to perform efficient lookups.
Note: Both HashMap and HashSet are part of the Java Collections Framework

#### An entry in a map
- [ ] associates a key with a value
- [ ] may not share a key value with any other entry in the map
- [ ] is called a mapping
- [x] All of the above

#### One way to iterate through a Map is:
- [x] to obtain the set of keys for the stored elements, and then iterate through that set of keys
- [ ] to use an integer index in a for loop to step through the elements
- [ ] to obtain the Map's iterator and use it

Note:
```
Map<String, Integer> map = new HashMap<>();
// Add entries...

for (String key : map.keySet()) {
    int value = map.get(key);
    // Process key-value pair...
}
```

-----

### Comparable & comparators

#### The notation `<E implements Comparable<E>>`:
- [ ] will be rejected by the Compiler as an error
- [ ] is used when there is a recursive definition of the generic type E
- [x] declares a generic type that implements the Comparable interface

Note: This is a constraint on the type E. It means that E must implement the Comparable<E> interface, which allows objects of type E to be compared to each other.
```
public static <E extends Comparable<E>> void compare(E e1, E e2) {
    // Compare logic...
}
```

#### `Comparable<T>` is
- [ ] a library module that is useful in implementing generics
- [ ] a generic class that you can use to instantiate objects that can be compared
- [ ] a method defined in the Java class libraries that is used to compare objects of generic type
- [x] an interface defined in the Java class libraries

Note: `<T>` defines it as a generic interface with one type parameter. The full declaration for this interface looks like:
```
public interface Comparable<T> {
    public int compareTo(T o);
}
```

#### `Comparable` specifies:
- A single method, compareTo

-----



-----

### Collections and Looping

#### The 3 major categories of Java collections are:
- lists, sets, and maps

#### The enhanced for loop, when used on a collection:
- [ ] should be avoided because it incurs runtime overhead
- [x] is converted by the compiler to a traditional loop that uses an iterator
- [ ] throws an runtime exception

Note: Enhanced for loop has negligible overhead, and doesn't cause exception