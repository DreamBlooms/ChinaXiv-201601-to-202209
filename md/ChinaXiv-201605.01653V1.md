# 中国GNSS-R机载实验综合评估：河流遥感

白伟华①，夏俊明①，万玮②③，赵利民④③，孙越强①，孟祥广①\*，柳聪亮①，谌华①，杜起飞①，王冬伟①，赵丹阳①，王先毅①，程诚⑥

$\textcircled{1}$ 中国科学院国家空间科学中心，北京100190;  
$\textcircled{2}$ 清华大学水科学与工程国家重点实验室，北京100084;$\textcircled{3}$ 清华大学水利工程学院，北京100084;  
$\textcircled{4}$ 中国科学院遥感与数字地球研究所，北京100101;$\textcircled{5}$ 国家航天局航天遥感论证中心，北京100101;  
$\textcircled{6}$ 国家知识产权和专利局，北京100088  
$*$ 联系人,E-mail: xgmeng @nssc.ac.cn

国家自然科学基金(41405040,41405039)、中国科学院科研装备预先研究项目(YZ201129)和"十二五"民用航天研究项目(Y1K0030044)资助

全球卫星导航定位系统的反射信号(GNSS-R)遥感是反演陆地和海洋表面地球物理参数的有力工具．而机载GNSS-R是一个很重要的实验平台，因为它不仅可以为空基实验提供校准依据，而且在中小尺度目标(比如河流和湖泊)的遥感方面独具优势.机载实验的研究主要包括海面风场的反演、海面高度的测量和土壤湿度的探测．首次反演海面风场和土壤湿度的机载GNSS-R实验都是由美国NASA和科罗拉多州立大学组织实施的．之后在西班牙IEEC (Institut d'Estudis Espacialsde Catalunya)/CSIC (Consejo SuperiordeInvestigaciones Cientificas)、Starlab实验室与NASA的联合实验中，海面风场的反演精度已经能够达到 $2 \ \mathrm { m / s }$ 两个最早利用GNSS-R探测海面高度的机载GNSS-R实验都是美国的JPL(JetPropulsionLaboratory)组织实施的,其中海面平均高度的探测精度已经达到了厘米级．在中国，北京航空航天大学和中国科学院遥感与数字地球研究所也组织了相应的机载GNSS-R实验.

本文讲述了2014年5月30日在中国河南上街地区开展的一次机载实验，此次实验有两个目的：（1）检测中国科学院国家空间科学中心研发的GNSS-R有效载荷的实验观测能力；（2）研究机载GNSS-R土壤湿度测量和河流遥感的具体算法，其中河流遥感包括高度和流速测量．本次机载试验是中国首次机载GNSS-R土壤湿度遥感试验，也是国际上首次开展的机载河流遥感试验．下面简要介绍河流遥感中的测高和测流速：

（i）河流表面高度测量．反射信号的传播距离比直射信号长，目标的高度信息就是从这段延时中提取出来的，这是GNSS-R的测高原理.GNSS-R码延迟遥感测高结果与GPS双频差分定位测高(其测量设备包括一个水面浮标和两个GPS基准站)结果对比，两者的偏差和标准偏差分别为-0.1053和$0 . 4 7 6 4 \mathrm { ~ m ~ }$ ·

（ii）河流流速测量．周跳和相位噪声会影响反射信号开环跟踪残差相位的高频谱部分，残差相位频谱中的低频分量会受到目标河流流速的影响(假定在短时观测时间内河流的流速是一个常向量)，所以，河流流速的信息可以从GNSS反射信号的残差相位谱中剥离出来．试验中，GNSS反射信号开环跟踪后取得的PRN24星的残差相位频率谱靠近零点的低频分量最大值为 $- 0 . 3 8 9 8 \mathrm { ~ H z }$ ，通过使用相关公式，可算出河流流速为 $0 . 1 4 7 1 \mathrm { \ m } / \mathrm { s }$ ．与水面浮标测出的流速 $0 . 1 2 \mathrm { \ m / s }$ 相比，GNSS-R的解算结果是合理的.

此次实验在河流测高的基础上，探索发现了GNSS-R的另一全新应用领域，即河流流速的测量．而且，通过码相位延迟测高法的测量结果与用GPS双频差分定位的结果相一致.GNSS-R测高的结果表明，使用此方法时，一分钟的滑动平均就可以达到分米级的精度．通过与现场的测量结果对比，GNSS-R的流速测量结果是合理的，其误差大概在 $0 . 0 2 7 ~ \mathrm { \ m / s }$ ，这也进一步说明了GNSS-R流速测量的可行性和有效性，从而为进一步的GNSS-R星载应用奠定了基础.