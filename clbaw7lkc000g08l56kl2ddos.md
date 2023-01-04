# The last Recursion Blog you’ll ever need

The ‘if’ statement that we need here is, either you know about recursion, or you don’t. If you know, then you can probably stop. But, if you don’t then you definitely must read on.

Recursion is a phenomenon which is said to have occurred when a function is called inside its block.

But before we dive into recursion, let’s try to write a code for a factorial. We’ll use JavaScript.

What is a Factorial?

Mathematically, it is written like this.

![fibonacci.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670250426534/yG6WUjqiK.png align="left")

Or as we humans call it, say 5!. That would mean 5 x 4 x 3 x 2 x 1 = 120. Observe the pattern here, that it *loops* from 5 to 1 and multiplies all the numbers it meets on the way. Observe the “loops”, and we can code that.

```
const num = 5;

const factorial = (n) => {
  let factorial = 1;
  for (let i = n; i > 0; i--) {
    factorial *= i;
  }
  return factorial;
}
  
console.log(factorial(num));

```

This is very nice and succinct, but according to the mathematical definition. We must be able to write it as, say 5! = 5 x 4!, where 4! = 4 x 3! and so on. Or in other words, for n!, n! = n x (n-1)!.

We can write a function that can return itself multiplied by a function on a value less than it.

```
const num = 5;

const factorial = (n) => {
  return n * factorial(n - 1);
};

console.log(factorial(num));

```
Looks fine, except its wrong. We have to tell the code to stop at n === 1, else it goes (1–1) and makes it 0. After that however low it goes it will only return 0.

Actually it won’t return anything, because the top-most function will never be finished, and so it'll keep creating stacks upon stacks until we meet our friend, Stack Overflow.

To fix this, we must explicitly tell it to stop when n = 1, and so our code will be:


```
const num = 5;

const factorial = (n) => {
  if (n === 1) return 1;
  return n * factorial(n - 1);
};

console.log(factorial(num));

```

Well, so clean and short. Congratulations. You just wrote your first recursive function, successfully that is.

Now that you know recursion, you’ll write all your for loops like this right? Actually you can, but it is not recommended, because of the single point of error of forgetting to add the break to the recursion. If you forget that one line, your computer will not forgive you. In fact, the opposite must be the go-to. Always use iteration wherever possible. Avoid recursion if you can.

So the moment you actually learn recursion, must also be the point where you stop writing it? No. There is a very real, very cool use for recursion that exists, and using recursion there is like putting the last jigsaw piece in a 5000 piece jigsaw-puzzle.

Suppose, we want to extract { name : ‘Albus’ } from this…

```
const ob = {
  layer1: {
    layer2: {
      layer3: {
        layer4: {
          layer5: {
            name: 'Albus',
          },
        },
      },
    },
  },
};

```
No amount of iteration will be useful. There exists no for loop or while loop that can return what we want from this object using loops. If you try to be a smart-ass and write a very specific code, you might as well write the console.log of the answer itself. We want code that scales and handles edge cases.

Observe, that for every key-value pair in this object, there are only two possible scenarios. Either the value is an object, or the value is not an object (It is a string, in this case). Consider if it is not an object, what shall we do? We return the key-value pair as an object. So we’ll make an empty object and populate it with our key-value pair.

```
let finalObj = {};
const flatter = (obj) => {
  //
  const keyList = Object.keys(obj);
  const firstKey = keyList[0];
  //
  if (typeof obj[firstKey] === 'object') {
   
  } else {
    finalObj[firstKey] = obj[firstKey];
  }
  return finalObj;
};

console.log(flatter(ob));

```
But “What If?”, right? well, we’ll run the same function on that object.

```
let finalObj = {};
const flatter = (obj) => {
  //
  const keyList = Object.keys(obj);
  const firstKey = keyList[0];
  //
  if (typeof obj[firstKey] === 'object') {
    flatter(obj[firstKey]); //                    <----- This line
  } else {
    finalObj[firstKey] = obj[firstKey];
  }
  return finalObj;
};

console.log(flatter(ob));

```
This is called ‘flattening of a tree’, similarly there is also ‘flattening of an array’ , which is very similar, and you can write it yourself.

What if we have to write a code that flattens a proper tree like this?

