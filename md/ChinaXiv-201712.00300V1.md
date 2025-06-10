# 连续变化钢筋尺寸快速翻样方法

潘顺琪1,2 李仲勤1,2

(1.兰州交通大学测绘与地理信息学院,兰州 730070；2.甘肃省地理国情监测工程实验室,兰州 730070)

【摘要】讨论了目前连续变化钢筋尺寸翻样的几种方法，介绍了利用Autocad 进行翻样的优势，并用lisp语言实现翻样的自动化,最后结合某桥墩实例详细的描述了利用lisp语言实现连续变化钢筋尺寸快速翻样的一般步骤。

【关键词】连续变化钢筋；Autocad；lisp语言；参数化绘图；自动化翻样标注【中图分类号】TP399 【文献标识码】A 【文章编号】1674-7461(2017)04-0098-04【DOI】10.16670/j.cnki.cn11-5823/tu.2017.04.18

在道路桥梁施工中，施工设计图给出不同结构的钢筋下料单。施工现场的工人根据钢筋下料单中给出的各种类型的钢筋的尺寸、形状、数量制作施工所需要的钢筋。但是，施工设计图中某些类型钢筋的形状相似，而具体的尺寸是随着结构的外形变换而逐渐变化的。并且施工设计图中只给出该类型钢筋尺寸变化范围，具体尺寸需要结合结构形状进行计算。在实际施工过程中,计算具体尺寸的方法有以下三种：

