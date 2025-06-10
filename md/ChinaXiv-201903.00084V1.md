# 永磁屏蔽电机不同齿尖结构参数的空载磁场分析

![](images/9b8803a984e9515650db09926582799953f64c6b0a5a3af9019e0812349347f6.jpg)

倪有源　孙　淼（合肥工业大学电气与自动化工程学院 合肥230009)

倪有源男1976年生，博士，副教授，硕士生导师，研究方向为电机设计及其控制。

摘要：有限元方法精度很高，适合求解复杂结构的电机磁场问题。运用三维有限元方法，比较分析了径向磁化、平行磁化两种磁化方向以及有齿尖及无齿尖两种结构永磁屏蔽电机的空载磁场参数。在此基础上，分析了齿尖平均弧长、齿尖厚度和外侧倾斜角等齿尖结构参数对两种磁化方向电机空载磁场参数的影响。计算结果表明，对于两种磁化方向，有齿尖结构永磁屏蔽电机的空载气隙磁通密度基波幅值、THD以及齿槽转矩都较大，而感应电动势较小。

关键词：永磁屏蔽电机空载磁场齿尖三维有限元方法中图分类号：TM351

# No-Load Magnetic Field Analysis of a PM Canned Motor with Different Structure Parameters of Tooth Tips

Ni YouyuanSun Miao (Hefei University of Technology Hefei 230009 China)

![](images/d4b226c990e3d77922c6179ce375186235b6af23078bacc7069839318097f40a.jpg)

孙森男1990年生，硕士研究生，研究方向为电机设计。

Abstract: Finite element method has a high computation accuracy and can be used to solve the magnetic field of the electric machine with complex structure.Using a three dimensional finite element method, the no-load magnetic field parameters of a permanent magnet canned motor with/without tooth tips for radial or parallel magnetization have been obtained. In addition, the no-load magnetic field parameters with two magnetizations in terms of the structure parameters of tooth tips have also analyzed. The computation results show that the fundamental amplitude and THD of the air gap flux density, and the cogging torque of the motor with tooth tips are higher for both magnetizations,while the back electromotive force is lower.

Keywords: PM canned motor, no-load magnetic field, tooth tips, three finite element method

# 1 引言

屏蔽电机与泵相配合组成的屏蔽电泵，一般安置于管道的内部，可用于输送普通、剧毒性、腐蚀性、放射性以及易燃易爆等液体。在历史上，早期使用的屏蔽电机多为感应屏蔽电机，但限于感应电机的原理，其效率较低[1-5]。随着对永磁材料研究的不断深入，永磁屏蔽电机得到了迅速发展[6-8]。永磁屏蔽电机的应用，一方面减少了转子的损耗，提高了效率；另一方面，对于结构的优化，使得永磁电机表现出更广泛的应用前景。所以对于永磁屏蔽电机的研究，既具有理论价值，又符合社会发展的客观需求。

国内外对于有齿尖和无齿尖结构的电机性能比较分析研究十分匮乏。文献[9-10]用解析方法分析了有齿尖和无齿尖结构的径向磁化永磁电机磁场参数，因其电机结构较为简单，适合用解析法求解；但并未分析齿尖结构参数对电机性能的影响。三维有限元法由于计算精度较高，适合求解复杂结构的电机磁场问题。本文首先给出了永磁屏蔽电机的结构，在Maxwell软件中建立电机三维仿真模型。然后分析了永磁屏蔽电机径向磁化、平行磁化以及有齿尖结构及无齿尖结构的空载磁场，给出了永磁屏蔽电机空载气隙磁场各参数。在此基础上，分析了齿尖平均弧长、齿尖厚度和外侧倾斜角等齿尖结构参数对两种磁化方向电机空载磁场参数的影响，得出齿尖结构参数对永磁屏蔽电机空载参数的影响规律。

# 2 永磁屏蔽电机的建模

# 2.1永磁屏蔽电机的结构及材料

本文分析的永磁屏蔽电机额定转速为 $3 ~ 0 0 0 \mathrm { r / m i n }$ 用于一款屏蔽电泵中。永磁屏蔽电机的主要结构参数见表1。

