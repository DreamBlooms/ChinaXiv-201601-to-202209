# 一种环状编码标记点的设计及解码算法\*

金滔，董秀成

(西华大学 信号与信息处理重点实验室，成都 610039)

摘要：针对近景摄影测量中对编码标志点的精确定位和准确识别的要求，提出一种环状编码标记点的设计和识别算法。在传统环状编码标记点的基础上添加3个定位符，用于确定标志点的精确位置和增加标志点的数量。解码时先检测定位符坐标及其在标志点中的位置，然后对编码标志点进行透视变换以实现图像校正的目的，最后用提出的基于圆环扫描的方法进行解码。实验结果表明，该算法对任意旋转角度下的编码标志点均能有较好的检测识别效果；当摄像机与标记平面的夹角小于 $6 5 ^ { \circ }$ 时，其识别准确率可达 $9 9 . 3 \%$ ；在复杂背景情况下的平均识别准确率为 $9 7 . 4 \%$ ，误识别率为 $1 . 2 5 \%$ ，识别平均速率为 $2 . 1 5 ~ \mathrm { s } /$ 幅。

关键词：编码标记点设计；编码标记点识别；定位符；透视变换；解码 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2017.11.0771

# Designing and decoding algorithm of circular coded target

Jin Tao, Dong Xioucheng (Signal &Information Processing Laboratory,Xihua University,Chengdu 61oo39,China)

Abstract:Ontherequests of coded targets in close range photogrammetry for precision location and accurate recognition, proposedadesigning anddecoding algorithmofcircularcodedtarget.This paperadded three locatorsonthebasis oftraditional circularcodedtargettoachieveprecisionpositionandincreasethenumberoftargets.Firstly,thealgorithmdetectedthelocator coordinates andtheirpositions inthetargets.Then,theperspectivetransformationofthecodedtarget wasused toachieve image distortioncorrction.Finally,used the method based on the ring scan toachieve thedecoding of the circularcoded target. Experimental results showthatthealgorithmin thispapercan have good detectionandrecognitionresults forall theoded targets which rotate any angle; when the angle between the camera and the marking plane is less than $6 5 ^ { \circ }$ ，the recognition accuracy rate can reach $9 9 . 4 \%$ ；the average recognition accuracy rate is $9 7 . 4 \%$ ,false recognition rate is $1 . 2 5 \%$ ,recognition rate is 2.15 seconds under the complex background.

Key words: coded target design; coded target recognition; locator; perspective transformation; decode

# 0 引言

在计算机视觉领域中，为降低相机标定和三维数据拼接的复杂程度，广泛使用编码标记点作为特征点。编码标记点的种类有点形编码标记点、方形编码标记点、分布式编码标记点、颜色信息编码标记点[1]、可纠错标记点[2]和环状编码标记点[3]。但在近景摄影测量中使用常见的是环状编码标记点，因为其设计简单，环境光照变化、图像采集时标志点畸变对最终的解码结果影响较小。

