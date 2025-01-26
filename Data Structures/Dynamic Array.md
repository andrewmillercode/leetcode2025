# Dynamic Arrays / Lists

Examples:

Python: List

Java: ArrayList

C++ : Vector 

Go : Slice


A dynamic array is an array which automatically resizes when adding elements into it. When an element is added and the array is full, the size of the array doubles in size to accomodate new elements. In this case, the time complexity of inserting elements is o(n), but in other cases it is o(1).

Time Complexities:

Add new value: O(1) (Amortized)

Iterate over values: O(N)

Access a value by index : O(1)

Update value by index : O(1)

Insert a value at index : O(N)

Delete value : O(N)

Search for value : O(N)