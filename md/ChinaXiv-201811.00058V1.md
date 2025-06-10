# 无人机影像三维重建在沙丘形态监测中的应用

张明远¹，张登山1,²，吴汪洋¹，田丽慧³，周鑫²演变与自然灾害教育部重点实验室/防沙治沙教育部工程研究中心,北京师范大学地理科学学部,北京100875;2青海大学农林科学院，青海西宁8100163；3青海大学省部共建三江源生态和高原农牧业国家重点实验室,青海西宁 810016)

摘要：沙丘形态监测对开展土地沙化防治工作具有重大意义。应用无人机,分别在2016年7月、2017年3月、7月和9月对青海湖克土沙区4个沙丘进行影像采集，借助PhotoScan软件进行三维重建生成高分辨率的沙丘正射影像和DEM数据，使用ArcGIS软件获取沙丘形态参数并分析变化。实验结果表明：基于无人机影像监测沙丘形态，具有可行性和准确性，正射影像精度较高,DEM数据通过校正后可正确反映沙丘形态，为逐天高精度监测变化提供了可能。

关键词：沙丘；形态监测；无人机遥感；三维重建中图分类号：P231.5 文献标识码：A 文章编号

沙丘是风沙地貌学的主要研究对象，关于沙丘形态的形成发育以及分布规律是其重要的研究内容之一[1]。而要对这些内容进行研究,首先需要对地貌形态进行监测,获取形态数据[2-5]。沙丘形态监测研究的进展,大致可分为4个阶段[6-7],监测方法,也由最开始的定性描述方法[8],发展为利用插标杆法等的定位半定位观测方法[9],借助卫星和雷达影像的遥感监测方法[10-1],以及近期被广泛使用的利用GPS、全站仪和三维激光扫描仪等的三维测量方法[12-14]。方法的逐步发展,都是源于对更高精度沙丘形态数据的追求。2011年以后，由于民用及消费级无人机的普及，无人机遥感（unmannedaerialvehicleremotesensing，UAV-RS）技术被广泛应用[15-16]。相较于传统遥感技术,其具有高分辨率、高时效性、云层下成像和移动性能高的优点。近年来逐渐开始应用于灾害预报监测与评估[17],正射影像生成[18],及三维重建等方面[19]。应用无人机影像进行三维重建，可用于生成数字高程模型DEM和数字地表模型 $\mathrm { D S M } ^ { [ 2 0 - 2 1 ] }$ ,这些数据可用于文物保护[22],灾害评估[23-24],以及地形地貌等方面的研究[25-26]。应用无人机影像进行三维重建,可获得高精度的DEM数据[27],但并无学者将此种数据用于

沙丘形态监测。

本文应用大疆公司的精灵4无人机在青海湖克土沙区对典型新月形沙丘进行4次不同时期野外沙丘影像采集，并在室内，应用Agisoft $\textsuperscript { \textregistered }$ 公司Photo-scanTM软件对影像进行三维重建[28],生成正射影像和数字高程模型DEM。结合Esri $\textsuperscript { \textregistered }$ 公司的数据分析软件ArcGISTM进行沙丘形态参数提取与比较，用于监测沙丘形态变化。尝试用这种方法探究应用无人机影像对沙丘形态进行监测的可行性和准确程度。从而实现快速准确且便捷地获取沙丘形态数据及了解其变化情况，为土地沙化防治提供支撑。

# 1研究区概况与数据获取

# 1.1 研究区概况

青海湖位于青藏高原东北部，北依大通山，南傍青海南山，东靠日月山，西与哈拉湖毗邻，构成独立封闭的青海湖盆地地貌。且该地区地处常年西风带、东部季风区和青藏高原季风区的交汇地带。受地形、海拔和大气环流影响,形成太阳辐射强烈、气温日较差大、区域风速强劲等气候特征[29]。年平均气温 $- 0 . 2 \sim 0 . 6 ^ { \circ } \mathrm { C }$ ,昼夜温差大。年降水量 $3 8 0 ~ \textdegree$

$4 2 0 ~ \mathrm { m m }$ ,年蒸发量为 $1 ~ 4 2 2 . 5 \sim 2 ~ 0 6 6 . 2 ~ \mathrm { m m } ^ { [ 3 0 ] }$ 。其特殊的地理位置，造成了该区生态环境的特殊性与脆弱性，土地沙漠化危害更加严重，特别是东岸分布有大片的沙丘。因此对本地区土地沙化问题的研究具有维护当地生态平衡的现实意义。

用于沙丘形态监测实验的4个沙丘位于青海湖东岸,海晏湾东南部的克土沙区[31],地理位置坐标为 $3 6 ^ { \circ } 4 7 ^ { \prime } \mathrm { N } , 1 0 0 ^ { \circ } 4 7 ^ { \prime } \mathrm { E }$ ,海拔高度在 $3 2 0 0 \ \sim 3 \ 3 0 0 \ \mathrm { m }$ 面积约 $0 . 6 2 \ \mathrm { k m } ^ { 2 }$ （图1）。1号和4号沙丘为典型新月形沙丘，相对高度分别为36和 $3 0 \mathrm { ~ m ~ }$ 。沙丘表面无植被覆盖，仅在丘间地有沙棘和沙蒿分布。2号为新月形沙垄，相对高度 $4 5 \mathrm { ~ m ~ }$ ，丘间地有沙棘和沙蒿分布。3号为大型沙垄，相对高度约 $1 0 0 \mathrm { ~ m ~ }$ ，脊线北侧存在小幅度波动。

# 1.2 技术路线

