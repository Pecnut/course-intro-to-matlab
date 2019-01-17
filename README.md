# course-intro-to-matlab
Introduction to Matlab course for the CM Hub at Imperial College

* Part 1: Call-and-response Matlab 
* Part 2: Writing Matlab programs

## Part 1. Call-and-response Matlab

### Where Matlab sits among other programming languages / mathematical software
* (Maths/popular graph)
* What Matlab is good for
* What Matlab is bad for

### Awareness of the Matlab desktop environment
* The command window allows for call-and-response interface

### Command-line arithmetic 

Join in:

* `3+4`
* `3*4`
* `3/4`
* `3^4`

Try:

* Does Matlab respect BIDMAS?: `3+4*5`

### Use of variables

Join in:

* `x=2`
* `x`
* `x=-9`
* `x`
* `length = 3` (long names are good)
* `area = length^2`
* `y=12/2+5`
* `(y+1)^2`
* `y=sin(x)*cos(x)`

### Getting help

* Find square root of x: Google the function
* Or use F1 on the function

Try:

* Find sin<sup>–1</sup>(1)
* Find the remainder when 14 is divided by 3
* Find |–4|

### The semicolon

Try:

* What's the difference between `x=40` and `x=40;` ?

### Creating vectors and matrices

Join in:

* `x = [29 43 13 3.2 -26]`
* `y = [1 2; 3 4]`
* `[1:10]` (note endpoints)
* `[1:2:10]`
* `[3:-0.1:2]` 

Try:

* What do apostrophes do? `x'` `y'`
* What do commas do?: `[29, 43, 13, 3.2, -26]`
* How long is `[1:0.5:10]`?

### Matrix manipulation

Join in:

* `x = [3 1 4 1 5 9]`
* `x(2)`
* `x(4) = 50`
* `x`
* `y = [3 10; -1 6]`
* `y(1,2) = 100`
* `y`
* `A = [1:10]'*[1:10]` (explanation later)
* `A(4, [1 2])`
* `A([8 9],[8 9])`
* `A(3,4:end)`
* `A(1:end,4)`
* `A(:,4)`
* `sum(A(:,4))`

Try:

* Create the matrix `A = magic(5)` (explanation later)
* Get the element in the 1st row, 1st column
* Get the element in the 5th row, 2nd column
* Get all elements in the last row
* Get the element in the 6 row, 4th column (...)
* What does `A([2 1 1 1],4)` do? Try it.

Now try:

* Show that the `sum` of the first column of `A` = the `sum` of the last column of `A`
* Find the `sum` of the diagonal of `A` (hint: search for the function that gives the diagonal of `A`... or guess!)
* Harder! Find the `sum` of the negative diagonal of `A`. Hint: try showing the rows of `A` in reverse before using `diag`
* Harder! Produce the elements of `A` for which both coordinates are odd
* Replace the bottom row of `A` with zeros

### Vector arithmetic

Join in:

* `x = [1:10]`
* `y = [11:20]`
* `x+y`
* `x-y`
* `2*x`
* `x/2`
* `x*y`... what do you expect to happen? Why is this problematic but `x+x` isn't? (Hint: think about matrices)
* `x.*y`
* `x.^2`
* `2.^x`

Try:

* `sum` the numbers from 1 to 100 (are you faster than Gauss?)
* `sum` the squares from 1 to 5
* What is the mean of the powers of 2 from the zeroth power to the sixth power? (Google the function to find the mean... or guess!)

### Matrix arithmetic

Join in:

* `A = [1 0 5; 2 1 6; 3 4 0]`
* `A.^2`
* `A^2`

Try:

* Create a 2x3 matrix, call it `B`
* Create a 3x4 matrix, call it `C`
* Try calculating `B*C` and `C*B`
* Multiply `B` by the transpose of `B`
* Make one of the elements of `B` imaginary (`i`)
* Calculate `B'`. What does the apostrophe *actually* do?

### Size

Size gives rows × columns

* `size(A)`
* `size(B)`
* `x = [1:10]`
* `size(x)` ... note it's 1×10 (a row vector), not 10×1 (a column vectors).

Vectors by default are row vectors in Matlab.

### More matrix arithmetic

Join in:

* `A`
* Let's multiply `A` by (3 1 4)<sup>T</sup>
* `x = [3 1 4]'` (note apostrophe) or `x = [3; 1; 4]` (note semicolons)
* `A*x`

Try:

* Let `x = [3 1 4]` (without the apostrophe). Will calculating `A*x` work? Try it.
* Create the 3×3 identity matrix `I = eye(3)`. Multiply *I* by *x*.

### Inversion of matrices (and when this is a bad idea)

Join in:

* `A`
* `inv(A)`
* Let's solve *Ax* = (–1 0 1)<sup>T</sup>
* `b = [-1; 0; 1]`
* If *Ax* = *b* then *x* = *A*<sup>–1</sup>*b*, so `inv(A)*b`
* `A\b`

Try: 

* Solve the system of equations *x*+*y*=2, 3*y*–*x*=3.
* Let `A = [1 2 3; 4 5 6; 5 7 9]` and `b = [-1; 0; 1]`. Solve *Ax=b*. What is the determinant of *A*? (Google!)

### Eigenvalues and eigenvectors

* `A = [-2 -4 2; -2 1 2; 4 2 5]`
* `eig(A)`

Try:

* How to get eigenvectors? (Google or F1)

### Plotting in 2D

Join in:

* `x = [0:10]`
* `y = exp(x)`
* `plot(x,y)`
* How do we make this graph smoother?

Try:

* `plot` sin(x) for x between 0 and 2π
* `plot` a circle (hint: think parametric)

