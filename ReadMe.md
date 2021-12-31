# data-structures-and-algorithms

Data structures and algorithms are usually the begining in the process of writting scalable software. the more requests your system has the more important it is to have an optimized algorithm . We understand optimized algorithm as those with the better time and space complexity .there are some weird cases where a better time complexity does not mean a better algotithm. Explanation of what time and space complexity is in sections below.

At the botom of this readMe file is **the most important thing in this journey**, the exercises where the concepts are applied.

I also would like to encourage you to try to explain all of these concepts and exercises because the best way of learning something is teaching it. Apart from that we should always try to give back something to the software community we owe so much.

## Concepts

### 1. Time and spacial complexity

Time complexity is a way of describing how long would it take for an algorithm to complete a task depending on the amount of data that it is receiving as input, for example in the algorimn below we are printing all of the elements in the array.

![Image](img/linearFunction.png "linear Function")


If the input for this function is an array of lenght 4 it would take half the time that it would take if the lenght of the array was 8. The difference between 8 milliesconds and 4 millisecons is not reaaly significant but when we are talking of millions of records thats when the time complexity of the algoithm is important.

There are several types of time complexity, constant O(1), linear O(n), logaritmic O(logn), linearitmic O(nlogn), cuadratic  O(n^2), cubic O(n^3), exponentioal O(2^n) and factorial O(n!)

![Image](img/typesOfTimeComplexity.png "types Of Time Complexity")

In the picture they are using the Big O notation, (well, almost everybody use big O notation). this is a convention used to describe an approximation of how long will it take for our algoritm to finish its job. in our first function the notation would be O(n), this mean that given an input of size n our task would take n units of time.

The Big O notation for our first function would be linear, for the picture below the time complexity would be constant. Constant time complexity means that it does not matter the amount of data it will always take the same amount of time to complete the job.

![Image](img/constantFunction.png "Constant Function")

For me the best way to define a logaritmic time complexity is saying that is a function that in every iteration rule out half of the remaining elements in the input, the best example of a function with logaritmic time complexity would be the binary search.

First off, binary search require the elements of the array to be already sorted. The inputs for binarySearch are an array, a variable for the leftmost and rightmost position in the array and the variable that we are looking for. In every iteration we ask if the position in the middle is equal to the variable that we are looking for.

If the position in the middle is not equal to the variable we are looking then we need to ask ourself if the variable in the middle is greater or smaller then the variable we are looking for, depending on the answer the value of right will be middle plus 1 or the value of left will be middle minus 1.

Notice in the picture below how in every iteration we are ruling out half of the elements in the array. In the picture after that there is an implementation of the binary search

![Image](img/binarySearchVisualization.png "binary Search Visualization")

![Image](img/binarySearchImplementation.png "binary Search Implementation")

A function with linearitmic time complexity is a function where we are using a logaritmic function everytime there is an element in the array, for example, imagine that that I receive a sorted array and for some reason I would like to apply the binary search in every iteration of the for loop (this funcion would not make any sense in the real world but for explaining linearimic functions is great).

Is important to have in mind that O(nlogn) means that the linear size of the function and the logaritmic part of the function apply on the same dataset, if we are applying the logaritmic function in a diferent dataset that would be O( nlogm ) because we can not use the same variable for two different things.

![Image](img/linearitmicFunction.png "linearitmic Function")

A function with cuadratic time complexity is a functiong where for each element in the dataset we are iterating throug all of the elements in the same dataset, if it is not the same dataset then we would call it O(mn) (an example in the picture below).

![Image](img/cuadraticFunction.png "cuadratic Function")


A cubic function would be one function where for every element in the datasest we are using a function with cuadratic time complexity, in the same way a function with n^4 time complexity would be one function where for every element in the dataset we are using a cubic function, and so on with  n^5, n^6, n^7 etc...

A function with exponential time complexity means that we are having a number of iterations equal to 2 pows the dataset size (O2^n). A great example of these algorithms is the one we used in problme number 1863, where we have to create all of the subsets of a given array.