本文应用无人机对沙丘地表进行三维重建的总体技术路线如图2所示。

# 1.3无人机数据获取方法

通过人工操控大疆精灵4无人机的方式进行影像采集，相机为DJIFC330，焦距 $4 ~ \mathrm { m m }$ 。控制无人机飞行高度为 $1 2 0 \mathrm { ~ m ~ }$ ,飞行速度在 $3 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ 左右，影像拍摄间隔为3s,拍摄时相机镜头垂直向下。尽量保证拍摄影像的航向重叠度和旁向重叠度在 $70 \%$ 以上，以便后期进行地表三维重建能生成更精确数据，理论上是航向重叠 $6 0 \%$ ,旁向重叠 $4 0 \% ^ { \left[ 2 7 , 3 2 \right] }$ 。本文中，在2016年7月15、16日，天气晴转多云；2017年3月 $2 4 \sim 2 6$ 日,有风,风速 $2 \sim 6 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ ;2017年7月 $2 3 \sim 2 5$ 日，晴；2017年9月 $1 3 \sim 1 5$ 日，晴。分别对4个沙丘进行实验区无人机影像采集。其中1号、2号和4号沙丘的四期影像全部成功获取，3号沙丘仅成功获取3期影像，2017年3月的无人机影像因采集区域位置错误而无法使用。

![](images/bdd61753da9b488bfdfe7656a7bbd3590481b4eb38ff0d6063b6399fe37a6d95.jpg)  
图1研究区沙丘位置无人机影像(2017年7月）示意图 ${ \mathit { \Omega } } _ { 1 } : 1 2 0 0 0 { \mathit { \Omega } } _ { . }$ ）  
Fig.1Location of study dunes in unmanned aerial vehicle images,July,2017 ( $1 : 1 2 0 0 0 \$ 0

![](images/ec816e12746a260c1bc472636116d63588fc78715f096009c089b8bd72df5686.jpg)  
图2技术路线Fig.2Technical route

# 1.4 三维重建

对无人机采集影像进行三维重建，并最终生成所需的DEM数据和正射影像。三维重建的基本原理是利用相似三角形[33-34]。已知参数（图3)为：基线（相机两次拍摄时镜头的连线)长，相机焦距和相机CCD大小，目标物体C在两个相机CCD上的位置。利用相似三角形可以建立方程，求出目标物体C 距基线的距离以及其距相机两次拍摄时镜头的距离。实际中要解算出目标物体C在空间中实际位置，还需要相机姿态参数及相机拍摄时的GPS位置等信息。

![](images/9d91223e1bde9be295dbb82dfc859b7cab5fcb26ce8c2723b2df4c1e059b758d.jpg)  
图3三维重建的基本原理  
Fig.3Foundation of 3D reconstruction

在相邻两次拍摄的无人机影像中，会有许多类似于目标物体C一样的点。借助Photoscan软件，可以解算出所有这些点的位置信息。使用软件时，首先将沙丘影像的照片导入，之后依次选择“对齐照片”、“生成网格”和“生成纹理”对影像进行处理。这些步骤中涉及的参数均按默认设置。完成后，即可输出正射影像及DEM数据,设置坐标系为WGS1984UTM zone 47N。

# 1.5沙丘形态数据提取

沙丘形态参数包括沙丘脊线长度、位置，沙丘体积，沙丘丘顶海拔高度，丘顶高度变化，沙丘蚀积变化位置及体积。沙丘蚀积变化是指不同时期，沙丘不同区域高度变化的差值，进行比较的区域是固定的。结果包括蚀积变化图，反应蚀积变化位置和总体蚀积变化体积。

借助ArcGIS软件，对正射影像和DEM数据进行沙丘形态数据提取。沙丘个体的脊线长度，位置及沙丘边界等形态参数可通过对正射影像进行矢量化的方式获得。

沙丘体积，则应用3DAnalystTools-FunctionalSurface-SurfaceVolume工具求得。输入选择沙丘的DEM数据,基准面高度选择沙丘DEM数据的最低值，或丘间地高度。选择Above，计算基准面之上的

体积。

之后，应用栅格计算器RasterCalculator对两次不同时期同一沙丘的DEM数据做差计算，从而得知沙丘形态变化情况，0代表不发生变化，正值代表堆积，负值代表侵蚀。由于沙丘形态变化在不同部位堆积或侵蚀不一样。借助SurfaceVolume工具，设置基准面为0，即不发生变化。参数选择Above即可求得沙丘变化时发生堆积部分的体积，选择below即可求得沙丘变化时发生侵蚀部分的体积。

# 2 1 无人机数据精度检验

应用Photoscan软件，对无人机影像进行三维重建，生成的正射影像和DEM数据结果（表1），其中2016年7月数据经过稀疏点云加密处理，精度较高，后面三期数据由于数据量加大，未进行稀疏点云加密处理。正射影像和DEM数据均是通过三维重建生成的模型获得，模型的空间位置信息会决定正射影像和DEM的空间位置信息。对于沙丘形态监测，准确的空间位置信息十分重要，因此在下面对生成数据进行检验。

# 2.1 水平精度

应用合众思壮（UnionStrong $\textsuperscript { \textregistered }$ )公司的集思宝G10A星站差分RTK记录沙丘的空间位置信息。记录方式选择水平误差和高程误差为厘米级的固定解。采点间隔约 $3 \mathrm { m }$ 。路线选择沙丘的边界以及脊线，同时，在1号、2号和4号沙丘还选择沿迎风坡和背风坡采集，采集点数量见表3。从采集的GPS数据中，选取沙丘脊线部分采集点。利用ArcGIS 处理无人机DEM数据提取沙丘脊线。对比点线距离，得到无人机影像三维重建数据的水平精度检验结果（图4、表2）。

