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
 ![Img1]()
where β0 = Level/ Inflation β1 = Slope/ Business Cycle β2 = Curvature/ Interest Rate Volatility λ = Time Constant t = Maturity

[Report](https://github.com/supreeth8/YieldCurve_interpolation/blob/master/Project_report.pdf)


#### Other creaters
- [Harnish Patel](https://www.linkedin.com/in/patel-harnish/)
- [Goutham Bacha](https://www.linkedin.com/in/gouthambacha/)
- [Laukik Tated ](https://www.linkedin.com/in/laukiktated/)
- [Pridhvi Raj](https://www.linkedin.com/in/pridhviraj-r-596a00173/)
