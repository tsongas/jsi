---
layout: post
title: Sudoku Solver & Node.js Modules
class: sudoku
date: 2015-02-19
---

Over the next couple of days, we're going to build an application that solves Sudoku puzzles.

## Approach

We need to approach this problem slowly.

When you tackle big problems, if you start writing code right away, you won't be focusing on solving the problem. You'll be so distracted by the code, that you'll lose track of what you're even doing. Plus, you'll write code that's not needed.

Here are some guidelines that will help keep you on track:

* Start on paper. The lo-tech environment helps keep the focus on the problem at hand.
* Write pseudo-code for solving the problem.
* Discuss whether or not the ideas in the pseudo-code will work.
* Go to the computer, write some code.
* Think about what functionality you need for your pseudo-code to work.
* Implement essential small pieces using TDD.
* Work on building medium/large pieces (using TDD) to get closer to the pseudo-code you wrote.
* If you get stuck, return to paper to discuss.


## Input

You should create a `Sudoku` class that can be instantiated with a single argument, the board. The board will be a string formed by reading the numbers of the board from the top left across, then continuing with the next row. Spaces represent unsolved cells.

For instance:

    '158 2  6 2   8  9  3  7 8 2 6 74      4 6 7      19 5 4 9 3  2  2  5   8 7  9 413'

will produce the following board and solution:

    +---------+---------+---------+    +---------+---------+---------+
    | 1  5  8 |    2    |    6    |    | 1  5  8 | 9  2  4 | 3  6  7 |
    | 2       |    8    |    9    |    | 2  4  7 | 6  8  3 | 1  9  5 |
    |    3    |    7    | 8     2 |    | 9  3  6 | 1  7  5 | 8  4  2 |
    +---------+---------+---------+    +---------+---------+---------+
    |    6    | 7  4    |         |    | 5  6  1 | 7  4  8 | 2  3  9 |
    |       4 |    6    | 7       |    | 3  9  4 | 5  6  2 | 7  8  1 |
    |         |    1  9 |    5    |    | 7  8  2 | 3  1  9 | 6  5  4 |
    +---------+---------+---------+    +---------+---------+---------+
    | 4     9 |    3    |    2    |    | 4  1  9 | 8  3  7 | 5  2  6 |
    |    2    |    5    |       8 |    | 6  2  3 | 4  5  1 | 9  7  8 |
    |    7    |    9    | 4  1  3 |    | 8  7  5 | 2  9  6 | 4  1  3 |
    +---------+---------+---------+    +---------+---------+---------+

The code should work something like this:

{% highlight javascript %}
var game = new Sudoku(str);
game.solve();
{% endhighlight %}


## Initial Solution

Your initial Sudoku solver will not solve all puzzles. It should only fill in cells when the basic rules narrow the possibilities for that cell down to one number.

Don't worry about complex boards or trying to make it solve every puzzle. You don't want your solver to be _smart_ just yet. If you're unsure if you're creating something that's too smart or not, just ask.

## Mindset

Over the course of this project, you'll probably experience huge swings in your emotional state and attitude toward the problem you're solving. It will be fun. It will be challenging. It will be rewarding. It will feel impossible. You'll get stuck. You'll feel angry. You'll question why you're working on such a silly problem, why you're even trying to learn how to be a programmer. You'll feel like an impostor. You'll solve a small piece of the problem and you'll feel elated, on top of the world, like you can solve anything. Then you'll cycle back around again.

Keep a positive mindset. When you feel the frustration coming on, take a break. Step away from the computer. Go for a walk. Get some sleep.

Hard problems are best solved by teams. You and your teammates will provide different views and ideas, different ways of looking at the problem. Explore all ideas. Keep your teammates on track and thinking positively.