表1无人机影像生成数据结果  
Tab.1 Reconstruction's result from unmanned   

<html><body><table><tr><td colspan="5">aerial vehicle images</td></tr><tr><td>采集时间</td><td>沙丘 编号</td><td>影像采 集数量 /张</td><td>正射影像 分辨率 /m</td><td>DEM 分辨率 /m</td></tr><tr><td>2016年7月</td><td>1号</td><td>68</td><td>0.016</td><td>0.032</td></tr><tr><td rowspan="8">2017年3月 2017年7月</td><td>2号</td><td>52</td><td>0.027</td><td>0.053</td></tr><tr><td>3号</td><td>96</td><td>0.035</td><td>0.069</td></tr><tr><td>4号</td><td>71</td><td>0.008</td><td>0.016</td></tr><tr><td>1号</td><td>177</td><td>0.023</td><td>0.504</td></tr><tr><td>2号</td><td>233</td><td>0.025</td><td>0.482</td></tr><tr><td>3号</td><td>1</td><td>1</td><td>1</td></tr><tr><td>4号</td><td>91</td><td>0.023</td><td>0.236</td></tr><tr><td>1号</td><td>167</td><td>0.017</td><td>0.281</td></tr><tr><td rowspan="6">2017年9月</td><td>2号</td><td>158</td><td>0.011</td><td>0.141</td></tr><tr><td>3号</td><td>251</td><td>0.028</td><td>0.374</td></tr><tr><td>4号</td><td>56</td><td>0.016</td><td>0.258</td></tr><tr><td>1号</td><td>190</td><td>0.020</td><td>0.235</td></tr><tr><td>2号</td><td>418</td><td>0.020</td><td>0.270</td></tr><tr><td>3号</td><td>427</td><td>0.038</td><td>0.392</td></tr><tr><td></td><td>4号</td><td>105</td><td>0.024</td><td>0.269</td></tr></table></body></html>

# 表2沙丘脊线位置水平精度检验表

Tab.2Accuracy test of dune's ridge line's horizontal coordinates   

<html><body><table><tr><td>沙丘编号</td><td></td><td>2017年7月</td></tr><tr><td>1号</td><td>GPS采集点数</td><td>14</td></tr><tr><td rowspan="3">2号</td><td>点线距离平均值／m</td><td>0.85</td></tr><tr><td>GPS采集点数</td><td>42</td></tr><tr><td>点线距离平均值／m</td><td>1.10</td></tr><tr><td rowspan="2">3号</td><td>GPS采集点数</td><td>83</td></tr><tr><td>点线距离平均值／m</td><td>2.09</td></tr><tr><td rowspan="2">4号</td><td>GPS采集点数</td><td>17</td></tr><tr><td>点线距离平均值／m</td><td>1.42</td></tr></table></body></html>

应用差分GPS 数据采集的2017年7月沙丘脊线位置数据与2017年7月基于无人机DEM数据提取的脊线较为接近（图4）。通过在ArcGIS中计算得到的点线距离的平均值及涉及GPS采集点数量如表2所示，点线距离平均值均小于 $2 . 1 \mathrm { ~ m ~ }$ ,其中1、2 和4号沙丘脊线位置点线距离平均值小于 $1 . 5 \mathrm { ~ m ~ }$ ，而3号沙丘点线距离平均值为 $2 . 0 9 \mathrm { ~ m ~ }$ 。考虑到在野外利用差分GPS采集位置数据时的人为误差和差分GPS自身误差影响，可以初步证明应用此种方法生成的正射影像和DEM数据在空间水平坐标上精度较高。

# 2.2 高程精度

应用与采集无人机影像相同时间采集的差分GPS 数据，在ArcGIS软件中将点数据转化为栅格数据，栅格数据格网大小与无人机影像生成DEM数据一致。上一小节已论证无人机影像三维重建数据在水平坐标上精度较高，因此可将差分GPS经处理得

