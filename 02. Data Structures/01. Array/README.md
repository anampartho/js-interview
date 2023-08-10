# Array

[x] What is an array?
[x] Time complexities of different operations on Array.
[x] Static an Dynamic Arrays
[x] How to define an array in Javascript
[] Different operations on an Array in Javascript
  [x] Getting an item from a particular index `O(1)`
  [x] Setting an item at a particular index `O(1)`
  [] Push `O(1)`
  [] Pop `O(1)`
  [] Shift `O(n)`
  [] map `O(n)`
  [] Some `O(n)`
  [] Filter `O(n)`
  [] Splice `O(n)`
[] Some problems
  [] Reversing a string
  [] merge sort

## What is an Array?

Array is a data structure which contains a collection of similar items in contiguous memory locations. Contiguous is a big word, we can simplify and say, that in an array data structure, the element of that array is stored in memory in a sequence. So, if the memory location of the first element of the array is 100 then the second element is 101 (this is just a simplification). We will see why this is useful.

Arrays are zero indexed. This means the first item is at index 0 and the second item is at index 1, so on and so forth.

## Time complexities of different operations on Array

### Accessing an element at `i`-th index

Accessing an element at `i`-th index of an array has a time complexity `O(1)`. Why is this? As we mentioned before that the array data structure stores the data in contiguous memory locations. This means, when an array is defined, the compiler knows the starting location of the array and using that and some pointer arithmetic, it is fairly easy to find out the location of a particular index. It usually follows the following formula: `Address of 0th index + i * (size of one element)`. Size of one element will depend on the data being stored in the array. No need to memorize the formula.

### Traversing all element

"Traversing all element" is a fancy way of saying "visiting all elements". So if we want to do an operation on all element, we will traverse or visit all elements at least once and do the operation. This can be done through loops. This has a time complexity of `O(n)` as we are visiting all the elements.

### Overriding an element at `i`-th index

This operation also has a time complexity of `O(1)`. Because, using the pointer arithmetic we can find out the exact location of the `i`-th index and replace the data there.


### Inserting an Element

Inserting an element has a time complexity of `O(n)`. This can be confusing. There are mostly two scenarios that can happen.

#### 1. Item is added at the beginning or middle

If an item is added at the beginning or middle, then we have to shift or move all the other elements (whose  indexes are larger than the index where the new item is being added) to the right. This means, we need to increment the index of all other elements by one. To do this, we need to traverse or visit all elements, move them to the new position. As we mentioned earlier, traversing an array has a time complexity of `O(n)`. So adding an item at the very beginning of an array will have a time complexity of `O(n)`. You might think that, if the array is empty, then we do not need to do any shifting. You're right. In that case, we get a time complexity of `O(1)`. This is the best case. But we always need to consider the worst case when figuring out the time complexity.

#### 2. Item is added at the end

If the array is static, meaning fixed in size, and all the spots or indexes are already taken, then adding an item will have a time complexity of `O(n)`. Because the array is fixed in size and has no place, we cannot add the new item unless we increase the size of the array. To do that, we will have to create another array with double the size and then traverse over the old array and copy over the items at proper indexes and then add the new one. So that is an `O(n)` operation. In case the array is empty, we do not need to do any traversal and we get a time complexity of `O(1)`, with the help of our handy dandy pointer arithmetic.


### Deleting an element

This also has a time complexity of `O(n)` because of the same reasons behind adding an element to the start or middle of an array. While adding we had to shift all other elements. To delete, we will have to un-shift all other elements.

## Static vs Dynamic Arrays

There are two types of arrays we need to understand. One is the static and the other is dynamic. The name might not be self explanatory for some.

### Static Array

A static array is fixed in size. This means, while declaring the array we need to define what the size of this array is and this size cannot be changed later. To change this we need to create another bigger size array and copy over the content and then remove the old array from the memory. Javascript does not have static arrays. Java has static arrays.

### Dynamic Array

A dynamic array is an array, which does not have a fixed size. So for these types of array, we can add any amount of items we want (obviously keeping in mind about the capacity of memory). Javascript uses dynamic arrays.

## Arrays in Javascript

### Defining an array

There are two ways we can define an array in javascript. We can define empty arrays, predefine the items of the array or the size the array should start with

```js
// Create an Empty Array
let arr = new Array();
let arr2 = [];

// Create an array with predefined values
let languages = ['javascript', 'python', 'java'];
let scores = new Array(10, 9, 10, 8.6);

// Create an array with 4 empty slots/indexes
let emptySpaceArray = new Array(4)
```

### Getting `i`-th item from an array - `O(n)`

To get an item from `i`-th index, we use the square bracket notation. Inside the square brackets we provide the index value i.

```js
// Define an array
let languages = ['javascript', 'python', 'java'];

// Get item at index 2
languages[2]; // 'java'
```

### Setting/Replacing value of `i`-th item in an array - `O(n)`

To set/replace a value at `i`-th index, we still use the square bracket notation to specify the position where the item should be set/replaced and then set the value using the assignment operator.

```js
// Define an array
let languages = ['javascript', 'python', 'java'];

console.log(languages); // ['javascript', 'python', 'java']

// Replace item at index 2
languages[2] = 'c++'; // 'c++'

// Set item at index 3
languages[3] = 'java'; // 'java'

console.log(languages); // ['javascript', 'python', 'c++', 'java']
```
