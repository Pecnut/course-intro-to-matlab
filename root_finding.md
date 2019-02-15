## Numerical Root Finding 

### Task 1: The Bi-section scheme

A numerical solution (or __root__) of an equation <img alt="$f(x)=0$" src="svgs/a6fc63aa1efb41cce557cf8cb517441f.png" align="middle" width="62.134673699999986pt" height="24.65753399999998pt"/> is a value of <img alt="$x$" src="svgs/332cc365a4987aacce0ead01b8bdcc0b.png" align="middle" width="9.39498779999999pt" height="14.15524440000002pt"/> that satisfies
the equation approximately, but not exactly. A simple and robust algorithm to
compute the roots of an equation is the bi-section method.

If, within a given interval <img alt="$[a,b]$" src="svgs/fe477a2781d275b4481790690fccd15f.png" align="middle" width="32.18228144999999pt" height="24.65753399999998pt"/>, <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/> is continuous and the equation has a solution, then
<img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/> will have opposite signs at the end points of <img alt="$[a,b]$" src="svgs/fe477a2781d275b4481790690fccd15f.png" align="middle" width="32.18228144999999pt" height="24.65753399999998pt"/>, i.e. <img alt="$f(a) \times f(b) &lt;0 $" src="svgs/9064914700946db752279d9b99bd78ba.png" align="middle" width="111.17767484999999pt" height="24.65753399999998pt"/>.
To start with, the midpoint between <img alt="$[a,b]$" src="svgs/fe477a2781d275b4481790690fccd15f.png" align="middle" width="32.18228144999999pt" height="24.65753399999998pt"/> i.e. <img alt="$x = \frac{a+b}{2}$" src="svgs/77cd89186e0c25cfa958665d4ca6e642.png" align="middle" width="56.28780959999999pt" height="28.92634470000001pt"/>, is taken as the first
estimate of the numerical solution. The true root is bracketed within either one of the
shorter intervals <img alt="$[a,x]$" src="svgs/78803621c5e4e61a79d2880c449812f3.png" align="middle" width="34.52247314999999pt" height="24.65753399999998pt"/> or <img alt="$[x,b]$" src="svgs/d839a293adc00245c3e2b75e7d4f1a33.png" align="middle" width="32.88811514999999pt" height="24.65753399999998pt"/>. The process is repeated, considering this shorter
interval as a new starting interval. The procedure is completed until the bracketing
interval is less than a specified tolerance <img alt="$\varepsilon$" src="svgs/9ae7733dac2b7b4470696ed36239b676.png" align="middle" width="7.66550399999999pt" height="14.15524440000002pt"/>. 

<img src="/svgs/bisection.png" alt="illustration of the bisection method" width="250" />

Find the roots of the equation:
<p align="center"><img alt="$$&#10;f(x) = x^2 + (x-2)^3 -5 = 0&#10;$$" src="svgs/835d2a9f275cfad6e03f30643e0f7abb.png" align="middle" width="207.0886257pt" height="18.312383099999998pt"/></p>

1. Write a function _myfunc_ that receives values of <img alt="$x$" src="svgs/332cc365a4987aacce0ead01b8bdcc0b.png" align="middle" width="9.39498779999999pt" height="14.15524440000002pt"/> and outputs the
corresponding values of <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/>.

2. Write another function, _mybisection_, to find the roots of _myfunc_ within a given
interval <img alt="$[a,b]$" src="svgs/fe477a2781d275b4481790690fccd15f.png" align="middle" width="32.18228144999999pt" height="24.65753399999998pt"/> and a specified tolerance <img alt="$\varepsilon$" src="svgs/9ae7733dac2b7b4470696ed36239b676.png" align="middle" width="7.66550399999999pt" height="14.15524440000002pt"/>.

