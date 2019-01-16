# course-intro-to-matlab
Introduction to Matlab course for the CM Hub at Imperial College

## Where Matlab sits among other programming languages / mathematical software
* (Maths/popular graph)
* What Matlab is good for
* What Matlab is bad for

## Awareness of the Matlab desktop environment
* The command window allows for call-and-response interface

## Command-line arithmetic 

Join in:

* `3+4`
* `3*4`
* `3/4`
* `3^4`

Try:

* Does Matlab respect BIDMAS?: `3+4*5`

## Use of variables

Join in:

* `x=2`
* `x`
* `x=-9`
* `x`
* `y=12/2+5`
* `(y+1)^2`
* `sqrt(x)` (complex numbers!)
* `length = 3` (long names are good)
* `area = length^2`

## Creating vectors and matrices

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

## Matrix manipulation

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
* `A(3, [4:end])`
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
* Find the `sum` of the diagonal (`diag`) of `A`
* Harder! Find the `sum` of the negative diagonal of `A`. Hint: try showing the rows of `A` in reverse before using `diag`
* Harder! Produce the elements of `A` for which both coordinates are odd
* Replace the bottom row of `A` with zeros

## Vector arithmetic

Join in:

* `x = [1:10]`
* `y = [11:20]`
* `x+y`
* `x-y`
* `2*x`
* `x/2`
* `x+x+x`
* `x*y`... what do you expect to happen?
* `x.*y`
* `x.^2`
* `2.^x`

Try:

* `sum` the numbers from 1 to 100 (are you faster than Gauss?)
* `sum` the squares from 1 to 5
* What is the `mean` of the powers of 2 from the zeroth power to the sixth power?

## Matrix arithmetic

Join in:

* `A = [1 0 5; 2 1 6; 3 4 0]`
* `A.^2`
* `A^2`

Try:

* Create a 2x3 matrix, call it `B`
* Create a 3x4 matrix, call it `C`
* Try calculating `B*C` and `C*B`

## Inversion of matrices (and when this is a bad idea)

Join in:

* `inv(A)`

Try: 

* Solving the linear equation
* Finding the eigenvalues

## Saving and reading data

## Plotting in 2D and 3D

## Writing and calling simple scripts and functions

## Debugging
