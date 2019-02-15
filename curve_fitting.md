## Curve fitting with polynomials

### Task1: Curve fitting introduction

Often data are available from experiments as set of points, and it would be useful to
describe these data with a known mathematical function. This is known as curve fitting.
Commonly used functions for fitting are polynomials. Fitting a set of <img alt="$N$" src="svgs/f9c4988898e7f532b9f826a75014ed3c.png" align="middle" width="14.99998994999999pt" height="22.465723500000017pt"/> points with a polynomial of order <img alt="$n&lt;N$" src="svgs/15605c10841a9ee639ca78a40d052b1d.png" align="middle" width="46.78449764999999pt" height="22.465723500000017pt"/>:

<p align="center"><img alt="$$&#10;p(x) = c_n x^n + c_{n-1} x^{n-1} + \dots + c_2 x^2 + c_1 x + c_0&#10;$$" src="svgs/5acec8a29d8d38ce60094393302bf1d2.png" align="middle" width="343.27229474999996pt" height="18.312383099999998pt"/></p>

consists of finding the optimal combination of coefficients <img alt="$c_n,c_{n-1},\dots,c_2,c_1,c_0$" src="svgs/72ffe5b7cef438ee72e52050f929c06d.png" align="middle" width="150.03996809999998pt" height="14.15524440000002pt"/> such that the curve <img alt="$p(x)$" src="svgs/c9ea84eb1460d2895e0cf5125bd7f7b5.png" align="middle" width="30.450987599999987pt" height="24.65753399999998pt"/> fits the data overall. The function _polyfit_ in Matlab generates these
coefficients, with the principle of the least square.

1. Use dlmread to read in the first 2 columns of the file [_experiment.txt_](./experiment.txt) and store
them in a matrix. Extract the first and second columns of the matrix into two
vectors _xexp_ and _yexp_, respectively. Plot _yexp_ vs _xexp_ as points.

2. Fit the points plotted in step 1 with three different polynomials, of order 1, 2 and 3 respectively. Call the coefficients of these fits _cn1_, _cn2_ and _cn3_.

3. Evaluate and plot the three polynomials <img alt="$p(x)$" src="svgs/c9ea84eb1460d2895e0cf5125bd7f7b5.png" align="middle" width="30.450987599999987pt" height="24.65753399999998pt"/> with coefficients found in step 2 at
points xf = [1:0.1:10]. Call them _p1_, _p2_, _p3_, and plot them vs _xf_ in the same
graph of step 1 (i.e. together with _yexp_ vs _xexp_). Use different data symbols and/or
line types for the 3 different data sets, use _legend_ to give each curve a name.
Turn the grid on.

### Task2: Measuring how good a fit is

The accuracy of the fit between a set of points and a polynomial is determined by first
calculating the error, also known as the __residual__, which is the difference between a
point and the value of the polynomial, at each point:

<p align="center"><img alt="$$&#10;r_i = yexp_i - p(xexp_i)&#10;$$" src="svgs/5c8f7a700d35502622ada16450324fb0.png" align="middle" width="155.58311175pt" height="16.438356pt"/></p>

Then the residuals are used to determine the total error. The total error E can be
evaluated in different ways: in the least square methods <img alt="$E$" src="svgs/84df98c65d88c6adf15d4645ffa25e47.png" align="middle" width="13.08219659999999pt" height="22.465723500000017pt"/> is the sum of the squares
of the residuals:

<p align="center"><img alt="$$&#10;E = \sum_i^N r_i^2&#10;$$" src="svgs/e321e89be284010798d87b4794889956.png" align="middle" width="75.90930764999999pt" height="47.806078649999996pt"/></p>

1. Calculate and display the total error <img alt="$E$" src="svgs/84df98c65d88c6adf15d4645ffa25e47.png" align="middle" width="13.08219659999999pt" height="22.465723500000017pt"/> for each polynomial fit done in the first curve fitting task.
For any number of <img alt="$N$" src="svgs/f9c4988898e7f532b9f826a75014ed3c.png" align="middle" width="14.99998994999999pt" height="22.465723500000017pt"/> points it is possible to fit them with a polynomial of order <img alt="$N-1$" src="svgs/e35caf405a5e9b4afd75a0d338c4dc12.png" align="middle" width="43.31036984999999pt" height="22.465723500000017pt"/>
that passes exactly for all the points. However, when many points are involved, the
use of high-order polynomials generates significant differences between some of the
points.

2. Approximate the points given in Task 1 with a polynomial of order 9. Plot this
fit at points xf = [1:0.1:10]. [Matlab may give you a warning: this is because it
knows already that it is not a good fitting, and in its kind generosity, warns you
about it].

3. Compute the total error <img alt="$E$" src="svgs/84df98c65d88c6adf15d4645ffa25e47.png" align="middle" width="13.08219659999999pt" height="22.465723500000017pt"/>. How does the error <img alt="$E$" src="svgs/84df98c65d88c6adf15d4645ffa25e47.png" align="middle" width="13.08219659999999pt" height="22.465723500000017pt"/> compare against the fitting
with lower order polynomials?

### Task 3: Write your own complete function for curve fitting

Since you may need to fit experimental data often during the rest of your studies, it is
convenient to write a function, once forever, that you may reuse at any time in the
future.

1. Write a function, _mypolyfit_, that receives a set of _x_ and _y_ data points and the
order desired for the fitting polynomial, and outputs the fitting polynomial at
points _x_ and the total error <img alt="$E$" src="svgs/84df98c65d88c6adf15d4645ffa25e47.png" align="middle" width="13.08219659999999pt" height="22.465723500000017pt"/>. You may test the function with the data of Tasks
1 and 2.

2. Read the file [_wave.txt_](./wave.txt), containing experimental data points. Fit these points
with polynomials of order 1 up to 8.
Within the same figure, but in two different tiled axes (to do so explore and
use the command subplot) plot:

	* The data points and the various fits together.
	* The total error vs the order of the fitting polynomials (as points).
	
### Task4: Analyse Real Data

A spring manufacturer measures the force-extension characteristics,<img alt="$F=kx$" src="svgs/2d259c3890b8ed4fc3f9dd934ddc2de2.png" align="middle" width="53.241902999999986pt" height="22.831056599999986pt"/>, of all
the manufactured tension springs. The data are automatically measured by a machine
and recorded in a data file. The file contains the spring serial number and the
measured extension (in mm) at 10 predefined loads of 10N to 100N in increments of
10 N, for a batch of 100 springs.
Write a Matlab script that fits a linear curve to the measurements for each spring and
deduces its spring constant <img alt="$k$" src="svgs/63bb9849783d01d91403bc9a5fea12a2.png" align="middle" width="9.075367949999992pt" height="22.831056599999986pt"/>.

1. Read in the measured data from [_springdata.csv_](./springdata.csv) and calculate the spring
stiffness for each spring. Save the spring serial number followed by the
computed spring stiffness in a separate file called _stiffness.csv_.

(Back to [README.md](./README.md))