# Tower of Hanoi

## Introduction
The Tower of Hanoi is a classic problem that involves moving disks from one rod to another, following specific rules. This puzzle is a great way to understand recursion and algorithmic problem solving.

## Problem Description

The Tower of Hanoi puzzle consists of three rods and a number of disks of different sizes, which can slide onto any rod. The puzzle starts with the disks neatly stacked in ascending order of size on one rod, the smallest disk at the top. The objective of the puzzle is to move the entire stack to another rod, following these rules:

1. **Only one disk can be moved at a time.**
2. **Each move consists of taking the top disk from one of the stacks and placing it on top of another stack or on an empty rod.**
3. **No larger disk may be placed on top of a smaller disk.**

## Solving the Puzzle Using Stacks

Stacks are an ideal data structure for solving the Tower of Hanoi problem in Java because they follow the Last In, First Out (LIFO) principle, which aligns with the puzzle's rules of moving the top disk.

### Step-by-Step Solution

1. **Initialize Stacks:**
   - Create three stacks to represent the three rods. Each stack will hold the disks in the order they are placed on the rod.

2. **Set Up the Initial State:**
   - Place all the disks on the first stack (source rod) in descending order, with the largest disk at the bottom and the smallest at the top.

3. **Recursive Algorithm:**
   - The recursive solution involves moving `n-1` disks from the source rod to an auxiliary rod, moving the nth (largest) disk directly to the target rod, and then moving the `n-1` disks from the auxiliary rod to the target rod.

4. **Base Case:**
   - If there is only one disk, simply move it from the source rod to the target rod.

5. **Recursive Steps:**
   - Move `n-1` disks from the source rod to the auxiliary rod using the target rod as a buffer.
   - Move the nth disk from the source rod to the target rod.
   - Move the `n-1` disks from the auxiliary rod to the target rod using the source rod as a buffer.

### Detailed Process

1. **Initialization:**
   - Create three stacks: `source`, `target`, and `auxiliary`.
   - Push all disks onto the `source` stack, starting with the largest disk.

2. **Recursive Function (Pseudo-code):**
   ```java
   void moveDisks(int n, Stack<Integer> source, Stack<Integer> target, Stack<Integer> auxiliary) {
       if (n == 1) {
           target.push(source.pop()); // Move the single disk to the target
           return;
       }
       moveDisks(n-1, source, auxiliary, target); // Move n-1 disks to auxiliary
       target.push(source.pop()); // Move the nth disk to target
       moveDisks(n-1, auxiliary, target, source); // Move n-1 disks from auxiliary to target
   }
## Recursive Steps

1. **First Recursive Call:** Move `n-1` disks from `source` to `auxiliary` using `target` as an auxiliary rod.
2. **Second Recursive Call:** Move the nth disk from `source` to `target`.
3. **Third Recursive Call:** Move `n-1` disks from `auxiliary` to `target` using `source` as an auxiliary rod.

## Execution

Call the recursive function with the total number of disks and the three stacks. The function will handle the moves and ensure all disks are transferred to the target rod following the rules.

By using stacks in Java, you can leverage the LIFO property to manage the disks and perform the required moves efficiently. The recursive approach breaks down the problem into manageable sub-problems, solving the Tower of Hanoi puzzle effectively.

## Conclusion

The Tower of Hanoi is a great way to understand recursion and algorithmic problem solving. It showcases how a complex problem can be broken down into simpler sub-problems, a fundamental concept in computer science.