表1永磁屏蔽电机的结构参数  
Tab.1 Structural parameters of aPM canned motor   

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>定子外径/mm</td><td>80</td><td>转子外径/mm</td><td>38.4</td></tr><tr><td>定子内径/mm</td><td>40</td><td>转子内径/mm</td><td>15.8</td></tr><tr><td>定子轴向长度/mm</td><td>25</td><td>转子轴向长度/mm</td><td>25</td></tr><tr><td>定子轭部宽度/mm</td><td>5</td><td>转动惯量/(kg·m)</td><td>4.5 × 10-</td></tr><tr><td>定子齿宽度/mm</td><td>6</td><td>阻尼系数/N·m/(r/min)</td><td>4.86 × 10-6</td></tr><tr><td>定子绕组匝数</td><td>1020</td><td>定子屏蔽套厚度/mm</td><td>0.30</td></tr><tr><td>定子绕组线径/mm</td><td>0.21</td><td>转子屏蔽套厚度/mm</td><td>0.15</td></tr></table></body></html>

永磁屏蔽电机的定子铁心采用的是牌号为50W470的硅钢片， $0 . 5 \mathrm { m m }$ 叠压而成。永磁体采用牌号为Y10T的铁氧体，相对回复磁导率1.05，剩磁 $0 . 2 \mathrm { T }$ ，矫顽力 $1 5 0 \mathrm { k A / m }$ ，电导率取 $2 \times 1 0 ^ { 6 } \mathrm { S / m }$ ，密度取 $4 . 5 \times 1 0 ^ { 3 } \mathrm { k g / m } ^ { 3 }$ 。屏蔽套的作用是隔离液体,采用牌号为 $0 6 \mathrm { C r 1 9 N i 1 0 }$ 的不锈钢材料，其电阻率为 $7 . 3 \times 1 0 ^ { - 5 } \Omega \cdot \mathrm { c m }$ ，密度为 $7 . 9 3 \times 1 0 ^ { 3 } \mathrm { k g } / \mathrm { m } ^ { 3 }$ 。转轴采用氧化铝陶瓷材料，这种材料机械强度高、经济耐用且抗摩擦及冲击能力好，可以长期使用而不变形。在电磁仿真分析中，略去该部分。

# 2.2永磁屏蔽电机的三维有限元模型

在Maxwell3D中建立的有齿尖结构的永磁屏蔽电机三维模型，为6槽4极结构，如图1所示。

![](images/546a9e096a9a8075b5eadcc65d82ac1d941b29a75dd26e7b52af6ce21708b790.jpg)  
图1永磁屏蔽电机三维结构  
Fig.13D model of the PM canned motor

在AnsoftMaxwell3D软件中，首先建立永磁同步屏蔽电机三维几何模型，然后由于Ansoft提供了一个具有强大编辑能力的材料库，可以对各个元件赋予对应的材料属性；再通过正确的剖分方法和设置准确的剖分精度，对需要求解的区域内的所有部件进行网络剖分；最后对模型施加边界条件以及激励源进行求解；求解之后可以通过对结果数据的进一步处理，得到需要的结果。

# 2.3有齿尖结构和无齿尖结构

有齿尖及无齿尖结构的永磁屏蔽电机分别如图2a 和2b所示。相较于无齿尖结构，有齿尖结构较复杂，二者的磁路不同，电机性能也显然不同。

# 3径向磁化永磁屏蔽电机空载磁场分析

运用三维有限元方法，计算得到径向磁化永磁屏蔽电机空载磁场参数。图3a和3b为有齿尖及无齿尖结构的径向磁化永磁屏蔽电机的空载感应电动势波形。可得，有齿尖结构及无齿尖结构的感应电动势有效值分别为15V及 $1 8 . 9 \mathrm { V }$ 。

![](images/d14e1768ede86a23b3d7257f67df869a685c0ca4a07f8199768c98c4f71b1e37.jpg)  
图2两种齿尖结构图

![](images/179ec7bcadd49aba849ef464815df502d1347e56415091b0177e597ab3951c1b.jpg)  
Fig.2Two structures with/without tooth tips

图4a和4b为有齿尖及无齿尖结构的径向磁化永磁屏蔽电机的齿槽转矩波形。有齿尖结构的齿槽转矩及无齿尖结构的齿槽转矩峰值分别为$6 . 2 5 \mathrm { m N \cdot m }$ 及 $5 . 6 \mathrm { m N } \cdot \mathrm { m }$ 。