(1)经验值法。经验值法是施工人员根据以往的施工经验,使用经验参数、经验公式，代入结构尺寸数据计算得到所需要的钢筋尺寸数据。(2)放大样法。放大样法是将结构按照某比例放出大样，再用钢尺实际量出所需要的不同尺寸。(3）Autocad 翻样法。Autocad 翻样法是将结构在Autocad中绘制出，再根据钢筋布局参数翻样出钢筋，然后借助Autocad标注的功能得到需要的尺寸数据。

通过比较三种方法可以发现，第一种方法的计算量大、耗时长，需要施工人员有丰富的施工经验。第二种绘制方法误差较大。第三种方法相对简单、精确。但是这种方法首先要对结构进行绘图，然后进行后续的翻样、标注工作。但是相似结构的重复绘制，大量图元的重复标注和数据抄录是耗时费

力的。

Autocad不但绘图功能完善、用户界面良好，而且用户可进行二次开发[1]。利用Autocad自带的lisp 编程软件,用户可以构建模型[2],调用模型,输入参数实现绘图、翻样、标注、结果输出的自动化，从而大大减轻施工人员的工作量，提高数据精度。

# 1快速翻样标注的实现

# 1.1快速翻样标注的一般流程

该功能实现的一般流程如图1所示，主要包括：模型选择、参数输入、绘制结构图、翻样、标注、结果输出。

![](images/5b082f25fef4aa796c4bb6c2c8bba3d5ac8ca555b870f31e3cf2b427a909322c.jpg)  
图1功能流程

用户首先根据自己的翻样需求选择相对应的模型，如：桥墩、桥台、齿板等。系统会根据用户的选择给出与所选模型对应的参数输入窗口[3],并在窗口上显示预先制作好的，用以提示用户各参数所代表的实际含义的图片，以方便用户从施工图上获取参数的实际值。

在用户输入各参数后，点击确定按钮，计算机就可自动绘制结构图[4],并进行翻样、标注和结果的输出。

# 1.2模型绘制及其参数输入

该功能模块主要有两个方面的工作：(1)幻灯片的制作；(2)绘图翻样参数的确定。

不同结构所需要的绘图、翻样参数由具体情况实际确定。在确定所有参数后，给出用户输人窗口，并配以幻灯片说明，让各参数的含义更加明确。对话框采用DCL设计，下面为某桥墩的参数输入对话框设计代码：

//对话框设计

111150000111 "le;p $\mathbf { \sigma } = \mathbf { \sigma }$ 驂麗模醬灿學壁 携携；，  
: boxed_column $\mathrm { \{ \ l a b e l = \mathrm { \Omega } } $ “模型选择”；  
//添加图形控件  
:image $\left\{ \begin{array} { c } { \begin{array} { r l } \end{array} } \\ { \begin{array} { r l } \end{array} } \end{array} \right.$ width $= 1 5$ ；height $= 6$ ${ \mathrm { k e y ~ } } = \mathrm { ~ } ^ { \ast } \mathrm { i m g } ^ { \prime \prime }$ $= - 2$ ; $\Bigg \}$   
//添加模型列表  
: popup_list {label $\mathbf { \sigma } = \mathbf { \sigma }$ “模型样式”；edit_width $\mathbf { \Sigma } = \mathbf { \Sigma }$ $1 0 { \cdot } { \mathrm { J i s t } } = \cdot$ ‘带弧桥墩 $\backslash \mathrm { n }$ 斜线桥墩 $\backslash \mathrm { n }$ 齿板 $\backslash \mathrm { n }$ 箱梁中腹板 $\backslash \mathrm { n }$ 箱梁边腹板”；value $\scriptstyle = 0$ ： $\mathrm { k e y = \ " { \bf p o p } ^ { \prime \prime } ; }$ $\{ \} \{$ （204号: boxed_column $\mathrm { \{ \ l a b e l = \mathrm { \Omega } } $ “绘图参数”；  
//添加用户输入控件  
冏1號 $\begin{array} { r l r } & { \underset { \mathrm { ( 0 , : k , e y ~ = ^ { 4 } t _ { 1 } ~ - b o x ~ \{ ~ l a b e l ~ = ~ ^ { 4 } { \& } a ~ ( ~ c m ~ ) ~ : } ~ \mathrm { ~ e d i t } _ { - } { \mathrm { ~ w i d t h } } ~ = ~ } } { \overset { \nabla } { \operatorname* { d i t } } }  & \\ & { \underset { \mathrm { ( 0 , : k , e y ~ = ~ ^ { 4 } a ^ { \ast } , ~ } \mathrm { { b o x ~ \{ ~ l a b e l ~ = ~ ^ { 4 } { \& } ~ \delta \mathrm { ~ g } } _ { \mathrm { { a } ~ ( ~ c m ~ ) ~ : } ~ } } , ~ \mathrm { e d i t } _ { - } { \mathrm { { \Theta } } } _ { \mathrm { { e } } } { \mathrm { { d } } } \mathrm { { t h } } ~ = ~ } } \\ & { \underset { \mathrm { ( 0 , : k , e y ~ = ~ ^ { 4 } b ^ { \ast } , ~ } \mathrm { { b o x ~ \{ ~ l a b e l ~ = ~ ^ { 4 } { \& } ~ \delta \mathrm { { \& } ~ ( ~ c m ~ ) ~ : } ~ } ~ } } } { \overset { \nabla } { \operatorname { d i t } } } ; ~ \mathrm { e d i t } _ { - } { \mathrm { { \Theta } } } { \mathrm { w i d t h } } ~ = ~   \\ & { } & \\ & { \quad } & { : ~ \mathrm { e d i t } _ { - } { \mathrm { b o x ~ \{ ~ l a b e l ~ = ~ ^ { \ast } { \& } c ~ ( ~ c m ~ ) ~ : } ~ } } ^ { \prime } ; ~ \mathrm { e d i t } _ { - } { \mathrm { { \Theta } } } { \mathrm { w i d t h } } ~ = ~  \end{array}$ 1  
10; $\mathrm { k e y } = \mathrm { ^ { * } c ^ { \prime \prime } }$ ；}  
$\mathrm { e d i t \_ b o x \{ \ l a b e l = \mathrm { ^ { \cdots } \& r ( \ c m ) } } $ :”；edit_width $= 1 0$ $\mathrm { k e y } = { } ^ { \mathrm { a } } \mathrm { r } ^ { \mathrm { { , } } } \ ; \ \nmid \}$   
: boxed_column $\mathrm { \left\{ l a b e l = \right. } $ “翻样参数”；  
${ \mathrm { e d i t } } \_ { \mathrm { b o x } } \{ \mathrm { l a b e l }  = \cdots$ 间隔 $\operatorname { \& d } ( \mathrm { { c m } } ) ^ { \prime \prime }$ ；edit_width$= 1 0$ ; $ { \mathrm { k e y } } = { } ^ { * } \mathrm { d } ^ { * }$ ；}  
${ \mathrm { e d i t } } _ { - } { \mathrm { b o x } } \ \{ \ \mathrm { l a b e l } \ = \ ^ {  }$ 保护层&e（cm）”；edit_width $= 1 0$ ： $k e y = { } ^ {  } \mathrm { e } ^ { \prime \prime } ; \ \nmid \ \nmid \$ 幻灯片的绘制是在Autocad中绘制好结构模  
型，在对应的地方标注上参数名称，调用MSLIDE命  
令，保存在计算机中，供对话框的图片框调用。下  
面为幻灯片的调用代码：(start_image img_key)

(slide_imageO O(dimx_tile img_key）（dimy_tile img_key)img_sld) (end_image)

# 1. 3 结构的绘制

结构的绘制是根据结构的几何特征，依据所选参数,调用函数,绘制出结构[5]。首先是使用get_tile函数获取用户的参数输入值：（setqe（atof（get_tile"e”）））。然后，结合结构的几何特征绘制图形：

//设置图形界限 (command"limits”"”(list r r）) //计算控制点 (setq p5(list(/r 2)0)) (setq $\mathrm { p } 6 ( \mathrm { l i s t } ( / \mathrm { r } 2 ) \mathrm { b } )$ ） (setq $\mathrm { p } 1 ( \mathrm { l i s t } ( / (  { \mathrm { ~ - ~ r ~ c ~ } } ) 2 ) 0 )$ ）） (setq $\mathrm { p } 2 ( \mathrm { l i s t } ( / (  { \mathrm { ~ + ~ r ~ c ~ } } ) 2 ) 0 )$ ） (setq $\mathrm { p } 3 ( \mathrm { l i s t } ( / (  { \mathrm { ~ + ~ r ~ a ~ } } ) 2 )  { \mathrm { b } } )$ ） (setq $\mathrm { p } 4 ( \mathrm { l i s t } ( / (  { \mathrm { ~ - ~ } }  { \mathrm { ~ r ~ } }  { \mathrm { ~ a ~ } } ) 2 )  { \mathrm { b } } )$ ） (setq s(/(distance pl p4)2)) (setq ang2(atan( $\mathrm { s q r t } \left( \mathrm { ~ - ~ } \left( / \left( \mathrm { ~ * ~ \ r ~ r ~ } \right) \left( \mathrm { ~ * ~ \ s ~ } \right) \right) \right.$ （204号   
1)))) （setq angl(angle pl p4）) （setq pO(polar pl(+angl ang2) r)） //调用绘图命令绘制图形 （command"line"pl p2””) （command"line"p3 p4””) （command“arc”“c"pO pl p4) (setq p7(list( -( \*（car p5)2)(car pO))(cadr   
p0)）） (command"arc”“c"p7 p3 p2)

# 1. 4 翻样功能

翻样功能是依据翻样参数算出翻样次数[]，调用循环命令翻样出结果：

//计算修剪控制点(setq n 0)(setq cs(fix(/b d)))(repeat cs(setq $\mathbf { n } ( \mathbf { \theta } + \mathbf { n } \mathbf { \theta } 1 )$ ）（setq pn6（list(car p6）（-（cadr p6）（\* 10n))))（command“copy”p6””p6 pn6））//循环实现图形修剪(setq n 0)

(repeat cs(setq $\mathbf { n } ( \mathbf { \theta } + \mathbf { n } \mathbf { \theta } 1 )$ ）（setq pn3（list(car p3）（-（cadr p3）（\*10n))))（setq pn4（list(car p4）（-（cadr p4）（\* 10n)))）（command “ trim”p1 p2 p3p4pn3 ””$\mathrm { p n } 3 \mathrm { \ p n } 4 ^ { \prime \prime \prime }$ ））

# 1.5 数据标注

数据的标注使用到图元属性[7]。Autocad 中所有绘制的图形都有一个属性列表。属性列表中各属性都以点对列表的形式给出，通过对点对列表的操作即可获取想要属性值，或者通过属性列表修改图元。数据标注通过提取出属性列表中的线段长度,线段的起点和端点，调用标注命令,实现尺寸数据的标注：

L setq pfl(list( -(car p5)1)(cadr p5)）)   
setq pf2(list(+（car p6)1)(cadr p6)）)   
(setq xzj(ssget“f"(list pfl pf2））)   
setq pdlx（cadr(assoc 1O（entget（ssname xzj setq pdly(caddr(assoc 1O(entget(ssname xzj n ））   
O(setq pd2y(caddr(assoc 11( entget ( ssname xzj n)))))   
(setq pd1(list pd1x pd1y))   
(setq pd2(list pd2x pd2y))   
(command"dimaligned"pd1 pd2 pd2)

# 1. 6 结果输出

为了方便用户观看结果，输出的结果有图形结果，和扣除保护层厚度后输出的数值结果，这样也使得用户省去数据抄录的繁琐工作。部分代码为：

(setq file(open“ \* \* \*”“a”)） （write-line"编号长度保护层"file） (setq data(entget(ssname xzj n））) (setq tp(cdr(assoc O data)）) (if( $\mathbf { \sigma } = \mathbf { \sigma }$ tp“DIMENSION”) (setq cd(cdr(assoc 42 data)))

(write-line(strcat(itoa k）“"（rtos(-cd（\*e 2))2 2))file) (close file)

# 2 实例展示

以某市的高架桥的某桥墩的弧线变化部分为例，展示处理流程和结果

该桥墩的所需绘图尺寸数据如图2所示，保护层厚度为 $3 \mathrm { c m }$ ,翻样间隔为 $1 0 \mathrm { c m }$ 。由于桥墩的弧线设计，该部分的某编号箍筋尺寸会随着弧线逐步变化，现展示如何简单、快速、准确的获得变化的尺寸数据。

选择翻样模型为带弧桥墩，绘图和翻样参数输入窗口[8]如图3所示，将各个参数对应输入后点击确定就获得了所需的翻样结果。

![](images/7e19bf26a86d004e1c6857823af5238d03063d81634dae8dddbc2340fee0beab.jpg)  
图2绘图参数

![](images/6d86bed6c874e355823bdc0c6b16c79f2b6d01be5a92d2fbe6dc5eeb3ee9970d.jpg)  
图3参数输入对话框

图形结果如图4所示，数值结果如表1所示。

从上述过程可以看出，用户除了完成选择模型和输入参数外,其余的工作都是由计算机自动完成，省去了人工绘图、翻样和逐线标注的繁琐工作，并且结果的自动化输出也节省了数据抄录的过程，省时，方便，具有较高的实用性。而且，模板是可以重复使用的，在下一次遇到相似结构时可直接调用。

![](images/01b4d2ba6b38a811dad7a01c66f5682a94550c44aeadc9f8b35c7c9703128460.jpg)  
图4输出的图形结果

表1输出数值结果(单位cm)   

<html><body><table><tr><td>编号长度 保护层</td><td>编号 长度 保护层</td><td>编号</td><td>长度</td><td>保护层</td></tr><tr><td>V 380 3</td><td>10 306.29</td><td>3</td><td>19 261. 15</td><td>3</td></tr><tr><td>2370.08 3</td><td>11 300.13</td><td>3</td><td>20 258.58</td><td>3</td></tr><tr><td>3 ③360. 62</td><td>12 294.35</td><td>3</td><td>21 256.34</td><td>3</td></tr><tr><td>3 3351.6</td><td>13 288.94</td><td>3</td><td>22 254.45</td><td>3</td></tr><tr><td>343.01 3</td><td>14 283.9</td><td>3</td><td>23 252.89</td><td>3</td></tr><tr><td>34.86 3</td><td>15</td><td>279.23 3</td><td>24 251.67</td><td>3</td></tr><tr><td>327. 11 3</td><td>16</td><td>274.91 3</td><td>25</td><td>250.78 3</td></tr><tr><td>8 319.78 3</td><td>17</td><td>270.95 3</td><td>26</td><td>250.22 3</td></tr><tr><td>9 312.84 3</td><td>18</td><td>264.07 3</td><td>27</td><td>250 3</td></tr></table></body></html>

# 结束语

使用lisp语言进行Autocad二次开发，使得Au软件和工作更加贴合,更有效率[9]。并且该语法规则简单，灵活且易学，方便不同用户根据自身工作需求来制作自己的程序来实现工作中重复，繁琐工作的自动化。在该程序示例中，用户还可将工作中遇到的其他不同结构制作成模型添加到程序中[10],以便日后遇到相似模型时调用,减少工作量，提高工作效率。

# 参考文献

[1］屠志炜．基于VisualLisp的AUTOCAD的二次开发[D].吉林大学，2008.  
［2］吴凯伟，石玮荃.基于VisualLISP的地铁轨道综合图辅助设计程序开发[J].铁道标准设计，2017，61(5)：27-31.  
[3」王晓玲．开发AutoCAD实现参数化绘图[J」.吉林化工学院学报，2016，33（1）：31-34.  
［4］江明明.LISP编程语言在CAD绘图中的应用[J].北京测绘，2016，（1）：113-115.  
[5］梁芳，尹守军.基于AutoLISP的参数化绘图技术与实例分析[J].企业技术开发，2014，33(24)：93-94.  
［6］王国岗，段庆伟，孙平.一种基于AutoLisp语言快速等分任意曲线的方法[J].山西建筑，2016，42(35）：257-25.  
[7］郑岘，卿谆谆,蒋胜华，薛卫星.基于AutoLISP的快速标注统计程序在勘测规划成图中的应用[J].科技广场，2015，(7):49-53.  
[8］孟建，刘猛.基于VisualLISP的凸轮参数化设计[J].机械传动，2012，36(4)：61-63.  
［9］郭亮.AutoCAD二次开发在混凝土结构施工图绘制中的应用[D].合肥工业大学，2007.  
[10］李少辉，王志远.AutoCAD二次开发技术在矿山工程设计中的应用[J].中国矿山工程，2017，46(1)：57-60.

# A Fast and Simple Lofting Method to Set-out the Continuously Changing Reinforcement

Pan Shunqi1,²，Li Zhongqin1,2

(1.Faculty of Geomatics，Lanzhou Jiaotong University，Lanzhou 73OO7O，China; 2. Gansu Provincial Enginering Laboratory for National Geographic State Monitoring，Lanzhou 73Oo70，China）

Abstract:This paper discusss several methods of reinforced lofting at present，and introduces the advantages of using AutoCAD inreinforced lofting.The automatic reinforced lofting can be realized by using lisp language.Finall，combined with an example of a concrete pier，the general steps of using lisp language to realize the rapid change of the dimension of continuously changing steel bar are described in details.

Key Words: Continuously Changing Reinforcement； AutoCAD；Lisp Language； Parameterized Drawing； Au-tomatic Reinforced Lofting