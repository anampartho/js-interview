# Big-O

*Big-O: How does the runtime of an algorithm grow as the input size increases*

Big-O relates to the scalability of code. This begs the question, what is Scalability? In perspective of programming, we can say that scalability simply means how well a program performs for different sizes of data. For instance, we can ask the question, if an algorithm we designed works well with an array that contains 5 elements, how well will it perform with an array of 5 million elements? How well will is scale?

We cannot actually measure the performance of the code by simply using different functions provided to us from the language itself. For example we can use the `Performance API` to see how long a code takes to run. But, we need a huge dataset to measure the performance and the performance of the code also depends on the hardware of the computer it is running on, what other programs are running in the background etc. To solve this issue, and to get a simplified understanding of how well a algorithm is performing, we use **Big-O** notation to understand how an algorithm scales based on the input size.

We can see the following chart to get a basic birds eye view at how the operations (run time) of an algorithm with different Big-O complexities rise based on the Element (input size).

![Big-O Chart](./images/big_o_chart.svg)
<p style="text-align: center;"><em>chart taken from <a href="https://www.bigocheatsheet.com/" target="_blank">Big-O Cheat Sheet</a></em></p>

## Big-O of n or O(n) or Linear Time Complexity

So in this complexity, the time complexity is linear. This means, as the inputs increase, the operation will increase in a linear fashion. For example, if an algorithm does 5 operations for an input size of 5 then it will do 10 operations for an input size of 10. So input size of n will give use n operations. If we pu it in a graph, we will see that the operations are increasing in a linear fashion.

A good example of this is a loop. Any loop running on an array, will have a complexity of O(n). n is the number of items inside the array.

```js
const numArray = [10, 2, 20];

function findNum(num, numArray) {
  // loops through the entire array, hence this has a time complexity of O(n)
  // n is the number of items in the array
  for (let i = 0; i < numArray.length; i++) {
    if (numArray[i] === num) {
      console.log(`Number ${num} found!`)
    }
  }
}

findNum(20, numArray);
```

## Big-O of 1 or O(1) or Constant Time Complexity

In this complexity, no matter how large the input size, the algorithm will take constant time to run. For example, if we try to get the length of an array, we use the `.length` property. This property is set when we declare the array. So no matter how large the array is, getting the length of that array will be a constant time operation. Another example will be getting an item from a particular index. How does that work? So as we know, arrays are stored in a contiguous manner in memory, so the parser/engine uses pointer arithmetic to find out the memory location of a particular index and retrieves that data. This is how it is also a constant time operation.

```js
const myArray = [12, 22, 10];

console.log(`Length is: ${myArray.length}`);
console.log(`Item at index 2 is: ${myArray[2]}`);
```

## Big-O of n^2 or O(n^2) or Quadratic Time Complexity
For the time complexity of O(n^2) an algorithm's time to complete will be proportional to the square of the amount of data.

If we pass 3 data, then the algorithm will take 3^2 time to complete. An example of this is nested loops.

## Big-O of log n factorial or O(log n) or Logarithmic Time Complexity

## Big-O of n log n factorial or O(n log n) or Super Linear Time Complexity

## Big-O of n factorial or O(n!) or Factorial Time Complexity

Just Don't!
