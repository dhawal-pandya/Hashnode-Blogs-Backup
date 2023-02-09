# Demystifying Big O Notations

You like coding right? You like maths too, right? right? So allow me to combine both to explain what the famous/infamous Big O notation is. It is like a forecast of your code, the time complexity and space complexity estimation of it. And exactly like a weather forecast, it is expected to be wrong 10 to 20 percent of the time. Nevertheless, it is still better to know what to expect than to not know it.

Big O notation is a mathematical representation of the upper bound of the growth rate of a function. It is used to describe the efficiency of algorithms, in terms of their time and space complexity. The notation provides an estimate of the maximum amount of resources (such as time or memory) that an algorithm will require, in the worst-case scenario.

### Time Complexity

Time complexity is a measure of the amount of time an algorithm requires to complete its operations. It refers to the number of operations or steps the algorithm needs to perform, relative to the size of the input. Time complexity is an important factor to consider when choosing algorithms, as it determines how efficiently the algorithm will run.

Time complexity when expressed using big O notation, which provides an upper bound on the growth rate of the running time of an algorithm. For example, an algorithm with a time complexity of O(n^2) means that the number of operations performed will grow quadratically with the size of the input.

### Space Complexity:

Space complexity is a measure of the amount of memory space an algorithm requires in order to execute its operations. It refers to the amount of memory or storage that an algorithm needs to run, regardless of its running time.

Space complexity is important to consider because memory is often a limited resource, especially for embedded systems or mobile devices with limited memory. An algorithm with high space complexity will require more memory, which may cause the program to crash or result in slow performance. On the other hand, an algorithm with low space complexity will require less memory, making it more efficient and less likely to cause problems.

Space complexity is typically expressed in terms of the size of the input, just like time complexity. For example, an algorithm with a space complexity of O(n) means that the amount of memory required by the algorithm will grow linearly with the size of the input. An algorithm with a space complexity of O(1) means that the amount of memory required by the algorithm is constant and does not depend on the size of the input.

### Big O Notation

By carefully considering both time and space complexity, one can choose the most efficient algorithm for a given situation. The big O notation is written as O(f(n)), where f(n) is a function that describes the growth rate of the algorithm.

It is important to note that the big O notation provides only an upper bound on the algorithm's growth rate. This means that the actual running time of the algorithm may be much better than the estimate provided by the big O notation. For example, suppose an algorithm has a time complexity of O(n^2). In that case, this means that the number of operations that the algorithm will perform will grow quadratically with the size of the input, in the worst-case scenario. However, the actual running time of the algorithm may be much better than this estimate, especially if the algorithm is optimized for specific cases or by factors such as the performance of the hardware, the compiler used, or the presence of other programs running simultaneously.

Another important aspect of the big O notation is that it ignores constant factors and lower-order terms. This is because the goal of the big O notation is to provide a general estimate of the growth rate of the algorithm, rather than a precise measure of its running time. For example, suppose an algorithm has a time complexity of O(n^2). In that case, it means that the number of operations that the algorithm will perform will grow quadratically with the size of the input, regardless of the specific constant factors and lower-order terms that may be involved.

Basically, the big O notation is a useful tool for describing the efficiency of algorithms, in terms of their time and space complexity. It provides an estimate of the maximum amount of resources that an algorithm will require, in the worst-case scenario, and helps to compare the efficiency of different algorithms.

### Big Theta Notation

Big Theta notation is similar to big O notation, in that it provides an estimate of the growth rate of a function. However, whereas big O notation provides only an upper bound on the growth rate of a function, big Theta notation provides a tight bound on the growth rate. In other words, big Theta notation offers an estimate of the exact running time of an algorithm, in the average-case scenario.

The big Theta notation is written as Θ(f(n)), where f(n) is a function that describes the growth rate of the algorithm. Here too, Θ(n) represents a linear growth rate, while Θ(n^2) represents a quadratic growth rate.

In contrast to big O notation, big Theta notation takes into account both the upper and lower bounds on the growth rate of an algorithm. This means that big Theta notation provides a more precise estimate of the running time of an algorithm, compared to big O notation.

big Theta notation is a more precise tool for describing the efficiency of algorithms, compared to big O notation. It provides a tight bound on the growth rate of an algorithm, in the average-case scenario, and is especially useful for comparing the efficiency of different algorithms, in terms of their average-case performance.

### Other Notations

Along with big O and big Theta notations, there are two other notations commonly used to describe the efficiency of algorithms: big Omega (Ω) and little o (o).

Big Omega notation is used to describe the lower bound on the growth rate of a function. It provides an estimate of the minimum amount of resources that an algorithm will require, in the best-case scenario. The big Omega notation is written as Ω(f(n)), where f(n) is a function that describes the growth rate of the algorithm.

Little o notation is used to describe an upper bound on the growth rate of a function, but it is less strict than big O notation. It provides an estimate of the maximum amount of resources that an algorithm will require, in the average-case scenario, but it ignores constant factors and lower-order terms. The little o notation is written as o(f(n)), where f(n) is a function that describes the growth rate of the algorithm.

### Conclusion

Big O, big Theta, big Omega, and little o notations are all useful tools for describing the efficiency of algorithms, each has its own specific purpose and usage. By understanding the differences between these notations, one can make informed decisions about the efficiency and performance of algorithms, and choose the most appropriate one for a given situation.

continued in the next post...