Download Link: https://assignmentchef.com/product/solved-cs1010-assignment-2
<br>
Question 1: Collatz—————————–

The Collatz Conjecture was introduced by the mathematicianLothar Collatz in 1937. Also known as the 3n+1 conjecture,the problem can be stated very simply but yet no one canprove that it is true or false. The conjecture states thefollowing:

Consider the following operation on a positive integer n: ifn is even, divide it by two; otherwise, triple it and addone. Suppose we form a sequence of numbers by performingthis operation repeatedly, beginning with any positiveinteger, then this process will eventually reach the number1, for any initial positive integer n.

For instance, if n=10, then we have the sequence

10 -&gt; 5 -&gt; 16 -&gt; 8 -&gt; 4 -&gt; 2 -&gt; 1

The smallest number of steps taken by this process for nto reach 1 is called the total stopping time. In theexample above, the total stopping time for 10 is 6.

Write a program collatz.c that reads in a positive integern from the standard input and finds out, among the numbersbetween 1 to n, inclusive, which one has the largest totalstopping time. If two numbers have the same total stoppingtime, we break ties by choosing the larger number as theanswer.

Your program should print to the standard output, the numberwith the largest total stopping time and its correspondingtotal stopping time in two different lines.

Sample Run———-

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="127d7d7b6566526277232326">[email protected]</a>:~/as02-skeleton$ ./collatz110<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a3cccccad4d7e3d3c6929297">[email protected]</a>:~/as02-skeleton$ ./collatz10919<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="3659595f4142764653070702">[email protected]</a>:~/as02-skeleton$ ./collatz1000871178

Question 2: Triangle——————————

Write a program `triangle.c` that draws an isoscelestriangle using ` ` (white space) and `#`.  The program mustread in a positive integer representing the height h of atriangle.  The triangle must have exactly h rows.  Each rowmust have exactly 2h-1 characters (including white spacesbut excluding a new line).  On each row, the sequence of “#”characters must be centralized, padded by white spaces onboth sides.

Sample Run———-

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="721d1d1b0506320217434340">[email protected]</a>:~/as02-ooiwt$ ./triangle5#########################<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="600f0f091714201005515152">[email protected]</a>:~/as02-ooiwt$ ./triangle3#########<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6a0505031d1e2a1a0f5b5b58">[email protected]</a>:~/as02-ooiwt$ ./triangle1#

Hints—–

1.First, find the pattern to draw the triangle.

On row k, how many #s should you draw?  how many whitespaces should be padded on the left and the right?

2.Write a function that draws a particular row of the triangle.Then, call this function repeatedly in a loop.

Question 3: Prime (6 marks)—————————

Write a program called `prime` that reads a positive integern from the standard input and prints the largest primesmaller or equal to n.

Recall that a prime number is a number that is onlydivisible by 1 and itself.

Your program must not make unnecessary checks or dorepetitive work.  In particular, once you found evidencethat a number is not a prime, there is no need to continuechecking.

Sample Run———-<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="cfa0a0a6b8bb8fbfaafefefc">[email protected]</a>:~/ex03-ooiwt$ ./prime22<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="deb1b1b7a9aa9eaebbefefed">[email protected]</a>:~/ex03-ooiwt$ ./prime107<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="7c1313150b083c0c194d4d4f">[email protected]</a>:~/ex03-ooiwt$ ./prime92233720368547758079223372036854775783

Hint—-Write a boolean function `is_prime` to check if a givennumber is prime.  Then call this function in a loop.

Question 4: Pattern——————————

Even though the sequence of prime numbers appears to berandom, mathematicians have found some intriguing patternsrelated to prime numbers. In this question, you are asked towrite a program to draw a variation of the “ParallaxCompression” pattern discovered by a software engineer,Shaun Gilchrist.

The pattern visualizes the distribution of prime numbers ina triangle, in the following way. The inputs given are aninterval n (n &gt;= 1) and the height of the triangle h.

The triangle has h rows. The first row of the triangle hasone cell, the second row has three cells, the third row hasfive, etc. The cells are centrally aligned so that visuallythey form an equilateral triangle. We call the left-mostcell of each row the leading cell.

