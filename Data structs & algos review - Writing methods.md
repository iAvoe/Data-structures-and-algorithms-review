# Data structures and algorithms review 2

## Writing code

A limited implementation of a LinkedList class is shown below:
```
class Node<T> {
    T value;
    Node<T> next;
    public Node(T val, Node n) {
        value = val;
        next = n;
    }
}

class MyLinkedList<T> {
    private Node<T> first;
    private Node<T> last;
    private int numberOfElements;
    
    public MyLinkedList() {
       first = null;
       last = null; 
       numberOfElements = 0;
    }
    public void add(T newItem) {
        if (first == null) {
            first = new Node(newItem, null);
            last = first;
        }
        else {
            last.next = new Node(newItem, null);
            last = last.next;
        }
        numberOfElements++;
    }
}  
```
### Write a public Boolean method called contains that will determine if the object is stored in the LinkedList.

```
public boolean contains(T item) {
    if (first == null) { return false; }
    Node<T> current = first;
    int elementRemains = numberOfElements;
    while (elementRemains > 0) {
        if (item.equals(current.value)) { return true; }
        current = current.next;
        elementRemains--;
    }
    return false;
} 
```

### Write a test under the main method

#### A LinkedList of String: John, Mary, Jasmine, Nahren, Ishwar, and searching for “Jasmine” (should return true) and “Stephen” (should return false).

```
public static void main(String[] args) {
    MyLinkedList<String> names = new MyLinkedList<>();
    names.add("John");
    names.add("Mary");
    names.add("Jasmine");
    names.add("Nahren");
    names.add("Ishwar");
    System.out.println(names.contains("Jasmine")); // true
    System.out.println(names.contains("Stephen")); // false
}
```

### Write a method that will convert the LinkedList into an ArrayList of the same type, as well as main method to test it.
```
public ArrayList<T> toArrayList() {
    ArrayList<T> result = new ArrayList<>();
    Node<T> node = first;
    for (int i=0; i<numberOfElements; i++) {
        result.add(node.value);
        node = node.next;
    }
    return result;
}

public static void main(String[] args) {
    ... Continue from the previous main method test ....
    ArrayList<String> convertedAryLst = names.toArrayList();
    System.out.println(convertedAryLst); // [John, Mary, Jasmine, Nahren, Ishwar]
}
```
#### What is the Big O notation for space complexity of this method?
- O(N). It loads a arrayList internally

#### What is the Big O notation for the time complexity of this method?
- O(N). It has a for loop over the amount of elements

### Use the following interface:
```
interface Matcher<T> {
    boolean match(T item);
}
```

**...to write a `findAll()` method that will return another LinkedList of all the items that match a passed in Lambda expression**
```
public LinkedList<T> findAll(Matcher<T> matcher) {
    if (first == null) { return null; }
    // Note: The matcher interface method already require input of the item to find
    LinkedList<T> result = new LinkedList<>();
    Node<T> current = first;
    while (current != null) {
        if (matcher.match(current.value)) {
            result.add(current.value);
        }
        current = current.next;
    }
    return result;
}

@Override
public String toString() {
    if (first == null) { return "[]"; }
    String result = "[";
    Node<T> node = first;
    for (int i=0; i<numberOfElements; i++) {
        result += node.value;
        if (node.next != null) {
            result += ", ";
        }
        node = node.next;
    }
    return result + "]";
}
``` 

### Write a main method to test letter starts with "J", then contains "a":
```
// Use the findAll method with a lambda that matches strings starting with "J"
MyLinkedList<String> matchedNames = names.findAll(item -> item.startsWith("J"));
System.out.println(matchedNames.toString());  // Output: [John, Jasmine]

matchedNames = names.findAll(item -> item.contains("a"));
System.out.println(matchedNames.toString());  // Output: [Mary, Jasmine, Nahren, Ishwar]
```

### Create an instance of the Queue class and add 100000 integers from 1 to 100000 to the Queue and then remove all elements until the Que is empty. Do the same thing with an ArrayList of integers. Explain the timing with Big O:
```
long st, ft;

// Test Queue dequeue timings

Queue<Integer> q = new Queue<>();
for (int i=1; i<=100000; i++) { q.enqueue(i); }
st = System.currentTimeMillis();
while (!q.isEmpty()) {
    q.dequeue();
}
ft = System.currentTimeMillis();
System.out.printf("Total time for dequeue 100000 items: %d ms\n", ft-st);

// Test arrayList remove timines

ArrayList<Integer> a = new ArrayList<>();
for (int i=1; i<=100000; i++) {
    a.add(i);
}
ArrayList<Integer> d = new ArrayList<>(a); //System.out.println(d.size()); // 100000
st = System.currentTimeMillis();
while (!a.isEmpty()) {
    a.remove(0);
}
ft = System.currentTimeMillis();
System.out.printf("Total time for removing 100000 items from first: %d ms\n", ft-st);

st = System.currentTimeMillis();
for (int i=99999; i>=1; i--) {
    d.remove(i);
}
ft = System.currentTimeMillis();
System.out.printf("Total time for removing 100000 items from last: %d ms\n", ft-st);
```

**Output:**
Total time for dequeue 100000 items: 0 ms
Total time for removing 100000 items from first: 110 ms
Total time for removing 100000 items from last: 2 ms

**So in general:**
- Dequeue in a Loop that is the length of the queue: O(N)
- Remove from head of arrayList is O(N), since array-shift happens after each removal, then folding happens after current arrayList has half of its previous values: O(N^2)
- Remove from tail of arrayList is O(1), this time only folding happens: O(N)

### Using the SimpleBinaryTree class, write a public/private size method that will return the number of element nodes in the tree, note that the private method is recursive

```
/**
 * Get size of the tree recursively
 * @param node The object that is not null
 * @param total The accumulating value of total size
 */
private int size(BTNode<T> node, int total) {
    if ( node == null ) { return total; } // Negative base case, don't return 0 here
    total++; // Positive base case
    total = size(node.leftTree, total); // Path 1/2
    total = size(node.rightTree, total); // Path 2/2
    return total; // Converge
}
public int size() { return this.size(root, 0); }
```
