# A New Interpolation Approach and Corresponding Instance-Based Learning

Shiyou Lian[0000-0002-7569-1438]

Xi'an Shiyou University,Xi'an,China sylian@xsyu.edu.cn

Abstract.Starting from finding approximate value of a function,introduces the measure of approximation-degree between two numerical values,proposes the concepts of “strict approximation”and “strict approximation region”,then,derives the corresponding onedimensional interpolation methods and formulas,and then presents a calculation model called “sum-times-difference formula” for high-dimensional interpolation,thus develops a new interpolation approach -ADB interpolation.ADB interpolation is applied to the interpolation of actual functions with satisfactory results.Viewed from principle and effect, the interpolation approach is of novel idea, and has the advantages of simple calculation, stable accuracy, facilitating parallel processing, very suiting for high-dimensional interpolation,and easy to be extended to the interpolation of vector valued functions.Applying the approach to instance-based learning,a new instance-based learning method-learning using ADB interpolation - is obtained. The learning method is of unique technique, which has also the advantages of definite mathematical basis,implicit distance weights, avoiding misclassification,high efficiency,and wide range of applications, as well as being interpretable,etc.In principle,this method is a kind of learning by analogy,which and the deep learning that belongs to inductive learning can complement each other,and for some problems,the two can even have an effect of “different approaches but equal results” in big data and cloud computing environment. Thus,the learning using ADB interpolation can also be regarded as a kind of “wide learning” that is dual to deep learning.

Keywords:Approximation-Degree·Interpolation·Strict Approximation· Sum-TimesDifference Formula· Instance-Based Learning· Wide Learning

# 1 Introduction

Instance-based learning[1,2] is also called nonparametric approach[3,4]. Instead of establishing a global model of sample data, the approach uses sample data to interpolate directly to achieve objective function approximation. Examples are the experience,and the specific manifestation of a general rule. From the cognitive perspective,the way of learning based on instances is closer to human learning. So,it makes sense to give machines this learning ability. Instancebased learning has been studied for a long time and many achievements have been made (such as $k$ -nearest neighbor algorithm,distance weighted nearest neighbor algorithm,locally weighted regression algorithm etc.), but there are stillsome problems and shortcomings on which (such as high-dimensional interpolation and misclasification). Therefore, instance-based learning as well as corresponding interpolation technique still needs us to continue to research and develop. On the other hand, the current environments of big data and cloud computing undoubtedly provide strong support for instance-based learning, and for which also open up a new place to display its prowess. Inspired by the approximate evaluation method of fexible linguistic functions[5, 6] in reference [7],in this paper,we intend to introduce a measure of degree of approximation between numerical values to study the approximate evaluation of numerical functions,and then explores new interpolation approaches based on the degree of approximation and corresponding instance-based learning methods.

# 2Approximation-Degree, Strict Approximation and Strict Approximation Region

Definition 2.1. Let $\mathbf { R }$ be real number field, $x _ { 0 } \in [ a , b ] \subset \mathbf { R }$ ，and $[ \alpha _ { 0 } , \beta _ { 0 } ] \subset [ a , b ]$ be a neighborhood of $x _ { 0 }$ ， which is called the approximation region of $x _ { 0 }$ .For $\forall x \in [ a , b ]$ ，say $x$ is approximate to $x _ { 0 }$ if and only if $x \in [ \alpha _ { 0 } , \beta _ { 0 } ]$ ：

Definition 2.2. Let $\mathbf { R } ^ { n }$ be $n$ -dimensional real vector space, $U \ = \ [ a _ { 1 } , b _ { 1 } ] \times [ a _ { 2 } , b _ { 2 } ] \times \ldots \times$ $[ a _ { n } , b _ { n } ] \subset \mathbf { R } ^ { n }$ ，and $\pmb { x } _ { 0 } = ( x _ { 1 _ { 0 } } , x _ { 2 _ { 0 } } , . . . , x _ { n _ { 0 } } ) \subset U$ .For $\forall x { } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) \subset U$ ，say $_ { x }$ is strictly approximate to $\scriptstyle { \mathbf { x } _ { 0 } }$ if and only if components $x _ { 1 } , x _ { 2 } , . . . , x _ { n }$ of $_ { \pmb { x } }$ are approximate to components $x _ { 1 _ { 0 } } , x _ { 2 _ { 0 } } , . . . , x _ { n _ { 0 } } \ o f \ x _ { 0 }$ , respectively， i.e., $x _ { i } \in [ \alpha _ { i } , \beta _ { i } ] \subset [ a _ { i } , b _ { i } ] ( [ \alpha _ { i } , \beta _ { i } ]$ is approximation region of （204 $x _ { i _ { 0 } } ) , i = 1 , 2 , . . . , n ; a n d$ “square” region $[ \alpha _ { 1 } , \beta _ { 1 } ] \times [ \alpha _ { 2 } , \beta _ { 2 } ] \times . . . \times [ \alpha _ { n } , \beta _ { n } ] \subset U$ is called the strict approximation region of $\scriptstyle { \mathbf { x } } _ { 0 }$ ：

In contrast to the strict approximation region in Definition 2.2, we refer to the “circle” region centered on point $\scriptstyle { \mathbf { x } _ { 0 } }$ as the ordinary approximation region of $\pmb { x } _ { 0 } \subset \pmb { U }$ .The relation between the strict approximation region and the ordinary approximation region of the same (2D) point $\scriptstyle { \mathbf { x } } _ { 0 }$ is shown in Fig.2.1. The illustration also shows the relationship between the strict approximation and the ordinary approximation. In fact, the reference [8] has stated: the geometric meaning of "close to point $( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) ^ { \mathfrak { N } }$ is different from that of “close to $x _ { 1 }$ and close to $x _ { 2 }$ .., and close to $x _ { n }$ ；

![](images/09d517cb9563a30083b26ecb1f63b0cdf084d56b82025e2db5ffbf576400a1b5.jpg)  
Fig.2.1.An illustration of the relation between strict approximation region and ordinary approximation region

Where the square region is the strict approximation region of point ${ \bf { \sigma } } _ { \bf { { x } 0 } }$ , and the circular region is its ordinary approximation region.

Definition 2.3. Let $\mathbf { R }$ be real number field, $x _ { 0 } \in [ a , b ] \subset \mathbf { R }$ ，and $[ \alpha _ { 0 } , \beta _ { 0 } ] \subset [ a , b ]$ be the approximation region of $x _ { 0 }$ . Set

