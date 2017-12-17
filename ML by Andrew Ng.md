ML by Andrew Ng
===
## week 1 note 
* supervised learning : we are told the "right answer"
    * regression : predict results within a continuous output
    * classification : predict results in a discrete valued output(0 or 1)
    * (support vector machine : the algorithn for computer to deal with infinite data)
* unsupervised learning : find structure of the data


#### Linear Regression 
There is a **dataset** -> training set
* m = number of training example
* x = input / features
* y = output / "target" variable
* (x,y) = one training example


Linear Regression -- one input model
h(x) = c0 + c1x

**Cost function**
* idea: come up with value c0 and c1 so that h(x) is close to **y** for our taining example (x,y)
* J(c0,c1) : minimize c0 and c1, called squared error function
![](https://i.stack.imgur.com/O752N.png)

* c1就是J的斜率，算J就是算兩條線中間距離平方的總和
* J是碗狀分佈，像U型


#### Gradient descent 
To minimize cost function
" := " means assignment 

![](http://lynnapan.github.io/images/ml_week1/11.png)
+ alpha : learning rate(how big the step is)
+ update simultaneously

* if learning rate is too small -> gradient descent too slow
* if learning rate is too arge -> overshoot, fail to converge, even diverge

*  for model in linear regression, it will always be a bowl-shape-> convex function, so no local optimal other than the global optimal
*  other function might converge to a local optimal

applying cost function into gradient descent
![](https://www.mathworks.com/matlabcentral/answers/uploaded_files/28889/2.21.png)

## week 2 note 

multiple variables for linear regression 
+ n = numbers of feartures
+ h(x) = c0+1x1+c2x2+....
==> multivariate linear regression

![](https://i.stack.imgur.com/9pcN2.png)

### feature scaling 
to make the gradient descent run faster
divide x by its range
try to make it to -1 < x < 1
### mean normalization 
x' = x - avg. / range
roughly be at -0.5 < x < 0.5
### how to make sure gradient descent is working?
1. look at the graph if it has converged
2. automatic convergence test - delcare convergence if e < 0.001
3. IF NOT: the curve goes up or fluctuate (meaning cost function getting larger) if it does happened, shuold be using SMALLER LEARNING RATE

### Polynomial Regression
h(x) = 二次方程式、三次方程式、開根號等等

### normal equation
solve theta -> only need one step to do gradient descent
kinda like 2nd derivitive of a equation to find the lowest point
if use this, feature scaling won't be necessary
![](http://upload-images.jianshu.io/upload_images/744392-9ad2082d76c1472a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
+ if xT*x is non-invertible matrix
    1. redundant feature. ex. same data in different units
    2. too many features with too few data set