![](images/1444c50ac2cf8b4d77727075fd0698efadba6ba8664d1d46acbb14734b104d03.jpg)  
图4水平精度检验示意图(2017年7月）  
Fig.4Accuracy test of data's horizontal coordinates,July,2017

# 表3DEM高程数据与差分GPS高程数据差异表

Tab.3Elevation data'sdifference between DEM anddifferential GPS   

<html><body><table><tr><td>沙丘 编号</td><td></td><td>2016年 7月</td><td>2017年 3月</td><td>2017年</td><td>2017年</td></tr><tr><td>1号</td><td>GPS采集点数</td><td>116</td><td>731</td><td>7月 798</td><td>9月 625</td></tr><tr><td></td><td>高程差极大值／m</td><td>116.7</td><td>101.7</td><td>107.2</td><td>69.6</td></tr><tr><td></td><td>高程差极小值／m</td><td>90.9</td><td>97.9</td><td>101.0</td><td>42.4</td></tr><tr><td></td><td>高程差平均值／m</td><td>95.8</td><td>100.0</td><td>104.1</td><td>57</td></tr><tr><td>高程差方差</td><td></td><td>12.7</td><td>0.6</td><td>1.9</td><td>9.0</td></tr><tr><td>2号</td><td>GPS采集点数</td><td>44</td><td>423</td><td>579</td><td>502</td></tr><tr><td></td><td>高程差极大值／m</td><td>92.2</td><td>109.5</td><td>141.9</td><td>67.4</td></tr><tr><td></td><td>高程差极小值／m</td><td>86.3</td><td>94.0</td><td>100.8</td><td>59.7</td></tr><tr><td></td><td>高程差平均值／m</td><td>89</td><td>103.3</td><td>120.7</td><td>63.8</td></tr><tr><td></td><td>高程差方差</td><td>3.2</td><td>9.1</td><td>13.1</td><td>1.2</td></tr><tr><td>3号</td><td>GPS采集点数</td><td>91</td><td></td><td>380</td><td>128</td></tr><tr><td></td><td>高程差极大值／m</td><td>91.7</td><td>一</td><td>101.1</td><td>80.1</td></tr><tr><td>高程差极小值／m</td><td></td><td>80.6</td><td>1</td><td>84.9</td><td>68.2</td></tr><tr><td></td><td>高程差平均值／m</td><td>87.4</td><td>一</td><td>95</td><td>74.9</td></tr><tr><td></td><td>高程差方差</td><td>9.8</td><td>1 一</td><td>14.6</td><td>6.9</td></tr><tr><td>4号</td><td>GPS采集点数</td><td>65</td><td>279</td><td>380</td><td>313</td></tr><tr><td></td><td>高程差极大值／m</td><td>98.6</td><td>110.1</td><td>106.8</td><td>76.9</td></tr><tr><td>高程差极小值／m</td><td></td><td>87.1</td><td>105.8</td><td>101.2</td><td>70.1</td></tr><tr><td>高程差平均值／m</td><td></td><td></td><td>108.2</td><td>104.5</td><td>73.7</td></tr><tr><td></td><td></td><td>92.8</td><td></td><td></td><td></td></tr><tr><td>高程差方差</td><td></td><td>7.3</td><td>0.8</td><td>0.9</td><td>1.9</td></tr></table></body></html>

到的栅格数据与无人机影像三维重建得到的DEM数据进行高程上的对比。对比二者在高程上的差异（表3），进行DEM高程数据精度检验。

应用无人机影像进行三维重建生成的DEM数据在高程数据上与差分GPS数据存在较大偏差（表3）。DEM数据均高于差分GPS 数据。但二者差值均集中于某一区间内，且高程差方差较小,数值波动有一定规律性。因此可应用ArcGIS中的栅格计算器工具，对DEM数据进行处理，让各沙丘DEM数据分别减去其相应的平均差值。消除高程差对精确提取沙丘形态参数的影响。

无人机影像三维重建生成的DEM数据的高程信息远高于差分GPS数据的高程信息主要是因为无人机DEM数据高程信息是基于拍摄时无人机机身上的GPS传感器记录的坐标进行运算生成的，而所使用的大疆精灵4无人机，其GPS传感器在高程上的误差较大，且并未购买可以提高无人机GPS精度的地面基站[34],因此高程上出现误差。

综上，基于无人机影像生成的正射影像和DEM数据，在水平坐标上，误差较小。而在高程上面，误差较大，应借助辅助高程数据进行校正。

# 3沙丘形态变化分析

应用无人机影像进行三维重建生成的正射影像和DEM数据，经过校正，导人ArcGIS获取形态参数（表4，图5、6），进行沙丘形态监测。以1号沙丘为例。

# 3.1 蚀积形态变化

应用无人机影像生成的高分辨率的DEM数据，可以获知不同时期沙丘高度，高度变化，蚀积体积变化情况（表4，图5）。图5d反映的是2016年7月至2017年7月1号沙丘的形态变化情况，在沙丘的西北侧，背风坡和丘间地交界处，有更严重的侵蚀（深蓝色)出现,可以判断是产生了涡流[35],因此造成侵蚀，涡流现象也出现在图5a的相同区域。这也证明了DEM数据分辨率较高，且较为可信。而在图5b和5d中，位于沙丘南侧，有一块较为明显的侵蚀区，这一区域由于地处1号沙丘(图5中所示沙丘)与2号沙丘(1号沙丘正南侧)中间的鞍部区域，有较强的峡谷风，因此出现了明显的侵蚀区。

表4沙丘形态数据  
Tab.4Attributive parameters of dune   

<html><body><table><tr><td>沙丘编号</td><td>时间</td><td>脊线长度 /m</td><td>体积 /m³</td><td>高度 /m</td><td>丘顶的高度变化 /m</td><td>变化体积中 堆积体积／m</td><td>变化体积中 侵蚀体积／m</td></tr><tr><td>1号</td><td>2016年7月</td><td>43.64</td><td>402 111</td><td>3 269.01</td><td>1</td><td>一</td><td>1</td></tr><tr><td></td><td>2017年3月</td><td>51.50</td><td>325143</td><td>3 263.45</td><td>-5.56</td><td>0.00</td><td>95 392.92</td></tr><tr><td></td><td>2017年7月</td><td>80.66</td><td>215 519</td><td>3 264.24</td><td>0.79</td><td>15 200.30</td><td>5 088.43</td></tr><tr><td></td><td>2017年9月</td><td>90.59</td><td>263 320</td><td>3 264.83</td><td>0.59</td><td>10 647.77</td><td>64 675.02</td></tr><tr><td></td><td>2016年7月至2017年7月</td><td>二</td><td>二</td><td>二</td><td>-4.77</td><td>0.00</td><td>85 281.06</td></tr></table></body></html>

注：沙丘体积蚀积变化体积指前后两次采集重叠区域的变化情况,如表格中2017年3月1号沙丘堆积体积结果,为2017年3月DEM 数据减去2016年7月DEM数据后经处理后得到