图5a和5b为两种结构永磁屏蔽电机的空载气隙磁通密度波形。从图中可以看出，有齿尖结构的气隙磁通密度幅值较大。同时计算了轴向不同截面的气隙磁通密度，气隙磁通密度在对称面附近气隙磁通密度大小相对稳定，但在两端有明显的下降，表明气隙磁通密度在定转子之间保持一个相对稳定的数值，但在接近端部时会明显减小。

![](images/4c9335c81d0b8c728996d639ddcba97bd7dc3816084efe0e7e5d5e1c5d1d4abe.jpg)  
图4径向磁化齿槽转矩波形  
Fig.4Cogging torque of two structures with

![](images/035b9f5d3fa71348baeb7b50816804f544c1e26d85eb6c0a10c1ebfb3a70d474.jpg)  
图3径向磁化空载感应电动势波形 Fig.3No-load EMF of two structures with radial magnetization   
图5径向磁化空载气隙磁通密度分布  
Fig.5No-load air gap flux density of two structures with radial magnetization

分别对气隙磁通密度进行傅里叶分解，得出径向磁化下两种结构的气隙磁通密度的基波和谐波，分别如图6a和图6b所示。并计算得出两种结构的空载气隙磁通密度的基波和THD，见表2。可以看出，有齿尖结构的气隙磁通密度基波幅值较大，说明了有齿尖结构的漏磁较小。由于有齿尖结构较为复杂，造成有齿尖结构的谐波比例较高。

![](images/d6cac7f9f48501f0270107b417b588c422c7ed8423a7187f347cf93703d24523.jpg)  
图6径向磁化空载气隙磁通密度基波和谐波

# 表2径向磁化空载气隙磁通密度基波和THD

Tab.2Fundamental component and THD of no-load air gap flux density for radial magnetization   

<html><body><table><tr><td>定子结构</td><td>基波幅值/T</td><td>THD(%)</td></tr><tr><td>有齿尖</td><td>0.117 4</td><td>67.58</td></tr><tr><td>无齿尖</td><td>0.098 3</td><td>51.30</td></tr></table></body></html>

# 3齿尖结构参数对电机空载磁场的影响

图7为齿尖结构参数图，齿尖的主要参数有平均弧长、厚度和外侧倾斜角。

只改变齿尖平均弧长，齿尖厚度和外侧倾斜角以及电机其他参数保持不变，计算得到电机不同的空载感应电动势及齿槽转矩，分别如图8及图9所示。

![](images/42a746010c5d3d379d0871bc49743cbe3117f895cff1d46adf606b3ddeaa28df.jpg)  
图7齿尖结构参数图

![](images/abc3775eeea1840e2a1e9f664778fed3e9332e41cb1a12b3852ccbdaca3f0a85.jpg)  
Fig.7Structure parameters of tooth tips   
图8齿尖平均弧长对径向磁化空载感应电动势的影响 Fig.8No-load EMF against the average arc length of tooth tips for radial magnetization

![](images/d43b94c18c447fc4c876b8860a6c8012acb1bb46140c9d17d5724663e6e71de9.jpg)  
Fig.6Fundamental and harmonic components of no-load air gap flux density for radial magnetization   
图9齿尖平均弧长对径向磁化齿槽转矩的影响 Fig.9Cogging torque against the average arc length of tooth tips for radial magnetization

计算得到了不同齿尖平均弧长下的径向磁化气隙磁通密度基波幅值及其THD值，见表3。可以看出，随着齿尖平均弧长的增加，感应电动势也增加。齿槽转矩则在齿尖平均弧长为中间值时最大，在齿尖平均弧长较短及较长时较小。在齿尖平均弧长较短时，气隙磁通密度基波幅值变化较不明显，随着齿尖平均弧长的增加，气隙磁通密度基波幅值逐渐增加。

表3不同齿尖平均弧长的径向磁化气隙磁通密度的基波幅值和THD  