This is a great example of a factorial time complexity [function](https://www.youtube.com/watch?v=Mo4vesaut8g&list=WL&index=7&t=6439s)

For competitive programming there are only two types of important spacial complexity O(1) meaning that you are creating new variables in every iteration and the non-constant meaning that you are doing it. When you are working with recursive functions is very likely that the spatial complexity will be linear, becasuse every invocation of the recursive function is creating a piece of information for the bigger problem like they mention in this  [video](https://www.youtube.com/watch?v=Mo4vesaut8g&list=WL&index=7&t=6439s)
### 2. storing two numbers in one using bitmasking, exrcise 1920

When you need two arrays, one for input and another for answer but can only use one (like in this occasion when they require constant space complexity) we will need to store two numbers in one. Notice that all numbers must be equal or less than the array lenght and the maximun lenght size is 1000. Binary representation of 1000 has 10 digits (1111101000) so we need to a number which binary representation has 10 digits and they all 1's (1023).

The easiest way to store two numbers is expanding the first number using a mask, in this way the mask will work as the limit for the begging of the first number and the begging of the second one.

Imagine that we want to store 8 and 3 in the same number. The binary representation of 3 is 11 and the binary of 8 is 1000.

The first thing that wee need to do is applying the mask 1023 with the "&" operator. The "&" operator apply the "AND" gate of true so it will only be true if both bits are set (in other words if both digits are 1). For our purpose applying this mask will always gave back the first 10 digits of the number like we see in the picture below.

![Image](img/bitMaskingFirstIteration.png "bit Masking First Iteration")

The second part is expanding the second  number using the mask.

After that we are storing the second number in the next 10 bits. To do that first wee need to move the binary representation of 8 (1000) 10 spaces to the right so we dont modify the first number (this is call bit shifting), after that we place the shifted number in the three value using the "|" operator, this apply and "OR" gate of true.

###  3. Given two points, finding the function, exercise 1512

Exercise 1512 is the type of exercise where is better to see it as three different problems, the firt problem is counting the appeareances of every number , the second one would be given a n number of apperance for every number how many pairs does it  
f(x) = mx + n, where m is the slope and n is the intersetction with the x axis (horizontal axis). When you have two unknown variables (in our case m and n) you must use an equation system like the exercise shown in this [video](https://www.youtube.com/watch?v=Qcq3PQSZotI) ..... it is in spanish, I will create an english version of every video or documentation, is already listed in my to-do list

### 4 sorting algoritms, exercise 1528

There are three important sorting algoritms, the quicksort, the mergesort and heapsort. In this readMe file we will mention some other sorting algoritms but it is very likely that you will never use them.

Quicksort is the most used, it has a time complexity of O(nlogn), space complexity of O(logn) and operate in place. It can have a time complexity of O(2^n) in its worst case escenario (when they array is already sorted and when all of the elements are the same) but for most cases it is faster than heapsort and mergesort. 

One edge case where quicksort is not the most optmial option is when the dataset is really tiny (like 15 elements) in these case insert sort could be faster, but in competitive programming or in real life algoritms are expected to scale.

The purpose of this Readme file is give you the skill for a competitive-programing like situation. for a more in detail explanation of quicksort performance and worst case scenario I recommend the book "Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein Introduction to Algorithms, Third Edition  2009".

Another great book if you want to dive deeper is "Algorithhms 4th Edition by Robert Sedgewick, Kevin Wayne".

MergeSort also has a time complexity of O(nlogn), spacial complexity of O(n) and it does not operate in-place

heapsort has a time compllexity of O(nlogn),  space complexity of o(1) and it operate in-place. This one is the algoritm that we use when we are using priority queue, it has a two great attributes and that is that some times we dont really want to to sort the whole array, we just want to store one element in its correct position in the data structure. The other one is that using the comparator class we can sort the data-structure for multiple attributes.

A sorting algoritmh is stable if it preserves the relative order of equal keys in the array, ( insertion sort
and mergesort are stable, selection sort, shellsort, quicksort, and heapsort are not (heapsort using priority queue can use a seconda atribute for comparisions throush the comparator interface).


When we are sorting data ussually we are not jus sorting the keys but also the rest of the data in every record, that is called satellite data

bubbleSort operate in place but it operate in O(n)

concepts to mention, key, record , satellite data, stability

### 5 logic gates  1528

If you are reading this you are a programmer and most likely you are already familiar with the gates of true "AND" "OR" because we use them a lot in our conditional statement in java or python.

Now XOR is something new or at least a not so used gate of true. in XOR the result is true if both of them are different like we see in the picture below

![Image](img/XORGATE.png "xor gate")

Now to do the xor between two numbers we are doing the xor between the binary representation of both numbers so 3 xor 8 would be 11 xor 1000 anthe result would be  1011 (11 in decimal) because the first two numbers from right to left  are different the result is true (1) in the third location both are equal so the result is 0 and in the last one. A picture below for a better visualization of the concept.

![Image](img/xotbetween8and3.png "xot between 8 and 3")

Now, to solve the problem 1528 the first thing that we need to do is find a number that xorted agains the number given in variable "first" result in the first element in the array "encoded". 

So in the example 2 of the exercise we have the first element of the array we have to return and the second element will be a number that that xorted against 4 result in 6.

The easiest way to do it is just xor 4 and 6 and that will give us the second element because ----> if (4 ^ 6 = x) then (4 ^ x = 6) 


### 6 when you need to sort by two values , exercise 1389

Notice that you could have several number with the same index, and the way we know the real position is using the position of the number in the array nums.

The way I would do it is using the priorityQueue and the comparator interface 

### 7 Binary tree (full,complete, perfect,Binary search tree) case 108

A full binary tree is a data structure where the nodes that decide to have children have two children, a complete binary tree is a data structure where we fill the tree from top to bottom and from left to right and the perfect binary tree is a binary tree that is both full and complete.

![Image](img/typesOfBT.png "types Of BT")

picture taken from this link, you should check that channel is amazing

### 8 Recursion

A recursive function is function that call itself, this video does a great job explaining it, all of the thing that I will mention (in a high level, please see the video) come from that video. Recursive function are pretty useful when we can see the problem as group of smaller problems where every execution bring a little piece of information for solving the bigger problem. Another important concept is the stack, all of the task that our program should execute (like a to-do list) is in the stack, it is pretty important that our recursive function have and ending condition because otherwise it will generate a stack overflow.

### 9 Graph

Graph is way to represent entities (that we call vertex) and the connections between those entities that we call edges. The two sources I used for this topic are this [video](https://www.youtube.com/watch?v=tWVWeAqZ0WU&t=531s) and this [book](https://www.amazon.com/Algorithms-4th-Robert-Sedgewick/dp/032157351X).

For representing grapth we usually use an adjacency list is a data structure for representing every entity and the entities it have a conection to (in could be a hashmap in java or a dictionary in python)

![Image](img/adjacencylist.png "adjacency list")

edges can be seen as street, some streets are two ways roads, anothers are unirectionals. when we have a graph is unidirectional we call that a directed grapth, when is bidirectional we call that undirected grapgh.

![Image](img/undirectedDitectedGraph.png "undirected Ditected Graph")

The two most important algoritms when it comes to graph are dfs (Depth-first search) and bfs (breadth first search).

Dfs is an algorithm for detecting the connection between entities. For every edge of every vertex we will recursibly call the dfs, in order to avoid an stack overflow we use a list where we indicate those vertex that has already been visited. Piece of code extracted from this [link](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)

![Image](img/dfsCode.png "dfs code")

To make this a little more clear let's see the following picture. We start by vertex 0, it has three edges 2, 1  and 5. we recursibly apply dfs on vertex 2 that has four vertex 0, 1, 3 and 4. 0 is already marked because we already visited so we apply dfs on the 1 vertex. vertex 1 has two edges but both of then are marked so we go back to vertex 2 to visit its next edge, vertex 3. and so on until the execution conclude.


![Image](img/traceDFS.png "trace DFS")

DFS has a time complexity of O(V + E), where V is the number of vertex and E are the number of edges.

When we want to know the shortest path between two components we use the bfs algoritm. In BFS we add all of the edges of the vertex to the queue and then we continue with the next vertex in the edge.

![Image](img/bfsCode.png "bfs Code")

For more clarity, let's see the trace of the program

![Image](img/bfs_trace.png "bfs trace")


And the final otutcome will be something like this for finding path from the vertex 0


![Image](img/bfs_outcome.png "bfs outcome")








### Summation

(n(n+1)) / 2   useful for problems like leetcode number 268

### prefix sum array and suffix array

A suffix array is a sorted array of all of the suffixes of a given array (video [explanation](https://www.youtube.com/watch?v=uxA__b23t2w&t=30s) ) , the prefix (could not find a good explanation of prefix array so following the leetcode problem number 654 as a guide we will asume that a prefix array is a counter part of a suffix array). The prefix sum array is (you know what, this explanation is [better](https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-competitive-programming/) ), I know the inverted prefix sum array (starting from the last element of the array until the first element) has a name but I don't remember what it is

### greedy problems

I would like to sound smart, but I won't sound smarter than [this](https://www.geeksforgeeks.org/greedy-algorithms/), for a better undestanding of the greedy algoritm see leetcode problem number 1710 

### greedy problems

Prim Algoritm

### ???? data structures (why I use hashmap so much)

### ???? how to know if two elements are in the same diagonal

### ???? preorder postorder inorder

### ???? sliding window

### ???? dfs , bfs

### ???? recursion and how careful we have to be with it


# Useful tips

1. Read markdown documentation to learn useful trick to apply in this ReadMe file or another file that you prefer.

# leetcode array exercises, easy level

1. exercise [link](https://leetcode.com/problems/build-array-from-permutation/) 1920
    1. link to my leetcode [post](https://leetcode.com/problems/build-array-from-permutation/discuss/1606100/A-solution-you-can-came-up-with-in-an-interview).

2. exercise [link](https://leetcode.com/problems/concatenation-of-array/) 1929


3. exercise [link](https://leetcode.com/problems/final-value-of-variable-after-performing-operations/) 2011 (no tiene ni gracia, pero suma para el cuadro de actividad)


4. exercise [link](https://leetcode.com/problems/number-of-good-pairs/) 1512, this one special, one of my first leetcode problems men
    1. link to my leetcode [post](https://leetcode.com/problems/number-of-good-pairs/discuss/1606891/given-two-point-find-the-function-O(n)).

5.  exercise [link](https://leetcode.com/problems/shuffle-string/) 1528, this one special, ok, there will be a section in my readMe to talk about sorting algorithms, I need to write a lot of times the quick sort algoritmn to memorize it ()
    1.  link to my leetcode [post](https://leetcode.com/problems/shuffle-string/discuss/1606902/just-do-the-quick-sort-O(nlogn)).

6. exercise [link](https://leetcode.com/problems/decode-xored-array/) 1720, another section in my documentation file, logic gates 

7. exercise [link](https://leetcode.com/problems/create-target-array-in-the-given-order/) 1389 comparator and priorityQueue, I have already talked about this in the sorting algorithm
    1.  link to my leetcode [post](https://leetcode.com/problems/create-target-array-in-the-given-order/discuss/1607597/Priority-queue-to-sort-based-in-two-variables)


8. exercise [link](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k/) 2006
    1.  link to my leetcode [post](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k/discuss/1607656/Using-a-map-(or-dict-in-python))

9. exercise [link](https://leetcode.com/problems/sum-of-all-odd-length-subarrays/) 1588 ----->> this is one of those moments where I thing is better to take notes into the interview

10. exercise [link](https://leetcode.com/problems/maximum-product-difference-between-two-pairs/) 1913, 

11. exercise [link](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/) 2037, it is a cool analisis

12. exercise [link](https://leetcode.com/problems/count-good-triplets/) 1534, not that cool but I need to do this one

13. exercise [link](https://leetcode.com/problems/find-greatest-common-divisor-of-array/) 1979

14. exercise [link](https://leetcode.com/problems/minimum-time-visiting-all-points/) 1266
    1.  link to my leetcode [post](https://leetcode.com/problems/minimum-time-visiting-all-points/discuss/1609023/Intuition-O(n))

15. exercise [link](https://leetcode.com/problems/cells-with-odd-values-in-a-matrix/) 1252
    1.  link to my leetcode [post](https://leetcode.com/problems/cells-with-odd-values-in-a-matrix/discuss/1609081/O(n)-first-find-the-value-of-every-row-and-every-column-then-find-the-value-of-each-cell)

16. exercise [link](https://leetcode.com/problems/matrix-diagonal-sum/) 1572
    1.  link to my leetcode [post](https://leetcode.com/problems/matrix-diagonal-sum/discuss/1609117/python-O(n)-diagonal-and-inverted-values-are-always-the-same-the-difference-would-be-i)

17. exercise [link](https://leetcode.com/problems/sum-of-all-subset-xor-totals/) how to create subssets 1863, this have to be a section in this readMe file and a good example of the O(2^n) time complexity
    1.  link to my leetcode [post](https://leetcode.com/problems/sum-of-all-subset-xor-totals/discuss/1610560/python-(2n)-backrtacking-something-you-can-came-up-with-in-an-interview)

18. exercise [link](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/) 1295 avoiding casting this to all cost
    1.  always see the [constraints](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/discuss/459489/JAVA-solution-with-100-better-space-and-Time)
    2.  now, I can easily see in a interview someone requiring to do it if the constraint does not [exist](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/discuss/458937/JAVA-MUST-READ-Solution-with-EXPLANATION-and-EXAMPLE-%3A))  

19. exercise [link](https://leetcode.com/problems/smallest-index-with-equal-value/) rewritting this, what is the highest number equal to its position

20. exercise [link](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/) beautifull opportunity to use the binary search

21. exercise [link](https://leetcode.com/problems/replace-elements-with-greatest-element-on-right-side/) 1299 

22. exercise [link](https://leetcode.com/problems/unique-number-of-occurrences/) 1207

23. exercise [link](https://leetcode.com/problems/maximum-units-on-a-truck/) 1710

24. exercise [link](https://leetcode.com/problems/minimum-subsequence-in-non-increasing-order/) 1403, this is a really cool one

25. exercise [link](https://leetcode.com/problems/peak-index-in-a-mountain-array/) 852
    1.  link to my leetcode [post](https://leetcode.com/problems/peak-index-in-a-mountain-array/discuss/1610595/0(log-n)-binary-search)

26. exercise [link](https://leetcode.com/problems/shortest-distance-to-a-character/) 821
    1.  link to my leetcode [post](https://leetcode.com/problems/shortest-distance-to-a-character/discuss/1610634/O(n)-from-right-to-left-and-from-left-to-right)

27. exercise [link](https://leetcode.com/problems/minimum-cost-to-move-chips-to-the-same-position/) 1217
    1.  link to my leetcode [post](https://leetcode.com/problems/minimum-cost-to-move-chips-to-the-same-position/discuss/1610999/O(n)-just-count-evenodd)

28. exercise [link](https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/) 1356
    1.  link to my leetcode [post](https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/discuss/1612217/java-O(nlogn)-priority-queue)

29. exercise [link](https://leetcode.com/problems/lucky-numbers-in-a-matrix/) 1380,,,,,passing Collections.reverseOrder() to the priority queue

30. exercise [link](https://leetcode.com/problems/can-make-arithmetic-progression-from-sequence/) 1502

31. exercise [link](https://leetcode.com/problems/projection-area-of-3d-shapes/) 883
    1.  link to my leetcode [post](https://leetcode.com/problems/projection-area-of-3d-shapes/discuss/1612885/O(n)-getting-the-information-from-every-point-of-view)

32. exercise [link](https://leetcode.com/problems/matrix-cells-in-distance-order/) 1030    could not do it without watching the answer

33. exercise [link](https://leetcode.com/problems/single-number/) 136 could not do it without watching the answer
    1.  link to my leetcode [post](https://leetcode.com/problems/single-number/discuss/1612941/O(n)-XOR-property)

34. exercise [link](https://leetcode.com/problems/sort-array-by-increasing-frequency/) 1636 easy but woul be good practice

35. exercise [link](https://leetcode.com/problems/smallest-range-i/) 908 ,,,,,,, I needed to see the discussion section
    1. I will do this post, but seeing the question again I still don't understand what do they want

36. exercise [link](https://leetcode.com/problems/number-of-lines-to-write-string/) 806
    1.  In order to understand this one you will need to see the discussion section because the question is not preoperly written (they don't say that the array widths is the size of every letter in the alphabet)

37. exercise [link](https://leetcode.com/problems/find-the-middle-index-in-array/) 1991,,,,,,,,,,,,,,,,,,,,,,,, Prefix and suffix sum
    1.  I need to think this a little more. 


class Solution:
    def findMiddleIndex(self, nums: List[int]) -> int:
        fromRightToLeft = []
        fromLeftToRight = []
        for numIndex in range(len(nums)):
            if numIndex == 0:
                fromLeftToRight[numIndex] = nums[numIndex]
                fromRightToLeft[-1] = nums[-1]
            else:
                fromLeftToRight[numIndex] = fromLeftToRight[numIndex] + nums[numIndex]
                fromRightToLeft[-1*(numIndex+1)] = fromRightToLeft[-1*(numIndex+1)] + nums[-1*(numIndex+1)]







38. exercise [link](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/) 108, I had to see the blog to confirm my hypothesis
    1.  link to my leetcode [post](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/discuss/1620589/python-O(n)-something-you-can-came-up-with-in-an-interview)

39. exercise [link](https://leetcode.com/problems/crawler-log-folder/) 1598, not that cool

40. exercise [link](https://leetcode.com/problems/design-hashset/) 705
    1.  link to my leetcode [post](https://leetcode.com/problems/design-hashset/discuss/1620634/python-O(1)-incomplete-solution)

41. exercise [link](https://leetcode.com/problems/design-hashmap/) 706

42. exercise [link](https://leetcode.com/problems/last-stone-weight/) 1046

43. exercise [link](https://leetcode.com/problems/shift-2d-grid/)  1260, este si esta es pero buenisimo compa
    1.  not a post I created, but problably will be the greatest one I will see. [Link](https://leetcode.com/problems/shift-2d-grid/discuss/434335/Python3%3A-2-simple-approaches-with-explanations-(by-creating-a-vector))

44. exercise [link](https://leetcode.com/problems/transpose-matrix/) 867, the headache you gave me
    1.  link to my leetcode [post](https://leetcode.com/problems/transpose-matrix/discuss/1620951/python-O(n)-columns-in-input-array-will-be-our-output-array-rows)

45. exercise [link](https://leetcode.com/problems/surface-area-of-3d-shapes/)  892
    1.  link to my leetcode [post](https://leetcode.com/problems/surface-area-of-3d-shapes/discuss/1622579/python-O(n))

46. exercise [link](https://leetcode.com/problems/pascals-triangle/)  118, The only possible way for this that I can think of is following the simulation

47. exercise [link](https://leetcode.com/problems/fair-candy-swap/) 888
    1.  not a post I created, but problably will be the greatest one I will see. [Link](https://leetcode.com/problems/fair-candy-swap/discuss/161269/C%2B%2BJavaPython-Straight-Forward)

48. exercise [link](https://leetcode.com/problems/largest-perimeter-triangle/)  976
    1.  not a post I created, but problably will be the greatest one I will see. [Link](https://leetcode.com/problems/largest-perimeter-triangle/discuss/217988/JavaC%2B%2BPython-Sort-and-Try-Biggest)

49. exercise [link](https://leetcode.com/problems/move-zeroes/) 283, another cool exercise to store two numbers in one position

50. exercise [link](https://leetcode.com/problems/element-appearing-more-than-25-in-sorted-array/) 1287, lo chevere seria hacerlo con busqueda binaria,,,,,,,,,,,,I owe this to myself men

51. exercise [link](https://leetcode.com/problems/rank-transform-of-an-array/) 1331
    1.  link to my leetcode [post](https://leetcode.com/problems/rank-transform-of-an-array/discuss/1622756/python-O(nlogn)-sort-and-python-hashMap-(dict))

52. exercise [link](https://leetcode.com/problems/missing-number/) 268
    1.  link to my leetcode [post](https://leetcode.com/problems/missing-number/discuss/1622781/python-O(n)-subtracting-numbers-from-the-summation)

53. exercise [link](https://leetcode.com/problems/most-visited-sector-in-a-circular-track/) 1560 , brain turned off  to do this,,,,,,,,,,,,,,,,I owe this to myself men

54. exercise [link](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) 167 , usando operaciones matematicas como llave
    1.  link to my leetcode [post](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/discuss/1622808/python-O(n)-given-a-number-use-a-dict-to-find-the-other-number-to-reach-the-target)

55. exercise [link](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/) 448
    1.  link to my leetcode [post](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/discuss/1622897/Python-O(n)-bitmasking)

56. exercise [link](https://leetcode.com/problems/teemo-attacking/) 495, mehhhhhhh

57. exercise [link](https://leetcode.com/problems/count-special-quadruplets/) 1995 , I had to see it, hint, I will need brute force

58. exercise [link](https://leetcode.com/problems/min-cost-climbing-stairs/) 746, do I have a section about dp ?? ,,,,,,, I still own this thing to mysql

59. exercise [link](https://leetcode.com/problems/reorder-data-in-log-files/)  937, opportunity for priority queue ,,, this would be way to easy need to progress

60. exercise [link](https://leetcode.com/problems/pascals-triangle-ii/) 119  could not do it without (start by the brute force implementation)

61. exercise [link](https://leetcode.com/problems/determine-whether-matrix-can-be-obtained-by-rotation/) 1886
    1.  link to my leetcode [post](https://leetcode.com/problems/determine-whether-matrix-can-be-obtained-by-rotation/discuss/1624393/python-O(n)-there-are-three-possible-positions-that-each-value-can-take)

62. exercise [link](https://leetcode.com/problems/range-addition-ii/) 598
    1.  link to my leetcode [post](https://leetcode.com/problems/range-addition-ii/discuss/1624418/Java-O(n)-find-the-min)

63. exercise [link](https://leetcode.com/problems/distance-between-bus-stops/)  1184 ,,,,,,, I needed to see the discussion section   and I still don't understand

64. exercise [link](https://leetcode.com/problems/range-sum-query-immutable/) 303, meeeeeehhhhhhhh

65. exercise [link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) 121
    1.  link to my leetcode [post](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/discuss/1624510/Python-O(n)-in-every-step-calculate-the-difference-with-the-lowest-value-you-have-seen-so-Far)

66. exercise [link](https://leetcode.com/problems/maximize-sum-of-array-after-k-negations/) 1005, easy but I want to implement it 

67. exercise [link](https://leetcode.com/problems/get-maximum-in-generated-array/) 1646,, another one where I could not came up with a solution,,,,,daaaaammmmmmmm,,,,,,,,,,,,,,,,,,,, I owe this to myself

68. exercise [link](https://leetcode.com/problems/find-the-town-judge/) 997,
    1.  link to my leetcode [post](https://leetcode.com/problems/find-the-town-judge/discuss/1624781/python-O(n)-2-Hashmaps-(dicts))

69. exercise [link](https://leetcode.com/problems/maximum-subarray/) 53,
    1.  link to my leetcode [post](https://leetcode.com/problems/maximum-subarray/discuss/1625571/Python-O(n)-prefix-postfix-and-exploring-the-space-between-the-Maxvalue-in-prefix-and-postfix)

70. exercise [link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) 26  

71. exercise [link](https://leetcode.com/problems/maximum-product-of-three-numbers/) 628

72. exercise [link](https://leetcode.com/problems/partition-array-into-three-parts-with-equal-sum/) 1013
    1.  link to my leetcode [post](https://leetcode.com/problems/partition-array-into-three-parts-with-equal-sum/discuss/1628038/python-O(n)-prefix-postfix-and-value-from-prefix-until-posfix)

73. exercise [link](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/) 1752,,,, rotation is the part where I need more practice

74. exercise [link](https://leetcode.com/problems/subrectangle-queries/) 1476, I enjoy creating classes

75. exercise [link](https://leetcode.com/problems/queries-on-number-of-points-inside-a-circle/) 1828, easy, when you know how to calculate the distance between two points.

76. exercise [link](https://leetcode.com/problems/minimum-number-of-operations-to-move-all-balls-to-each-box/) 1769, this logic was quite cool
    1.  link to my leetcode [post](https://leetcode.com/problems/minimum-number-of-operations-to-move-all-balls-to-each-box/discuss/1628321/Python-O(n)-two-variables-one-for-the-number-of-balls-another-for-the-number-of-operation)

77. exercise [link](https://leetcode.com/problems/max-increase-to-keep-city-skyline/) 807

import java.util.*;

class Solution {

    
	public int maxIncreaseKeepingSkyline(int[][] grid) {
        int total = 0;
        HashMap<Integer, PriorityQueue<Integer>> hmapRows = new HashMap<>();
        HashMap<Integer, PriorityQueue<Integer>> hmapCols = new HashMap<>();
        for  (int i = 0; i < grid.length ; i ++){
            hmapRows.putIfAbsent(i, new PriorityQueue<>());
            for (int j=0; j < grid.length;j++){
                hmapCols.putIfAbsent(j, new PriorityQueue<>());
                hmapRows.get(i).add(grid[i][j]);
                hmapCols.get(j).add(grid[i][j]);
            }
        }
        
        for  (int i = 0; i < grid.length ; i ++){
            for (int j=0; j < grid.length;j++){
                total = total + (grid[i][j]-Math.min(hmapRows.get(i).peek(),hmapCols.get(j).peek())); 
            }
        } 
        return total;
    }
}

78. exercise [link](https://leetcode.com/problems/maximum-binary-tree/) 654, way too easy but it will be fun to write

public class Solution {
    public TreeNode constructMaximumBinaryTree(int[] nums) {
        return construct(nums, 0, nums.length);
    }
    public TreeNode construct(int[] nums, int l, int r) {
        if (l == r)
            return null;
        int max_i = max(nums, l, r);
        TreeNode root = new TreeNode(nums[max_i]);
        root.left = construct(nums, l, max_i);
        root.right = construct(nums, max_i + 1, r);
        return root;
    }
    public int max(int[] nums, int l, int r) {
        int max_i = l;
        for (int i = l; i < r; i++) {
            if (nums[max_i] < nums[i])
                max_i = i;
        }
        return max_i;
    }
}


79. exercise [link](https://leetcode.com/problems/sort-the-matrix-diagonally/) 1329
    1.  link to my leetcode [post](https://leetcode.com/problems/sort-the-matrix-diagonally/discuss/1632841/Java-(nlogn)-identify-the-elements-of-that-diagonal)

80. exercise [link](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/) 1008, I had to see this one in youtube
    1.  probably better than the code I was going to write, [post](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/discuss/252232/JavaC%2B%2BPython-O(N)-Solution)


81. exercise [link](https://leetcode.com/problems/find-valid-matrix-given-row-and-column-sums/)  1605, needed to see
    1.  probably better than the code I was going to write, [post](https://leetcode.com/problems/find-valid-matrix-given-row-and-column-sums/discuss/876904/Python-and-C%2B%2B-(Greedy)-Easy-python-solution.-Explained-using-images)

82. exercise [link](https://leetcode.com/problems/design-a-stack-with-increment-operation/) 1381, have not tried yet, should be easy, but I have not created a single class in leetcode

83. exercise [link](https://leetcode.com/problems/maximum-xor-for-each-query/) 1829 had to see, what a hard problem
    1.  link to my leetcode [post](https://leetcode.com/problems/maximum-xor-for-each-query/discuss/1633273/Java-O(n)-with-explanation)

84. exercise [link](https://leetcode.com/problems/count-number-of-maximum-bitwise-or-subsets/) 2044, hint, is a dp problem, have not been able to do the optimized solution..........I am stiill owing e this one

85. exercise [link](https://leetcode.com/problems/matrix-block-sum/) 1314
    1.  partial explanation (need to reach those 100 questions mark): So we need the prefixSum to avoid repeating calculations, the thing is that we can not just flatten the array and do the prefixSum, we need the prefixSum of rows and columns and using that we can obtain any value in the array.


86. exercise [link](https://leetcode.com/problems/find-the-winner-of-the-circular-game/) 1823, did not even undertand what am I suppose to do

87. exercise [link](https://leetcode.com/problems/score-after-flipping-matrix/) 861, lost again

88. exercise [link](https://leetcode.com/problems/count-square-submatrices-with-all-ones/) 1277, putting my analysis along with lee analisys I ended with a brilliant explanation (I know which one this is, so I will go with the next one I really need the 100 quetions mark)

89. exercise [link](https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/) 1442

90. exercise [link](https://leetcode.com/problems/design-browser-history/) 1472

91. exercise [link](https://leetcode.com/problems/spiral-matrix-iii/) 885
    1. this is way too easy, I have   a partial solution in my book

92. exercise [link](https://leetcode.com/problems/find-all-duplicates-in-an-array/) 442
    1. I already know the answer to this one, just turn those that already appeared into negative  and using the index we will know which one appeared twice

93. exercise [link](https://leetcode.com/problems/xor-queries-of-a-subarray/) 1310 , that xor prefix thou
    1. trying to get to that 100 questions mark as soosn as I can, I already have a great explanation in my notes.

94. exercise [link](https://leetcode.com/problems/minimum-number-of-operations-to-reinitialize-a-permutation/) 1806, no clue of what are we doing

95. exercise [link](https://leetcode.com/problems/partition-array-for-maximum-sum/) 1043, that explanation that I created is sweet
    1.  I already feel I have a great understanding of the problem, so I will move on

96. exercise [link](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/) 889, along with the youtube video would be the explanation
    1.  I already feel I have a great understanding of the problem, so I will move on

97. exercise [link](https://leetcode.com/problems/subsets/) 78, another great opportunity for explainig backtracking

98. exercise [link](https://leetcode.com/problems/max-area-of-island/) 695, really easy but I would like to practice some recursion.

99. exercise [link](https://leetcode.com/problems/apply-discount-every-n-orders/) 1357, well let's create another class

100. exercise [link](https://leetcode.com/problems/restore-the-array-from-adjacent-pairs/) 1743, hint find the head or tail

101. exercise [link](https://leetcode.com/problems/single-number-iii/) 260, I really need to print the

102. exercise [link](https://leetcode.com/problems/minimum-falling-path-sum/) 931 

103. exercise [link](https://leetcode.com/problems/path-with-maximum-gold/) 1219, I don't know nothing abouth dfs or bfs right now

104. exercise [link](https://leetcode.com/problems/find-all-groups-of-farmland/) 1992 cool oportunity to practice recursion

105. exercise [link](https://leetcode.com/problems/number-of-times-binary-string-is-prefix-aligned/) 1375 I am definitily writting a post about this one 

106. exercise [link](https://leetcode.com/problems/stone-game-ii/) 1140, what a weird question

107. exercise [link](https://leetcode.com/problems/sum-of-absolute-differences-in-a-sorted-array/) 1685 a post is comiiiiiiinggggggggg, 

108. exercise [link](https://leetcode.com/problems/rotate-image/) 48, cool post about bitmasking

109. exercise [link](https://leetcode.com/problems/construct-quad-tree/) it's not clear what they want

110. exercise [link](https://leetcode.com/problems/beautiful-array/) 932, I don't understand what they want but sound easy

111. exercise [link](https://leetcode.com/problems/simple-bank-system/) 2043, did not reas, but looks easy

112. exercise [link](https://leetcode.com/problems/top-k-frequent-elements/) 347, this is really easy, but maybe I will do a post about this one

113. exercise [link](https://leetcode.com/problems/rotating-the-box/) 1861, well a lot of easy questions is a faster arrival

114. exercise [link](https://leetcode.com/problems/minesweeper/) 529, well now thanks to that video I understand what they [want](https://www.youtube.com/watch?v=lla6QlAF4HQ&t=481s)

115. exercise [link](https://leetcode.com/problems/beautiful-arrangement/)  526, post incoming

116. exercise [link](https://leetcode.com/problems/minimum-numbers-of-function-calls-to-make-target-array/) 1558 , easy

117. exercise [link](https://leetcode.com/problems/find-duplicate-file-in-system/) 609
    1.  what a great [explanation](https://www.youtube.com/watch?v=4KGl6PMwVXE&t=138s)

118. exercise [link](https://leetcode.com/problems/minimum-cost-for-tickets/) 983, a post iiiiiin comiiiiiiiiiiiingggg 

119. exercise [link](https://leetcode.com/problems/product-of-array-except-self/) 238, some bitmasking, some preSum and Buoalaaaaaa

120. exercise [link](https://leetcode.com/problems/combination-sum/) 39, backtrack this

121. exercise [link](https://leetcode.com/problems/combination-sum-iii/) 216, I just thought of a really cool way of solving this but probably when I try to do this thing for real I will forget it

122. exercise [link](https://leetcode.com/problems/flip-columns-for-maximum-number-of-equal-rows/) 1072, looking for the other parntner using the xor

123. exercise [link](https://leetcode.com/problems/number-of-closed-islands/) 1254

124. exercise [link](https://leetcode.com/problems/jump-game-iii/) 1306, at least with this video I understan what they want, and a little idea of how to implement a [bfs](https://www.youtube.com/watch?v=7Cz91Uj0VCU)

125. exercise [link](https://leetcode.com/problems/find-kth-largest-xor-coordinate-value/) 1738, after watching this youtube video, this question looks [weider](https://www.youtube.com/watch?v=UgsURtz0v94)

126. exercise [link](https://leetcode.com/problems/ways-to-make-a-fair-array/) 1664, still no end to end idea of how will I do it, but I feel a post coming

127. exercise [link](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) 1011, still no end to end solution but this is an easy problem

128. exercise [link](https://leetcode.com/problems/find-unique-binary-string/) 1980, esasy

129. exercise [link](https://leetcode.com/problems/count-sub-islands/) 1905, and easier

130. exercise [link](https://leetcode.com/problems/max-consecutive-ones-iii/) 1004, a post is comiiiiiing

131. exercise [link](https://leetcode.com/problems/combinations/) 77, cool practice

132. exercise [link](https://leetcode.com/problems/arithmetic-slices/) 413, some great ideas for this thing

133. exercise [link](https://leetcode.com/problems/game-of-life/) 289. game of life

134. exercise [link](https://leetcode.com/problems/average-waiting-time/) 1701

135. exercise [link](https://leetcode.com/problems/replace-words/) 648

136. exercise [link](https://leetcode.com/problems/image-overlap/) 835

137. exercise [link](https://leetcode.com/problems/minimum-time-to-make-rope-colorful/) 1578

138. exercise [link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/) 122

139. exercise [link](https://leetcode.com/problems/next-greater-element-ii/) 503, I did not understand, I will see a video or something

140. exercise [link](https://leetcode.com/problems/spiral-matrix-ii/) 59, I still don't have an end to end solution, but this sound easy as fuck

141. exercise [link](https://leetcode.com/problems/number-of-enclaves/) 1020, there was a similar question

142. exercise [link](https://leetcode.com/problems/reduction-operations-to-make-the-array-elements-equal/) 1887, another easy question

143. exercise [link](https://leetcode.com/problems/compare-strings-by-frequency-of-the-smallest-character/) 1170

144. exercise [link](https://leetcode.com/problems/sum-of-even-numbers-after-queries/) 985

145. exercise [link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/) 714

146. exercise [link](https://leetcode.com/problems/largest-values-from-labels/) 1090 , I don't understand what they want

147. exercise [link](https://leetcode.com/problems/min-cost-to-connect-all-points/) 1584 , well I thought there would be a funnier way to do [this](https://www.youtube.com/watch?v=f7JOBJIC-NA)

148. exercise [link](https://leetcode.com/problems/merge-triplets-to-form-target-triplet/) 1899

149. exercise [link](https://leetcode.com/problems/tuple-with-same-product/) 1726

150. exercise [link](https://leetcode.com/problems/escape-the-ghosts/) 789

151. exercise [link](https://leetcode.com/problems/largest-submatrix-with-rearrangements/) 1727

152. exercise [link](https://leetcode.com/problems/two-city-scheduling/) 1029

153. exercise [link](https://leetcode.com/problems/car-pooling/) 1094 , wat roo easy

154. exercise [link](https://leetcode.com/problems/the-k-strongest-values-in-an-array/) 1471, another quite easy

155. exercise [link](https://leetcode.com/problems/range-sum-of-sorted-subarray-sums/) 1508

156. exercise [link](https://leetcode.com/problems/count-submatrices-with-all-ones/) 1504

157. exercise [link](https://leetcode.com/problems/next-greater-node-in-linked-list/) 1019

158. exercise [link](https://leetcode.com/problems/print-words-vertically/) 1324, back to the easy questions

159. exercise [link](https://leetcode.com/problems/beautiful-arrangement-ii/) 667, well, once I see the explanation is way clearer

160. exercise [link](https://leetcode.com/problems/maximum-sum-of-two-non-overlapping-subarrays/) 1031

161. exercise [link](https://leetcode.com/problems/decode-xored-permutation/) 1734

162. exercise [link](https://leetcode.com/problems/least-number-of-unique-integers-after-k-removals/) 1481

163. exercise [link](https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/) 378

164. exercise [link](https://leetcode.com/problems/stone-game-vii/) 1690

165. exercise [link](https://leetcode.com/problems/single-element-in-a-sorted-array/) 540 , hint , one in odd position, the  other one is in an even position

166. exercise [link](https://leetcode.com/problems/exclusive-time-of-functions/) 636

167. exercise [link](https://leetcode.com/problems/map-of-highest-peak/) 1765

168. exercise [link](https://leetcode.com/problems/maximum-alternating-subsequence-sum/) 1911

169. exercise [link](https://leetcode.com/problems/maximum-compatibility-score-sum/) 1947

170. exercise [link](https://leetcode.com/problems/optimal-division/) 553

171. exercise [link](https://leetcode.com/problems/minimum-path-sum/) 64

172. exercise [link](https://leetcode.com/problems/filter-restaurants-by-vegan-friendly-price-and-distance/) 1333

173. exercise [link](https://leetcode.com/problems/rank-teams-by-votes/) 1366

174. exercise [link](https://leetcode.com/problems/find-the-duplicate-number/) 287

175. exercise [link](https://leetcode.com/problems/removing-minimum-and-maximum-from-array/) 2091

176. exercise [link](https://leetcode.com/problems/rle-iterator/) 900

177. exercise [link](https://leetcode.com/problems/remove-covered-intervals/) 1288

178. exercise [link](https://leetcode.com/problems/count-servers-that-communicate/) 1267

179. exercise [link](https://leetcode.com/problems/filling-bookcase-shelves/) 1105, way too long, did not read

180. exercise [link](https://leetcode.com/problems/count-number-of-nice-subarrays/) 1248

181. exercise [link](https://leetcode.com/problems/uncrossed-lines/) 1035

182. exercise [link](https://leetcode.com/problems/longest-string-chain/) 1048

183. exercise [link](https://leetcode.com/problems/max-chunks-to-make-sorted/) 769

184. exercise [link](https://leetcode.com/problems/count-unhappy-friends/) 1583

185. exercise [link](https://leetcode.com/problems/design-circular-deque/) 641

186. exercise [link](https://leetcode.com/problems/best-sightseeing-pair/) 1014

187. exercise [link](https://leetcode.com/problems/corporate-flight-bookings/) 1109

188. exercise [link](https://leetcode.com/problems/grumpy-bookstore-owner/) 1052

189. exercise [link](https://leetcode.com/problems/minimum-moves-to-equal-array-elements-ii/) 462

190. exercise [link](https://leetcode.com/problems/minimum-difference-between-largest-and-smallest-value-in-three-moves/) 1509

191. exercise [link](https://leetcode.com/problems/maximum-element-after-decreasing-and-rearranging/) 1846

192. exercise [link](https://leetcode.com/problems/sum-of-subarray-ranges/) 2104

193. exercise [link](https://leetcode.com/problems/maximum-product-of-word-lengths/)

194. exercise [link](https://leetcode.com/problems/shuffle-an-array/) 384

195. exercise [link](https://leetcode.com/problems/evaluate-division/) 399

196. exercise [link](https://leetcode.com/problems/array-nesting/) 565

197. exercise [link](https://leetcode.com/problems/people-whose-list-of-favorite-companies-is-not-a-subset-of-another-list/) 1452

198. exercise [link](https://leetcode.com/problems/divide-array-in-sets-of-k-consecutive-numbers/) 1296

199. exercise [link](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) 105

200. exercise [link](https://leetcode.com/problems/hand-of-straights/) 846, sound pretty similar to one I saw before

201. exercise [link](https://leetcode.com/problems/maximum-absolute-sum-of-any-subarray/) 1749

202. exercise [link](https://leetcode.com/problems/single-number-ii/) 137

203. exercise [link](https://leetcode.com/problems/rabbits-in-forest/) 781

204. exercise [link](https://leetcode.com/problems/4sum-ii/) 454

205. exercise [link](https://leetcode.com/problems/coin-change-2/) 518

206. exercise [link](https://leetcode.com/problems/minimum-limit-of-balls-in-a-bag/) 1760

207. exercise [link](https://leetcode.com/problems/loud-and-rich/) 851

208. exercise [link](https://leetcode.com/problems/design-front-middle-back-queue/) 1670

209. exercise [link](https://leetcode.com/problems/maximum-xor-of-two-numbers-in-an-array/) 421

210. exercise [link](https://leetcode.com/problems/maximum-length-of-pair-chain/) 646

211. exercise [link](https://leetcode.com/problems/open-the-lock/) 752

212. exercise [link](https://leetcode.com/problems/short-encoding-of-words/) 820

213. exercise [link](https://leetcode.com/problems/moving-stones-until-consecutive-ii/) 1040

214. exercise [link](https://leetcode.com/problems/remove-stones-to-minimize-the-total/)

215. exercise [link](https://leetcode.com/problems/accounts-merge/) 721

216. exercise [link](https://leetcode.com/problems/adding-spaces-to-a-string/) 2109

217. exercise [link](https://leetcode.com/problems/diagonal-traverse/) 498

218. exercise [link](https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/) 1482

219. exercise [link](https://leetcode.com/problems/last-moment-before-all-ants-fall-out-of-a-plank/) 1503

220. exercise [link](https://leetcode.com/problems/koko-eating-bananas/) 875

221. exercise [link](https://leetcode.com/problems/find-a-peak-element-ii/) 1901

222. exercise [link](https://leetcode.com/problems/shopping-offers/) 638

223. exercise [link](https://leetcode.com/problems/delete-and-earn/) 740

224. exercise [link](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/) 106

225. exercise [link](https://leetcode.com/problems/minimum-area-rectangle-ii/) 963

226. exercise [link](https://leetcode.com/problems/task-scheduler/) 621

227. exercise [link](https://leetcode.com/problems/valid-sudoku/) 36

228. exercise [link](https://leetcode.com/problems/max-number-of-k-sum-pairs/) 1679

229. exercise [link](https://leetcode.com/problems/find-and-replace-in-string/) 833

230. exercise [link](https://leetcode.com/problems/sort-colors/) 75

231. exercise [link](https://leetcode.com/problems/number-of-boomerangs/) 447

232. exercise [link](https://leetcode.com/problems/container-with-most-water/) 11

233. exercise [link](https://leetcode.com/problems/minimum-area-rectangle/) 939

234. exercise [link](https://leetcode.com/problems/minimum-time-difference/) 539

235. exercise [link](https://leetcode.com/problems/minimum-moves-to-equal-array-elements/) 453

236. exercise [link](https://leetcode.com/problems/peeking-iterator/) 284

237. exercise [link](https://leetcode.com/problems/word-subsets/) 916

238. exercise [link](https://leetcode.com/problems/magnetic-force-between-two-balls/) 1552

239. exercise [link](https://leetcode.com/problems/stone-game-vi/) 1686

240. exercise [link](https://leetcode.com/problems/permutations-ii/) 47

241. exercise [link](https://leetcode.com/problems/form-array-by-concatenating-subarrays-of-another-array/) 1764

242. exercise [link](https://leetcode.com/problems/number-of-smooth-descent-periods-of-a-stock/) 2110

243. exercise [link](https://leetcode.com/problems/subarray-sums-divisible-by-k/) 974

244. exercise [link](https://leetcode.com/problems/find-the-smallest-divisor-given-a-threshold/) 1283

245. exercise [link](https://leetcode.com/problems/number-of-islands/) 200

246. exercise [link](https://leetcode.com/problems/brick-wall/) 554

247. exercise [link](https://leetcode.com/problems/previous-permutation-with-one-swap/) 1053

248. exercise [link](https://leetcode.com/problems/number-of-subarrays-with-bounded-maximum/) 795

249. exercise [link](https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60/) 1010

250. exercise [link](https://leetcode.com/problems/maximum-side-length-of-a-square-with-sum-less-than-or-equal-to-threshold/) 1292

251. exercise [link](https://leetcode.com/problems/maximum-erasure-value/) 1695

252. exercise [link](https://leetcode.com/problems/minimum-score-triangulation-of-polygon/) 1039

253. exercise [link](https://leetcode.com/problems/largest-sum-of-averages/) 813

254. exercise [link](https://leetcode.com/problems/subsets-ii/) 90

255. exercise [link](https://leetcode.com/problems/shortest-bridge/) 934

256. exercise [link](https://leetcode.com/problems/combination-sum-ii/) 40

257. exercise [link](https://leetcode.com/problems/total-hamming-distance/) 477

258. exercise [link](https://leetcode.com/problems/online-election/) 911

259. exercise [link](https://leetcode.com/problems/vowel-spellchecker/) 966

260. exercise [link](https://leetcode.com/problems/watering-plants-ii/) 2105

261. exercise [link](https://leetcode.com/problems/maximum-length-of-repeated-subarray/) 718

262. exercise [link](https://leetcode.com/problems/path-with-minimum-effort/) 1631

263. exercise [link](https://leetcode.com/problems/rotting-oranges/) 994

264. exercise [link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/) 309

265. exercise [link](https://leetcode.com/problems/advantage-shuffle/) 870

266. exercise [link](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/) 452

267. exercise [link](https://leetcode.com/problems/equal-sum-arrays-with-minimum-number-of-operations/) 1775

268. exercise [link](https://leetcode.com/problems/insert-delete-getrandom-o1/) 380

269. exercise [link](https://leetcode.com/problems/longest-word-in-dictionary-through-deleting/) 524

270. exercise [link](https://leetcode.com/problems/minimum-domino-rotations-for-equal-row/) 1007

271. exercise [link](https://leetcode.com/problems/largest-magic-square/) 1895

272. exercise [link](https://leetcode.com/problems/maximum-length-of-a-concatenated-string-with-unique-characters/)

273. exercise [link](https://leetcode.com/problems/greatest-sum-divisible-by-three/) 1262

274. exercise [link](https://leetcode.com/problems/maximum-of-absolute-value-expression/) 1131

275. exercise [link](https://leetcode.com/problems/construct-the-lexicographically-largest-valid-sequence/) 1718

276. exercise [link](https://leetcode.com/problems/longest-word-in-dictionary/) 720

277. exercise [link](https://leetcode.com/problems/maximum-number-of-consecutive-values-you-can-make/) 1798

278. exercise [link](https://leetcode.com/problems/increasing-subsequences/) 491

279. exercise [link](https://leetcode.com/problems/video-stitching/) 1024

280. exercise [link](https://leetcode.com/problems/last-stone-weight-ii/) 1049

281. exercise [link](https://leetcode.com/problems/predict-the-winner/) 486

282. exercise [link](https://leetcode.com/problems/maximum-average-pass-ratio/) 1792

283. exercise [link](https://leetcode.com/problems/boats-to-save-people/) 881

284. exercise [link](https://leetcode.com/problems/maximum-points-you-can-obtain-from-cards/) 1423

285. exercise [link](https://leetcode.com/problems/longest-arithmetic-subsequence-of-given-difference/) 1218

286. exercise [link](https://leetcode.com/problems/valid-triangle-number/) 611

287. exercise [link](https://leetcode.com/problems/satisfiability-of-equality-equations/) 990

288. exercise [link](https://leetcode.com/problems/triangle/) 120

289. exercise [link](https://leetcode.com/problems/find-right-interval/) 436

290. exercise [link](https://leetcode.com/problems/minimum-sideway-jumps/) 1824

291. exercise [link](https://leetcode.com/problems/largest-1-bordered-square/) 1139

292. exercise [link](https://leetcode.com/problems/plates-between-candles/)

293. exercise [link](https://leetcode.com/problems/diagonal-traverse-ii/) 1424

294. exercise [link](https://leetcode.com/problems/longest-arithmetic-subsequence/) 1027

295. exercise [link](https://leetcode.com/problems/find-the-winner-of-an-array-game/) 1535 

296. exercise [link](https://leetcode.com/problems/largest-plus-sign/) 764

297. exercise [link](https://leetcode.com/problems/length-of-longest-fibonacci-subsequence/) 873

298. exercise [link](https://leetcode.com/problems/combination-sum-iv/) 377

299. exercise [link](https://leetcode.com/problems/minimum-increment-to-make-array-unique/) 945

300. exercise [link](https://leetcode.com/problems/longest-consecutive-sequence/) 128

301. exercise [link](https://leetcode.com/problems/design-circular-queue/) 

302. exercise [link](https://leetcode.com/problems/partition-array-into-disjoint-intervals/) 915

303. exercise [link](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/) 80

304. exercise [link](https://leetcode.com/problems/most-beautiful-item-for-each-query/) 2070

305. exercise [link](https://leetcode.com/problems/longest-increasing-subsequence/) 300

306. exercise [link](https://leetcode.com/problems/maximum-distance-between-a-pair-of-values/) 1855

307. exercise [link](https://leetcode.com/problems/minimum-operations-to-make-a-uni-value-grid/) 2033

308. exercise [link](https://leetcode.com/problems/the-time-when-the-network-becomes-idle/) 2039, what a long description, just readed the discussion section

309. exercise [link](https://leetcode.com/problems/binary-subarrays-with-sum/) 930

310. exercise [link](https://leetcode.com/problems/maximum-width-ramp/) 962

311. exercise [link](https://leetcode.com/problems/coloring-a-border/) 1034

312. exercise [link](https://leetcode.com/problems/finding-pairs-with-a-certain-sum/) 1865

313. exercise [link](https://leetcode.com/problems/find-the-most-competitive-subsequence/) 1673

314. exercise [link](https://leetcode.com/problems/array-with-elements-not-equal-to-average-of-neighbors/) 1968

315. exercise [link](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) 153

316. exercise [link](https://leetcode.com/problems/longest-turbulent-subarray/)  978

317. exercise [link](https://leetcode.com/problems/as-far-from-land-as-possible/) 1162

318. exercise [link](https://leetcode.com/problems/minimum-cost-homecoming-of-a-robot-in-a-grid/) 2087

319. exercise [link](https://leetcode.com/problems/search-a-2d-matrix-ii/) dannnmmmmm this is cool

320. exercise [link](https://leetcode.com/problems/detect-cycles-in-2d-grid/) 1559

321. exercise [link](https://leetcode.com/problems/set-matrix-zeroes/) 73

322. exercise [link](https://leetcode.com/problems/car-fleet/) 853

323. exercise [link](https://leetcode.com/problems/product-of-the-last-k-numbers/) 1352

324. exercise [link](https://leetcode.com/problems/pacific-atlantic-water-flow/) 417

325. exercise [link](https://leetcode.com/problems/3sum-closest/) 16

326. exercise [link](https://leetcode.com/problems/non-overlapping-intervals/) 435

327. exercise [link](https://www.starplus.com/live-event/73JiB7Zx9FCj) 1722

328. exercise [link](https://leetcode.com/problems/decrease-elements-to-make-array-zigzag/) 1144

329. exercise [link](https://leetcode.com/problems/alert-using-same-key-card-three-or-more-times-in-a-one-hour-period/) 1604

330. exercise [link](https://leetcode.com/problems/check-if-word-can-be-placed-in-crossword/) 2018

331. exercise [link](https://leetcode.com/problems/super-ugly-number/) 313

332. exercise [link](https://leetcode.com/problems/check-if-there-is-a-valid-path-in-a-grid/) 1391

333. exercise [link](https://leetcode.com/problems/expressive-words/) 809

334. exercise [link](https://leetcode.com/problems/range-sum-query-2d-immutable/) 304

335. exercise [link](https://leetcode.com/problems/bag-of-tokens/) 948

336. exercise [link](https://leetcode.com/problems/partition-to-k-equal-sum-subsets/) 698

337. exercise [link](https://leetcode.com/problems/house-robber/) 198

338. exercise [link](https://leetcode.com/problems/closest-dessert-cost/) 1774 

339. exercise [link](https://leetcode.com/problems/describe-the-painting/) 1943, 

340. exercise [link](https://leetcode.com/problems/maximum-number-of-non-overlapping-subarrays-with-sum-equals-target/) 1546

341. exercise [link](https://leetcode.com/problems/count-nodes-with-the-highest-score/) 2049

342. exercise [link]()

343. exercise [link]()

344. exercise [link]()

345. exercise [link]()

346. exercise [link]()

347. exercise [link]()

348. exercise [link]()

349. exercise [link]()

350. exercise [link]()

351. exercise [link]()

352. exercise [link]()

353. exercise [link]()

354. exercise [link]()

355. exercise [link]()

356. exercise [link]()

357. exercise [link]()

358. exercise [link]()

359. exercise [link]()

360. exercise [link]()

361. exercise [link]()

362. exercise [link]()

363. exercise [link]()

364. exercise [link]()

365. exercise [link]()

366. exercise [link]()

367. exercise [link]()

368. exercise [link]()

369. exercise [link]()

370. exercise [link]()

371. exercise [link]()

372. exercise [link]()

373. exercise [link]()

374. exercise [link]()

375. exercise [link]()

376. exercise [link]()

377. exercise [link]()

378. exercise [link]()

379. exercise [link]()

380. exercise [link]()

381. exercise [link]()

382. exercise [link]()

383. exercise [link]()

384. exercise [link]()

385. exercise [link]()

386. exercise [link]()

387. exercise [link]()

388. exercise [link]()

389. exercise [link]()

390. exercise [link]()

391. exercise [link]()

392. exercise [link]()

393. exercise [link]()

394. exercise [link]()

395. exercise [link]()

396. exercise [link]()

397. exercise [link]()

398. exercise [link]()

399. exercise [link]()

400. exercise [link]()

401. exercise [link]()

402. exercise [link]()

403. exercise [link]()

404. exercise [link]()

405. exercise [link]()

406. exercise [link]()

407. exercise [link]()

408. exercise [link]()

409. exercise [link]()


# Questions that I think are poorly written

1. 1656 ---> ordered stream
2. 1385 ---> Find the Distance Value Between Two Arrays
3. 2073 ---> Time Needed to Buy Tickets 
4. 1854 ---> Maximum Population Year
5. 717  ---> 1-bit and 2-bit Characters
6. 950  ---> Reveal Cards In Increasing Order
7. 893  ---> Groups of Special-Equivalent Strings
8. 969  ---> Pancake Sorting


# TO-DO

1. Create an english version of every video or documentaion used in the documentation 
