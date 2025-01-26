# Heap

A heap is a tree based data structure which is a complete binary tree (all levels of the tree are filled except last level. Last level of the tree is filled left to right). A heap can be either a max heap or a min heap.

## Min Heap
Value of parent <= value of child. Root node is the smallest


<img src="https://media.geeksforgeeks.org/wp-content/uploads/20201106115157/MinHeap.jpg" />


## Max Heap

Value of parent >= value of child. Root node is the biggest

<img src="https://media.geeksforgeeks.org/wp-content/uploads/20201106115254/MaxHeap.jpg" />

## Structure

Insertions in a heap happen from top -> bottom, left -> right. If an element is out of place in a heap, it needs to bubble up (swap with parent until in the right place).

In a heap, the deletion operation removes the root node of the heap (top most node).
To delete, swap root node with bottom-most node. When picking the bottom-most node, we pick right -> left. 
Since the root node now is likely to not follow the rules of the heap as it was in the bottom previously, we perform balancing on the heap by swapping the new root with it's smallest child until the heap is balanced.

Both insertions and deletions often need to 'bubble' up/down in the heap. Because the height of a binary tree is log(n) with n being the number of elements in the tree, the time complexity of insert / delete is o(log(n))
## Time Complexities:

Heapify (building a heap from array) : O(N)

Add / Delete : O(log N)

Access min / max : O(1)

## Implementation

By default, the heapq library in Python creates a min-heap with heapify.

To use a max heap instead of a min heap w/heapify, simplify invert the values going into the heap. Instead of pushing 5 into the heap, you would push -5, and vice versa.

When getting the max value of max heap, use -heapq.heappop(heap) to get the highest negative value (ex. -40) and inverse it to get the actual highest value (40).

```

import heapq
# min heap:

# Array -> Heap
h = [10, 20, 15, 30, 40]
heapq.heapify(h)

# Adding to heap
heapq.heappush(h, 5)

# Pop the root from heap 
min = heapq.heappop(h)

print(h)

print("Smallest:", min)
print(h) -> 5

# max heap:

#invert values
for i in range(len(h)):
    h[i] = -h[i]

#rebuild heap
heapq.heapify(h)

max = -heapq.heappop(h)

print(max) -> 40

```