Each cell in the triangle contains n integers. The firstcell in the first row contains the numbers 1, 2, …, n. Theleading cell of the next row, Row 2, contains n numbersbetween n + 1 and 3n, with an increment of 2: i.e., n + 1, n+ 3, n + 5, .., n + (2n – 1). The leading cell of the nextrow, Row 3, contains the numbers 3n + 1 and 6n, withincrement of 3: i.e., 3n + 1, 3n + 4,3n + 7,..  3n+(3n−2),etc.

For instance, if n is 5, the leading cells of the firstthree rows contain the numbers– {1, 2, 3, 4, 5},– {6, 8, 10, 12, 14},– {16, 19, 22, 25, 28},respectively.

The rest of the cells in each row contains n numbers whereeach is one more than a number contained in the cell on itsleft. So, in Row 2, the numbers in the three cells are– {6, 8, 10, 12, 14},– {7, 9, 11, 13, 15}, and– {8, 10, 12, 14, 16}.

In Row 3, the cells contain– {16, 19, 22, 25, 28},– {17, 20, 23, 26, 29},– {18, 21, 24, 27, 30},– {19, 22, 25, 28, 31}, and– {20, 23, 26, 29, 32}.

Now, to visualize the distribution of primes, we do thefollowing, for each cell of the triangle that containseither 1 or at least one prime, we print # to the standardoutput at the corresponding position. Otherwise, we print (awhite space).

Your output must contain exactly h rows, each row exactly2h−1 characters (including the white spaces but excludingthe newline). Note that in the sample runs below, the whitespaces are not visible.

Example——-

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5a3535332d2e1a2a3f6b6b6e">[email protected]</a>:~/as02-skeleton$ ./pattern2 4## ### ### # # #

To understand the output, consider the two numbers containedin each cell, in the four rows:

Row 1: {1,2}Row 2: {3,5} {4,6} {5,7}Row 3: {7,10} {8,11} {9,12} {10,13} {11,14}Row 4: {13,17} {14,18} {15,19} {16,20} {17,21} {18,22} {19,23}

Now, we check whether the numbers contained in each cell hasat least one prime, and replace them with either ‘#’ or ‘ ‘.

Row 1: ‘#’Row 2: ‘#’, ‘ ‘, ‘#’Row 3: ‘#’, ‘#’, ‘ ‘, ‘#’, ‘#’Row 4: ‘#’, ‘ ‘, ‘#’, ‘ ‘, ‘#’, ‘ ‘, ‘#’

Drawing it nicely as an equilateral triangle yields the output

## ### ### # # #

Sample Runs———–

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b5dadadcc2c1f5c5d0848481">[email protected]</a>:~/as02-skeleton$ ./pattern11 11#### ### # # ##### ##### #   # ####### # ##### # # # # # # ### ## ## ## ## ### # # #   # # # ####### ### ##########<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="bbd4d4d2cccffbcbde8a8a8f">[email protected]</a>:~/as02-skeleton$ ./pattern100 29## ### ### # # ##### #####   # #   ####### ####### # # # # # # ### ## ## ## ## ### #   # # # #   # ########### ###########   # #   # #   # #   ############# ############# # #   # # # # # #   # # ### #  ##  # ## ## #  ##  # ### # # # # # # # # # # # # # # ################# #################   # #   # #   # #   # #   # #   ################### ################### #   # # # #   # # # #   # # # #   # ### ##  # ## #  ## ## ## ##  # ## #  ## ### # # # #   # # # # # # # # # #   # # # # ####################### #######################   # #   # #   # #   # #   # #   # #   # #   ##### #### #### #### #### #### #### #### #### ##### # # # # #   # # # # # # # # # # # #   # # # # # ### ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ## ### # #   # # # # # #   # # # # # #   # # # # # #   # # ############################# ############################

Hints—–

Solve this problem by breaking it down into smallerproblems.

In addition to drawing triangles and checking if a numberis prime, you might find the following sub-problems useful

– Find the first number of each leading cell of each row,given the row number and the interval n.

– Given the row, the col, and the interval n, does thecell contains a prime?