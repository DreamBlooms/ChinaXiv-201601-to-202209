# 深圳市天文台全天云图监测系统的设计与实现

梅林1，吴翔²，周作超²

（1.深圳市国家气候观象台，广东 深圳518040；2.深圳市一思佛科技有限公司，广东 深圳 518040）

摘要：全天云图监测对天文观测至关重要，目前大多数天文台站安装了实时云图监测相机，但共同的难题是如何在光线变化较大的情况下进行正确曝光。为解决这一问题，深圳市天文台自行开发了一套拍摄控制系统，根据相机可用的拍摄参数，计算得到曝光值索引曲线，采用0.3作为曝光值误差，在亮度变化较大的各种环境下进行正确曝光拍摄全天云图，并采用最大类间方差自适应阈值算法，对云进行有效识别。经多次测试，系统在亮度变化较大较快的环境下能拍摄到正确曝光的云图，为天文观测计划提供了极大的便利。

关键词：全天相机；自动拍摄；曝光参数；云识别；图像处理中图分类号：P412.15 文献标识码：A 文章编号：1672-7673

# 1全天云图监测的现状与不足

全天云图观测面临一个关键问题，如何在复杂变化环境以及光线变化较大的情况下进行正确曝光。目前相机自带的自动测光程序无法较好解决该问题。以佳能单反相机为例，它提供了一款控制软件EOSUtility④，支持通过计算机对相机进行快门速度、光圈、感光度、白平衡等曝光参数的控制，可进行等间隔连续拍摄，并对拍摄的图片按顺序存储到指定目录。当相机设置为自动拍摄模式时，控制软件可根据相机自带测光模式对曝光参数进行自动调整，一般光线充足的白天能获得正确曝光的图片，但是在日落、日出、天气突变等天空亮度变化较大的环境下，导致曝光过度或曝光不足，尤其在夜晚，控制程序更不能获得正确的曝光图像。图1、图2为使用相机自带测光程序拍摄的曝光过度和曝光不足的云图序列。

D000  
2015_12_29_05_55_35_7451 2015_12_29_06_00_39_7452 2015_12_29_06_05_43_7453 2015_12_29_06_10_48_7454 2015_12_29_06_15_52_7455  
o1ololo  
2015_12_29_06_20_56_7456 2015_12_29_06_26_00_7457 2015_12_29_06_31_04_7458 2015_12_29_06_36_09_7459 2015_12_29_06_41_13_7460  
2015_12_29_06_46_17_7461 2015_12_29_06_51_21_7462 2015_12_29_06_56_26_7463 2015_12_29_07_01_30_7464 2015_12_29_07_06_34_7465  
2015_12_29_07_11_38_7466 2015_12_29_07_16_42_7467 2015_12_29_07_21_47_7468 2015_12_29_07_26_51_7469 2015_12_29_07_31_55_7470OIOO

12月29日黎明日出阶段的云图序列，出现曝光过度现象

Fig. 1 Overexposured images captured by the camera built-in program in the dawn of December 29，2015

O00  
2015_12_29_13_43_47_7486 2015_12_29_14_04_04_7487 2015_12_29_14_24_21_7488 2015_12_29_14_44_38_7489 2015_12_29_15_04_54_7490Qlor 1  
2015_12_29_15_25_11_7491 2015_12_29_15_45_28_7492 2015_12_29_16_05_45_7493 2015_12_29_16_26_02_7494 2015_12_29_16_46_18_7495  
2015_12_29_17_06_35_7496 2015_12_29_17_26_52_7497 2015_12_29_18_10_23_7499 2015_12_29_18_30_40_7500 2015_12_29_18_50_56_7501O○  
2015_12_29_19_11_13_7502 2015_12_29_19_31_30_7503 2015_12_29_19_51_47_7504 2015_12_29_20_10_09_7505 2015_12_29_20_15_14_7506  
0l000o

12月29日黄昏日落阶段的云图序列，出现曝光不足现象

Fig. 2 Underexposured images captured by the camera built-in program in the evening of December 29， 2015

为弥补相机自动测光程序的不足，目前国内各天文台主要采用了以下3种修正方法。

（1）预设固定曝光参数法，即采用预先设定好两个曝光参数，分别用于白天和夜晚。该方法可以获得白天和夜晚的正确曝光，但是在黎明日出以及黄昏日落的时间段不能获得正确的曝光。中国科学院国家天文台兴隆观测站的全天云图监测相机②就采用该方法。

（2）预测天光法，即根据地理经纬度、海拔、日期时间推算太阳月亮的位置，得到一个天光亮度值，设定一条曝光曲线。这个方法只对晴朗的天空有效，如果阴天有云或者有其他光害情况，则无法正确曝光。

