# Data structures and algorithms review 2

## BIG-O notation 

Predict what the following code will print AND indicate the BIG O notation for each based on loop used ) and method(s) called in the loop.
```
// Initialize
Stack<Integer> testStack = new Stack<>(); 
ArrayList<Integer> testArrayList = new ArrayList<>();
Queue<Integer> testQueue = new ArrayDeque<>();
LinkedList<Integer> testList = new LinkedList<>();
```

``` 
int N=5; // A 
for (int i=0; i<N; i++) { testStack.push(i); }
System.out.println(testStack);
```
- Prints [4, 3, 2, 1, 0]. LIFO order
- Big O: O(N)

```
testStack = new Stack<>(); // B
for (int i=0; i<N; i++) {
    for (int j=0; j<N; j++) {
        testStack.push((i*10) + j);
    }
}
System.out.println(testStack);
```
- Prints [[44, 43, 42, 41, 40], [34, 33, 32, 31, 30], [24, 23, 22, 21, 20], [14, 13, 12, 11, 10], [4, 3, 2, 1, 0]]
- Big O: O(N^2)

```
N=1000; // C
for (int i=1; i<N; i*=2) {
    testQueue.enqueue(i);
    testArrayList.add(i);
}
System.out.println(testQueue);
```
- Prints [1, 2, 4, 8, 16, ..., 512]
- Big O: O(log N)

```
int count=0; // D
int N=7;
testStack = new Stack<>();

for (int i=2; i<8; i++) { // Prints [7, 6, 5, 4, 3, 2], Big O: O(N)
    testStack.push(i);
}

testArrayList = new ArrayList(Arrays.asList(1,2,3,4,5,6,7,8,9));  
M = testArrayList.size();

while (!testStack.isEmpty()) {
    if ( testArrayList.contains(testStack.pop()/2) ) { // [3.5, 3, 2.5, 2, 1.5, 1]
        count++;
    }
}
System.out.println("Count = " + count);
```
- Prints Count = 3
- Big O: O(N^2 )

Note:
- The `testArrayList.conains()` is O(N), and chained with while loop, thus O(N^2)
- The for loop does not scale over 8, which is just a group of basic steps, thus O(1)

-----

### Performance evaluation

You have been given two data structures (A, B) that have been implemented in Java. Each has an `addAll()` and a `contains()` method. The big O notation and the basic instruction time is:

- **Data structure A:** addAll() takes 12us of `O(n^2)`, contains takes 30us of `O(log N)`
- **Data structure B:** addAll() takes 400us of `O(sqrt(N))`, contains takes 200us of `O(1)`

Given that you will add all the elements (N) to each structure once, but search the array 500 (M) times, which data structure gives the best overall performance in terms of time using the values of N=100 and M=500 ? 

1. `addAll()` adds everything to data structure once
2. `addAll()` will take an array of 100 elements (N = data size)
3. `contains()` would search the entire data structure in worst case
4. `contains()` will be ran for 500 times (N = 1)

#### Data structure A:
- `addAll()`: (100^2)*12
- `contains()`: (log_2 30)*500

#### Data structure B:
- `addAll()`: sqrt(100)*400
- `contains()`: 200*500

The data structure that takes accumulatively lowest time would perform the best