目前，国内外很多学者对环状编码标记点的检测和识别做了大量研究工作并取得相应的成果。梁晋等人将编码标记点用于多相机的全局标定中，光照和拍摄角度对解码结果的影响较大[4]。解则晓等人根据环状编码标记点的仿射变换不变性提出的等分椭圆内切圆法，实现环状编码标记点的识别[5]。宋丽梅等提出 ALPC（AffineLOGPolar Coordinate）变换将环形码映射成平行直线，实现环状编码标记点的。但是该算法运算量大，识别效率低[。Hu等根据提取得到的成像椭圆参数，反复采样标记带，最终实现解码。但是该算法对编码标志点成像要求较高，识别准确度不高[7]。

为了实现摄影测量中标记点精确定位和提高编码标记点检测识别的鲁棒性，本文提出一种编码标志点的设计和基于圆环扫描的解码方法。在传统编码标记点的基础上添加3个定位符，用于确定标志点的位置及增加标志点的数量。首先，依据定位符的特点检测定位符位置。然后，根据定位符的位置对标志点图像进行透视变换，实现对图像的校正。最后，通过对编码圆环进行扫描取点解码。实验结果表明，编码标志点的设计及解码算法对标志点图像的旋转和投影角度的影响较小。为近景摄影测量中提供一种编码标志点和检测算法。

# 1 环状编码标记点的设计

编码标记点的设计应具有互异性、尺寸适当、易于检测与定位和编码标志点数目多的特点[8]。其中，SchneiderCT和Sinnreich设计的环状编码标记点[3]，如图1所示，其主要组成部分为中心圆和外部均等12分的环状编码点构成，其中中心圆主要用于标记点定位，环状编码点主要用于标记点识别，实现快速、准确的同名标记点匹配。

![](images/497791118ce00fe90632b9d9147d04ca75f507972dd68f5539aff0b0ec91b54b.jpg)  
图1传统环状编码标记点

环状编码标记点中每个编码点在满足编码条件下可为黑或白，以二进制0和1分别代表白色和黑色，以任意一位编码作为起始位顺时针读取产生1个码值，12位共可以读取12个二进制数，选取这12个二进制数对应的十进制数中的最小值作为该编码环的编码值。环状编码标记点的外圆环可以根据实际的进行不同数目的等分，比如10、12、15等分，不同的等分情况对应的标志点数和二进制数如表1所示。从表1中可以得出对于外圆环进行12等分而言，由于在解码的后期对12位二进制数进行循环移位的，其实际能表示的标志点个数为351个，与12位二进制数表示的个数4096相差甚远，编码标志点的数量大大减少。

表1编码数、标志点数与二进制数关系表  

<html><body><table><tr><td>编码点数</td><td>标志点数</td><td>二进制数</td></tr><tr><td>10</td><td>107</td><td>1024</td></tr><tr><td>12</td><td>351</td><td>4096</td></tr><tr><td>15</td><td>2191</td><td>32767</td></tr><tr><td>18</td><td>14601</td><td>262144</td></tr><tr><td>20</td><td>52487</td><td>1048576</td></tr></table></body></html>

本文在传统的环形编码标记点基础之上重新设计编码标志点，如图2所示，即在现在编码标志点的基础之上添加3个相同的用于确定标志点位置的定位符以及增加标志点的数量。其中，编码标志点的定位符在水平和垂直方向上黑白之间的像素点满足黑：白：黑：白：黑 $^ { - 1 }$ ：1：3：1：1的关系。而且在设计时左下角和右上角这两个定位符的中心点是编码标志点中心圆的圆心。三个定位符用于确定编码标志点外圆环的相对位置。中心圆的直径 $d = 1 0 m m$ ，圆环内侧到中心圆圆心的距离$r _ { 1 } = 2 5 m m$ ，圆环内侧到中心圆圆心的距离 $r _ { 2 } = 3 0 m m$ ，定位符的长和宽均为 $c = 1 4 m m$ ，即在水平或垂直方向上黑色的宽度为 $a = 2 m m$ ，水平和垂直方向上两个定位符之间的距离均为$b = 6 4 m m$ 。因而各个参数满足 $r _ { 1 } = 2 . 5 d$ 、 $r _ { 2 } = 3 d$ 、 $d = 5 a$ ，在实际的使用中可以根据需要放大或缩小整个编码标志点的面积，但不能改变各个参数之间的相应关系。

![](images/0e8fb0f97f62cd9fb9eed0df96add34f294898802bc30bb9f36b8b1979a2edf5.jpg)  
图2添加定位符的编码标记点  
图3编码标记点解码流程

重新设计之后的编码标志点具有如下两个优点。一是在解码的后期不需要对解码得到的二进制进行循环移位，因而在外圆环为相同等分时，其表示的不同编码标志点数量将大大增加。二是在解码过程中确定编码标志点中心时检测定位符算法比检测圆或椭圆算法简单且效率更高。

# 2 环状编码标记点的检测和识别

# 2.1编码标记点检测流程

环状编码标记点检测流程如图3所示。首先，对CCD 摄像机采集得到的原始图像进行预处理，包括图像的灰度化和二值化，图像预处理的目的在于减少彩色图像存储的信息量，为之后的算法设计减轻负担，提高整个解码的效率。其次，根据定位符的特点检测定位符的中心位置并确定其具体的位置（左上点、右上点或左下点）。然后，根据检测出的3个定位符计算出用于透视变换的四边形第四个点的位置，依据四边形的四个点对整个图像进行透视变换，即对倾斜、旋转或畸变的原始图像进行图像校正。最后对校正后的图像进行解码。

原始图像 灰度化 定位符 透视变换 解码（图像采集） 二值化 检测 (校正图像） (结果）

# 2.2图像预处理

图像预处理包括图像灰度化和二值化。图像的灰度化9是彩色图像（RGB 模型）中对分别对R、G、B三个分量的量化过程，即三个通道转换为一个通道的过程，取值范围为 $0 { \sim } 2 5 5$ 。灰度化的方法有分量法（式1）、最大值法（式2）、平均值法（式3）和加权平均法（式4）。其中加权平均法是对R、G、B 用不同的权值加权求平均，对不同的分量使用不同的权值的可以得到适合于后期图像处理的灰度图像，因而本文选取加权平均法。

$$
f ( i , j ) = R ( i , j ) o r G ( i , j ) o r B ( i , j )
$$

$$
f ( i , j ) = \operatorname* { m a x } ( R ( i , j ) , G ( i , j ) , B ( i , j ) )
$$

$$
f ( i , j ) = ( R ( i , j ) + G ( i , j ) + B ( i , j ) ) / 3
$$

$$
f ( i , j ) = 0 . 3 0 R ( i , j ) + 0 . 5 9 G ( i , j ) + 0 . 1 1 B ( i , j )
$$

图像的二值化是对灰度图像信息的再次浓缩，使之变为只有0或255这两个灰度值的图像。二值化的方法有全局二值化和局部二值化，由于编码标志点主要是由黑白两种像素构成的，其灰度图像的直方图会存在两个波峰，而且两个波峰之间的间距会很大，因而采用全局二值化较为合适。全局二值化中主要确定二值化的分割阈值，其中Otsu 算法[10](又称大律法或最大类间方差法）一种自适应的阈值确定的方法，通过搜索计算类间方差最大值，得到最优阈值，从而将背景和目标分割出来，且鲁棒性较好。Otsu算法中类间方差由式（8）决定，采用遍历的方法得到使类间方差最大的阈值，其中图像的大小为 $m \times n$ ，$n _ { 1 }$ 为灰度值小于阈值的像素个数， $w _ { 1 }$ 为其对应的比例， $n _ { 2 }$ 为灰度值小于阈值的像素个数， $w _ { 2 }$ 为其对应的比例，且 $n _ { 1 } , n _ { 2 }$ 、$w _ { 1 }$ 、 $w _ { 2 }$ 满足式（6）的关系。

$$
\omega _ { 1 } = n _ { 1 } / ( m \times n ) , \omega _ { 2 } = n _ { 2 } / ( m \times n )
$$

$$
n _ { 1 } + n _ { 2 } = m \times n , \omega _ { 1 } + \omega _ { 2 } = 1
$$

$$
\mu = \mu _ { 1 } \times \omega _ { 1 } + \mu _ { 2 } \times \omega _ { 2 }
$$

$$
\mathrm { g } = \omega _ { 1 } \times ( \mu - \mu _ { 1 } ) ^ { 2 } + \omega _ { 2 } \times ( \mu - \mu _ { 2 } ) ^ { 2 }
$$

# 2.3 定位符检测识别

定位的检测依据定位符的特点，定位符在其水平和垂直方向上黑白像素点数量满足黑：白：黑：白：黑 $^ { - 1 }$ :1:3:1:1。首先，定义一个元素个数为5的一维数组s[5]并全部初始化为0。从二值图像中从左往右依此计算像素灰度值连续为0或255（即黑或白）的像素个数并依次保存在数组s中，当数组s中5 个元素全被赋值，此时需要判断s[0]：s[1]：s[2]：s[3]：s[4]是否满足1：1：3：1：1（在实际中因图像的畸变，允许最大误差为 $50 \%$ ），如果条件满足则此处可能存在定位符，然后初步计算出定位符在水平方向上中心点的横坐标（纵坐标即为当前的行数，已知），根据定位符初步的坐标检测其在垂直方向是否满足定位符的条件，如果满足计算出在垂直方向上定位符的中心坐标（即Y坐标）。然后用刚计算得到的坐标值来判断在水平方向上是否同样符合定位符的特点，如符合则计算出定位符在水平方向上的中心坐标（即X坐标）。定位符检测的流程图如图4所示，用同样的方法检测其余定位符的中心坐标。

在得到3个定位符的中心坐标之后，需要判别定位符在编码标志点中的具体位置，即检测出定位符属于图5中的A 点（左下定位符）、B点（左上定位符）或C点（右上定位符）。定位符位置检测方法分为两步：第一步是检测出左上定位符（即B 点),先计算定位符之间的距离 $l _ { A B } \setminus l _ { B C } \setminus l _ { A C }$ ，再由 $l _ { A B } < l _ { A C }$ 、$l _ { B C } < l _ { A C }$ 即可求得左上定位符(B点);第二步计算 $\overrightarrow { B A } \times \overrightarrow { B C }$ ，如果 $\overrightarrow { B A } \times \overrightarrow { B C } > 0$ ，则说明此时A点即为左下定位符，C 点即为左上定位符，如果 $\overrightarrow { B A } \times \overrightarrow { B C } < 0$ ，则说明此时C点即为左下定位符，A点即为左上定位符，根据具体情况做相应调整。

![](images/572c35a7b8fff36c79604b342adbb026fec23d90f07340ac9f0d7c2052746c10.jpg)  
图4定位符检测流程

![](images/4533d5f3d2e53954707a47310bbb97d8937dc466dcaffbeaa63c1c65ea9f5d82.jpg)  
图5定位符位置关系图

# 2.4标志点图像透视变换

检测到3个定位符的中心坐标并确定其在编码标志点的具体位置后，接下来就可进行图像的透视变换。透视变换[14]指利用透视中心、像点、目标点三点共线的条件，按透视旋转定律使承影面(透视面)绕迹线(透视轴)旋转某一角度，破坏原有的投影光线束，仍能保持承影面上投影几何图形不变的变换，即将原始图像投影到新的平面，其通用的变换公式为式（9）。

$$
{ \Big [ } x ^ { \prime } , y ^ { \prime } , w ^ { \prime } { \Big ] } { = } { \Big [ } u , \nu , w { \Big ] } { \left[ \begin{array} { l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { a _ { 1 3 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { a _ { 2 3 } } \\ { a _ { 3 1 } } & { a _ { 3 2 } } & { a _ { 3 3 } } \end{array} \right] }
$$

其中 $\left( u , \nu \right)$ 是原始图像的坐标，透视变换后的坐标为 $( x , y )$ ，且$x = x ^ { \prime } / w ^ { \prime } , y = y ^ { \prime } / w ^ { \prime }$ 。对式（9）进行矩阵运算可得：

$$
\left\{ \begin{array} { c } { \displaystyle x = \frac { x ^ { \prime } } { w ^ { \prime } } = \frac { a _ { 1 1 } u + a _ { 2 1 } \nu + a _ { 3 1 } } { a _ { 1 3 } u + a _ { 2 3 } \nu + a _ { 3 3 } } } \\ { \displaystyle y = \frac { y ^ { \prime } } { w ^ { \prime } } = \frac { a _ { 1 2 } u + a _ { 2 2 } \nu + a _ { 3 2 } } { a _ { 1 3 } u + a _ { 2 3 } \nu + a _ { 3 3 } } } \end{array} \right.
$$

下面以原图像中正方形到变换图像中为四边形的透视变换来说明变换矩阵各参数的求解，变换的4组点选 $( 0 , 0 ) \ $ $( \boldsymbol { x } _ { 0 } , \boldsymbol { y } _ { 0 } )$ 、 $( 1 , 0 )  ( x _ { 1 } , y _ { 1 } )$ 、 $( 1 , 1 )  ( x _ { 2 } , y _ { 2 } )$ 、 $( 0 , 1 )  ( x _ { 3 } , y _ { 3 } )$ 根据透视变换式（10）可得：

$$
\left\{ \begin{array} { l l } { x _ { 0 } = a _ { 3 1 } } \\ { x _ { 1 } = a _ { 1 1 } + a _ { 3 1 } - a _ { 1 3 } x _ { 1 } } \\ { x _ { 2 } = a _ { 1 1 } + a _ { 2 1 } + a _ { 3 1 } - a _ { 1 3 } x _ { 2 } - a _ { 2 3 } x _ { 2 } } \\ { x _ { 3 } = a _ { 2 1 } + a _ { 3 1 } - a _ { 2 3 } x _ { 3 } } \\ { y _ { 0 } = a _ { 3 2 } } \\ { y _ { 1 } = a _ { 1 2 } + a _ { 3 2 } - a _ { 1 3 } y _ { 1 } } \\ { y _ { 2 } = a _ { 1 2 } + a _ { 2 2 } + a _ { 3 2 } - a _ { 1 3 } y _ { 2 } - a _ { 2 3 } y _ { 2 } } \\ { y _ { 3 } = a _ { 2 2 } + a _ { 3 2 } - a _ { 2 3 } y _ { 3 } } \end{array} \right.
$$

为求解变换矩阵的参数，定义如下中间变量：

$$
\left\{ \begin{array} { l l } { \Delta x _ { 1 } = x _ { 1 } - x _ { 2 } } \\ { \Delta x _ { 2 } = x _ { 3 } - x _ { 2 } } \\ { \Delta x _ { 3 } = x _ { 0 } - x _ { 1 } + x _ { 2 } - x _ { 3 } } \\ { \Delta y _ { 1 } = y _ { 1 } - y _ { 2 } } \\ { \Delta y _ { 2 } = y _ { 3 } - y _ { 2 } } \\ { \Delta y _ { 3 } = y _ { 0 } - y _ { 1 } + y _ { 2 } - y _ { 3 } } \end{array} \right.
$$

当 $\Delta x _ { 3 } , \Delta y _ { 3 }$ 均为0时可得透视变换矩阵 $T$ (式13)。

$$
T = { \left[ \begin{array} { l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { a _ { 1 3 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { a _ { 2 3 } } \\ { a _ { 3 1 } } & { a _ { 3 2 } } & { a _ { 3 3 } } \end{array} \right] } = { \left[ \begin{array} { l l l } { x _ { 1 } - x _ { 0 } } & { y _ { 1 } - y _ { 0 } } & { 0 } \\ { x _ { 2 } - x _ { 1 } } & { y _ { 2 } - y _ { 1 } } & { 0 } \\ { x _ { 0 } } & { y _ { 0 } } & { 1 } \end{array} \right] }
$$

当 $\Delta x _ { 3 } , \Delta y _ { 3 }$ 不为0时可得透视变换矩阵 $T$ (式14)。

$$
T = \left[ { \begin{array} { c c c } { x _ { 1 } - x _ { 0 } + a _ { 1 2 } x _ { 1 } } & { y _ { 1 } - y _ { 0 } + a _ { 1 3 } y _ { 1 } } & { a } \\ { x _ { 3 } - x _ { 0 } + a _ { 1 2 } x _ { 2 } } & { y _ { 3 } - y _ { 0 } + a _ { 2 3 } y _ { 3 } } & { b } \\ { x _ { 0 } } & { y _ { 0 } } & { 1 } \end{array} } \right]
$$

$$
a = \frac { \Delta x _ { 3 } \Delta y _ { 2 } - \Delta x _ { 2 } \Delta y _ { 3 } } { \Delta x _ { 1 } \Delta y _ { 2 } - \Delta x _ { 2 } \Delta y _ { 1 } } \ , b = \frac { \Delta x _ { 1 } \Delta y _ { 3 } - \Delta x _ { 3 } \Delta y _ { 1 } } { \Delta x _ { 1 } \Delta y _ { 2 } - \Delta x _ { 2 } \Delta y _ { 1 } } \circ
$$

所以，在已知透视变换在变换前对应图像的4个点和图像变换后所对应的4个点，可以解出透视变换矩阵，从而实现对整个图像进行透视变换，完成对图像的畸变校正。由于透视变换需要原始图像和变换后图像中4个相对应的点方可求出变换矩阵，而编码标志点的定位符只有3个，因而在原图像中第四个点是通过计算而得的，在式（15）中点(bottomRightX，bottomRightY）为第四个计算的点坐标，(topLeftX,topLeftY）为左上定位符坐标，(topRightX，topRightY）为右上定位符坐标，（bottomLeftX,bottomLeftY)为左下定位符坐标。而变换后对应的4个点分别为（start,start）、 $( s t a r t + a , s t a r t )$ ）、(start,start +a)、（204号 $( s t a r t + a , s t a r t + a )$ ，其中 $a$ 为定位符 AB 和 BC 之间距离较小者，start则为定位符宽度的0.65倍，start的取值需保证左上和右上两个定位符在图像的显示区域内。根据透视变换前后的4个点可以求解变换矩阵，然后再将图像进行透视变换可得校正之后的图像。

$$
\begin{array} { r } { \int b o t t o m R i g h t X = b o t t o m L e f t X + t o p R i g h t X - t o p L e f t X } \\ { \ b o t t o m R i g h t Y = b o t t o m L e f t Y + t o p R i g h t Y - t o p L e f t Y } \end{array}
$$

为检验透视变换对图像校正的效果，选取一组图片进行检测实验。图6左图为原始图像，图6中图为是二值化之后的图像，图6右图为是透视变换之后得到的校正图像。

![](images/6e43cc030afd811569f1f27ef23ef6e041575040cba3c63c8de18dbef96ac25b.jpg)  
图6透视变换效果图

# 2.5 编码标志点解码

在透视变换后得到校正图像便可实现对编码标记点的解码。本文提出的基于圆环扫描的解码方法，具体步骤如下：

（1）根据左下定位符（A点）和右上定位符（C点）计算中心圆圆心大致坐标，其大致坐标在这两个定位符的中心位置；

（2）截取中心圆区域，在该区域中使用灰度重心法计算出中心圆圆心的坐标(realCenter $X$ ,realCenterY)，并计算出中心圆的直径 $d$ ：

（3）计算圆环中心到中心圆圆心的距离 $r$ ，由第1节可知，圆环内侧 $r _ { 1 }$ 和外侧 $r _ { 2 }$ 与中心圆直径的关系为 $r _ { 1 } = 2 . 5 d$ 、$r _ { 2 } = 3 d$ ，因而圆环中心到中心圆圆心的距离 $r = 2 . 7 5 d$ ：

（4)定义元素个数为60 的数组record[60]并初始化全为0，该数组用于保存圆周上点的像素值；利用圆的参数方程（式16）从圆环的正上方开始顺时针方向每隔 $6 ^ { \circ }$ （圆周为 $3 6 0 ^ { \circ }$ ，等分为60份）对校正后的二值图像进行取点并判断该点的灰度值是0（黑）还是255（白），是0则对应索引的数组record[index]为1，否者为0。选取的60个点如图7所示，其中红色的点代表算法中取的点；

$$
\left\{ \begin{array} { l } { x = r e a l C e n t e r X + r \cdot \cos \theta } \\ { y = r e a l C e n t e r Y + r \cdot \sin \theta } \end{array} \right.
$$

![](images/fea79db517e41468a622f8f6b5c6af62277b625a5bc6a78ba714c96459d1527b.jpg)  
图7圆环扫描示意图

（5）编码标志点圆环为12等分，在圆环上取60个点，因而每个小环段对应5个点，对数组record[60]依次取5个点并计算这5个点的值，如果其值大于3，则表明该小环段所对应的编码值为1，反之则为0，将该数值保存在解码结果数组rlt[12]中；图7最终解码结果的二进制为101100110100；

（6）二进制解码结果转为十进制结果result，转换关系如式（17）。

$$
r e s u l t = \sum _ { i = 0 } ^ { 1 1 } 2 ^ { 1 1 - i } \cdot r l t [ i ]
$$

# 3 实验结果及分析

为验证本文编码标记点设计的合理性和解码算法的有效性，选取不同的标记点，并对标记点以其中心圆为旋转中心旋转不同的角度（ $0 { \sim } 3 6 0 ^ { \circ }$ ，每次增加约 $4 5 ^ { \circ }$ ），且相机的光轴垂直于编码标记点所在的平面进行检测识别实验，检测结果如图所示。在图中，第1行第1幅图中的编码标志点为标准位置安放，即旋转角度为 $0 ^ { \circ }$ ，从第1幅开始旋转角度依次增加 $4 5 ^ { \circ }$ ，直至第9幅旋转角度为 $3 6 0 ^ { \circ }$ ，即回到标准位置。

![](images/06556363f67d52725e287f8c10aaa2a714c2450316a162cca4e9883bc70188b9.jpg)  
图8不同旋转角度标志点解码结果

图9是对编码标记点进行畸变校正后用于解码的图，从图9 中可得对于不同旋转角度的编码标志点，通过透视变换后均能使其变换到标志点标准位置。透视变换对编码标志点的畸变校正很准确，适用于后期的解码处理。

![](images/ac609ec84ec446b110c851ff6fb3701f5507a9bbfa8b306223e8936f9ea79626.jpg)  
图9畸变校正的编码标志点图

为验证本文对编码标记点解码算法的鲁棒性，采用不同的倾斜角度采集编码标志点图像进行实验。图像采集所使用的相机是佳能相机CanonEOS550D，采集图像的分辨率为 $3 9 6 8 \times$ 2976。对含有十二个编码标记点的平面从倾斜角度为 $0 \sim 8 0 ^ { \circ }$ 进行图像采集，总共采集80幅图像。使用本文提供的解码算法对采集的图像进行解码，算法运行环境为计算机CPUIntel(R)Core(TM)i3-41603.5GHz,内存8GB,Windows 64bit专业版，开发环境为MicrosoftVisualStudio 2010中MFC应用程序。对解码结果进行统计，不同拍摄角度 $\theta$ 和解码结果正确率 $p$ 之间的关系详见图10。

![](images/8c15e82f6c9d3a2bc73d0b95516f7eaddcb13672f60ee5bf4f81bca880820241.jpg)  
图10不同角度下解码正确率

从图10 中可知当其拍摄角度小于 $6 5 ^ { \circ }$ 时，综合统计其解码准确率为 $9 9 . 3 \%$ ；角度为 $7 0 ^ { \circ }$ 、 $7 5 ^ { \circ }$ 、 $8 0 ^ { \circ }$ 时相应的准确率为 $91 . 6 \%$ 、 $8 3 . 3 \%$ 、 $6 6 . 6 \%$ ，即在大倾角情况下，识别效果还是比较理想。其中拍摄角度为 ${ 6 0 } ^ { \circ }$ 、 $6 5 ^ { \circ }$ 、 $7 0 ^ { \circ }$ 、 $7 5 ^ { \circ }$ 和 $8 0 ^ { \circ }$ 时解码结果如图 $1 1 \sim 1 5$ 所示。

![](images/5c862d6f064e8933df367bdec249d92b2f3fc5b7510c3fde878eef923f2ebf04.jpg)  
图11倾角为 $6 0 ^ { \circ }$ 识别结果

![](images/9917fbdd1506d0818977ea03c51b852dfb33135140fda08f37e128d132b486bd.jpg)  
图12倾角为 $6 5 ^ { \circ }$ 识别结果

![](images/dfd578f23aed1569a6a574291273679dfe60d151673ca5299cc6697ffb04cc11.jpg)  
图13倾角为 $7 0 ^ { \circ }$ 识别结果

![](images/b28d8c31eefe3f47c6a22b74dd52e4bbf2c452f04427d925576d3d7bc2fd7275.jpg)  
图14倾角为 $7 5 ^ { \circ }$ 识别结果

![](images/fb6adb5451676d152bce4ef24c481376c97a4a8e8daea0b3ad8007f9dfe007b1.jpg)  
图15倾角为 $8 0 ^ { \circ }$ 识别结果

为验证本文改进的编码标志点及其解码算法在复杂的背景下的解码效果。将编码标记点张贴在实验室SCARA机器人和rethinkrobotics七轴机器人的机身上面，分别拍摄10幅图像并对其解码，部分实验结果如图16、17所示，说明本文算法在复杂的环境下表现出良好的识别效果。

将本文改进的编码标志点及其解码算法与其他文献的解码算法从解码时间、解码结果的准确率和误解码率三个方面进行比较，结果如表2所示。本文提出的算法检测准确率为 $9 7 . 4 \%$ 误识别率为 $1 . 2 5 \%$ ，识别平均速率为2.15秒/幅。对比于其他文献的算法，本文算法的综合性能最优。

![](images/37f91335a8c297b77986065f9a6e0497f031e4e6a9ccddbd663f7ff8a52d5ab7.jpg)  
图16SCARA机器人上解码结果

![](images/a0f56ebddbbe215afac336f589f3022674481a0951b1c5a91aca16665a2ec81e.jpg)  
图17rethink robotics 机器人上解码结果

表2标记点解码性能对比表  

<html><body><table><tr><td>算法</td><td>解码速度(s/幅)</td><td>准确率(%)</td><td>错误率(%)</td></tr><tr><td>本文</td><td>2.15</td><td>97.4</td><td>1.25</td></tr><tr><td>文献[5]</td><td>2.83</td><td>97.1</td><td>0.86</td></tr><tr><td>文献[11]</td><td>2.65</td><td>95.2</td><td>3.095</td></tr><tr><td>文献[12]</td><td>4.36</td><td>90.3</td><td>1.89</td></tr></table></body></html>

# 4 结束语

视觉测量中，对编码标记点的检测识别要求具有较高的稳定性和精确性。本文设计出在传统编码标记点的基础上添加定位符，用于确定标志点的精确位置和增加标志点的数量，为近景摄影测量提供一种新的编码标记点及其解码算法。实验结果表明，本文算法对编码标记点检测和识别具有一定的鲁棒性。但是，本文算法针对倾角过大（ $8 0 ^ { \circ }$ 及以上），对定位符的成像较模糊时可能识别不到，仍然有待改进。

# 参考文献：

[1]Moriyama T,Kochi N,Yamada M,et al.Automation target identification with the color-coded-target [C]// Proc of International Archives of Photogrammetry and Remote Sensing.20o8:39-44.   
[2] 杨剑，韩建栋，秦品乐．视觉测量中可纠错的编码点识别及提取[J] 光学精密工程,2012,20(10):2293-2299.   
[3]Schneider C T, Sinnreic HK. Optical 3D measurement systems for quality control in industry [C]/ Proc of International Archives of Photogrammetry and Remote Sensing,1993:56-59.   
[4]胡浩，梁晋，唐正宗，等．大视场多像机视频测量系统的全局标定[J]. 光学精密工程,2012,20(02):369-378.   
[5]宋丽梅，陈昌曼，陈卓，等．环状编码标记点的检测与识别[J]．光学 精密工程,2013,21(12):3239-3247.   
[6]Hu Hao,Liang Jin, Xiao Zhen Zhong,et al.A four-camera videogrammetric system for 3-D motion measurement of deformable object [J].Journal of Optoelectronics Laser,2014,25(5): 937-946.   
[7]倪章松，成垒，顾艺，等.视觉测量中环形编码标志点的精确识别算法 研究[J].新技术新工艺,2016,(12):21-25.   
[8]宋凤菲．彩色图像灰度化及其效果的客观评价方法研究[D].泉州：华 侨大学,2014.   
[9]Hou Jiali; Li Baokui.An Improved Algorithm for Horizon Detection Based on OSTU[C]// Proc of the 7th International Conference on Intelligent Human-Machine Systems and Cybernetics.2015:414-417.   
[10]程增木，王悦宏，程琳琳．基于逆透视变换的道路检测技术[J].电子 科学技术,2016,03(02):113-116.   
[11]周玲，张丽艳，郑建冬，等．近景摄影测量中标记点的自动检测[J] 应用科学学报,2007,(03):288-294.   
[12]Doring T,Meysel F,Reulke R.Autonomous calibration of moving line scanners with coded photogrammetric targets recognition $[ \mathrm { C } ] / \AA$ Proc of ISPRS Commission V Symposium.2006: 84-89.