# Data structures and algorithms review 2

## Code tracing and evaluation

### Evaluate placement in a Binary Tree. The following code uses the SimpleBinaryTree class

#### Show the structure of the tree by filling in the diagram below:  
```
SimpleBinaryTree <String> mtree = new SimpleBinaryTree <String>((s1,s2) -> s1.compareTo(s2));
String[] sdata = {
    "Melinda",
    "Bobby",
    "Alex",
    "Sade",
    "Zelda",
    "Carlos",
    "Morayo",
    "Prim",
    "Jaswinder",
    "Candice"
};
for (int i = 0; i < sdata.length; i++) { mtree.add(sdata[i]); }
```

1:

    Melinda

2:

        Melinda
        /
    Bobby

3:

            Melinda
            /
        Bobby
        /
    Alex

... 6:

            Melinda
            /     \
        Bobby      Sade
         /  \        \
     Alex   Carlos   Zelda

... Final:

Here is another binary tree:
    
               Melinda
            /          \
        Bobby           Sade
       /    \          /    \
     Alex Carlos     Morayo Zelda
          /   \        \
      Candice Jaswinder Prim 
    
The toString method would show as:

Alex
Bobby
Candice
Carlos
Jaswinder
Melinda
Morayo
Prim
Sade
Zelda

#### Is this a balanced binary tree?
- Yes, each left and right subtree extended from any node doesn't have a height difference more than 1

### Show the structure of a Min Heap (minimum value always at top):
```
Heap<Integer> h = new Heap <>();
int[] hdata = {5, 22, 4, 9, 12, 63, 3, 1};
for (int i = 0; i < hdata.length; i++) { h.add(hdata[i]); }
```

#### Heap Implementation:
```
class Heap<T extends Comparable> {
    ArrayList<T> aryLst;
    int count;
    Heap() {
        aryLst = new ArrayList<T>();  // Create the Heap
        count = 0;       // Heap is empty
    }
    /**
     * add a single item to the heap
     * @param item the item to be added
     */
    public void add(T item) {
        // 1. Add item to bottom/end of heap
        aryLst.add(item);
        // Get index of the most recently added item
        int currIdx = aryLst.size() - 1;

        // 2. Walk up the heap
        while (currIdx > 0) {
            // Calculate parent index
            int prenIdx = (currIdx - 1) / 2;
            // Max heap: Swap if the new element is smaller than its parent
            // if (aryLst.get(prenIdx).compareTo(aryLst.get(currIdx)) < 0)
            // Min heap: Swap if the new element is greater than its parent
            if (aryLst.get(prenIdx).compareTo(aryLst.get(currIdx)) > 0) {
                T temp = aryLst.get(currIdx);
                aryLst.set(currIdx, aryLst.get(prenIdx));
                aryLst.set(prenIdx, temp);
            }
            else break; // Already a heap, no need to loop
            // Move upwards the heap
            currIdx = prenIdx;
        }
    }
    
    @Override
    public String toString() {
        return aryLst.toString();
    }
}
```

#### Steps to add:

1. Add 5:  `aryLst = [5]`
2. Add 22: `aryLst = [5, 22]`
3. Add 4:  `aryLst = [5, 22,4]`
            → `[4, 22,5]`
4. Add 9:  `aryLst = [4, 22,5, 9]`
            → `[4, 9,5, 22]`
5. Add 12: `aryLst = [4, 9,5, 22,12]`
6. Add 63: `aryLst = [4, 9,5, 22,12,63]`
7. Add 3:  `aryLst = [4, 9,5, 22,12,63,3]`
            → `[4, 9,3, 22,12,63,5]`
            → `[3, 9,4, 22,12,63,5]`
8. Add 1:  `aryLst = [3, 9,4, 22,12,63,5, 1]`
            → `[3, 9,4, 1,12,63,5, 22]`
            → `[3, 1,4, 9,12,63,5, 22]`
            → `[1, 3,4, 9,12,63,5, 22]`