（3）外部测光法，即使用测光仪，根据环境亮度的变化，测量天空亮度值，自动调整相机的曝光参数，准确曝光。云南天文台丽江天文观测站自行开发了一款控制程序，采用实时天光亮度设置拍摄参数，解决了全天24小时正确曝光拍摄的问题1]。

# 2深圳市天文台全天云图监测系统的设计与实现

深圳市天文台自行开发了一套拍摄控制系统，根据相机可用的拍摄参数，计算得到曝光值索引曲线，采用0.3作为曝光值误差，在亮度变化较大的各种环境下进行正确曝光拍摄全天云图，并采用最大类间方差自适应阈值算法，对云进行有效识别。

# 2.1系统构成

深圳市天文台全天云图监测系统由全天相机、拍摄控制系统、云识别系统3部分构成。其中，全天相机负责对全天云图进行实时拍摄，拍摄控制系统对全天相机的拍摄参数进行自动调整，云识别系统对拍摄得到的全天云图进行云判别，最终监测结果通过深圳市天文台网站③、深圳市综合气象监测业务平台、深圳天文微信以及移动App等服务渠道对外发布。

![](images/9bebea4766d1b71f9d40ef0c9eade01ebe2bc960a83b271b105601cb0f7c5d0a.jpg)  
图3深圳市天文台全天云图监测系统图示  
Fig. 3 Diagram of the all-sky cloud monitoring system

at Shenzhen astronomical observatory

# 2.2全天相机的安装

深圳市天文台位于广东省深圳市大鹏新区南澳半岛，距离市区 $8 0 ~ \mathrm { k m }$ ，地理坐标为北纬 $2 2 ^ { \circ } 2 8 . 9 4 ^ { \prime }$ ，东经 $1 1 4 ^ { \circ } 3 3 . 3 6 ^ { \prime }$ ，海拔高度 $1 7 0 \mathrm { ~ m ~ }$ ，其东、南、西三面环海，周围无遮挡，全天相机的安装位置选择在天文台最高点户外水池上。拍摄相机采用佳能 EOS5D MarkII单反相机，镜头采用佳能EF $8 \mathrm { m m } ^ { - 1 5 } \mathrm { m m }$ F4.0变焦鱼眼镜头，并将拍摄焦距固定在8mm，可实现对角线 $1 8 0 ^ { \circ }$ 的覆盖。为保证相机能够在全天候环境下工作，相机和一台用于控制的微型电脑被安装在一个防护箱内。防护箱的顶部装有一个直径为20cm的半球玻璃罩。玻璃罩和侧面密封防水，底部留有通风口。箱体内安装了一个螺旋导流风扇，可对相机、微型电脑进行散热，保证箱体内外环境温度一致，防止箱体过热或玻璃罩结露。拍摄图像通过光纤传输到远端服务器。图4为安装于室外的全天相机。

![](images/c6d825c4010a10d43a72216ca0a112332ffe37939db97039a51d16b7fbbb1552.jpg)  
图4安装于室外的全天相机

Fig. 4 The all-sky cloud monitoring camera stands

outdoors

# 2.3根据曝光值设置对应的拍摄参数

为了获得正确的曝光全天云图，在相机可用光圈、快门、感光度3个可用参数的基础上，根据曝光值计算公式[2]，进行曝光值预计算④，公式为

其中， $E V$ 为曝光值； $F$ 为光圈值； $t$ 为快门速度；ISO为感光度，将相机所有可用参数进行组合，计算出曝光值并对其按大小进行排序，可得到如表1的曝光参数表以及图5的曝光值索引曲线。同时，将曝光值索引曲线相邻取值相减，即可得出EV变化范围，如图6，将曝光值误差允许范围取值0.3。

# 表1曝光值索引与曝光参数

Table 1 The index of exposure value and corresponding exposure

parameters   

<html><body><table><tr><td>曝光索引</td><td>光圈</td><td>快门</td><td>感光度</td><td>曝光值</td></tr><tr><td>0</td><td>2.8</td><td>1</td><td>100</td><td>2.97</td></tr><tr><td>1</td><td>4</td><td>1</td><td>200</td><td>3</td></tr><tr><td>2</td><td>4</td><td>1/2</td><td>200</td><td>4</td></tr><tr><td>3</td><td>5.6</td><td>1/2</td><td>200</td><td>4.7</td></tr><tr><td></td><td></td><td></td><td>....</td><td></td></tr></table></body></html>

![](images/b1eb1404927ea7ec98e2ffc3095e9b67276c70166a288d93074c1255935e9b58.jpg)  
图5曝光值索引曲线图

Fig. 5 The index curve of exposure value

拍摄时，先使用预定参数拍摄一张照片，并计算这张照片的曝光值，假设参考图片曝光值为 $E V _ { \mathrm { r e f } }$ ，则误差量为

