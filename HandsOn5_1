class MinHeap:
    def __init__(self):
        self.heap = []

    def parent(self, i):
        return (i - 1) >> 1

    def left(self, i):
        return (i << 1) + 1

    def right(self, i):
        return (i << 1) + 2

    def heapify(self, i):
        l = self.left(i)
        r = self.right(i)
        smallest = i
        if l < len(self.heap) and self.heap[l] < self.heap[i]:
            smallest = l
        if r < len(self.heap) and self.heap[r] < self.heap[smallest]:
            smallest = r
        if smallest != i:
            self.heap[i], self.heap[smallest] = self.heap[smallest], self.heap[i]
            self.heapify(smallest)

    def build_min_heap(self, arr):
        self.heap = arr
        n = len(arr)
        for i in range(n // 2 - 1, -1, -1):
            self.heapify(i)

    def insert(self, item):
        self.heap.append(item)
        i = len(self.heap) - 1
        while i != 0 and self.heap[self.parent(i)] > self.heap[i]:
            self.heap[i], self.heap[self.parent(i)] = self.heap[self.parent(i)], self.heap[i]
            i = self.parent(i)

    def pop_root(self):
        if len(self.heap) == 0:
            return None
        if len(self.heap) == 1:
            return self.heap.pop()
        root = self.heap[0]
        self.heap[0] = self.heap.pop()
        self.heapify(0)
        return root


# Example usage:

# Creating a min heap with integers
heap_int = MinHeap()
arr_int = [8, 5, 3, 10, 2, 7, 1]
heap_int.build_min_heap(arr_int)
print("Min Heap (integers) after build_min_heap:", heap_int.heap)

# Inserting a new integer into the heap
heap_int.insert(4)
print("Min Heap (integers) after insert(4):", heap_int.heap)

# Removing the root node from the heap
root_int = heap_int.pop_root()
print("Removed root from Min Heap (integers):", root_int)
print("Min Heap (integers) after pop_root:", heap_int.heap)

# Creating a min heap with floats
heap_float = MinHeap()
arr_float = [3.14, 1.618, 2.718, 0.577, 1.732]
heap_float.build_min_heap(arr_float)
print("Min Heap (floats) after build_min_heap:", heap_float.heap)

# Inserting a new float into the heap
heap_float.insert(0.001)
print("Min Heap (floats) after insert(0.001):", heap_float.heap)

# Removing the root node from the heap
root_float = heap_float.pop_root()
print("Removed root from Min Heap (floats):", root_float)
print("Min Heap (floats) after pop_root:", heap_float.heap)
