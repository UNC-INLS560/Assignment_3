# Assignment 3: Square Roots

> [!IMPORTANT]
> This assignment is to be completed individually. It is not a team project.  You must document (using comments in your code) all resources (beyond our official textbook, Canvas, the class discussion forum, or the class website) that you used to help you complete this assignment. For example, if you referenced a code example from an online website such as Stackoverflow or github you could acknowledge it as follows: 
>
> ```
> # Next we print 'Hello, World' to the console.
> # Based on help from: https://stackoverflow.com/questions/826948/syntax-error-on-print-with-python-3
> print("Hello, world!")
> ```
>
> You must provide an attribution to any resource you consulted to complete this assignment except for our official textbook, Canvas, the class discussion forum, or the class website. Resources that require attribution include — but are not limited to — AI tools (even those built in to VS Code), websites, books, notes from other students, tutors, or help from other people (friends, classmates, etc.). Under no circumstances are you to look at or copy any material related to another person's solution for this assignment.
>
> To repeat, you must attribute any resource you consulted to complete this assignment other than our official textbook, Canvas, class discussion forum, or the class website. You must cite all AI technologies you used, if any, to complete this assignment. Failure to provide attribution is a violation of the honor code.

## Overview

One of the oldest methods for computing the [square root](https://mathworld.wolfram.com/SquareRoot.html) of a number is the [Babylonian Method](https://en.wikipedia.org/wiki/Square_root_algorithms). The Babylonian Method uses an iterative algorithm to make successively more accurate estimates of a number's square root. The algorithm stops iterating when the estimate shows no further sign of improvement, or when the estimate is within some acceptable margin of error. The acceptable margin of error is often called an _epsilon_.

Assuming that you need to solve for the square root of $x$, the algorithm works as follows:

1. **Choose an epsilon value** that determines how close your solution should be to the actual square root value before you decide it is "good enough." Because this assignment asks you to solve for the square root to three decimal places, we can safely set the epsilon value to 0.0001 (four decimal places). This guarantees that our solution will be accurate to the precision we need for displaying to the screen.

1. **Choose an initial estimate** $e$ for the square root of $x$. An easy and perfectly valid approach is to set the initial estimate $e=x$. For example, you could set the first estimate for the square root of 4 to be 4.

1. **Evaluate the estimate** by dividing the value $x$ by your estimate $e$, and comparing the result of that division to the current estimate $e$. If your estimate $e$ were to be exactly equal to the square root, then you would find that $\frac{x}{e}=e$. In practice, unless you are lucky, there will typically be some difference between these two values ($\frac{x}{e}$ and $e$) even after many iterations of the algorithm.

1. **Determine if the estimate is "good enough" to stop.** A smaller difference between $\frac{x}{e}$ and $e$ reflects a more accurate estimate. If the difference is smaller than your epsilon value, then you've found the answer! If not---if the difference is greater than the epsilon value---then you need to proceed to step 5 below to make your estimate more accurate.

   - Note that you'll want to look at the absolute value of the difference between $\frac{x}{e}$ and $e$. This is because $e$ may be too large or too small. To test for the absolute value, you could use if/else logic to see which term ($\frac{x}{e}$ or $e$) is smaller. You could then subtract the smaller value from the larger one. Alternatively, you could use the Python's built-in function abs().

1. **Revise the estimate** (if needed based on Step 4) by setting $e$ to the average of the fraction $\frac{x}{e}$ and your old estimate $e$. Using this new estimate, go back to Step 3.

For this assignment, you'll need to write a program that solves for square roots using the algorithm outlined above. See the "Basic" and "Advanced" requirements sections below for more detailed instructions.

> [!WARNING]
> While Python has its own way of calculating square roots, you are not allowed to use it for this assignment. Instead, you must implement your own solution to this classic mathematical problem. To be clear, you should NOT use any pre-defined Python square root function anywhere in your assignment solution.

## Basic Requirements

> [!NOTE]
> Satisfying only the basic requirements perfectly, with no points deducted for any reason, would earn a maximum score of 8 out of 10 for this assignment.

You need to implement the Babylonian Method for computing square roots. Based on that core functionality, you are to write an interactive program that:

* Prompts the user to enter a integer value above zero.
* Checks to ensure that the value is indeed above zero. If not, the program displays an error message and asks for the input again.
* Computes the square root of the value using the Babylonian Method outlined above.
* Displays the square root to the user formatted to show exactly 3 decimal places (no more than 3, and no less than 3).

## Advanced Requirements

> [!NOTE]
> Satisfying both the basic and advanced requirements perfectly, with no points deducted for any reason, will result in a full 10 out of 10 score for this assignment.

Expand on the basic requirements by extending your program as follows.

* Ask the user if they want to calculate square roots for a single value, or for a range of values.
* If the user chooses to calculate the square root for a single value, the program should operate exactly as described in the Basic Requirements.
* If the user chooses to calculate the square root for a range, then the program should behave as follows:
   * Ask the user to enter a minimum integer value (the start of the range) and make sure that it is a valid integer above zero.
   * Ask the user to enter a maximum integer value (the end of the range) and validate that it is a valid integer above zero.
   * Print a table displaying the square root value for each number in the range (starting with the minimum value, ending with the maximum value, and for every value in between). The table should have two columns: one for the initial value, and the send for its square root.
   * The table should display the square root values with exactly 3 decimal places, and should right-align the numbers when printing. In this way, the square root for 100 will appear aligned with the square root for 90 in your table.

For example, if the user enters 9 as the minimum for the range and 11 as the maximum for the range, your answer should produce a table with three rows (for 9, 10, and 11) and two columns (one for the initial values 9,10,11; and a second for the corresponding square root values).


## Sample Output

First, the following is an example of the output produced by the basic requirements:

```
Enter 'single' or 'range' to solve for a single square root or a range of values, respectively: single

Enter a positive integer value: 9
Value	Square Root
   9	   3.000

```

In contrast, an example of the output produced by the advanced requirements can be found below:

```
Enter 'single' or 'range' to solve for a single square root or a range of values, respectively: range

Enter a positive integer value to start your range: 1
Enter a positive integer value to end your range: 16
Value   Square Root
   1       1.000
   2       1.414
   3       1.732
   4       2.000
   5       2.236
   6       2.449
   7       2.646
   8       2.828
   9       3.000
  10       3.162
  11       3.317
  12       3.464
  13       3.606
  14       3.742
  15       3.873
  16       4.000
```

## Grading Criteria

This assignment will be graded on a 10 point scale. Your grade for this assignment will be based on a combination of factors, including:

* Correct functionality (e.g., Does your Python code do what it is supposed to do as outlined in the basic and/or advanced requirements?)
* Clarity of your solution (e.g., Did you solve the problem directly and efficiently? Or is your answer excessively complex and/or inefficient?)
* Coding style (e.g., Is your code readable with comments, meaningful variable names, and good whitespace/indentation?)
* Meets submission requirements (see below)

## Seeking Help

For general questions about Python, please use the class forum on Piazza to seek assistance. For questions that are personal in nature or that would reveal a solution to the assignment, you ask for help by email or during office hours. However, please note that emailed questions will not receive an immediate response. It is likely that it will take 24-48 hours for me to respond.

## Submitting Your Solution

When you have completed your work on the assignment, it is time to submit your solution via Canvas.  You can submit your assignment by taking the following steps:
1. Be sure that all of your changes have been pushed to your GitHub repository for the assignment.
2. Go to the web page for your repository on github.com
3. Click the green button labeled "< > Code &#9660;" which should open a popup menu.
4. From the popup menu, click on "Download ZIP" which will download a zip file containing your entire project to your computer. 
5. Submit the zip file you just downloaded via Canvas as your solution for this assignment.


> [!WARNING]
> NOTE FOR MAC USERS: Mac users who use the Safari browser will notice that the browser will, by default, automatically unzip and delete zip files you download from the internet. To change this behavior, press and hold the Option key when clicking the "Download ZIP" menu item.  This will prevent Safari from automatically unzipping and deleting the Zip file. Instead, it will just download the Zip file as it is just as you would get on any other browser.  Only Safari users need to take this extra step.


## Due Date

The due date for this assignment can be found in the official class schedule and on Canvas.

