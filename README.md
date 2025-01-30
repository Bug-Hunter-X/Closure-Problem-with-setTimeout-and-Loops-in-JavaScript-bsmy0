# Closure Problem with setTimeout and Loops in JavaScript

This repository demonstrates a common closure-related bug in JavaScript when using `setTimeout` within a loop.  The issue arises because the closure created by the `setTimeout` callback function does not capture the value of `i` at the time of its creation, but rather captures a reference to the `i` variable itself. This means that by the time the `setTimeout` function finally executes, the loop has already completed, and `i` will hold its final value (10 in this case).

## Bug Description
The provided `bug.js` file contains a function that uses a `for` loop and `setTimeout` to log numbers from 0 to 9. Due to the closure issue, it incorrectly logs 10 ten times instead of logging numbers 0 through 9 sequentially.

## Solution
The `bugSolution.js` file offers a solution to this problem by using an immediately invoked function expression (IIFE) or `let` to correctly capture the value of `i` for each iteration of the loop.