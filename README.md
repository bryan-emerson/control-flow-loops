[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Control Flow: Loops

In programming, loops offer developers a quick and easy way to do something
repeatedly. There are many different kinds of loops, but they all essentially do
the same thing: they repeat an action some number of times. In today's class, we
will learn about two kinds of loops: for loops and while loops.

## Prerequisites

- JavaScript Syntax
- Basic Data Types (Numbers, Booleans, Strings)
- Operators (Arithmetic, Logic, and Comparison)
- Arrays and Objects

## Objectives

By the end of this, developers should be able to:

- Iterate over arrays using loops
- Utilize `while` loops and `for` loops
- Identify problem types and match to the appropriate control flow statements

## Loops
### `while` Loops (10 min / 1:05)

A `while` loop is like an `if` statement but it will execute the content of its
block repeatedly until the condition becomes false. (i.e. the `while` loop
continues _while_ the condition is true).

```js
num = 0;
while (num <= 10) {
  console.log(num);
  num += 1; // short-hand for num = num + 1
}
```

There's a potential gotcha with working with `while` loops: because the loop
continues for as long as the condition is true, you **have to break the loop
manually**. In a `for` loop, the conditions to break the loop are all
encapsulated in the definition of the loops. In a `while` loop, that logic has
to be inside the code block. This makes `while` loops very useful in some cases (a lot of games
are built with `while` loops) but it also means you have to be
careful as you can run into an _infinite loop_.

A `while` loop is perfect for when you need a block of code to repeat an unknown number of times:

```js
let passwordGuess = "";
while (passwordGuess !== "password") {
  passwordGuess = prompt(
    "You have been imprisoned in the code-block of a while loop! What is the magic word to exit?"
  );
}
alert("Argh! You have escaped! I am so lonely, no one ever wants to stay.");
```

#### Practice `while` Loops (15 min / 1:20)
Work through the prompts in Part 1 in [this exercise](https://git.generalassemb.ly/dc-wdi-fundamentals/js-loops-practice). 
Get as far as you can in the time allotted and feel free to come back and review these!

### `for` Loops (10 min / 0:15)

Often looping is done for a set amount of times. For example, to loop five times with a `while` loop:
```js
let i=0;
while (i<5) {
  console.log(i)
  i++
 }
```

This pattern is so common that most langauges have a more specialized loop called the `for` loop. 
The syntax is more succinct but can be complicated at first.
Here's the previous example written as a `for` loop:
```js
for (let i=0; i<5; i++) {
  console.log(i)
}
```

The first thing to notice here is the overall structure. We need the `for`
keyword, followed by the parentheses and everything inside of them
(`(let i = 0; i < 10; i++)`), and then the block of code you want to repeatedly
run (inside the `{}` braces).

Let's break down what's happening between the parenthesis (`()`), because there
are three parts to this expression:

1. `let i = 0` sets up an iteratee, a variable that we will iterate (increase or
   decrease by some number) with each iteration of the loop. Consider this the
   starting point of your loop.

   It is important to use a variable keyword, and
   [`let` is the best choice](https://wesbos.com/for-of-es6/)

2. `i < 5` is the comparison expression - it's actually a conditional! The loop
   will continue to execute until this expression evaluates to false.
3. `i++` controls how the iteratee should change after each iteration. In this
   case, `++` increases the iteratee's value by `1`.

These three pieces of the `for` loop are what make them powerful - we can alter
these to iterate in hundreds of different ways. Before we get to that, let's
walk through how this loop works, as if we were the JavaScript interpreter:

1. We arrive at the for loop. Create a variable, `i`, and set it equal to 0.
2. Check our condition (`i < 5`). Is it true? Is `i` less than 5? Yes!
3. Run the block of code - in this case, print the value of `i` to the console.
4. Increment the value of `i`. In this case, increase it by 1.
5. Return to step 2 and repeat until our condition is no longer true.

We have a lot of flexibility in how we iterate our loop just based on the three
expressions inside our `for` loop. We can count up or down by changing the third
expression, we can also change the iteration by more than just one:

**This loop counts up to 100 in increments of 5:**

```js
for (let i = 0; i < 100; i += 5) {
  // code goes here...
}
```

**This loop counts down from 100:**

```js
for (let i = 100; i >= 0; i--) {
  // code goes here...
}
```

**This loop has two iterators:**

```js
for (let i = 1, j = 5; i < 5; i++, j--) {
  console.log(i, j);
}
```

**Nested loops:**

```js
for (let i = 1; i < 5; i++) {
  for (let j = 1; j < 5; j++) {
    console.log(i, j);
  }
}
```

#### Practice `for` Loops (15 min / 0:30)

Open up [this exercise](https://git.generalassemb.ly/dc-wdi-fundamentals/js-loops-practice)
and work the prompts in Part 2. 

### Iterating over Arrays (10 min / 0:40)

One of the areas where `for` loops really shine is when working with arrays. We
can set the value of `i` to `0` and use the array's length in the condition to
perform some action on every item in the array. That looks like this:

```js
let instructors = ["Tosin", "Tyler", "Zakk", "Murray", "Brock", "Paula"];

for (let i=0; i<instructors.length; i++) {
  console.log(instructors[i]);
}
```

Let's unpack what's happening here:

- We're setting our incrementer to be 0 and our condition is set up to continue
  looping while i is less than the length of the array
  (`i < instructors.length`)
- Inside our loop, we're using `i` to retrieve values from the array by their
  index.

For the first iteration of the loop, `i` is set to 0 (`let i = 0`). Since `i` is
0, we can use it to retrieve the first item in the array, at an index of 0
(`instructors[i]`). That will continue while `i` is less than
`instructors.length` (in this case, 5). With each iteration, the value of `i`
will increase by 1, so we'll retrieve the next item in the array!

#### Practice Iterating over Arrays (15 min / 0:55)

Return to [the previous exercise](https://git.generalassemb.ly/dc-wdi-fundamentals/js-loops-practice) and work through the prompts in Part 3. 

## Closing (5 min / 1:25)

You can get really far in programming with the knowledge you have right now:
data types, arrays, conditionals, and loops! The biggest challenge beginners
have with control flow is expressing their thinking in code and combining the
patterns together (like putting a `for` loop in a `while` loop or a
`conditional` in a `for` loop, etc), but don't worry - you'll get lots of
practice!

## Additional Resources

Look at Codewars challenges on
[loops](https://www.codewars.com/kata/search/javascript?beta=false&q=&r=-8&r=-7&tags=Loops)

## [License](LICENSE)

1. All content is licensed under a CC­BY­NC­SA 4.0 license.
1. All software code is licensed under GNU GPLv3. For commercial use or
   alternative licensing, please contact legal@ga.co.