若误差值在允许范围内，则此照片直接作为拍摄结果进行保存；若误差超出范围，则需根据曝光值索引曲线查找出正确的曝光参数进行重拍。

![](images/059b989d881f905b986660af851eafbf8918b8395c7bc59388b57b7abdc886fb.jpg)  
图6曝光值误差索引图

Fig. 6 The index of the exposure value errors

经多次测试，该方法在不同环境下以及亮度变化较大较快的阶段均能拍摄到正确曝光的云图。图7、图8为夜晚以及白天得到的正确曝光的云图，图9至图12为黎明日出、黄昏日落过渡阶段以及白天、夜晚得到的正确曝光云图序列。

![](images/0125a7d2855f06593d0b98657a9d63268171141d4f810025e44852986a5673ea.jpg)  
图7根据曝光值索引曲线，拍摄得到的2017年6月11日20时16分的正确曝光云图

Fig. 7 Image with accurate exposure adjusted by index curve of

exposure value on 20:16，June 11，2017

![](images/9686868745f99aff1abf8381e1dd96e432dad86a2e5d8988ae5597fbdd58d3c4.jpg)  
图8根据曝光值索引曲线，拍摄得到的2017年6月3日16时36分的正确曝

# 光云图

Fig. 8 Image with accurate exposure adjusted by index curve of exposure value on 16:36，June 3，2017

![](images/9de3b61e01f0cd183c711942c0bce00c02aa9b3186e5efd6e1191c0b9d753847.jpg)  
图9根据曝光值索引曲线和曝光值误差，拍摄得到的2017年7月12日03时

至09时黎明日出过渡阶段的正确曝光云图序列

Fig. 9 Images with accurate exposure adjusted by index curve of exposure value with errors from 3:00 to 9:00，July 12，2017

![](images/fc2d724244a12fc04015185cc80e6119fd6b23bc5b3e8d0ba9189a34ecda2a8f.jpg)

图10根据曝光值索引曲线和曝光值误差，拍摄得到的2017年7月12日16时

# 至21时黄昏日落过渡阶段的正确曝光云图

Fig. 10 Images with accurate exposure adjusted by index curve of exposure value with errors， froml6:00 to 21:00，July 12，2017

![](images/749b7c64066b4019a95c5c4ae57f1a8dc88106be80cacb07df9fc7b1164eb159.jpg)

图11根据曝光值索引曲线和曝光值误差，拍摄得到的2017年7月12日10时至15时之间阳光直射时间段的正确曝光云图序列

Fig. 11 Images with accurate exposure adjusted by index curve of exposure value with errors from 10:00 to 15:00， July 12， 2017

OOOOO0 O 请用 一   
2017-01-23-1-2146jg017012-1-4jpg 2017-01-23-01-41-46jpg 2017-01-23-01-51-46.jpg 2017-01-23-02-01-46.jpg 2017-01-23-02-11-46pg 2017-01-23-21-4jpg207013-4pg O   
201714g 2017-01-23-04-21-46jpg 2017-01-2-04-31-46jpg20170123-441-46jpg 2017-01-23-04-51-46jpg   
2017-01-23-05-21-46.ipq 2017-01-23-05-31-46.ipq 2017-01-23-05-41-46.ipg 2017-01-23-05-51-46.ipq 2017-01-23-06-01-46.ipq 2017-01-23-06-11-46ipq 2017-01-23-06-21-47.ipg 2017-01-23-06-31-19.ipg

图12根据曝光值索引曲线和曝光值误差，拍摄得到的2017年1月23日00 时

# 至06时之间正确曝光云图序列

Fig. 12 Images with accurate exposure adjusted by index curve of exposure value with errors ，from O:00 to 6:00，January 23，2017

# 2.4全天云图中云识别

已有不少文献阐述对全天相机拍摄到的云图进行云自动识别的方法。如文[3]介绍了一种数字云量白天观测处理方法，选择合适的云判别的辐射比阈值，可对全天云量进行正确判断。文[4]提出了利用图像直方图理论直接计算和阈值分割两种计算云量的方法，均可对白天云图进行正确的云量判断。本文采用文[5]提出的最大类间方差自适应阈值算法对白天云进行识别。

由于全天云图为鱼眼镜头拍摄，在执行云判别前，需对云图进行预处理：先将原始云图裁剪成 $1 9 0 0 * 1 8 0 0$ 像素的文件，再对云图中的非天空部分进行排除，排除后剩下的像素被分成若干小方格，最后对每个小方格进行云判断，判断流程如图13。

![](images/8023a67c85bfeec3b9e135cfb3e171cff825a699dac6a9b262a3febb22013826.jpg)  
图13最大类间方差自适应阈值算法识别云流程

Fig. 13 Flowchart of cloud detection by maximum interclass variance adaptive threshold selection method

以下为具体事例：

