# Term Structure Modelling
Yield curve Interpolation using Cubic Spline and Nelson Seigel model.


## Introduction
The aim of this project is to calibrate the daily yield curves based on the benchmak
bonds of the Australian market for the month of December 2018. The yield curve will
be generated using the non parametric Cubic Spline Method and the parametric Nelson
Siegel Method for each day throughout the month based on the daily reference data of
the "Constant Maturity Treasury Rates" or CMTs sourced from Bloomberg(BBG).

## Cubic Spline
As mentioned earlier, the Cubic Spline is an non parametric model which relies on the third order polynomial equations for the interpolation of the existing market reference data with a smooth curve which is usually prone to over-fitting of the data. The model constructed is based on the assumption that the CMTs are on zero coupon bonds with the mentioned expiration and hence have no intermediate payments.

## Nelson Siegel
The Nelson Siegel is a parametric model with parameters β0,β1,β2 which are optimized to reduced the mean square error between the actual and estimated prices. Though the curve generated from this method doesn’t always pass through the existing points, it is considered a better approximation taking in to regard the additional information it conveys through the parameter values. This model defines the yield curve by the function-
 ![Img1](https://github.com/supreeth8/Term_structure_modeling/blob/master/Misc/NS_equation.png)
> where, `β0 = Level/ Inflation`,
`β1 = Slope/ Business Cycle`, 
`β2 = Curvature/ Interest Rate Volatility`, 
`λ = Time Constant`,`t = Maturity`

## Execution
1. Step 1 - Data Collection: We have downloaded the Australian Bonds data for month of December 2018 from Bloomberg terminal. Our program reads the excel files downloaded using pandas library. For bonds having tenor as 12, 20 and 30 years, we have same maturity date for different yields as tenor 10, 15 and 15 years respectively. So, we removed these data points to reduce complexity in yield curve fitting.
2. Step2-ImportDatatoPython:Afunctiontoretrieveallthenecessaryinputdata(yields, time to maturity in months, bond prices, coupons, schedule of all cash flows) from the .xlsx files to our python code was written.
3. Step3-CubicSplineGeneration:UsingtheCubicSplinelibraryfunctionscipy.interpolate from module to get (n-1) piece-wise cubic equations between (n) points and plot the yield curve obtained. In addition to this, an extension of the program which runs on the entire data for the month of December 2018 has also been inculcated.
4. Step 4 - Nelson Siegel Optimization: Initialize parameters with a starting value of β0 = 1,β1 = 1,β2 = 1 and the Time constant λ= 0.0605 for all calculations and the optimum value of βs are estimated. All calculations for factor-loadings are done with time to maturity taken in units of months. The Optimization is done in order to reduce the error difference between the Actual and Predicted values of the Bond prices which are calculated taking in to account every cash flow payment (unlike Cubic Spline) discounted with its corresponding yield value derived from the NS equation. In addition, similar extensions of the program to run on the entire data and also calculate the progression of the βs throughout the 31 Day period have also been inculcated.

## Result
### Cubic Spline
 
 ![Cubic Spline](https://github.com/supreeth8/Term_structure_modeling/blob/master/Misc/Cubic%20Spline.png)
 
 Values predicted
 
 
 ![Values](https://github.com/supreeth8/Term_structure_modeling/blob/master/Misc/Predicted_cubic_spline_values.png)
 
 
### Nelson Seigel
 ![NS](https://github.com/supreeth8/Term_structure_modeling/blob/master/Misc/Nelson%20Seigel.png)
 
 Values predicted
 
 
 ![values_predicted](https://github.com/supreeth8/Term_structure_modeling/blob/master/Misc/Predicted_NS.png)

[Report](https://github.com/supreeth8/YieldCurve_interpolation/blob/master/Project_report.pdf)


#### Other creaters
- [Harnish Patel](https://www.linkedin.com/in/patel-harnish/)
- [Goutham Bacha](https://www.linkedin.com/in/gouthambacha/)
- [Laukik Tated ](https://www.linkedin.com/in/laukiktated/)
- [Pridhvi Raj](https://www.linkedin.com/in/pridhviraj-r-596a00173/)