3. Find the numerical root of the equation. To decide about the starting interval,
you may plot <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/> vs <img alt="$x$" src="svgs/332cc365a4987aacce0ead01b8bdcc0b.png" align="middle" width="9.39498779999999pt" height="14.15524440000002pt"/> first and inspect visually where the solution lies. Find
and compare the root with tolerances <img alt="$\varepsilon=0.1$" src="svgs/946d41bc6d842a13d5592e2a97cc48fd.png" align="middle" width="50.58777734999998pt" height="21.18721440000001pt"/>, <img alt="$\varepsilon=0.01$" src="svgs/b1a0aae36cb870f0a253a00be6779cea.png" align="middle" width="58.80698669999999pt" height="21.18721440000001pt"/> and <img alt="$\varepsilon=0.001$" src="svgs/9b116e7a8f3c57513b421bee243fc44f.png" align="middle" width="67.02619605pt" height="21.18721440000001pt"/>.

### Task 2: Exploring the bi-section method and its limitations

Find the roots of the equation:
<p align="center"><img alt="$$&#10;f(x) = \sin(x^2) -x + 5&#10;$$" src="svgs/6de5525d67b88f311455ff282ce00d05.png" align="middle" width="161.44961249999997pt" height="18.312383099999998pt"/></p>

1. Alter _myfunc_ with this <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/>. Invoke _mybisection_ with interval <img alt="$[3.8,6]$" src="svgs/88f6ef37e874472bf419b4f5aea16dc6.png" align="middle" width="45.66218414999998pt" height="24.65753399999998pt"/> and a
tolerance <img alt="$\varepsilon = 0.001$" src="svgs/5c373f96e30e64ee0f462b47e74f9d5e.png" align="middle" width="67.02619605pt" height="21.18721440000001pt"/>.
2. Repeat the exercise by slightly changing the initial interval as <img alt="$[3.8,5.5]$" src="svgs/74e246438a091f8e4f0ab26a16f1e70b.png" align="middle" width="58.44761669999998pt" height="24.65753399999998pt"/> and
same tolerance <img alt="$\varepsilon = 0.001$" src="svgs/5c373f96e30e64ee0f462b47e74f9d5e.png" align="middle" width="67.02619605pt" height="21.18721440000001pt"/>.
3. Why are the two roots different? [Plot the function in a range that comprises
both the intervals, i.e. 0 to 10, to explore what is happening].
4. Find the roots of the equation <img alt="$f(x) = (x-2)^2$" src="svgs/c629c1045710d6e63387bde1815f51fd.png" align="middle" width="110.95883369999999pt" height="26.76175259999998pt"/>. What is the problem when finding the roots? [Plot the function to help your
judgement].

5. Find the roots of the equation <img alt="$f(x) = \tan x$" src="svgs/d95d9a659b47cde2f37126ab560f9780.png" align="middle" width="89.79447674999999pt" height="24.65753399999998pt"/> within the range <img alt="$[1,2]$" src="svgs/4bacaa9b3789e39bb761a7b8f0b1cc7a.png" align="middle" width="32.87674994999999pt" height="24.65753399999998pt"/>. What is the problem when finding the roots? [Plot the
function, as points, to help your judgement].

### Task3: Matlab root finding functions

Beside using your own function _mybisection_, you could also use some of the Matlab
built in functions to find roots. There are two major root finding functions: a) _roots_, to
determine the zeros of a specified polynomial, and b) _fzero_, to determine the roots of
any user defined function. Explore the use of these two functions within the _Help_.

1. Find find the roots of the polynomial <img alt="$p(x)=-x^3 + 5x^2 +2x-7$" src="svgs/802f5770942b99cb51644267246d4b36.png" align="middle" width="193.01913674999997pt" height="26.76175259999998pt"/>. Verify that the roots you have found are correct by plotting the polynomial.

2. Find the roots of the function <img alt="$f(x) = \sin(x^2) - x + 5$" src="svgs/bb657787e09384948718abbaef6c56bc.png" align="middle" width="161.44961249999997pt" height="26.76175259999998pt"/>. Use _fzero_ with initial
point <img alt="$x = 5$" src="svgs/1486f15d8fb65398773c720894089ae0.png" align="middle" width="39.53182859999999pt" height="21.18721440000001pt"/>. Define <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/> in _myfunction_ from Task 1.
Verify that the root you have found is correct by plotting <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/>. The function <img alt="$f(x)$" src="svgs/7997339883ac20f551e7f35efff0a2b9.png" align="middle" width="31.99783454999999pt" height="24.65753399999998pt"/> has multiple roots; try to determine a few more, still using _fzero_.

