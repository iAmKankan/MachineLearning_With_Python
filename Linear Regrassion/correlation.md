### Colinearity

<img src="https://latex.codecogs.com/svg.image?Y&space;=\beta_0&plus;\beta_1&space;X_1&plus;\beta_2&space;X_2&plus;\epsilon" title="Y =\beta_0+\beta_1 X_1+\beta_2 X_2+\epsilon" />

* Two independent variables <img src="https://latex.codecogs.com/svg.image?X_1,X_2" title="X_1,X_2" />  are colinear when they are correlated with each other
* In a multiple regression study, we assume theat the X variables are independent to each other.
* We also assube that each X-variable has a unique piece of information about Y.
* We belive that 
  * <img src="https://latex.codecogs.com/svg.image?\beta_1=" title="\beta_1=" /> The change of Y for a 1-unit change in <img src="https://latex.codecogs.com/svg.image?X_1" title="X_1" /> , while <img src="https://latex.codecogs.com/svg.image?X_2" title="X_2" /> is held constant
  * <img src="https://latex.codecogs.com/svg.image?\beta_2=" title="\beta_2=" /> The change of Y for a 1-unit change in <img src="https://latex.codecogs.com/svg.image?X_2" title="X_2" /> , while <img src="https://latex.codecogs.com/svg.image?X_1" title="X_1" /> is held constant

* In the condition of Multicorrelation exists then above two believes are oppositive or negetive.

### Effects of Multicollinearity
t statistic for <img src="https://latex.codecogs.com/svg.image?\beta_1=\frac{b_1}{StdErrof&space;b_1}" title="\beta_1=\frac{b_1}{StdErrof b_1}" />

1. Variances (and standard errors) of regression coefficient estimators (i.e. the b.) are inflated. This means that Var(b) is too large.
2. The magnitude of the <img src="https://latex.codecogs.com/svg.image?b_1" title="b_1" />, may be different from what we expect.
3. The signs of the <img src="https://latex.codecogs.com/svg.image?b_1" title="b_1" />; may be the opposite of what we expect.
4. Adding or removing any of the X-variables produces large changes in the values of remaining <img src="https://latex.codecogs.com/svg.image?b_1" title="b_1" />, or their signs.
5. Sometimes removing a data point causes large changes in the value of the <img src="https://latex.codecogs.com/svg.image?b_1" title="b_1" />, or their signs.
6. In some cases, F is significant, but the t-values (for the <img src="https://latex.codecogs.com/svg.image?b_1" title="b_1" />) may not be significant.




* Independent variables(X) having relationshiop with dependent variable(Y).
* By increasing X1 the Y variables should be increase otherwhise it would be insignifigent variable.
* In multivariate regression independent variables - X1,X2,X3,..Xn should not have relationshiop with each other. Otherwise it will be called **Multi-colinearity**
* The result falls between **-1 to 1**.
* The numbers fall between **-0.4 to 0.4** cannot be consider as a co-related.
![corr](https://cio-wiki.org/images/2/22/Pearson_Correlation_Coefficent.png)
### Detection
* There are solutions where programmetically detection of colinearity-
   - Bivariate correlation
   - Variance Inflation Factor (VIF)




* Bibilography
* https://en.wikipedia.org/wiki/Correlation_and_dependence
