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

<img src="/svgs/bisection.png" alt="illustration of the bisection method"/>