Join in:

* `x = [0:0.1:10]`
* `y = exp(x)`
* `plot(x,y,'r-')`
* `plot(x,y,'go')`

Try:

* Plot a magenta, dotted line with large line width and squares as markers. (Look at the F1 help file for `plot`)

Join in:

* `xlabel('x')`
* `ylabel('exp(x)')`
* `title('Exponential growth is fast')`
* `xlim([0 5])`
* Now let's try multiple plots
* `x = [0:0.1:10]`
* `y1 = exp(x)`
* `y2 = exp(2*x)`
* `plot(x,y1,'r-')`
* `hold on`
* `plot(x,y2,'k--')`
* `legend('exp(x)','exp(2x)')`

Try:

* The same but use `loglog`, `semilogx` or `semilogy` instead of `plot` (the syntax is the same). What do they do?

### Challenge for the end of the day

* Create a 10×10 matrix of random numbers (hint: use `rand`) and call it `A`
* Find the eigenvalues of *A*
* Show that the sum of the eigenvalues of *A* = the trace of *A*
* Plot the eigenvalues on an Argand diagram, using a circular marker at each eigenvalue
* Now add a row and column of zeros to *A*, to form *B*, which is therefore an 11×11 matrix. (Think about how you might want to do this!)
* Now plot the eigenvalues of *B* on the same graph as the eigenvalues of *A*, in another colour.
* What can you say about the eigenvalues of *B* compared to the eigenvalues of *A*?

### Built-in functions to try

Try:

* `sin(x)`, `cos(x)`, `tan(x)`
* `floor(x)`, `ceil(x)`
* `max(x)`, `min(x)`
* `triu(A)`, `rand(n)`

## Part 2. Writing Matlab programs

Now we move from simple call-and-response to writing whole programs

### Challenge to see if you remember yesterday

* Solve the simulaneous equations for *a*, *b* and *c*:
  - *a* + *c* = 4
  - –*a* – 2*b* + *c* = –2
  - 2*a* + 3*b* = 8
* Plot the graphs of sin(*ax*), sin(*bx*) and sin(*cx*) for *x* from –π to π, with these plots in different colours. Include a legend, a title and a label for the *x*-axis.

### Writing and calling simple scripts and functions

Join in:

* Create a new file `myfunction.m` and inside it write:
``` 
function [y] = myfunction(x)
  y = 3*x+1;
end;
```
* Save and run `myfunction(5)` from the command line

Try:

* Create a function `my_first_my_last_my_everything.m` which takes a vector `v` and returns the sum of the first element in the vector and the last element in the vector

Join in:

* Change `my_first_my_last_my_everything.m` so it outputs the first and last elements separately
* `[first, last] = my_first_my_last_my_everything(v)`

### If

Join in:

* Change `myfunction.m` so that the core functionality reads:
```
if x > 0
  y = 1;
elif x == 0
  y = 0;
else
  y = -1;
endif
```
* Note: `==` is not `=`

Try:

* Plot `myfunction` from *x* = –5 to 5.

Now try:

* Change `myfunction.m` so that if *x* is even, it returns *x*/2, otherwise it returns 3*x*+1.

### For and while loops

Join in:

* Create a new function `squares_up_to.m`. Inside let's write
``` 
function squares_up_to(n)
  for i=1:n
    disp(i^2); % this squares i and then displays it on the screen
  end
end
```
* This function has no output! It just does something and prints to the screen

* Create a new function `count_up_to.m`. Inside let's write
```
function count_up_to(n,start)
  i = start;
  disp(i);
  while i < n
    i = i + 1;
    disp(i);
  end
end
```

Try:

* The Collatz conjecture: adapt `myfunction.m` to take a number `n`, and while `n` does not equal 1, run the algorithm already described in `myfunction.m`.

### Saving and reading data (incl. comments)

* Save output of Collatz function to CSV file
* Read in a CSV file
* `min`, `max` and the locations

### Plotting in 3D

Join in:

* `t = [0:0.1:10];`
* `x = sin(t);`
* `y = cos(t);`
* `z = t;`
* `plot3(x,y,z)`
* `grid on`

Visualise *f*(*x,y*) = sin(*x*)cos(2*y*) for 0 ≤ *x,y* ≤ 2π:

* Create grid 
  - `x = linspace(0,2*pi,300)`
  - `y = linspace(0,2*pi,300)`
  - `[xg,yg] = meshgrid(x,y);`
* `f = sin(xg).*cos(2*yg);`
* `contour(xg,yg,f,20);`
* `surf(x,y,f)`
* `shading interp`

### Debugging

### End of day challenge

* Create a new function `fib.m`. Let this function take a number `n` and output the `n`th Fibonacci number. Recall the algorithm:
  - F(1) = 1
  - F(2) = 1
  - F(i) = F(i-2) + F(i-1)
* Create a vector of the first 20 Fibonacci numbers
* Save them to a file
* Plot them

# Extra stuff

### Strings

Single-quote strings are vectors, with each character an element in the vector

Join in:

* `greeting = 'hello there'` (note: single quotes)
* `greeting(3)`
* `[greeting(1:4) greeting(7)]`

Double-quote strings (R2016b upwards only) are individual things. You can create vectors of multiple strings

* `greeting = "hello there"`
* `greeting(3)`
* `greeting(1)`
* `conversation = ["hello there", "general kenobi"]`
* `conversation(2)`

Try:

* Let `surname` equal your surname
* Find the last letter of your surname
* Output the first and last letter of your surname, put together
* If `conversation = ['hello there', 'general kenobi']` (with single quotes), what is `conversation(2)`?