<html><body><table><tr><td>齿尖平均弧长</td><td>气隙磁通密度基波幅值</td><td>气隙磁通密度THD (%)</td></tr><tr><td>/mm 0.8</td><td>/T 0.124 6</td><td>55.04</td></tr><tr><td>1.6</td><td>0.122 4</td><td>51.36</td></tr><tr><td>2.4</td><td>0.1263</td><td>46.38</td></tr><tr><td>3.2</td><td>0.132 4</td><td>43.03</td></tr><tr><td>4.0</td><td>0.135 2</td><td>45.92</td></tr><tr><td>4.8</td><td>0.136 3</td><td>51.67</td></tr><tr><td>5.6</td><td>0.137 0</td><td>49.75</td></tr><tr><td>6.4</td><td>0.141 7</td><td>46.48</td></tr><tr><td></td><td></td><td></td></tr><tr><td>7.2</td><td>0.142 8</td><td>45.20</td></tr></table></body></html>

只改变齿尖厚度，齿尖平均弧长和外侧倾斜角以及电机其他参数保持不变，计算得到电机的空载磁场参数，见表4。由表中可以看出，感应电动势基本不变，齿尖厚度对感应电动势影响很小。随着齿尖厚度的改变，齿槽转矩、气隙磁通密度的基波幅值以及THD变化规律不明显。在某些厚度，如$1 . 2 \mathrm { m m }$ 、 $2 . 1 \mathrm { m m }$ 及 $3 . 0 \mathrm { m m }$ 等，气隙磁通密度的幅值和THD、齿槽转矩的计算结果较优。

# 表4不同齿尖厚度的径向磁化空载磁场参数

Tab.3Fundamental component and THD with different average arc lengths of tooth tips for radial magnetization   

<html><body><table><tr><td>齿尖倾斜角</td><td>感应电动势</td><td>齿槽转矩</td><td>气隙磁通密度</td><td>气隙磁通密度</td></tr><tr><td>(arctan) 0.6</td><td>/V 1.05</td><td>/(mN·m) 6.08</td><td>基波幅值/T 0.139 8</td><td>THD(%) 46.40</td></tr><tr><td>0.9</td><td>1.05</td><td>6.32</td><td>0.1402</td><td>47.25</td></tr><tr><td>1.2</td><td>1.05</td><td>6.10</td><td>0.140 6</td><td>47.24</td></tr><tr><td>1.5</td><td>1.05</td><td>6.50</td><td>0.1411</td><td>49.01</td></tr><tr><td>1.8</td><td>1.05</td><td>6.33</td><td>0.1369</td><td>49.86</td></tr><tr><td>2.1</td><td>1.05</td><td>6.19</td><td>0.140 5</td><td>47.93</td></tr><tr><td>2.4</td><td>1.05</td><td>6.25</td><td>0.1403</td><td>45.48</td></tr><tr><td>2.7</td><td>1.05</td><td>6.58</td><td>0.1400</td><td>47.71</td></tr><tr><td>3.0</td><td>1.05</td><td>6.61</td><td>0.1405</td><td>47.58</td></tr></table></body></html>

Tab.4No-load magnetic field parameters with different thicknesses of tooth tips for radial magnetization   
表5不同齿尖外侧倾角的径向磁化空载磁场参数 Tab.5No-load magnetic field parameters with different angles of tooth tips for radial magnetization   

<html><body><table><tr><td>齿尖厚度</td><td>感应电动势</td><td>齿槽转矩</td><td>气隙磁通密度</td><td>气隙磁通密度</td></tr><tr><td>/mm 0.6</td><td>/V 1.05</td><td>/(mN·m) 6.42</td><td>基波幅值/T 0.137 5</td><td>THD(%) 44.18</td></tr><tr><td>0.9</td><td>1.05</td><td>6.35</td><td>0.139 6</td><td>46.16</td></tr><tr><td>1.2</td><td>1.06</td><td>5.89</td><td>0.1421</td><td>49.25</td></tr><tr><td>1.5</td><td>1.06</td><td>6.39</td><td>0.141 9</td><td>44.06</td></tr><tr><td>1.8</td><td>1.05</td><td>6.27</td><td>0.139 3</td><td>47.10</td></tr><tr><td>2.1</td><td>1.05</td><td>6.12</td><td>0.140 2</td><td>44.73</td></tr><tr><td>2.4</td><td>1.06</td><td>6.37</td><td>0.140 6</td><td>43.25</td></tr><tr><td>2.7</td><td>1.06</td><td>6.31</td><td>0.1382</td><td>48.10</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>3.0</td><td>1.05</td><td>5.92</td><td>0.141 4</td><td>46.45</td></tr></table></body></html>