$$
A _ { x _ { 0 } } ( x ) = \left\{ \begin{array} { l l } { 1 - \frac { x _ { 0 } - x } { x _ { 0 } - \alpha _ { 0 } } = \frac { x - \alpha _ { 0 } } { x _ { 0 } - \alpha _ { 0 } } , x \in [ \alpha _ { 0 } , x _ { 0 } ] } \\ { 1 - \frac { x - x _ { 0 } } { \beta _ { 0 } - x _ { 0 } } = \frac { x - \beta _ { 0 } } { x _ { 0 } - \beta _ { 0 } } , x \in [ x _ { 0 } , \beta _ { 0 } ] } \end{array} \right.
$$

to be called the degree of approximation, shortening as approximation-degree, of x to $x _ { 0 }$ . We call the function relation defined by the Equation (2.1) to be the approximation-degree function of $x _ { 0 }$ ：

# 3 Approximate Evaluation of Functions Based on ApproximationDegree

# 3.1Finding Approximate Value of a Univariate Function Based on Approximation-Degree

Let $\mathbf { R }$ be real number field, $U = [ a , b ] \subset \mathbf { R }$ ， $V = [ c , d ] [ \mathbf { { c } } \mathbf { { R } }$ ， $y = f ( x )$ is a continuous function relation from $U$ to $V$ . In the condition that a pair $( x _ { 0 } , y _ { 0 } )$ of corresponding values of function （204号 $y = f ( x )$ and $x ^ { \prime }$ approximate to $x _ { 0 }$ are known, find the approximate value of $f ( x ^ { \prime } )$

Let the approximation region of $x _ { 0 }$ be $[ a _ { 1 } , b _ { 1 } ] \subset [ a , b ]$ . According to the definition of the approximation-degree function above, the approximation-degree function of $x _ { 0 }$ is

$$
A _ { x _ { 0 } } ( x ) = \left\{ \begin{array} { l l } { \frac { x - a _ { 1 } } { x _ { 0 } - a _ { 1 } } , \quad x \in [ a _ { 1 } , x _ { 0 } ] } \\ { \frac { x - b _ { 1 } } { x _ { 0 } - b _ { 1 } } , \quad x \in [ x _ { 0 } , b _ { 1 } ] } \end{array} \right.
$$

And let the approximation region of $y _ { 0 }$ is $[ c _ { 1 } , d _ { 1 } ] \subset [ c , d ]$ , the approximation-degree function of （ $y _ { 0 }$ is

$$
A _ { y _ { 0 } } ( y ) = \left\{ \begin{array} { l l } { \frac { y - c _ { 1 } } { y _ { 0 } - c _ { 1 } } , } & { y \in [ c _ { 1 } , y _ { 0 } ] } \\ { \frac { y - d _ { 1 } } { y _ { 0 } - d _ { 1 } } , } & { y \in [ y _ { 0 } , d _ { 1 } ] } \end{array} \right.
$$

It can be seen that the range of approximation-degree function $A _ { x _ { 0 } } ( x )$ is [0,1] and which is also reversible.In fact,it's easy to obtain that

$$
A _ { y _ { 0 } } ( y ) ^ { - 1 } = \left\{ \begin{array} { l } { { d _ { y } ( y _ { 0 } - c _ { 1 } ) + c _ { 1 } , \quad d _ { y } \in [ 0 , 1 ] } } \\ { { d _ { y } ( y _ { 0 } - d _ { 1 } ) + d _ { 1 } , \quad d _ { y } \in [ 0 , 1 ] } } \end{array} \right.
$$

where $d _ { y }$ is the approximation-degree of $y$ to $y _ { 0 }$

Now we find the approximation-degree $A _ { x _ { 0 } } ( x ^ { \prime } )$ ，and then set $A _ { y _ { 0 } } ( y ^ { \prime } ) = A _ { x _ { 0 } } ( x ^ { \prime } )$ (that is, transmitting the approximation-degree of $x ^ { \prime }$ (to $x _ { 0 }$ )to $y ^ { \prime }$ (to $y _ { 0 }$ )); Further,we derive the required approximate value of $y ^ { \prime }$ from approximation-degree $A _ { y _ { 0 } } ( y ^ { \prime } )$ and inverse function $A _ { y _ { 0 } } ( y ) ^ { - 1 }$ of approximation-degree function of $A _ { y _ { 0 } } ( y )$ ：

It can be seen that the inverse function $A _ { y _ { 0 } } ( y ) ^ { - 1 }$ of $A _ { y _ { 0 } } ( y )$ is a piecewise function,which has two parallel expressions. Thus, substituting approximation-degree $A _ { y _ { 0 } } ( y ^ { \prime } ) = d$ into $A _ { y _ { 0 } } ( y ) ^ { - 1 }$ we can get two $y$ （ $y _ { 1 }$ and $y _ { 2 }$ ).Then，which $y$ should be chosen as the desired approximate value of function?

Obviously, the desired $y$ is related to the position of $x ^ { \prime }$ relative to $x _ { 0 }$ and the trend (i.e., being increasing,decreasing,or a constant）of $f ( x )$ near $x _ { 0 }$ . Thus,we have the following ideas and techniques:

(1） Consider the derivative $f ^ { \prime } ( x _ { 0 } )$ of the function $f ( x )$ at point $x _ { 0 }$ . If the derivative $f ^ { \prime } ( x _ { 0 } )$ is known，we can estimate the trend of $f ( x )$ near $x _ { 0 }$ according to the $f ^ { \prime } ( x _ { 0 } )$ being positive, negative or zero,and then determine the choice of $y$ 's value.

(2)Consider whether there is a point $x ^ { * }$ on the $x ^ { \prime }$ side near the point $x _ { 0 }$ (which does not beyond the approximation region of $x _ { 0 }$ ),whose corresponding value of function, $f ( x ^ { * } ) = y ^ { * }$ ，is known.If there is such a point $x ^ { * }$ ,we can estimate the trend of $f ( x )$ between the $x _ { 0 }$ and $x ^ { * }$ by utilizing the size relation between the corresponding $y ^ { \ast }$ and $y _ { 0 }$ ,and then determine the choice of $y$ 's value. For instance, when $x ^ { * } < x ^ { \prime } < x _ { 0 }$ ,if $y ^ { * } < y _ { 0 }$ , which then shows that the general trend of function $f ( x )$ is increasing on the sub interval $( x ^ { * } , x _ { 0 } )$ ,thus the $y _ { 1 }$ , i.e., that value less than $y _ { 0 }$ , should be chosen; while if $y ^ { * } > y _ { 0 }$ , which then shows that the general trend of function $f ( x )$ （204 is decreasing on the sub interval $( x ^ { * } , x _ { 0 } )$ ,thus the $y _ { 2 }$ ,i.e., that value larger than $y _ { 0 }$ ， should be chosen.

(3） If the derivative $f ^ { \prime } ( x _ { 0 } )$ is unknown and there is no such reference point $x ^ { * }$ ，take the average $( y _ { 1 } + y _ { 2 } ) / 2$ or take the $y _ { 0 }$ directly as the approximate value of $f ( x ^ { \prime } )$ =

Due to the space limit,in the following, we only discuss the second method further,and use third method to classification problems.As for the first method,it willbe introduced in another article.

# 3.2Finding Approximate Value of a Multivariate Function Based on Approximation-Degree

Let's take the function of two variables as an example to discuss this problem.

Let $z = f ( x , y )$ be a function (relation） from $[ a _ { 1 } , b _ { 1 } ] \times [ a _ { 2 } , b _ { 2 } ]$ to $[ c , d ]$ . Suppose a pair of corresponding values, $( ( x _ { 0 } , y _ { 0 } ) , z _ { 0 } )$ ， of function $y = f ( x , y )$ and point $( x ^ { \prime } , y ^ { \prime } )$ approximate to point $( x _ { 0 } , y _ { 0 } )$ are known.In the case that expression of function $f ( x , y )$ is unknown or not used, find the approximate value of $f ( x ^ { \prime } , y ^ { \prime } )$ ：

By the definition of strict approximation, $( x ^ { \prime } , y ^ { \prime } )$ approximate to $( x _ { 0 } , y _ { 0 } )$ is equivalent to $x ^ { \prime }$ approximate to $x _ { 0 }$ and $y ^ { \prime }$ approximate to $y _ { 0 }$ . Thus, we can find the approximate values $z _ { x }$ and $z _ { y }$ of function $f ( x , y _ { 0 } )$ and $f ( x _ { 0 } , y )$ at points $x ^ { \prime }$ and $y ^ { \prime }$ , respectively. It can be seen that this is really two approximate evaluation problems of univariate functions.Thus,we further imagine that if there is respectively an adjacent point $( x ^ { * } , y _ { 0 } )$ and $( x _ { 0 } , y ^ { * } )$ in the $x$ -direction and $y$ -direction of the point $( x _ { 0 } , y _ { 0 } )$ , as shown in Fig. 3.1， whose corresponding function values $f ( x ^ { * } , y _ { 0 } )$ and $f ( x _ { 0 } , y ^ { * } )$ are known, then the approximate value $z _ { x }$ of $f ( x ^ { \prime } , y _ { 0 } )$ can be got by utilizing $f ( x ^ { * } , y _ { 0 } )$ ， and the approximate value $z _ { y }$ of $f ( x _ { 0 } , y ^ { \prime } )$ can be got by utilizing $f ( x _ { 0 } , y ^ { * } )$ , just like that of the previous unary function. Thus, we firstly get separately the approximation-degree $A _ { x _ { 0 } } ( x ^ { \prime } )$ and $A _ { y _ { 0 } } ( y ^ { \prime } )$ ,then set $A _ { z _ { 0 } } ( z ) = A _ { x _ { 0 } } ( x ^ { \prime } )$ and $A _ { z _ { 0 } } ( z ) = A _ { y _ { 0 } } ( y ^ { \prime } )$ ; and then,substitute them separately into inverse function $A _ { z _ { 0 } } ( z ) ^ { - 1 }$ of $A _ { z _ { 0 } } ( z )$ and get two pairs of candidate approximations, then taking separately $f ( x ^ { * } , y _ { 0 } )$ and $f ( x _ { 0 } , y ^ { * } )$ as reference, choose $z _ { x }$ and $z _ { y }$ from respective candidate values (as shown in Fig. 3.1).

Having got the approximate values $z _ { x }$ and $z _ { y }$ , how can we further get the approximate value z we need?

Let $z _ { 1 } = ( z _ { x } + z _ { y } ) / 2$ be the average of $z _ { x }$ and $z _ { y }$ . It can be seen from Fig. 3.2 that $z _ { 1 }$ can actually be viewed as an approximate value of $f ( x , y )$ at midpoint (denoted by $( x _ { 1 } , y _ { 1 } )$ ）between $( x ^ { \prime } , y _ { 0 } )$ and $( x _ { 0 } , y ^ { \prime } )$ .We can see from the figure that $z _ { 1 } < z _ { 0 }$ ,i.e.,the varying trend of function values from $z _ { 0 }$ to $z _ { 1 }$ is decreasing. Set $z _ { 0 } - z _ { 1 } = c _ { 1 } ( c _ { 1 }$ is the length of segment $B C$ in Fig. 3.3(a)), then $z _ { 1 } = z _ { 0 } - c _ { 1 }$ . According to the varying trend of function values from $z _ { 0 }$ to $z _ { 1 }$ (i.e., the slope of segment $A B$ in Fig. 3.3(a)),also,taking into account that point $( x _ { 1 } , y _ { 1 } )$ is just the midpoint of segment joining points $( x ^ { \prime } , y ^ { \prime } )$ and $( x _ { 0 } , y _ { 0 } )$ ,that is, $( x ^ { \prime } , y ^ { \prime } ) - ( x _ { 0 } , y _ { 0 } ) = 2 ( x _ { 1 } , y _ { 1 } ) - ( x _ { 0 } , y _ { 0 } )$ ， so we infer that the approximate value of function at point $( x ^ { \prime } , y ^ { \prime } )$ can be $z _ { 0 } - 2 c _ { 1 }$ (as shown in Fig.3.3(a)).Thus,it follows that

![](images/6b3e14c9950ad8f32673d43220bd5c3c738ee230e8784c91eb59117d89c5930c.jpg)  
Fig.3.1.Utilizing the values of the function at points $( x ^ { * } , y _ { 0 } )$ and $( x _ { 0 } , y ^ { * } )$ to determine the approximate values of $f ( x ^ { \prime } , y _ { 0 } )$ and $f ( x _ { 0 } , y ^ { \prime } )$ ,respectively

$$
z = z _ { 0 } - 2 c _ { 1 } = z _ { 0 } - 2 ( z _ { 0 } - z _ { 1 } ) = z _ { 0 } - 2 [ z _ { 0 } - ( z _ { x } + z _ { y } ) / 2 ] = z _ { x } + z _ { y } - z _ { 0 }
$$

![](images/490a0fef54b76e71581c62d56846d8390e8e7eb0fe636200d552fca31dffa1ff.jpg)  
Fig.3.2.Illustration-1 of synthesizing $z _ { x }$ and $z _ { y }$ into $z$

Of course, $z _ { 1 }$ may also be greater than $z _ { 0 }$ or equal to $z _ { 0 }$ .If $z _ { 1 } > z _ { 0 }$ , then the varying trend of function values from $z _ { 0 }$ to $z _ { 1 }$ is increasing (as shown in Fig. 3.3(b)). Set $z _ { 0 } - z _ { 1 } = c _ { 2 } ( c _ { 2 }$ is the length of segment $B C$ in Fig. 3.3(b)), then $z _ { 1 } = z _ { 0 } - c _ { 2 }$ . Then, according to the varying trend of function values from $z _ { 0 }$ to $z _ { 1 }$ (i.e.,the slope of segment $A B$ in Fig.3.3(b)),we infer that the value of function at point $( x ^ { \prime } , y ^ { \prime } )$ can be $z _ { 0 } - 2 c _ { 2 }$ . Thus,

$$
z = z _ { 0 } + 2 c _ { 2 } = z _ { 0 } + 2 ( z _ { 1 } - z _ { 0 } ) = z _ { 0 } + 2 [ ( z _ { x } + z _ { y } ) / 2 - z _ { 0 } ] = z _ { x } + z _ { y } - z _ { 0 }
$$

The third case: $z _ { 1 } = z _ { 0 }$ . This indicates that the values of function remain unchanged from $z _ { 0 }$ to $z _ { 1 }$ . Thus, we can take $z = z _ { 0 }$ . And by $z _ { 0 } = z _ { 1 } = ( z _ { x } + z _ { y } ) / 2$ , it follows that $2 z _ { 0 } = z _ { x } + z _ { y }$ . Thus,

$$
z = 2 z _ { 0 } - z _ { 0 } = z _ { x } + z _ { y } - z _ { 0 }
$$

In summary,we see that, no matter what relationship may be between the average of $z _ { x }$ and （20 $z _ { y }$ and the $z _ { 0 }$ , or no matter how the value of the function varies from $z _ { 0 }$ to $z _ { 1 }$ , the approximate value of the function at point $( x ^ { \prime } , y ^ { \prime } )$ can always be taken as

$$
z = z _ { x } + z _ { y } - z _ { 0 }
$$

![](images/80d802c30961dd83c99642b79a8ef8e91f579e6ce6763793431ae00de1e75175.jpg)  
Fig.3.3.Illustration-2 of synthesizing $z _ { x }$ and $z _ { y }$ into $z$

This equation is also the calculation model of the approximate value of function of two variables, （204号 $z = f ( x , y )$ ：

It can be seen that this is actually splitting the approximate evaluation of a function of two variables into the approximate evaluation of two functions of one variable,firstly, then, synthesizing two obtained approximate values into a value as an approximate value of the original function of two variables.Extending this technique of “first splitting then synthesizing” to the approximate evaluation of a function of 3 variables, $u = f ( x , y , z )$ ，we obtain the formula synthesizing approximate value of the function is

$$
u = u _ { x } + u _ { y } + u _ { z } - 2 u _ { 0 }
$$

And then, for a function of $n$ variables, $y = f ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } )$ , the corresponding formula synthesizing approximate value of the function is

$$
y = y _ { x _ { 1 } } + y _ { x _ { 2 } } + \ldots + y _ { x _ { n } } - ( n - 1 ) y _ { 0 }
$$

or

$$
y = \sum _ { i = 1 } ^ { n } y _ { x _ { i } } - ( n - 1 ) y _ { 0 }
$$

For convenience of narration, we may as well refer to the Equations (3.4),(3.5) and (3.6) as the sum-times-differenceformula.

# 4Interpolation Based on Approximation-Degree

Let $y = f ( x )$ be a function (relation） from $[ a , b ]$ to $[ c , d ]$ . A set of pairs of corresponding values of function $y \ = \ f ( x )$ ， $( x _ { 1 } , y _ { 1 } )$ ， $( x _ { 2 } , y _ { 2 } )$ ，…， $( x _ { n } , y _ { n } )$ ，is known，where $x _ { 1 } < x _ { 2 } < , . . . , < x _ { n }$ Now the question is: in the case that the expression of function $f ( x )$ is unknown or not used, construct an interpolating function $g ( x )$ such that $g ( x _ { i } ) = f ( x _ { i } )$ 1 $\langle i = 1 , 2 , . . . , n$ )，and for other （204号 $x \in [ a , b ]$ ， $g ( x ) { \approx } f ( x )$ . This is the usual interpolation problem.We now use the approach that finding approximate value of a function above to solve the interpolation problem.

Let $a = x _ { 1 } , x _ { n } = b$ ，then $x _ { 1 } , x _ { 2 } , . . . , x _ { n }$ is a group of interpolation base points (or nodes). We definite the approximation region of $x _ { 1 }$ as $[ x _ { 1 } , x _ { 2 } ]$ ， the approximation region of $x _ { i }$ as $[ x _ { i - 1 } , x _ { i + 1 } ] ( i \ = \ 2 , 3 , . . . , n \ - \ 1 )$ ，and the approximation region of $x _ { n }$ as $[ x _ { n - 1 } , x _ { n } ]$ ，and then definite separately the approximation-degree functions of base points $x _ { 1 }$ ， $x _ { i }$ ,and $x _ { n }$ as

$$
A _ { x _ { 1 } } ( x ) = { \frac { x - x _ { 1 } } { x _ { 1 } - x _ { 2 } } } , \quad x \in [ x _ { 1 } , x _ { 2 } ]
$$

$$
A _ { x _ { i } } ( x ) = \left\{ \begin{array} { l l } { \frac { x - x _ { i - 1 } } { x _ { i } - x _ { i - 1 } } , \quad x \in [ x _ { i - 1 } , x _ { i } ] } \\ { \frac { x - x _ { i + 1 } } { x _ { i } - x _ { i + 1 } } , \quad x \in [ x _ { i } , x _ { i + 1 } ] } \end{array} \right.
$$

$$
A _ { x _ { n } } ( x ) = { \frac { x - x _ { n - 1 } } { x _ { n } - x _ { n - 1 } } } , \quad x \in [ x _ { n - 1 } , x _ { n } ]
$$

Note that it is not hard to see from the above expressions of approximation-degree functions that when $x \in [ x _ { 1 } , ( x _ { 1 } + x _ { 2 } ) / 2 ]$ ，[（x $_ { - 1 } + x _ { i } ) / 2 , ( x _ { i } + x _ { i + 1 } ) / 2 ] , o r [ ( x _ { n - 1 } + x _ { n } ) / 2 , x _ { n } ]$ , the corresponding approximation-degrees $A _ { x _ { 1 } } ( x ) , A _ { x _ { i } } ( x ) , a n d A _ { x _ { n } } ( x )$ are always $\geq 0 . 5$ . This means that $x$ is closer to the corresponding base point $x _ { 1 } , x _ { i } , o r x _ { n }$ ：

We then define the approximation-degree functions of $y _ { i } ( i = 1 , 2 , . . . , n )$ in the same principle and way.

$$
\begin{array} { r l } & { A _ { y _ { i } } ( y ) = \cfrac { y - y _ { i - 1 } } { y _ { i } - y _ { i - 1 } } = \cfrac { 1 } { y _ { i } - y _ { i - 1 } } y - \cfrac { y _ { i - 1 } } { y _ { i } - y _ { i - 1 } } , \quad y \in [ y _ { i - 1 } , y _ { i } ] } \\ & { A _ { y _ { i } } ( y ) = \cfrac { y _ { i - 1 } - y } { y _ { i - 1 } - y _ { i } } = \cfrac { 1 } { y _ { i } - y _ { i - 1 } } y - \cfrac { y _ { i - 1 } } { y _ { i } - y _ { i - 1 } } , \quad y \in [ y _ { i } , y _ { i - 1 } ] } \\ & { A _ { y _ { i } } ( y ) = \cfrac { y _ { i + 1 } - y } { y _ { i + 1 } - y _ { i } } = \cfrac { 1 } { y _ { i } - y _ { i + 1 } } y - \cfrac { y _ { i + 1 } } { y _ { i } - y _ { i + 1 } } , \quad y \in [ y _ { i } , y _ { i + 1 } ] } \\ & { A _ { y _ { i } } ( y ) = \cfrac { y - y _ { i + 1 } } { y _ { i } - y _ { i + 1 } } = \cfrac { 1 } { y _ { i } - y _ { i + 1 } } y - \cfrac { y _ { i + 1 } } { y _ { i } - y _ { i + 1 } } , \quad y \in [ y _ { i + 1 } , y _ { i } ] } \end{array}
$$

Obviously, in the four expressions above, $( 4 . 4 ) = ( 4 . 5 )$ and $( 4 . 6 ) = ( 4 . 7 )$ . Thus, the 4 functional expressions can be reduced as two expressions:

$$
\begin{array} { l } { { A _ { y _ { i } } ( y ) = \displaystyle \frac { 1 } { y _ { i } - y _ { i - 1 } } y - \displaystyle \frac { y _ { i - 1 } } { y _ { i } - y _ { i - 1 } } } } \\ { { \ } } \\ { { A _ { y _ { i } } ( y ) = \displaystyle \frac { 1 } { y _ { i } - y _ { i + 1 } } y - \displaystyle \frac { y _ { i + 1 } } { y _ { i } - y _ { i + 1 } } } } \end{array}
$$

And then, we get the inverse expressions of these two functional expressions:

$$
\begin{array} { r } { A _ { y _ { i } } ( y ) ^ { - 1 } = d _ { y } ( y _ { i } - y _ { i - 1 } ) + y _ { i - 1 } } \\ { \qquad \quad } \\ { A _ { y _ { i } } ( y ) ^ { - 1 } = d _ { y } ( y _ { i } - y _ { i + 1 } ) + y _ { i + 1 } } \end{array}
$$

Here $d _ { y } = A _ { y _ { i } } ( y ) \in [ 0 , 1 ]$ is the approximation-degree of $y$ to $y _ { i }$ Now, set

$$
d _ { y } = d _ { x } = A _ { x _ { i } } ( x )
$$

Also, considering that on the sub interval $\textstyle { \left[ { \frac { x _ { i - 1 } + x _ { i } } { 2 } } , x _ { i } \right] }$ ,the interpolated function $y = f ( x )$ may   
being increasing, decreasing, or a constant; while when $y = f ( x )$ is increasing,certainly $y _ { i - 1 } < y _ { i }$ ，   
so the corresponding $y \in \left[ \frac { y _ { i - 1 } + y _ { i } } { 2 } , y _ { i } \right]$ ;when $y = f ( x )$ is decreasing, certainly $y _ { i } < y _ { i - 1 }$ ,so the $\begin{array} { r } { y \in [ y _ { i } , \frac { y _ { i - 1 } + y _ { i } } { 2 } ] } \end{array}$ 21 $y = f ( x )$ 1 $y _ { i } = y _ { i - 1 }$   
$\begin{array} { r } { y = y _ { i } \in [ \frac { y _ { i - 1 } + y _ { i } } { 2 } , y _ { i } ] } \end{array}$ $\boldsymbol { y } \in [ y _ { i } , \frac { y _ { i - 1 } + y _ { i } } { 2 } ]$ $\textstyle x \in [ { \frac { x _ { i - 1 } + x _ { i } } { 2 } } , x _ { i } ]$   
$y _ { i }$ $y _ { i - 1 }$ $\begin{array} { r } { A _ { x _ { i } } ( x ) = \frac { x - x _ { i - 1 } } { x _ { i } - x _ { i - 1 } } } \end{array}$   
of the corresponding inverse function $A _ { y _ { i } } ( y ) ^ { - 1 }$ ，becomes

$$
\begin{array} { r } { A _ { y _ { i } } ( y ) ^ { - 1 } = \frac { x - x _ { i - 1 } } { x _ { i } - x _ { i - 1 } } ( y _ { i } - y _ { i - 1 } ) + y _ { i - 1 } = \frac { y _ { i } - y _ { i - 1 } } { x _ { i } - x _ { i - 1 } } x + \frac { x _ { i } y _ { i - 1 } - x _ { i - 1 } y _ { i } } { x _ { i } - x _ { i - 1 } } } \end{array}
$$

namely

$$
y = \frac { y _ { i } - y _ { i - 1 } } { x _ { i } - x _ { i - 1 } } x + \frac { x _ { i } y _ { i - 1 } - x _ { i - 1 } y _ { i } } { x _ { i } - x _ { i - 1 } } , \quad x \in [ \frac { x _ { i - 1 } + x _ { i } } { 2 } , x _ { i } ]
$$

Similarly, the Expression (4.9) of the inverse function $A _ { y _ { i } } ( y ) ^ { - 1 }$ becomes

$$
y = \frac { y _ { i } - y _ { i + 1 } } { x _ { i } - x _ { i + 1 } } x + \frac { x _ { i } y _ { i + 1 } - x _ { i + 1 } y _ { i } } { x _ { i } - x _ { i + 1 } } , \quad x \in [ x _ { i } , \frac { x _ { i } + x _ { i + 1 } } { 2 } ]
$$

Thus,with the two expressions,we can obtain directly the corresponding $y \in \left[ { \frac { y _ { i - 1 } + y _ { i } } { 2 } } , y _ { i } \right]$ $[ y _ { i } , \frac { y _ { i - 1 } + y _ { i } } { 2 } ]$ from $x \in [ \frac { x _ { i - 1 } + x _ { i } } { 2 } , x _ { i } ]$ ,and obtain directly the corresponding $\begin{array} { r } { y \in [ y _ { i } , \frac { y _ { i } + y _ { i + 1 } } { 2 } ] } \end{array}$ Or [i+yi+²,yi] from x ∈[xi, $\textstyle x \in [ x _ { i } , { \frac { x _ { i } + x _ { i + 1 } } { 2 } } ]$ x+xi+11.

Actually, Equations (4.10) and (4.11) are two interpolation formulas. In this way, we actually derive an interpolation approach by using the approximate evaluation of function based on approximation-degree.We call this approach to be the approximation-degree-based interpolation,or ADB interpolation for short.

Specifically, the practice of ADB interpolation is: take base points $a = x _ { 1 } , x _ { 2 } , . . . , x _ { n } = b$ as points of view,according to base points and their approximation regions to partition interval $[ a , b ] = [ x _ { 1 } , x _ { n } ]$ into $2 n - 2$ subintervals as shown in Fig. 4.1, $[ x _ { 1 } , ( x _ { 1 } + x _ { 2 } ) / 2 ] , [ ( x _ { 1 } +$ （204 $x _ { 2 } ) / 2 , x _ { 2 } ]$ ， $[ x _ { 2 } , ( x _ { 2 } + x _ { 3 } ) / 2 ] , . . . , [ ( x _ { n - 1 } + x _ { n } ) / 2 , x _ { n } ]$ ，as interpolation intervals; then, for evaluated point $x \ \in \ [ ( x _ { i - 1 } + x _ { i } ) / 2 , x _ { i } ]$ do interpolating with Formula (4.1O), for evaluated point （20 $x \in [ x _ { i } , ( x _ { i } + x _ { i + 1 } ) / 2 ]$ do interpolating with Formula (4.11). Since each specific interpolating formula implies the trend of interpolated function $y = f ( x )$ on the corresponding subintervals, therefore, there is no much error between the obtained approximate value and the expected value,and there would not occur the case that two $y$ -values are got from an $x$ ：

![](images/e7d2f95a2228c07bf8214042e36bede5f484b319f7b25039609b0808516f1409.jpg)  
Fig.4.1. Illustration of interpolation intervals partitioned by base points and their approximation regions in one-dimensional interpolation

Example 4.1.Use ADB interpolation to do interpolation for function $y = \sin x$

We take sampled data points of $y = \sin x , ( x _ { i } , y _ { i } )$ , as follows: （202 $x _ { i } : 0 \times \pi , 0 . 1 \times \pi , 0 . 2 \times \pi , . . . , 1 . 9 \times \pi , 2 \times \pi$ ： （204号 $y _ { i } : \sin x _ { i }$ ： and take interpolation points, $x : 0 \times \pi , 0 . 0 2 \times \pi , 0 . 0 4 \times \pi , 0 . 0 6 \times \pi , . . . , 1 . 9 8 \times \pi , 2 \times \pi$ Using our ADB interpolation to do interpolation, the corresponding $y$ -values obtained are as follows: 00.0624 0.1249 0.1873 0.2497 0.3118 0.36810.42450.4808 0.5371 0.5923 0.63690.6816 0.7263 0.7710 0.81330.8420 0.8707 0.89940.9281 0.95300.9629 0.9728 0.9827 0.9926 0.9975 0.9876 0.9778 0.9679 0.9580 0.9424 0.9138 0.88510.8564 0.8277 0.7934 0.74870.7040 0.65930.6146 0.5653 0.5089 0.4526 0.39630.34000.28090.21850.15610.09360.0312-0.0312-0.0936-0.1561-0.2185-0.2809-0.3400-0.3963 -0.4526-0.5089-0.5653-0.6146-0.6593-0.7040-0.7487-.7934-0.8277-0.8564-0.8851-0.9138-0.9424 -0.9580-0.9679-0.9778-0.9876-0.9975-0.9926-0.9827-0.9728-0.9629-0.9530-0.9281-0.8994-0.707 -0.8420-0.8133-0.7710-0.7263-0.6816-0.6369-0.5923-0.5371-0.4808-0.4245-0.3681-0.3118-0.2497 -0.1873 -0.1249 -0.0624 0.0000

And the effect is shown in Fig. 4.2.

![](images/50f79a9d40ef153eb7a254c8aaad0c84528857e59f5559046eeea746aba76160.jpg)  
Fig.4.2.The effect drawing of ADB interpolation for function $y = \sin x$

From the interpolation method of the univariate function and the method of finding the approximate value of the function of $n$ -variables above,we obtain a general $n$ -dimensional ADB interpolation method, that is: splits an $n$ -dimensional interpolation into $n$ one-dimensional interpolation,then use one-dimensional ADB interpolation to find the corresponding approximate values, respectively, and finally synthesize the $n$ approximate values by using sum-times-difference formula into one value as the approximation value of the function of $n$ variables.The $n$ pairs of one-dimensional interpolation formulas are required for $n$ -dimensional ADB interpolation, they are as follows:

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { y = \frac { y _ { i j \ldots s } - y _ { i - 1 , j \ldots s } } { x _ { 1 } \ldots x _ { 1 \ - 1 } } x _ { 1 } + \frac { x _ { 1 _ { i } } y _ { i - 1 , j \ldots s } - x _ { 1 _ { i - 1 } } y _ { i  j \ldots s } } { x _ { 1 _ { i } } \ldots x _ { 1 _ { i - 1 } } } } \\ { y = \frac { y _ { i j \ldots s } - y _ { i + 1 , j \ldots s } } { x _ { 1 _ { i } } - x _ { 1 _ { i + 1 } } } x _ { 1 } + \frac { x _ { 1 _ { i } } y _ { i + 1 , j \ldots s } - x _ { 1 _ { i + 1 } } y _ { i j \ldots s } } { x _ { 1 _ { i } } - x _ { 1 _ { i + 1 } } } } \\ { \qquad \quad \vdots } \\ { y = \frac { y _ { i j \ldots s } - y _ { i - 1 , j \ldots s } } { x _ { 2 _ { i } } - x _ { 2 _ { i - 1 } } } x _ { 2 } + \frac { x _ { 2 _ { i } } y _ { i - 1 , j \ldots s } - x _ { 2 _ { i - 1 } } y _ { i j \ldots s } } { x _ { 2 _ { i } } - x _ { 2 _ { i - 1 } } } } \\ { y = \frac { y _ { i j \ldots s } - y _ { i + 1 , j \ldots s } } { x _ { 2 _ { i } } - x _ { 2 _ { i + 1 } } } x _ { 2 } + \frac { x _ { 2 _ { i } } y _ { i + 1 , j \ldots s } - x _ { 2 _ { i + 1 } } y _ { i j \ldots s } } { x _ { 2 _ { i } } - x _ { 2 _ { i + 1 } } } } \end{array} \right. } \end{array}
$$

$$
\left\{ \begin{array} { l l } { y = \frac { y _ { i j \dots s } - y _ { i - 1 , j \dots s } } { x _ { n _ { i } } - x _ { n _ { i - 1 } } } x _ { n } + \frac { x _ { n _ { i } } y _ { i - 1 , j \dots s } - x _ { n _ { i - 1 } } y _ { i j \dots s } } { x _ { n _ { i } } - x _ { n _ { i - 1 } } } } \\ { y = \frac { y _ { i j \dots s } - y _ { i + 1 , j \dots s } } { x _ { n _ { i } } - x _ { n _ { i + 1 } } } x _ { n } + \frac { x _ { n _ { i } } y _ { i + 1 , j \dots s } - x _ { n _ { i + 1 } } y _ { i j \dots s } } { x _ { n _ { i } } - x _ { n _ { i + 1 } } } } \end{array} \right.
$$

where $y _ { i j \ldots s }$ is the value of function at base point $( x _ { 1 _ { i } } , x _ { 2 _ { j } } , . . . , x _ { n _ { s } } )$ ,i.e., $y _ { i j \ldots s } = f ( x _ { 1 _ { i } } , x _ { 2 _ { j } } , . . . , x _ { n _ { s } } )$ And the final synthesis formula (i.e., sum-times-difference formula) of approximate value of the function is

$$
y = \sum _ { i = 1 } ^ { n } y _ { x _ { i } } - ( n - 1 ) y _ { i j \ldots s }
$$

here $y _ { x _ { i } }$ is the approximate value of function that obtained by one-dimensional ADB interpolation for $x _ { i } ( i = 1 , 2 , . . . , n )$

Actually, it is not difficult to see that the equation (4.12) can also be said to be the formula of multidimensional ADB interpolation,which is also a calculation model of high-dimensional interpolation.

Example 4.2. Using ADB interpolation to do interpolation for function $\begin{array} { r } { z = \frac { 1 } { 4 } x ^ { 2 } - \frac { 1 } { 4 } y ^ { 2 } } \end{array}$ ,the effect is shown in Fig. 4.3.

![](images/c9163d9630d8df78f18b456c0780546b4b4a5a27a16b121e276ac0aa14ba4bdd.jpg)  
Fig. 4.3. The effect drawing of ADB interpolation for function $\begin{array} { r } { z = \frac { 1 } { 4 } x ^ { 2 } - \frac { 1 } { 4 } y ^ { 2 } } \end{array}$ Where the left is the functional graph before interpolating,and the right is the functional graph after interpolating.

Example 4.3.Using ADB interpolation to do interpolation for function of three variables, （204号 $u = z e ^ { - x ^ { 3 } - y ^ { 3 } - z ^ { 3 } }$ ,the effect (slice chart) is shown in Fig. 4.4.

# 5 Instance-Based Learning Using ADB interpolation

In the above,we develop a new interpolation approach,ADB interpolation, from finding approximate value of a function. Since ADB interpolation is a local interpolation,it can be used for instance-based machine learning. In the following, we present two learning algorithms.

![](images/7eb438661c44a0bad6ba9c0473df0cea660cb587662c37507544f330defb2341.jpg)  
Fig. 4.4. The efect drawing of ADB interpolation for function ze-3-y-3

# (1)A leaning algorithm for regression problems

· Put samples in sample set $X \ = \ \{ ( { \pmb x } ^ { \prime } , f ( { \pmb x } ^ { \prime } ) ) \} _ { i = 1 } ^ { m } ( { \pmb x } \ = \ ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) )$ into a corresponding data structure $S$ in centralized or distributed manner (as training examples);

· For the currently being queried $\pmb { x } ^ { \prime } = ( x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , . . . , x _ { n } ^ { \prime } )$

· According to its coordinate components $x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , . . . , x _ { n } ^ { \prime }$ look up in $S$ sequentially or in parallel to determine a $\pmb { x } ^ { k } ( k \in \{ 1 , 2 , . . . , m \} )$ to which the approximation-degree of $\mathbf { { x } ^ { \prime } }$ is highest; · Take $\scriptstyle { \pmb { x } } ^ { k }$ as the center,and according to the position of $\mathbf { x } ^ { \prime }$ relative to $\scriptstyle { \pmb { x } } ^ { k }$ , choose $n$ corresponding nearest neighbors $\pmb { x } ^ { 1 } , \pmb { x } ^ { 2 } , . . . , \pmb { x } ^ { n }$ (The data points here are renumbering.） from $S$ ,then construct the corresponding one-dimensional interpolation formulas

$$
y _ { x _ { j } } = g ( x _ { j } | x _ { j } ^ { k } , f ( x ^ { k } ) , x _ { j } ^ { l } , f ( x ^ { l } ) ) \qquad ( j = 1 , 2 , . . . , n ; l \in \{ 1 , 2 , . . . , n \} )
$$

and then compute $y _ { x _ { 1 } } , y _ { x _ { 2 } } , . . . , y _ { x _ { n } }$ sequentially or in parallel; · Return

$$
\begin{array} { r } { \hat { f } ( \pmb { x } ^ { \prime } ) = \sum _ { j = 1 } ^ { n } y _ { x _ { j } } - ( n - 1 ) f ( \pmb { x } ^ { k } ) } \end{array}
$$

Example 5.1. Take the following pairs of corresponding values of function $z = - x ^ { 2 } -$ $y ^ { 2 } , ( ( x _ { i } , y _ { j } ) , z _ { i j } )$ , as example data: $x _ { i }$ : -20,-18,-16，..,-2,0,2，..，16,18,20. （20 $y _ { j }$ : -20,-18,-16,.,-2,0, 2,.,16,18,20. （204 $z _ { i j } : - x _ { i } ^ { 2 } - y _ { j } ^ { 2 }$ （204号   
and take the following data points, $( x , y )$ , as query data: x: -20,-20,20,-19.5,-17.8,-18,-15.3,-12,-10.2,-10,-10,0,0,10,10,5.6,4.7,-3.4,-1.8,-2.3,-3.6,   
1.2,-5.4,-15.6,-20,-20,-20,-18.3,18.4,17.5,16.2,14.5,11.1,-5.4,-12.1,-8.5,-13.9,-7.5,-7.8,-9.8,   
-12.4,-13.5,-14.6,-17.5,-17.8. y: -20,20,-20,-19.5,-17.8,-5,-15.5,2.5,-10.2,10,-20,0,-20,-20,-10,-15.3,-3.8,-13.4,-2.8,-1.9,   
-5.6,-10.2,-6.5,5.6,0,-10,10,10.4,-18.1,-16.3,-14.4,-12.3,-6.3,-15.8,-8.2,-15.6,0.9,1.6,3.2,4.6,   
6.6, 2.8,-0.9, 18.6, 13.2. we use the above learning algorithm,the corresponding z-values obtained are as follows:   
-800.0000-800.0000-800.0000-762.000-634.4000-350.0000-476.0000-151.0000-208.8000-200.0000

-500.00000-400.0000-500.0000-200.0000-267.0000-37.8000-192.8000-12.4000-9.6000-45.6000- 106.8000 -73.0000-276.0000-400.0000-500.0000-500.0000-444.2000-667.0000-573.2000-470.8000- 362.8000-164.4000-280.0000 -214.2000-317.0000 -195.2000-60.2000-72.4000 -118.4000-198.8000- 191.8000 -215.8000 -653.8000 -492.4000

The effect drawing is shown in Fig. 5.1.

![](images/60233c9b5408e029f36270f68d8c3fd2adfb853c57d26444a9149d61031d0b38.jpg)  
Fig.5.1.An effect drawing of the learning using ADB interpolation

Where the grid curve is the graph formed by example data from function $z = - x ^ { 2 } - y ^ { 2 }$ , and the red circles indicate the points obtained by learning using ADB interpolation.

Example 5.2. Fig. 5.2 below shows an effect drawing of learning using ADB interpolation. The example data are taken from the peaks function in MATLAB,and the query data is also designed according to this function.Limited by space, these data are omitted.

As can be seen from the above, this instance-based learning using ADB interpolation has the following characteristics:

$\bullet$ The learning method takes data points ( $\mathbf { \Delta } _ { \mathbf { \boldsymbol { x } } ^ { l } }$ ）of training examples $( { \pmb x } ^ { l } , f ( { \pmb x } ^ { l } ) )$ as centers to set approximation regions and compute approximation-degrees.   
$\bullet$ ADB interpolation is a local interpolation,the training examples involved in interpolation are related to the position of the currently queried data point $\mathbf { { x } ^ { \prime } }$ relative to its nearest data point （20 $\scriptstyle { \boldsymbol { { x } } } ^ { k }$ , the number of which is related to the dimension of the vector $_ { x }$ ， $n$ -dimensional $_ { x }$ only involves $1 + n$ training examples（ $( \pmb { x } ^ { k } , f ( \pmb { x } ^ { k } ) )$ and $( { \pmb x } ^ { 1 } , f ( { \pmb x } ^ { 1 } ) ) , ( { \pmb x } ^ { 2 } , f ( { \pmb x } ^ { 2 } ) ) , . . . , ( { \pmb x } ^ { n } , f ( { \pmb x } ^ { n } ) )$ ） But since the point $\mathbf { { x } ^ { \prime } }$ is only approximate to the point $\scriptstyle { \boldsymbol { x } } ^ { k }$ ， the corresponding $y _ { x _ { j } } ( j ~ =$ （20 $1 , 2 , . . . , n )$ are most affected by the example $( \pmb { x } ^ { k } , f ( \pmb { x } ^ { k } )$ , and the final synthesized value $\hat { f } ( { \pmb x } ^ { \prime } )$ is also most affected by $( \mathbf { \boldsymbol { x } } ^ { k } , f ( \mathbf { \boldsymbol { x } } ^ { k } )$ ：   
· If distributed storage and parallel processing (including parallel lookup and parallel computation） are used,the time complexity of corresponding algorithm is independent of the

![](images/640f093bb2ce0f31031ed854284da75f841e2e310e9a9b0b4aaf9eaf09cf1288.jpg)  
Fig.5.2.An illustration of the effect of learning using ADB interpolation

Where the left is the functional graph formed by example data and the right is the functional graph obtained by learning using ADB interpolation

dimension of vector $_ { x }$ ,and its efficiency is almost equal to that of one-dimensional interpolation at all time.   
The interpolation formulas (including sum-times-difference formula) are derived entirely by the mathematical method, so they have definite mathematical basis.   
The sum-times-difference formula is actually a linear combination of coordinate components of an interpolation point,and the denominators of the coefficients before each coordinate component are separately the difference between the coordinate component and the corresponding coordinate component of corresponding base point, that is, the distance between the two,so, these coefficients happen to also have a function of the weight values. Thus, viewed from the form, the sum-times-difference formula is a linear weighted regression formula.That is to say, the sum-times-difference formula here coincides with the traditional local weighted linear regression model. However,in local weighted linear regression, these coeffcients are determined by searching,while in our ADB interpolation, these coefficients are determined by looking up. The former is guided and constrained by error function (e.g. （204号 $\begin{array} { r } { E \ = \ \frac 1 2 \sum _ { { \pmb x } \in X _ { 1 } \subset X } ( f ( { \pmb x } ) - \hat { f } ( { \pmb x } ) ) ^ { 2 } ) } \end{array}$ ， and the latter by approximation-degree function (e.g. $A _ { x _ { i } } ( x ) ,$ . In the sense of approximation-degree, the approximate value $\hat { f } ( { \pmb x } ^ { \prime } )$ of the function obtained from the sum-times-difference formula is always the most accurate.   
The accuracy of the returned approximate value $\hat { f } ( { \pmb x } ^ { \prime } )$ of a function is positively related to the approximation-degree of $\mathbf { { x } ^ { \prime } }$ to $\scriptstyle { \boldsymbol { { x } } } ^ { k }$ ：   
· Comparing the learning using ADB interpolation with the deep learning, the deep learning is to approximate objective function with the strategy of deepening vertically[9],yet the learning using ADB interpolation can approximate objective function with the strategy of increasing density horizontally. So, the learning using ADB interpolation and the deep learning can complement each other,and can even have an effect of “different approaches but equal results” in the case of sufficient samples.

(2)A learning algorithm for classification problems ·Put samples in sample set $X = \{ ( { \pmb x } ^ { i } , f ( { \pmb x } ^ { i } ) ) \} _ { i = 1 } ^ { m } ( { \pmb x } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) , f ( { \pmb x } )$ is a class label) into a corresponding data structure $S$ in centralized or distributed manner;

· For the currently being queried $\pmb { x } ^ { \prime } = ( x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , . . . , x _ { n } ^ { \prime } )$

$\bullet$ According to its coordinate components $x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , . . . , x _ { n } ^ { \prime }$ look up in $S$ sequentially or in parallel to determine a $\pmb { x } ^ { k } ( k \in \{ 1 , 2 , . . . , m \} )$ to which the approximation-degree of $\pmb { x } ^ { \prime }$ is highest; · If such a $\scriptstyle { \pmb { x } } ^ { k }$ is found,return

$$
{ \hat { f } } ( \mathbf { x } ^ { \prime } ) = f ( \mathbf { x } ^ { k } )
$$

· Else exit.

Example 5.3. Suppose that the data points of training examples of a classfication problem are shown as the black circles in Fig.5.2,and the small boxes surrounding them are their respective strict approximation regions;and the white circles represent data points to be classified. Using the learning algorithm that using ADB interpolation to clasify these data points, the clasifying results are shown in the figure.As you can see, there are two queried data points are respectively classified to two classes to which the corresponding training example data points belong,because they are located respectively in the strict approximation regions of the corresponding data points, while the two queried data points outside the small boxes are not classified.

![](images/412b482cd85dd2f2ae873ee51a398c9a5185c6c1621c621b0de2fb5dacca2bc9.jpg)  
Fig.5.3.An illustration of applying the learning using ADB interpolation to classification

It can be seen that for classification problems,the learning using ADB interpolation has the following advantages:

· Although similar to the traditional 1-NN algorithm,the approximation regions in the algorithm are aimed at the data points of training examples,and which are strict approximation regions of square.   
· Since the approximation and approximation regions involved in the algorithm are strict approximation and strict approximation regions, for classfication problems, learning using ADB interpolation avoids,from the source,the problem in traditional instance-based learning (e.g. $k$ -NN algorithm) that some datum objects with similar partial attributes are classified into a class.   
· The classifying result of learning using ADB interpolation is unique,and there is no the phenomenon like $k$ -NN algorithm, that classifying result may change with the change of $k$ ,S value.

# 6 Summary

In this paper, started from finding approximate value of a function, we introduced the measure of approximation-degree between numerical values,proposed the concepts of "strict approximation” and "strict approximation region”, then, derived the corresponding one-dimensional interpolation methods and formulas,and then presented a calculation model called "sum-timesdifference formula” for high-dimensional interpolation, thus we developed a new interpolation approach - approximation-degree-based interpolation,i.e.,ADB interpolation.ADB interpolation was applied to the interpolation of actual functions with satisfactory results. Viewed from principles and examples, the approach is of novel idea,and it has the advantages of simple calculations (they are all arithmetic),stable accuracy (benefitting from local interpolation and that the approximation-degrees are always not less than 0.5); especially,the approach facilitates parallel processing, very suiting for high-dimensional interpolation,and easy to be extended to the interpolation of vector valued functions.

Applying ADB interpolation to instance-based learning,we obtained a new instance-based learning method - learning using ADB interpolation,and we also gave several examples of the learning.Viewed from principles and examples,the learning method is of unique technique (e.g.,taking data points of training examples as centers to set approximation regions that are also strict approximation regions and compute approximation-degrees). Besides the advantages of ADB interpolation,the learning method has also the advantages of definite mathematical basis, implicit distance weights,avoiding misclassification (guaranteed by strict approximation), high efficiency (benefiting from distributed storage and paralel processing), and wide range of applications (which can be applied to the regression or classification problems,and can be used for large sample learning or small sample even single sample learning),as well as being interpretable, etc. In principle, this method is a kind of learning by analogy, which and the deep learning that belongs to inductive learning can complement each other,and for some problems, the two can even have an effect of “different approaches but equal results” in big data and cloud computing environment. Thus,the learning using ADB interpolation can also be regarded as a kind of “wide learning” that is dual to deep learning.

# References

1.Tom M.Mitchel: Machine Learning.MecGraw-Hill Companies,Inc.(1997)   
2.Stuart Russell,Peter Norvig: Artificial Intelligence: A Modern Approach. Second Edition.Pearson Education Limited,London (2003)   
3.Ethem Alpaydin: Introduction to Machine Learning.Third Edition.Massachusetts Institute of Technology (2014)   
4.Stuart J. Russell, Peter Norvig: Artificial Intelligence: A Modern Approach. Third Edition.Pearson Education Limited, London (2016)   
5.Shiyou Lian: Correspondence between Flexible Sets,and Flexible Linguistic Functions,in: Shiyou Lian,Principles of Imprecise-Information Processing: A New Theoretical and Technological System, pp.205-228. Springer,Singapore (2016)   
6.Shiyou Lian: Approximate Evaluation of Flexible Linguistic Functions,in: Shiyou Lian,Principles of Imprecise-Information Processng: A New Theoretical and Technological System，pp. 393-417. Springer, Singapore (2016)   
7.Shiyou Lian: Principles of Imprecise-Information Processing: A New Theoretical and Technological System. Springer, Singapore (2016)   
8.Shiyou Lian: Multidimensional Flexible Concepts and Flexible Linguistic Values and Their Mathematical Models,in: Shiyou Lian,Principles of Imprecise-Information Processing: A New Theoretical and Technological System，pp.45-79.Springer,Singapore (2016)   
9.Yoshua Bengio: Deep Learning.July 23,2015,LxMLS (2015),Lisbon Machine Learning Summer School,Lisbon Portugal,htp://www.iro.umontreal.ca/bengioy/talks/lisbon-mlss-19juilet2015.pdf