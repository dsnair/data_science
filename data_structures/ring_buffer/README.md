## Ring (or Circular) Buffer

A ring buffer is a non-growable buffer with a fixed size. When the ring buffer is full and a new element is inserted, the oldest element in the ring buffer is overwritten with the newest element. 

This kind of data structure is very useful for use cases such as storing logs and history information, where you typically want to store information up until it reaches a certain age, after which you don't care about it anymore and don't mind seeing it overwritten by newer data.

### Implementation

Implement this behavior in the RingBuffer class. RingBuffer has two methods: `append` and `get`. 
- The `append` method adds elements to the buffer. 
- The `get` method returns all of the elements in the buffer in a list in their given order. It should not return any `None` values in the list even if they are present in the ring buffer.

For example:

```python
buffer = RingBuffer(3)

buffer.get()   # should return []

buffer.append('a')
buffer.append('b')
buffer.append('c')

buffer.get()   # should return ['a', 'b', 'c']

# 'd' overwrites the oldest value in the ring buffer, which is 'a'
buffer.append('d')

buffer.get()   # should return ['d', 'b', 'c']

buffer.append('e')
buffer.append('f')

buffer.get()   # should return ['d', 'e', 'f']
```

### Runtime

1. What is the runtime complexity of your ring buffer's `append` method? O(1)

2. What is the space complexity of your ring buffer's `append` function? O(n)

3. What is the runtime complexity of your ring buffer's `get` method? O(n)

4. What is the space complexity of your ring buffer's `get` method? O(n)