此外，只改变齿尖外侧倾斜角，齿尖平均弧长和齿尖厚度以及电机其他参数保持不变，计算得到电机空载磁场的各性能参数，见表5。可以看出，

齿尖外侧倾角对感应电动势及气隙磁通密度基波幅值基本没有影响。而齿槽转矩和气隙磁通密度THD随着齿尖厚度的改变，变化规律不明显。

# 4平行磁化永磁屏蔽电机空载磁场分析

将转子永磁体的磁化方向设置为平行磁化后，对有齿尖及无齿尖结构的永磁屏蔽电机进行三维空载磁场分析。图10a和10b分别为两种结构的平行磁化永磁屏蔽电机的空载感应电动势波形。不难得出，有齿尖结构及无齿尖结构的感应电动势有效值分别为20.8V及 $2 6 . 7 \mathrm { V }$ 。

![](images/0bcede808da4afb4a52b3f858a42691c4dfae32a25ebe35a895cff8a0bbe0caf.jpg)  
图10平行磁化空载感应电动势波形 Fig.10No-load EMF of two structures with parallel magnetization

图11a和11b分别为两种结构的平行磁化永磁屏蔽电机的齿槽转矩波形。有齿尖结构及无齿尖结构的齿槽转矩峰值分别为 $6 . 1 \mathrm { m N \cdot m }$ 及 $4 . 6 8 \mathrm { m N \cdot m }$ 。

![](images/0cad0eee0cc92030a09b1b31dbd2570b684286ef1937ec0d82410d7dfd2986ae.jpg)

图12a和12b分别为有齿尖及无齿尖结构的平行磁化永磁屏蔽电机的空载气隙磁通密度波形。从图中可以看出，有齿尖结构的气隙磁通密度幅值较大。

分别对气隙磁通密度进行傅里叶分解，得到两种结构平行磁化气隙磁通密度的基波和谐波，分别如图13a和13b所示，并得出两种结构的空载气隙磁通密度基波和THD，见表6。