![](images/f3f8adabd6724f82fc0d1d1d8c5c431c89c6f2ba2b4af4d810ac4bd4b11bdc80.jpg)

（3）通过最大类间方差法计算整个图像的自适应阈值T

![](images/ac2743bf01d927b1af6f3efdf9b82ac538fc33d824775ef4b1b0ac3236caab24.jpg)

（4）逐个像素判断是否为云。先判断蓝红波比值是否符合云标准，符合直接判断为云。如不符合，再通过像素点灰度值与自适应阀值 $T$ 进行比较，小于阀值则为云。

通过自适应阀值分隔后，白色部分为云。

![](images/b15a1db1d6a4e26bb98461b705089454d322c13f383bc934ed3db4967e678c2f.jpg)

本例中计算出自适应阀值 $T \mathrm { = ~ } 1 6 7$

云判别完成后，系统获取图片信息中的拍摄时间、感光度、光圈值、曝光时间，并连同云量值以及文件名存入数据库中，每10分钟执行一次。

# 3结语

深圳市天文台全天云图监测系统上线后运行稳定，各时间段以及各种天气环境下均能拍摄曝光正确的全天云图，为天文观测提供了有效保障，同时也为观测数据提供了质量控制的参考依据。在流星雨等重要天象事件期间，系统还可根据不同需求，设置拍摄间隔时间，以记录重要天象信息，图14为监测到的火流星。此外，深圳市天文台还装有天空成像仪，可提供白天低分辨率云图、云量和云高信息，未来，可将二者进行参照对比，进行数据标校。

![](images/4d2cb8a4cea712c4362eb9c6489a7d8f096d907631023978faa6d5794cf5a2be.jpg)  
图142016年12月15日晚监测到的火流星

Fig. 14 A meteor captured by the all-sky cloud monitoring system on

December 15，2016

# 参考文献：

[1]彭焕文，辛玉新，和寿圣，等.丽江天文观测站全天相机介绍[J].天文研究

与技术,2015，12(1):89-95.

Peng Huanwen, Xin Yuxin, He Shousheng, et al. An introduction to the all-sky camera at the YNAO Lijiang astronomical station [J]. Astronomical Research & Technology, 2015, 12(1):89-95.

[2] Jacobson R E, Ray S F, Atteridge G G， et al. The manual of photography: photographic and digital imaging [M]. 9th ed. [S.l.]: Focal Press, 2000: 318.

[3]施洋，姚永强，刘立勇.天文选址数字云量白天观测处理方法[J].天文研究与技术—国家天文台台刊，2008，5(4):415-419

Shi Yang, Yao Yongqiang, Liu Liyong. A method for observing and counting daytime cloud amounts in an astronomical site survey [J]. Astronomical Research & Technology-Publications of National Astronomical Observatories of China， 2008, 5(4):415-419.

[4]杨健，沈彦燕，宋志刚.基于图像处理技术的地基云图云量的识别[J].气象水文海洋仪器，2009(3):42-45.

Yang Jian, Shen Yanyan, Song Zhigang. The recognition of ground nephogram cloudage based on imageprocessingtechnology [J]. Meteorological, Hydrological and Marine Instruments,2009(3):42-45.

[5]杨俊，吕伟涛，马颖,等.基于自适应阈值的地基云自动检测方法[J].应用气象学报，2009，20(6):713-721.

Yang Jun, Lv Weitao, Ma Ying, et al. An automatic groung-based cloud detection method based on adaptive threshold [J]. Journal of Applied Meteorological Science, 2009,20(6):713-721.

# Design and Implementation of the All-Sky Cloud Monitoring System at Shenzhen Astronomical

# Observatory

Mei Lin1,Wu Xiang², Zhou Zuochao²

(1. Shenzhen National Climate Observatory (Shenzhen Astronomical Observatory), Shenzhen 518040,Guandong，China; Email: meilin4587@163.com；2. Shenzhen YSF Technology Co., Ltd., Shenzhen 518040, Guangdong, China)

Abstract: Al-sky cloud monitoring is of key importance for astronomical observation.Most astronomical observatories in the world have allsky cloud cameras now. But one common concern is to get accurate exposure in a vast range of illumination conditions.To solve this problem，Shenzhen Astronomical Observatory has developed independently an automatic exposure control system. By using the parameters of the allsky camera,this system calculates an index curve of exposure value, with error of O.3,to adjust the exposure of each picture that the camera captures. And based on the pictures with accurate exposure,cloud can be effectively detected by the maximum interclass variance adaptive threshold selection method.It has been proved in practice that this system works well in varying illumination changes,obtaining accurate exposure even in low-light circumstances,and therefore providing substantial convenience to observation planning.

Key words: Al-sky camera; Automatic exposure; Exposure parameters; Cloud detection; Image processing