```
const names = {
  name1: {
    ActualName: 'Dhawal',
    Tricks: {
      Unreversed: {
        capitalised: {
          Greek: {
            nameGre: 'ALBUS',
          },
          Japanese: {
            nameJap: 'SHIROI',
          },
        },
        uncapitalised: {
          Greek: {
            nameGre: 'albus',
          },
          Japanese: {
            nameJap: 'shiroi',
          },
        },
      },

      Reversed: {
        capitalised: {
          Greek: {
            nameGre: 'SUBLA',
          },
          Japanese: {
            nameJap: 'IORIHS',
          },
        },
        uncapitalised: {
          Greek: {
            nameGre: 'subla',
          },
          Japanese: {
            nameJap: 'iorihs',
          },
        },
      },
    },
  },
  name2: {
    ActualName: 'Viral',
    Tricks: {
      Unreversed: {
        capitalised: {
          Greek: {
            nameGre: 'EXIMIUS',
          },
          Japanese: {
            nameJap: 'ERAI',
          },
        },
        uncapitalised: {
          Greek: {
            nameGre: 'eximius',
          },
          Japanese: {
            nameJap: 'erai',
          },
        },
      },

      Reversed: {
        capitalised: {
          Greek: {
            nameGre: 'SUIMIXE',
          },
          Japanese: {
            nameJap: 'IARE',
          },
        },
        uncapitalised: {
          Greek: {
            nameGre: 'suimixe',
          },
          Japanese: {
            nameJap: 'iare',
          },
        },
      },
    },
  },
  error: null,
};

```
Here we can use the for..in loop to loop through all the objects in the parent, and apply our recursion to all the children. We can also set names for them, so that the final object that is returned will have the layering separated by whatever string we want. Like so.

```
let finalObj = {};
const flatter = (obj, parent) => {
  for (let key in obj) {
    if (typeof obj[key] === 'object') {
      flatter(obj[key], parent + '_' + key); //    <---- This line
    } else {
      finalObj[parent + '_' + key] = obj[key];
    }
  }
};

flatter(names, 'names');

console.log(finalObj);

```
But wait! Observe the last key-value pair in our object that shows how I write my codes. The ‘null’ there, is read by JavaScript as an object, but since it is just ‘null’, it is ignored in the final object. But that also means that our answer is incomplete. So, we must also check for it in our ‘if’ condition.

```
let finalObj = {};
const flatter = (obj, parent) => {
  for (let key in obj) {
    if (typeof obj[key] === 'object' && obj[key]) {//                           <---- This line
      flatter(obj[key], parent + '_' + key); 
    } else {
      finalObj[parent + '_' + key] = obj[key];
    }
  }
};

flatter(names, 'names');

console.log(finalObj);

```
Viola! We’re done!

Now, that you *kNoW* recursion, let try to write a function that returns the Fibonacci sequence till that point. (Should be called ‘The Pingala Sequence’, tbh).

What is a Fibonacci Sequence?

It starts with 1, then it adds the two previous numbers to get the second number. But there is only one number, I hear you say. So what is 1 + 0? Anyway, this pattern is followed for the rest of the numbers. So it is,

1, 1, 2, 3, 5, 8, 13, and so on.

Before we start to write recursion, try to think what are the ‘if’ statements here? What is the ‘IF’ of my Fibonacci sequence? When we traverse from the nth Fibonacci number to the first one, where must we stop? When n === 1? or something else? More importantly, what shall our function return?

Fibonacci(n) = Fibonacci(n - 1) + Fibonacci(n - 2)

So, let’s write that.

```
let num = 5;

const fib = (n) => {  
  if (n === 1) return 1;//                     <------This Line
  return fib(n - 1) + fib(n - 2);
};

console.log(fib(num));

``` 
This is a good recursion question, because it calls the function inside itself more than one times. But since we also have to deal with (n — 2), for the 2nd Fibonacci number, it will make it (0), which will not stop our recursion. So we just write (n <= 1), and were good.

```
let num = 5;

const fib = (n) => {  
  if (n <= 1) return 1;//                     <------This Line
  return fib(n - 1) + fib(n - 2);
};

console.log(fib(num));

```
Now, for funsies, let’s also write it without recursion.

```

let num = 5; // goes exponent above 102, goes apeshit above 1476, try it.

const fib = (n) => {
  let fibArr = [1, 1];
  for (i = 0; i < n - 2; i++) {
    let m = fibArr[i] + fibArr[i + 1];
    fibArr.push(m);
  }
  //
  for (let i = 0; i < fibArr.length; i++) {
    console.log(i + 1, fibArr[i]);
  }
};

```
If you run the recursion code, it will not give answers for beyond n = 50, in a reasonable amount of time. But the iteration code will not only tell you that beyond n = 102, the values need to written using exponents, but also that beyond n = 1457 the values are literally considered as infinity by the computers. Iteration is just that good.

I know, I know. I could have used “memoization” to make the recursion perform better, but that is not recursion, and I want to show that recursion is not ideal for an iterative process.

If you finally have confidence in recursion, try writing a function which checks whether a string is a palindrome or not, using recursion.

For further reading, read about ‘Tower of Brahma/Hanoi’, and try to apply recursion to solve that problem.

If you are still confused about Recursion, read the first line again.