![](images/9af58f1d273c3f671072a265ffbf17ae354fd80533ee6ce467d4f003567c4224.jpg)  
图11平行磁化齿槽转矩波形  
(a）有齿尖结构

![](images/c74924089aec86715bfffb59c16c8768adfece8050d23a2b46aadedf4d0ee1c1.jpg)  
图12平行磁化空载气隙磁通密度分布 Fig.12No-load air gap flux density of two structures with radialmagnetization

![](images/b669eba79932f3c868f309d99faf40861a48f5b1e9279a0b197411b989f5e3ed.jpg)  
Fig.11Cogging torque of two structures with parallel magnetization   
图13平行磁化空载气隙磁通密度基波和谐波 Fig.13Fundamental and harmonic components of no-load air gap flux density for parallel magnetization

# 表6平行磁化空载气隙磁通密度基波和THD

Tab.6Fundamental component and THD of no-load air gap flux density for parallel magnetization   

<html><body><table><tr><td>定子结构</td><td>基波幅值/T</td><td>THD(%)</td></tr><tr><td>有齿尖</td><td>0.164 4</td><td>49.12</td></tr><tr><td>无齿尖</td><td>0.136 9</td><td>46.35</td></tr></table></body></html>

显然，有齿尖结构的气隙磁通密度基波幅值较大，说明在平行磁化永磁屏蔽电机中有齿尖结构的漏磁仍然较小。同样，对于平行磁化永磁屏蔽电机，有齿尖结构由于其齿尖结构较为复杂，造成谐波比例较高。

# 5齿尖结构参数对电机空载磁场的影响

对于平行磁化的永磁屏蔽电机，只改变齿尖平均弧长，齿尖厚度和外侧倾斜角以及电机其他参数保持不变，计算得到不同的空载感应电动势及齿槽转矩，分别如图14及图15所示。同样，可以得到不同平均弧长下的气隙磁通密度的基波幅值及THD，见表7。可以看出，随着齿尖平均弧长的增加，感应电动势同时增加。在齿尖平均弧长中间值时齿槽转矩较大，在齿尖平均弧长较短及较长时齿槽转矩较小。气隙磁通密度基波幅值与齿尖平均弧长基本呈正相关性，但在齿尖平均弧长较短及较长时，变化较不明显。

![](images/46128955b1764759ea150ba158879ef95f1b3db0f1b80809e85f7a762e2cbf25.jpg)  
图14齿尖平均弧长对平行磁化感应电动势的影响 Fig.14No-load EMF against the average arc length of tooth tips for parallel magnetization

![](images/38e029a88d5d0009253a28023c7d99e62a09a36de084508a1a9875526084e1b1.jpg)  
图15齿尖平均弧长对平行磁化齿槽转矩的影响 Fig.15Cogging torque against the average arc length of tooth tips for parallel magnetization

只改变齿尖厚度，齿尖平均弧长和外侧倾斜角以及电机其他参数保持不变，计算得到平行磁化永

# 表7不同齿尖平均弧长的平行磁化空载气隙磁通密度基波幅值和THD

Tab.7Fundamental component and THD with different average arc lengths of tooth tips for parallel magnetization   

<html><body><table><tr><td>齿尖平均弧长 /mm</td><td>气隙磁通密度基波幅值 /T</td><td>气隙磁通密度THD (%)</td></tr><tr><td>0.8</td><td>0.172 9</td><td>43.50</td></tr><tr><td>1.6</td><td>0.172 7</td><td>40.92</td></tr><tr><td>2.4</td><td>0.177 4</td><td>37.59</td></tr><tr><td>3.2</td><td>0.184 4</td><td>33.14</td></tr><tr><td>4.0</td><td>0.190 3</td><td>34.07</td></tr><tr><td>4.8</td><td>0.188 6</td><td>36.92</td></tr><tr><td>5.6</td><td>0.193 5</td><td>32.56</td></tr><tr><td>6.4</td><td>0.199 3</td><td>27.18</td></tr><tr><td>7.2</td><td>0.198 7</td><td>27.66</td></tr></table></body></html>

磁屏蔽电机空载磁场的各性能参数，见表8。可以看出，齿尖厚度对感应电动势基本没有影响。而齿槽转矩、气隙磁通密度的基波幅值和THD随着厚度的改变，变化规律不明显；在某些厚度，如 $1 . 2 \mathrm { m m }$ 及 $3 . 0 \mathrm { m m }$ 时，齿槽转矩、气隙磁通密度的幅值和THD 较优。

# 表8不同齿尖厚度的平行磁化空载磁场参数

Tab.8No-load magnetic field parameters with different thicknesses of tooth tips for parallel magnetization   

<html><body><table><tr><td>齿尖厚度</td><td>感应电动势</td><td>齿槽转矩</td><td>气隙磁通密度</td><td>气隙磁通密度</td></tr><tr><td>/mm 0.6</td><td>/V 1.45</td><td>/mN · m 5.81</td><td>基波幅值/T 0.194 8</td><td>THD(%) 29.17</td></tr><tr><td>0.9</td><td>1.45</td><td>5.85</td><td>0.1968</td><td>28.60</td></tr><tr><td>1.2</td><td>1.45</td><td>5.45</td><td>0.197 3</td><td>30.89</td></tr><tr><td>1.5</td><td>1.45</td><td>5.58</td><td>0.196 5</td><td>27.76</td></tr><tr><td>1.8</td><td>1.45</td><td>5.92</td><td>0.195 7</td><td>28.90</td></tr><tr><td>2.1</td><td>1.45</td><td>5.75</td><td>0.194 5</td><td>27.90</td></tr><tr><td>2.4</td><td>1.45</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>6.07</td><td>0.1973</td><td>26.29</td></tr><tr><td>2.7</td><td>1.45</td><td>5.82</td><td>0.178 7</td><td>40.28</td></tr><tr><td>3.0</td><td>1.45</td><td>5.58</td><td>0.197 4</td><td>29.66</td></tr></table></body></html>

此外，只改变齿尖外侧倾斜角，齿尖厚度和齿尖平均弧长以及电机其他参数保持不变，计算得到平行磁化永磁屏蔽电机空载磁场的各性能参数，见表9。可以看出，齿尖外侧倾角对感应电动势和气隙磁通密度基波幅值影响很小。而齿槽转矩和气隙磁通密度THD随着齿尖厚度的改变，变化规律不明显。

表9不同齿尖外侧倾斜角的平行磁化空载磁场参数 Tab.9No-load magnetic field parameters with different angles of tooth tips for radial magnetization   

<html><body><table><tr><td>齿尖倾斜角 (arctan)</td><td>感应电动势 /V</td><td>齿槽转矩 /mN · m</td><td>气隙磁通密度 基波幅值/T</td><td>气隙磁通密度 THD(%)</td></tr><tr><td>0.6</td><td>1.45</td><td>5.50</td><td>0.197 0</td><td>28.39</td></tr><tr><td>0.9</td><td>1.45</td><td>5.51</td><td>0.1974</td><td>28.26</td></tr><tr><td>1.2</td><td>1.45</td><td>5.73</td><td>0.1951</td><td>30.16</td></tr><tr><td>1.5</td><td>1.45</td><td>5.96</td><td>0.1969</td><td>29.09</td></tr><tr><td>1.8</td><td>1.45</td><td>5.71</td><td>0.194 1</td><td>29.37</td></tr><tr><td>2.1</td><td>1.45</td><td>5.76</td><td>0.197 2</td><td>28.77</td></tr><tr><td>2.4</td><td>1.45</td><td>5.76</td><td>0.197 3</td><td>28.07</td></tr><tr><td>2.7</td><td>1.45</td><td>5.85</td><td>0.195 9</td><td>29.01</td></tr><tr><td>3.0</td><td>1.45</td><td>5.97</td><td>0.198 0</td><td>27.34</td></tr></table></body></html>

# 6 结论

对于复杂结构的电机，需要用有限元法才能精确计算其性能。本文运用三维有限元方法计算了永磁屏蔽电机径向磁化、平行磁化以及有齿尖结构及无齿尖结构的空载磁场，得出了永磁屏蔽电机空载气隙磁通密度波形、反电动势波形以及齿槽转矩波形，并对气隙磁通密度进行了傅里叶分解。计算结果表明，对于两种磁化方向，有齿尖结构气隙磁通密度的基波幅值和THD以及齿槽转矩都较大，而感应电动势较小。分析了齿尖平均弧长、齿尖厚度和外侧倾斜角等齿尖结构参数对两种磁化方向电机空载磁场参数的影响，得出了齿尖参数对空载磁场参数影响的规律。本文为永磁电机及永磁屏蔽电机的结构优化提供了理论参考。

# 参考文献

[1] 赵博．实心转子屏蔽电机电磁参数计算与性能分析[D]．哈尔滨：哈尔滨理工大学，2008.[2] 梁艳萍，张建涛，索文旭．双屏蔽复合转子电

机涡流损耗分析[J]．中国电机工程学报，2009,29(24): 78-83.Liang Yanping,Zhan Jiantao,Suo Wenxu.Eddycurrent losses analysis of double-cans composite-rotor motor[J]. Proceedings of the CSEE,2009,29(24): 78-83.  
[3] 张建涛．双屏蔽复合转子电动机涡流损耗计算与性能分析[D]．哈尔滨：哈尔滨理工大学，2009.  
[4] 郭纯治．核电用屏蔽电动机的损耗分析与温升计算[D]．沈阳：沈阳工业大学，2013.  
[5] 张晓晨，李伟力，曹君慈．屏蔽电机屏蔽损耗与电机性能的计算与分析[J]．哈尔滨工业大学学报,2007，39(9):1422-1426.Zhang Xiaocheng,Li Weili, Cao Junci. Calculationand analysis for the can loss and performance ofcanned motors[J]. Journal of Harbin Institute ofTechnol0gy, 2007,39(9): 1422-1426.  
[6] 黄亚．新型永磁屏蔽电机本体与控制系统研究[D].合肥：合肥工业大学，2014.  
[7] Burkhardt Y, Huth G, Urschel S. Eddy current lossesin PM canned motors[C]. The XIX InternationalConference on Electrical Machines,Rome,2010:1-7.  
[8] 周明荣．永磁屏蔽电泵电磁场有限元分析及其屏蔽套涡流损耗计算[D]．杭州：浙江工业大学，2004.  
[9] Wu L J, Zhu Z Q, Staton D,et al. An improvedsubdomain model for predicting magnetic fieldof surface-mounted permanent magnet machinesaccounting for tooth-tips[J]. IEEE Transactions onMagnetics,2011,47(6): 1693-1704.  
[10]Wu L J, Zhu Z Q, Staton D,et al. Subdomain modelfor predicting armature reaction field of surface-mounted permanent-magnet machines accounting fortooth-tips[J]. IEEE Transactions on Magnetics,2011,47(4): 812-822.