![](images/31a1756ad61c11c0219476b98b89b7635319d8a8a50f8e8585b09aee9a254ae5.jpg)  
图5沙丘形态变化示意图(1号沙丘,底图为2017年7月无人机影像)  
Fig.5Dynamicchanging ofdune morphology(example:dune NO.1，base map:unmannedaerial vehicle images,July,2017)

由于克土沙区冬春季主要为西风、西南风和西北风[30],且风速较大,因此在图5a中,侵蚀主要集中于西侧，而在东北侧侵蚀量较少。图5b所反映时期以西南和东南风为主,但由于风速较小，主要以堆积为主，集中于沙丘北侧。在夏季，以西南和西北风为主，但风速较小，因此在图5c中，侵蚀主要集中于沙丘西侧，而堆积集中于沙丘东北侧。

总体而言(图5d)，1号沙丘整体发生侵蚀，主要受冬春季较为强劲的西风和西南风影响。侵蚀严重区域集中于沙丘西北侧(涡流)和南侧(峡谷风影响），总体侵蚀量见表4。尽管在2017年3月至7月有少许堆积，但由于2016年7月至2017年3月这段时期侵蚀量较大。因此总体上发生侵蚀，且在图5d中，无堆积区域出现。表4所反映的1号沙丘1年蚀积变化体积，为2017年7月无人机DEM数据与2016年7月无人机DEM数据对比得到结果，无中间过程。因此仅有侵蚀体积数据。

# 3.2 脊线变化特征

高分辨率正射影像，可用于脊线长度、位置及其变化等沙丘形态参数的提取（表3，图6）。总体来看，丘顶的位置变化不大，固定在几条脊线相交的地方。而丘顶南北两侧相对较为平缓的脊线部分，移动频繁，北侧脊线在2016年7月至2017年7月向西移动，之后向东移动到9月；而南侧脊线在2016年7月至2017年3月向东移动，之后改为向西，但即便到了9月，其位置也并未退回到最开始2016年7月的位置。从脊线来看沙丘整体由东向东北发生偏转，且向西南移动。

综上，应用无人机影像对1号沙丘进行形态监测生成的结果，经过校正后，其形态变化情况反映出：堆积主要集中东北至东方向，与克土沙区输沙势和输沙量主要集中于北北东到东方向的情况基本一致[36]。这说明利用无人机对沙丘地表进行三维重建监测沙丘形态变化具有可行性和准确性。

![](images/05cf84ae95fa0bf7b8362afc152223490f30383231dc8d89d3b7382856c3f6dd.jpg)  
图6沙丘脊线变化示意图(1号沙丘，底图为2017年9月无人机影像)  
Fig.6Changing of dune crest line(example:dune No.1,base map:unmanned aerial vehicle images,September,2017)

# 4讨论

# 4.1无人机三维重建结果精度

应用无人机影像进行三维重建，对沙丘形态进行监测。数据的精度主要取决于无人机GPS的定位精度，可通过设置如差分GPS原理一样的地面基站的方式[34],提高其定位精度。当然,也可以通过直接用差分GPS在实地进行测量，在后期利用Pho-toScan软件对无人机影像处理的第一步“对齐照片”开始前,加载这些测量点作为地面控制点[37],以便能生成更高精度的数据。本文中则是在生成数据后，利用差分GPS数据对无人机影像三维重建结果进行精度检验和校正。借助差分GPS数据对无人机影像三维重建生成的DEM数据进行校正这个方法是可行的，有助于提高DEM数据精度，从而准确的对沙丘形态进行观测。差分GPS的误差可通过借助水准点数据进行消除。

本文中所设计的精度检验方式，也可以在今后的实验之中进行完善。可以在沙丘上随机设置9个$1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ 的彩色布条或泡沫板，之后再用无人机进行影像采集。影像采集完成后，在利用差分GPS在彩色布条或泡沫板上记录位置数据。既可以用做地面控制点，辅助三维重建。也可以作为精度检验的标准，检验正射影像的精度，并利用软件对影像进行校正，以获取更高精度的正射影像和DEM数据。通过对比利用差分GPS采集的脊线高度位置数据与无人机影像三维重建得到DEM数据提取出的脊线高度位置数据对比，检验正射影像和DEM数据的精度，但此种方法需要在野外利用差分GPS采集脊线数据时，有较高的准确性，减少人工采集误差。

# 4.2沙丘形态变化与监测

应用无人机数据来监测沙丘形态变化，相较于传统遥感手段，其具有很多优势，分辨率高是其中最主要的一点。并且获取数据的时间较为灵活，只要野外条件允许，便可以利用无人机采集影像。不同于使用差分GPS测量沙丘形态，使用无人机采集数据较为省时省力，采集 $0 . 0 2 \ \mathrm { k m } ^ { 2 }$ (2号沙丘： $2 0 0 ~ \mathrm { m } \times \mathrm { \Omega }$ $1 0 0 \mathrm { ~ m ~ }$ )仅需半小时，且通过运算可生成分辨率达厘米级的正射影像和小于 $1 \mathrm { ~ m ~ }$ 的DEM数据。青海湖克土沙区，在夜间风速较大，如2017年3月25日至26日夜间（18：00到23：00），小时平均风速在6\~13$\mathbf { m } \cdot \mathbf { s } ^ { - 1 }$ ,最大时达 $1 3 . 2 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ 。在这两天的白天,我们均对1号沙丘进行无人机影像采集，分析后结果表明,在迎风破(东北），最大堆积高度达 $1 . 1 \mathrm { ~ m ~ }$ ，背风坡(西)最大堆积高度为 $0 . 6 \mathrm { ~ m ~ }$ 。这为对同一沙丘逐天监测提供了可能。但目前的是结果仅能达到厘米级，对较为微观的沙丘形态变化无法准确监测，目前只能应用差分GPS[3]

图5a 明显的反映了涡流现象[35]。当然,图5b和5d南侧翼角受峡谷风影响发生较大侵蚀还需要结合风速风向和集沙量数据深入分析。但实验结果已经能正确反映出沙丘形态变化情况，说明应用无人机影像进行三维重建生成的正射影像和DEM数据，经过校正后，可以用于沙丘形态监测，且较为准确。

# 5结论

（1）应用无人机采集青海湖东岸克土沙区影像，并进行三维重建生成厘米级的正射影像和分辨率小于 $1 \mathrm { ~ m ~ }$ 的DEM数据,数据精度在水平坐标上与差分GPS记录结果接近，在高程坐标上与差分GPS高程数据相差较大，但可以借助差分GPS高程数据进行校正。校正后的结果能正确反映沙丘形态。

（2）1号沙丘在2016年7月至2017年9月这段时间，沙丘整体发生侵蚀，主要集中于沙丘西侧、南侧和北侧与丘间地交界处。丘顶的位置变化不大，位于4条不同时期脊线相交的位置。脊线由东向东北转动，沙丘整体西南方向移动。

（3）通过应用对无人机影像进行三维重建的方法，可生成高分辨率正射影像和DEM数据，且该方法在沙丘形态监测的应用方面具有一定的可行性和准确性。为逐天准确监测沙丘形态并分析其变化提供了可能，但目前无法应用于较为微观的沙丘形态变化监测中。

# 参考文献(References)

[1]吴正.风沙地貌与治沙工程[M].北京;科学出版社,2003:4, 144-150,166-169.［WU Zheng.Geomorphology of wind-drift sands and their controlled engineering[M].Beijing:Science Press, 2003:4,144-150,166 -169.]   
[2]丁连刚,严平,杜建会,等.基于三维激光扫描技术的草方格沙 障内蚀积形态监测[J].测绘科学,2009,34（2)：90－92. [DING Liangang,YAN Ping,DU Jianhui,et al.Monitoring the state of erosion and deposition in straw checkerboard barriers based on 3d laser scanning technique[J]. Science of Surveying and Mapping,2009,34(2）:90-92.]   
[3］李爱敏,韩致文,钟帅,等.基于CASS 和 ArcGIS 的新月形沙丘 属性参数提取［J].中国沙漠,2018,38（3）：1-8.［LIAimin， HAN Zhiwen,ZHONG Shuai,et al. Atributive parameter extraction of the barchan dune based on CASS and ArcGIS[J]. Journal of Desert Resarch,2018,38(3):1-8.]   
[4］丛殿阁,庞红丽,方苗,等.基于DEM 和 ETM 的腾格里沙漠北 缘沙丘形态特征提取[J].中国矿业,2014,23（S2）：163-169. [CONG Diange,PANG Hongli,FANG Miao,et al.Dunes distribution study on north of Tengery Desert based on remote sensig and dem[J].China Mining Magazine,2014,23（S2）:163-169.]   
[5］杜会石,哈斯,吴霞,等.3S技术在抛物线沙丘形态特征研究中 的应用[J].地理与地理信息科学,2011,（5):2,33-36.［DU Huishi,HASI Eerdun,WU Xia,et al.Application of 3s technology in morphological character research of parabolic dune[J]. Geography and Geo-Information Science,2011,(5）:2,33 -36.]   
[6]杜会石,哈斯.沙丘地貌形态监测与模拟研究进展[J].北京师 范大学学报（自然科学版）,2013,49（4）：400－406.［DU Huishi,HASI Eerdun. Morphological monitoring and dynamic simulation of dunes[J]. Journal of Beijing Normal University(Natural Science）,2013,49(4):400-406.]   
[7］张正傯,董治宝.风沙地貌形态动力学研究进展[J].地球科学 进展,2014,29(6）:88-101.[ZHANG Zhengcai,DONG Zhibao. Research progress on aeolian geomorphology and morphodynamics [J].Advances in Earth Science,2014,29(6）:88-101.]   
[8] BAGNOLD R A. The physics of blown sand and desert dunes [M].London:Methuen,1941:25-28,38 -41.]   
[9]FINKEL H J.The barchans of Southern Peru[J].University of Chicago Press,1959,67(6):614 -647.]   
[10］ANTHONSENKL,CLEMMENSENLB,JENSENJH.Evolution of a dune from crescentic to parabolic form in response to shortterm climatic changes: Rabjerg Mile,Skagen Odde,Denmark[J]. Geomorphology,1996,17（1）:63-77.]   
[11］张正傯,董治宝.黑河流域中游沙漠风能环境与风沙地貌[J]. 中国沙漠,2014,34（2）:28-37.[ZHANG Zhengcai,DONG Zhibao.Dune field paterns and wind environments in the middle reaches of the Heihe Basin[J]. Journal of Desert Resarch,2014, 34(2) :28 -37.]   
[12]NAGIHARA S,MULLIGAN KR,XIONG Wei. Use of a three-dimensional laser scanner to digitally capture the topography of sand dunes in high spatial resolution[J].Earth Surface Processes and Landforms,2004,29(3） :391-398.]   
[13]ANDREWS B D,GARES P A,COLBY J D. Techniques for GIS modeling of coastal dunes[J].Geomorphology,2002,48:289- 308.]   
[14］陈秀玲,李志忠,陈蜀江,等.基于差分GPS 测量数据的抛物线 沙丘形态特征研究［J].福建师范大学学报（自然科学版)， 2010,26(3）:84-89.[CHEN Xiuling,LI Zhizhong,CHEN Shujiang,et al.The morphological character research of parabolic dune-based on the date of diferential GPS survey[J].Journal of Fujian Normal University(Natural Science Edition）,2O10,26(3）: 84 -89.]   
[15］李德仁,李明.无人机遥感系统的研究进展与应用前景［J].武 汉大学学报（信息科学版）,2014,39（5）:4-12,39.[LI Deren,LI Ming. Research advance and application prospect of unmanned aerial vehicle remote sensing system[J]. Geomatics and Information Science of Wuhan University,2014,39(5）:4-12, 39.]   
[16］胡健波,张健.无人机遥感在生态学中的应用进展[J].生态学 报,2018,38（1）:1-11.[HU Jianbo,ZHANG Jian.Unmanmed aerial vehicle remote sensing in ecology:Advances and propects [J].Acta Ecological Sinica,2018,38(1）:1-11.]   
[17］臧克,孙永华,李京,等.微型无人机遥感系统在汶川地震中的 应用[J].自然灾害学报,2010,19（3）:162－166.[ZANG Ke, SUN Yonghua,LI Jing,et al.Application of miniature unmanned aerial vehicle remote sensing system to Wenchuan Earthquake[J] Journal of Natural Disasters,2010,19(3）:162 -166.]   
[18］陈杰,童小华,刘向锋,等.黑河流域中游无人机遥感影像数据 处理[J].地理信息世界,2014,21（1）:63-67.[CHEN Jie, TONG Xiaohua,LIU Xiangfeng,et al.Photogrammetricprocessing of unmanned aerial vehicle imagery in Heihe middle reaches[J]. Geomatics World,2014,21(1) :63 -67.]   
[19］吴俣,余涛,郑利娟,等.基于无人机遥感图像的三维地表模型 构建方法研究［J].系统仿真学报,2014,26（2）：376－381. [WU Yu,YU Tao,ZHENG Lijuan,et al. Study of 3d dsm construction method based on UAV remote sensing images[J]. Journal

of System Simulation,2014,26(2):376-381.]

[20]NIETHAMMERU,JAMESMR,ROTHMUNDS,etal.UAV-based remote sensing of the Super-Sauze landslide:Evaluation and results [J].Engineering Geology,2012,128:2-11.]   
[21］李立春.基于无人机序列成像的地形重建及其在导航中的应 用研究[D].长沙：国防科学技术大学,2009.［LILichun.3d reconstruction from image sequence of uav and its application on vision-based navigation[D]. Changsha: National University of Defense Technology,2009.]   
[22］于丙辰,陈刚,段淼然,等.无人机遥感在大型不可移动文物三 维重建中的应用[J].测绘通报,2017,482（5)：47-50,65. [YU Bingchen,CHEN Gang,DUAN Miaoran,et al. UAV RS applied in 3d reconstruction of huge immovable cultural relics[J]. Bulletin of Surveying and Mapping,2017,482(5）:47 -50,65.]   
[23］王鹤,刘军,王秋玲.利用无人机影像进行滑坡地形三维重建 [J].测绘与空间地理信息,2015,38（12）:78-81.[WANG He,LIU Jun,WANG Qiuling.3d reconstruction of landslide terrain from UAV images[J].Geomatics & Spatial Information Technology,2015,38(12):78-81.]   
[24］王果,蒋瑞波,肖海红,等.基于无人机倾斜摄影的露天矿边坡 三维重建[J].中国矿业,2017,26（4）：161－164.［WANG Guo,JIANG Ruibo,XIAO Haihong,et al.Reasearch on slope reconstruction technique based on UAV oblique photogrammetry [J].China Mining Magazine,2017,26(4）:161-164.]   
[25］陈亮,熊自明,邓涛,等.一种基于无人机序列图像的地形地貌 三维快速重建方法[J].北京测绘，2013（6）：29－32.［CHEN Liang,XIONG Ziming,DENG Tao,et al.An approach to automatic great-scene 3d reconstruction based on UAV sequence images[J]. Beijing Surveying and Mapping,2013（6）:29-32.]   
[26］常方媛.基于无人机航拍图像的三维地形重建[D].天津：天 津大学,2014.［CHANG Fangyuan.3d terrain reconstruction based on unmanned aerial vehicle images[D]. Tianjin: Tianjin University,2014.]   
[27］郭复胜，高伟.基于辅助信息的无人机图像批处理三维重建方 法[J].自动化学报,2013,39（6）:834-845.[GU0 Fusheng, GAO Wei.Batch reconstruction from UAV images with prior information[J].Acta Automatica Sinica,2013,39(6):834-845.]   
[28] JAVERNICK L,BRASINGTON J,CARUSO B. Modeling thetopography of shallow braided rivers using structure-from-motion photogrammetry[J].Geomorphology,2014（213）:166 -182[J].2014 (213):166 -182.]   
[29］张登山,高尚玉.青海高原沙漠化研究进展［J].中国沙漠, 2007,27(3）:367-372.[ZHANG Dengshan,GAO Shangyu.Re search progress on sand desertification in Qinghai Plateau[J]. Journal of Desert Research,2007,27(3）:367 -372.]   
[30］张登山,高尚玉，石蒙沂,等.青海高原土地沙漠化及其防治 [M].北京:科学出版社,2009:8-10.[ZHANG Dengshan,GAO Shangyu,SHI Mengyi,et al.Sandy desertification and its control in the Qinghai Plateau[M].Beijing:Science Press,2Oo9:8-10.]   
[31］吴汪洋,张登山,田丽慧,等.青海湖沙地人工治理沙丘的风速 廓线变化特征［J].水土保持研究,2013,20(6)：168－173. [WU Wangyang,ZHANG Dengshan,TIAN Lihui,et al. Variable characteristics of wind profile of the artificial sand dune in sandy land around Qinghai Lake[J].Research of Soil and Water Conservation,2013,20(6):168-173.]   
[32］张祖勋,张剑清.数字摄影测量学[M].武汉:武汉测绘科技大 学出版社,1997:88,100 -109.［ZHANG Zuxun,ZHANG Jianqing.Digital photogrammetry[M].Wuhan:Wuhan Technical University of Surveying and Mapping Press,1997:88,100 -109.]   
[33］程效军,朱鲤,刘俊领.基于数字摄影测量技术的三维建模 [J].同济大学学报（自然科学版）,2005,33（1）：40－44. [CHENG Xiaojun,ZHU Li,LIU Junling.Three dimension modeling based on digital photogrammetry method[J]. Journal of Tongji University（Natural Science）,2005,33（1） :40-44.]   
[34］王家杰.无人机低空摄影测量系统研究[D].哈尔滨::哈尔滨 工业大学,2016.［WANG Jiajie.Research on low-altitude aerial photographical systems based on unmanned aerial vehicle[D]. Harbin: Harbin Institute of Technology,2016.]   
[35］杨景春,李有利.地貌学原理[M].北京:北京大学出版社, 2012:119.[YANG Jingchun,LI Youli. The fundamentalsof geomorphology[M].Beijing:Peking University Press,2012:119.]   
[36］张登山,张佩,吴汪洋,等.青海湖东克土沙区风沙运动规律及 防治对策[J].中国沙漠,2016,36(2）:31-37.[ZHANG Dengshan,ZHANG Pei,WU Wangyang,et al.Wind-blown sandactivity and control way of sand hazards at Ketu sandy land in eastern shore of Qinghai Lake[J].Journal of Desert Research,2016,36(2）:31 -37.]   
[37］陈获,李卫正,孔文丽,等.基于低空高分辨影像的三维绿量计 算方法—以南京林业大学校园为例[J].中国园林,2015,31 （9）:30-34.[CHEN Di,LI Weizheng,KONG Wenli,et al. On the method of three-dimensional green volume calculation based on low—altitude high-definition images:case study of the Nanjing Forestry University campus[J]. Chinese Landscape Architecture, 2015,31(9):30 -34.]

# Application of UAV image based 3D reconstruction in morphological monitoring of dunes

ZHANG Ming-yuan’，ZHANG Deng-shan1²，WU Wang-yang1，TIAN Li-hui³，ZHOU Xin $^ 2$ （20 (1Key Laboratory of Environmental Changes and Natural Disaster,Ministry of Education,School of Geography, Beijing 100875,China；2Qinghai Academy of Agricultural Forestry Sciences,Xining 810016,Qinghai,China; 3State Key Laboratoryof Plateau Ecology and Agriculture,Qinghai University,Xining 810016,Qinghai,China)

Abstract：Morphological monitoring of dunes has an important value to controlland desertification.Compared with using diffrential GPS to monitor dune's morphology,the method using smallcivilian drone was easierand had higher reliability.This method could notonlysave time and labor but also produce high resolution results.Andthe images could turn out high resolution dune's morphological data which was smaller than $1 \mathrm { ~ m ~ }$ .However,few studies monitored dunes'morphologyby using unmanned aerial vehicle to colect images.In this paper,unmanned aerial vehicle（UAV）images of four dunes in Ketu,eastern of Qinghai Lake,Qinghai Province,China were taken by DJI Phantom4,in July 2O16,March,Julyand September 2017,respectively.These images were 3D reconstructed by PhotoScan to produce high resolution digital elevation model（DEM）and orthophoto images.And also dunes’morphological data was colected in the same time byusing UniStrong G1OAreal time kinematic platform（differential GPS）to test orthophoto images‘accuracy and corrected these images if there were some geometric eror.For the DEM,differential GPS's data was selected to test its accuracy.The results showed that these DEM's elevation data were average 90 to $1 1 0 \mathrm { ~ m ~ }$ higher than differential GPS's data.But it could be fixed by using raster calculator tool in ArcGIS.Then through analyzing DEMand orthophoto images which were rectified through above steps by using ArcGIS,thedynamic change of dune's elevation,length and location of crest line,anddune's volume could be understood intuitively.Theresultsshowedas follows:firstly,the orthophoto image and DEM'sresolution were smaller than $1 \mathrm { ~ m ~ }$ .And the orthophoto images’horizontal position was close to differential GPS's data.But the DEM'selevation was much higher than differential GPS'saltitude.This error couldbe revised and after thatthe DEMdata could accuratelyreflect the true morphology of dunes.Secondly,the dynamic changes of sample dune's morphology characters from July 2O16 to September 2O17 were consistent with previous studies.The erosion areas were mainly concentrated inthe west and south ofthe sample dune.Italso concentrated inthe brderarea of leeward slope and the area between sand dunes where it was inthe north of the sample dune.Meanwhile,the sample dune moved to the downwind directionof main wind（southwest）andits crest linerotated from eastto northeast.The position of the sample dune's crest changed litle.It was just at the junction of the sample dune's four crest lines which were extracted fromorthophoto images in diffrent time,respectively.Thirdly,applying high resolution DEMand orthophoto images in morphological monitoring of dunes was feasible and accurate.It made daily monitoring possible.

Key words: dune；morphological monitoring；UAV remote sensing；3D reconstruction.