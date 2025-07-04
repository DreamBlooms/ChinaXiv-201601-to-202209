# 基于统计学特征的android恶意应用检测方法

冷波ä，李建彬 b†

(中南大学a.信息科学与工程学院;b.信息安全与大数据研究院，长沙 410083)

摘要：针对 Android 恶意应用检测中忽略特征统计学意义的问题，提出一种基于统计学特征的 Android 恶意应用检测方法。该方法提取应用统计学特征作为训练数据集，并采用聚类算法预处理恶意数据集以降低个体差异性对实验结果的影响。另一方面，该方法结合特征和多种机器学习算法（如线性回归、神经网络等）建立了检测模型。该方法提出的两个模型准确率均能达到 $9 5 \%$ 以上，检测时间相比于对比实验也能大幅度降低。实验结果表明，应用的统计学特征能够很好地区分良性和恶意应用，并且通过聚类算法预处理数据能够提高检测精度。

关键词：统计学特征；机器学习；个体差异性；恶意应用检测 中图分类号：TP309 doi: 10.3969/j.issn.1001-3695.2018.03.0173

# Android malicious application detection method based on statistical features

Leng Boa, Li Jianbinb† (a.Schoolof InformationScience&Engineering,b.Information Security&BigData Research Institute,Central South University,Changsha 410083,China)

Abstract: Aiming at the problem of ignoring the statistical significance of features in detectionof Android malicious applications,an Android malicious application detection method basedon statistical features was proposed.This method extracted thestatisticalcharacteristicsofthetrainingdatastand usedaclusteringalgorithmtopreprocessthe malicious data setforreducingthe impactof individualdiferencesontheexperimentalresults.Ontheotherhand,this methodcombinedthe featuresandvarious machinelearningalgorithms (suchas inearregresion,neuralnetwork,etc.)toestablishadetectionmodel. The accuracy rate of the two models proposed by this method could reach more than $9 5 \%$ , and the detection time could be greatlyreduced compared with thecomparison experiment.Experimentalresultsshow thatthe statisticalcharacteristicsof the applicationcan beused to distinguishbetween benignand malicious applications,and preprocessing thedata byclustering algorithm can improve the detection accuracy.

Key words: statistical features; machine learning; individual difference; malware detection.

# 0 引言

据International Data Corporation (IDC)[1]报道，从 2016 年第一季度到2017年第一季度Android 智能手机在全球智能手机市场份额中一枝独秀，以压倒性的优势遥遥领先其他的智能手机平台。智能手机的迅猛发展导致了人们生活发生了翻天覆地的变化。一方面智能手机已经不再是简单的通信工具，用户使用智能手机可以网上冲浪、浏览视频、购物聊天、office 办公等；另一方面智能手机也成为了用户信息的小小缩影，它包含了用户的几乎所有信息，如常见的用户身份信息、银行卡信息、通讯录等。一旦丢失或者被不法分子盗取，其后果不堪设想。同时，随着Android设备的日益普及，便利的网络和高价值的个人信息已经吸引了恶意软件开发者的极大兴趣。360安全中心[2]称Android平台平均每天新增恶意应用2.1万个。因此，如何检测出Android恶意软件并阻止其对用户造成危害是非常迫切的。同时，这也是非常具有挑战性。目前，关于Android应用程序检测的研究主要集中在结合特征和机器学习算法来校验应用程序的恶意与否。通过分析Android应用程序的源代码或者二进制信息，恶意应用研究者提出了利用权限特征[3]、组件特征[4]、dex特征[5]以及smali特征[进行恶意应用检测模型的训练。其中，权限特征和组件特征均来自Android应用的资源清单文件AndroidManifest.xml。应用程序申请的权限和组件由特殊的标签所包含。在应用程序安装时，Android系统会读取该文件并进行配置。Dex特征是指从解压后应用程序的dex文件中解析出来的特征。Dex文件是Android虚拟机Dalvik的执行文件并且有自己固定的格式。而smali特征来源于反编译应用程序后的smali文件。通过提取应用程序的静态特征构建的检测方法能够准确地进行恶意应用检测。

但是上述方法着重于理解每个特征的含义，并且忽视了个体的特殊性。同时，恶意应用的检测时间尚未受到足够的重视。因此，本文提出基于统计学特征的Android恶意应用检测方法，它利用权限、组件、dex信息和smali信息并结合多种机器学习算法（如SVR、MLP等）用于恶意软件检测。该方法包括两个模型。每个模型分析和提取统计特征，充分降低个体差异性对应用检测的影响。模型1旨在更快地检测，而模型2提供更高的检测精度。本文的贡献如下：a)从崭新的角度分析Android应用，提取apk代码的统计学特征，而不是关注特征本身的意义;b)首次通过聚类算法降低个体差异性的影响，并且根据每簇大小的波动性选择聚类数目来最小化随机聚类的影响;c)使用双层学习模型以获得更好的准确性;d)根据不同场景提供两种模型。模型1用于更快的检测，而模型2用于更精确的检测。

# 1 相关工作

Android恶意应用检测方法主要分为静态检测、动态检测以及动静结合的检测方法。

静态检测方法主要通过分析Android应用的源代码或二进制信息、提取权限、组件、函数调用、Intent、ICC（组件间通信）、操作码等内容并结合多种机器学习算法进行分析检测。权限、组件分析是指利用AndroidManifest.xml文件中声明的permission、activity、service、provider、receiver 等内容进行分析7]。其中权限代表应用程序的执行能力，能够很好地反映应用的潜在行为。而其他的组件信息是应用程序的入口，同样也能够反映应用程序的执行流程。函数调用分析是通过对应用程序源代码中使用的API进行结构化的处理并形成函数调用图。函数调用图从每个应用程序MainThread开始执行，中间能够进行复杂的逻辑处理，最后由系统保持应用程序状态。利用生成的函数调用图能够全面地反映应用程序的执行过程[8]。Android应用中组件通信的载体是AndroidIntent。Intent能够跨越组件边界传递数据并且几乎所有的恶意应用都离不开Intent。Feizollah等人[9]证明了AndroidIntents作为检测恶意应用程序的特征的有效性。Idress等人[10]利用权限和意图构建了识别Android恶意软件应用程序的框架。ICC（组件间通信）是指Android应用中的四大组件之间相互传递数据。通过分析ICC在应用中的使用可以进行Android恶意应用的检测[11]。Android应用本质是二进制文件，是一串0101序列。通过分析其格式并提取操作指令可以有效地甄别恶意行为[12]。

动态分析是指利用沙盒技术，模拟用户的点击事件，自动地完成应用程序的安装、运行、卸载等操作，并记录信息以检测恶意应用的分析方法。应用程序在沙盒环境中的行为可以用于产生模型。不同的模型属于不同的类别。当应用被检测出不属于良性应用类别时就是恶意应用[13]。通过改变点击事件序列可以让应用程序产生不同的行为，并比较应用的行为以确定应用程序的恶意性[14]。系统数据在部分应用运行时会被应用所使用，研究者通过将系统数据打上标记并跟踪标记数据分析应用的信息流从而检测出应用的异常行为[15]，并且在应用运行过程中监测应用产生的网络流量也能较好地反映应用的行为[16]。部分恶意应用会检测自身是否处于真机状态从而隐藏自己的行为，因此Salehi等人[17创建了一个基于主机的轻量级的检测系统，该系统在移动设备上进行检测，并可以重建应用程序的行为。

静态分析方法具有检测速率快、准确率高的特点，但不能检测出新生的恶意应用；而动态检测方法能够检测新生的恶意应用，但又特别地耗费资源。为了充分发挥两者的优势并弥补两者的不足，有研究者提出动静结合的Android恶意应用检测方法。动静结合的检测方法是指在恶意应用的检测过程中先使用静态分析方法进行检测，如果检测出是恶意应用，则不需要提交动态检测方法检测，否则就提交给动态分析方法进行检测[18]。

上述的几种检测方法是目前Android恶意应用检测研究的中心，但是这些方法都强调特征本身的内容，而忽视了特征的统计学意义，并且没有很好地解决个体差异性的影响。本文提出的方法对Android恶意应用检测具有一定的参考意义。

# 2 设计与实现

基于统计学特征的Android恶意应用检测方法是一种静态的检测方法。该方法包括三部分，即收集数据、提取特征和训练模型(图1)。

![](images/b614c0c3a7b05e2890bc43249a9c5be2ab72f9a083c70131fce2f0ec083886f4.jpg)  
图1系统架构

# 2.1数据收集

本文收集了大量的恶意样本和良性样本。其中恶意样本均来自Arp $\mathrm { { D } ^ { [ 1 9 ] } }$ 数据集，该数据集包含5560个恶意应用，并且属于179个不同的恶意软件家族，如木马、广告软件、间谍软件和信息窃取应用等。良性样本均来自Google Play 商店。GooglePlay商店是Android智能手机的官方应用市场，并且具有严格的应用检测制度。在GooglePlay 市场上出现的应用程序必须经过开发者、应用程序代码、元数据等多重检测才能发布。所以可以认为GooglePlay上发布的应用是良性的。良性样本数据集包含来自GooglePlay 中27个目录共3000个良性应用。

# 2.2提取特征

Apktool[20]可用于对Android apk文件进行反编译，并可轻松将资源解码为最接近的原始形式。Unzip[21]可以用来解压apk文件。在本文中利用这两个工具来提取特征。通过反编译apk 获得了大量文件夹和文件，这些文件如图2所示。

![](images/e367e6c3cc81424a9dcf72518675617c94e66967b11d93488ef73f6c3264aa96.jpg)  
图2 反编译示例

AndroidManifest.xml声明应用程序申请的所有权限和组件。Apktool.xml包含一些附加信息，如版本和版本信息。Res文件夹包含不同的资源。Smali文件夹包含来自Java字节码的smali文件，而original文件夹包含一些二进制信息。图3显示了解压缩的apk文件示例。

![](images/ac36f4cad7813eb51c528c0d4f2a6e9c0e1897092b40cb6e779f36187ac61398.jpg)  
图3解压缩示例

本文分析了图2中的AndroidManifest.xml并提取了大量特征，如一个apk有多少activity。表1显示了该应用程序的一个示例。

表1权限组件特征  

<html><body><table><tr><td>特征</td><td>示例</td></tr><tr><td>Activity</td><td>Activity : 10</td></tr><tr><td>Receiver</td><td>Receiver : 5</td></tr><tr><td>Service</td><td>Service : 3</td></tr><tr><td>Action</td><td>Action : 68</td></tr><tr><td>Category</td><td>Category :16</td></tr><tr><td>Intent-filter</td><td>Intent-filter : 20</td></tr><tr><td>Meta-data</td><td>Meta-data :10</td></tr></table></body></html>

DexFormat[22]列出了.dex文件遵循的特定格式，本文通过分析其格式收集了表2中列出的特性。

表2 Dex 特征  

<html><body><table><tr><td>特征</td><td>示例</td></tr><tr><td>Link_szie</td><td>Link_size:0</td></tr><tr><td>Proto_ids_size</td><td>Proto_ids_size:6899</td></tr><tr><td>String_ids_size</td><td>Stirng_ids_size:28714</td></tr><tr><td>Field_ids_size</td><td>Field_ids_size:20594</td></tr><tr><td>Type_ids_size</td><td>Type_ids_size:5463</td></tr><tr><td>Method_ids_size</td><td>Method_id_size:35882</td></tr></table></body></html>

来自同一应用程序的所有smali文件都通过反编译存储在smali文件夹中。每个.smali文件都遵循固定的语法格式。本文记录来自smali文件的特征信息的数量，如静态域和保护域。

表3列出部分统计特征。

表3Smali 特征  

<html><body><table><tr><td>特征</td><td>示例</td></tr><tr><td>Avg_parameter_num</td><td>Avg_paramter_num:7.2146</td></tr><tr><td>Min_invoke_num</td><td>Min_invoke_num:4.66666</td></tr><tr><td>Method_num</td><td>Method_num:42.428571286</td></tr><tr><td>Min_register_num</td><td>Min_register_num:0.76190</td></tr></table></body></html>

本文提取的统计学特征包括权限组件、smali和dex特征。这些特征与应用程序运行密切相关，部分特征还能清晰地反映应用程序所能执行的行为。所以本文提取的特征具有一定的意义。

# 2.3构建模型

![](images/45b014d2ce9e7ee3a111f44074bad82ac95bccdb37a04fb1dcc79024ba1701ce.jpg)  
图4所示的学习训练模块是本文的重要组成部分。  
图4训练模块

该训练模块总共由两层组成。

第一层首先通过聚类算法降低恶意应用个体差异性对实验结果的影响。因为聚类算法本身在选取质点中心时具有随机性，所以通过多次实验的方法选取聚类数目波动性最小的聚类结果作为最终聚类结果。随后，本文在恶意应用聚类产生的每簇中加入良性样本组成训练集，并利用多种机器学习算法进行训练。所用的机器学习算法包括线性回归、支持向量机回归、神经网络、随机森林、K-近邻算法、岭回归以及贝叶斯岭回归算法。最后，本文抽取剩余数据集中的部分恶意和良性样本构建测试集来评估每个模型，并获得恶意应用每个簇每个算法的AUC(ROC 曲线下面积)，AUC 值最大的模型就是每簇的最终模型。

在训练的第二层当中，本文首先构建了临时训练集和测试集。随后，利用第一层恶意应用每个簇模型计算临时训练集和测试集，每簇模型得到的结果并结合样本标签组成最终训练集和测试集。最后，与第一层相同，在训练集执行了多种算法，使用测试集进行测试以获得每种算法的AUC，并决定AUC最佳的模型作为第二层的最终模型。

# 3 实验结果与分析

本文提供两种模型来满足不同场景的需求。模型1结合了权限、组件和smali特征。模型2结合了权限、组件和dex 特征。以下以模型为单位分别讨论。

# 3.1聚类分析

KMeans算法是最受欢迎的聚类算法之一。其通过随机选取质心并将样本放入一个最近质心类中来实施聚类。因此随机质心将导致聚类簇的大小不一。当质心数从3变化到5时，本文运行实验10次，其结果如图5所示。在图5的每个子图中，横坐标轴表示质心的数目，而纵轴表示每个簇的大小。模型1和2在四个质心时保持每个簇的大小的基本稳定。因此，聚类算法显示聚类效果最稳定的簇数大小是4。

![](images/cc658d2873b53160ccfbf3e959ccd39a60d2a81321b34222990c7a8d1de76677.jpg)  
图5聚类分析

# 3.2 簇模型

基于多种算法，本文记录了每簇每个算法的真阳性率（TPR）如下：

$$
\begin{array} { l } { { T P R \displaystyle = \frac { T P } { T P + F N } } } \\ { { y _ { i } = T P R ( C l u s t e r _ { i } d l g o r i t h m _ { j } ) ( i = 1 , 2 , 3 , 4 ; j = 1 , 2 , 3 , 4 , 5 , 6 , 7 ) } } \end{array}
$$

其中：TP代表真阳性样本，阳性样本检测结果为阳性；FN 显示假阴性样本，检查为阴性但实际是阳性的样本。 另外，计算每个簇每个算法的假阳性率（FPR）如下：

$$
\begin{array} { l } { { F P R { = } \displaystyle \frac { F P } { F P + T N } } } \\ { { y _ { i } { = } F P R ( C l u s t e r _ { i } d l { \mathrm { g } o r i t h m } _ { j } ) ( i { = } 1 { , } 2 { , } 3 { , } 4 { ; } j { = } 1 { , } 2 { , } 3 { , } 4 { , } 5 { , } 6 { , } 7 ) } } \end{array}
$$

其中：FP表示假阳性样本，该样本为阴性但检查为阳性；相反，TN显示真阴性样本，阴性样本为阴性且检测结果也为阴性。

此外，本文记录了每个簇每个算法的准确度，即预测的正确结果除以所有结果。

$$
\begin{array} { l } { { A c c u r a c y { = } \displaystyle \frac { T N + T P } { F P + T P + F N + T N } } } \\ { { y _ { i } = A c c u r a c y ( C l u s t e r _ { i } d \ l g o r i t h m _ { j } ) ( i { = } 1 , 2 , 3 , 4 ; j { = } 1 , 2 , 3 , 4 , 5 , 6 , 7 ) } } \end{array}
$$

然后，本文通过绘制ROC曲线获得了每簇算法的AUC。$y _ { i } = A U C ( C l u s t e r _ { i } A l g o r i t h m _ { j } ) ( i = 1 , 2 , 3 , 4 ; j = 1 , 2 , 3 , 4 , 5 , 6 , 7 )$ (4)

本文记录了最优算法的AUC，如表4和5所示。

表4Dex 最优算法  

<html><body><table><tr><td>Dex簇</td><td>最优算法</td><td>AUC(曲线下面积)</td></tr><tr><td>第一簇</td><td>MLPRegressor</td><td>0.960402</td></tr><tr><td>第二簇</td><td>LinearRegression</td><td>0.967626</td></tr><tr><td>第三簇</td><td>LinearRegression</td><td>0.950732</td></tr><tr><td>第四簇</td><td>BayesianRidge</td><td>0.97165</td></tr></table></body></html>

表5Smali最优算法  

<html><body><table><tr><td>Smali簇</td><td>最优算法</td><td>AUC(曲线下面积)</td></tr><tr><td>第一簇</td><td>MLPRegressor</td><td>0.98157</td></tr><tr><td>第二簇</td><td>Ridge</td><td>0.932828</td></tr><tr><td>第三簇</td><td>LinearRegression</td><td>0.964847</td></tr><tr><td>第四簇</td><td>MLPRegression</td><td>0.970324</td></tr></table></body></html>

# 3.3最终模型

本文使用每个簇模型将临时训练集和测试集转换为最终集合。每个模型计算临时集以获得一列数据。由于四个簇模型，所以获得了四列，如下所示：

$$
y _ { i } = M o d e l C l u s t e r _ { i } ( t e m p o r a r y \lrcorner s e t ) ( i = 1 , 2 , 3 , 4 )
$$

然后，本文合并四列的数据和标签列如下：

$$
Z = \{ y _ { i } , l a b e l \} ( i = 1 , 2 , 3 , 4 )
$$

本文对模型1和2的最终训练集和测试集执行了不同的算法。最后，实验结果记录在表6和7中。

表6Dex 最终算法  

<html><body><table><tr><td>算法</td><td>AUC(曲线下面积)</td></tr><tr><td>SVR</td><td>0.9625</td></tr><tr><td>MLP</td><td>0.9735</td></tr><tr><td>RandomForest</td><td>0.9715</td></tr><tr><td>KNeighbors</td><td>0.9716</td></tr><tr><td>Ridge</td><td>0.9635</td></tr><tr><td>LinearRegression</td><td>0.9634</td></tr><tr><td>BayesianRidge</td><td>0.9635</td></tr></table></body></html>

表7Smali最终算法  

<html><body><table><tr><td>算法</td><td>AUC(曲线下面积)</td></tr><tr><td>SVR</td><td>0.9854</td></tr><tr><td>MLP</td><td>0.9938</td></tr><tr><td>RandomForest</td><td>0.9867</td></tr><tr><td>KNeighbors</td><td>0.9825</td></tr><tr><td>Ridge</td><td>0.9835</td></tr><tr><td>LinearRegression</td><td>0.9835</td></tr><tr><td>BayesianRidge</td><td>0.9835</td></tr></table></body></html>

结果显示模型1和2中MLPRegressor具有最好的AUC。因此，本文使用MLPRegressor作为最终算法，并基于此算法构建模型。

# 3.4对比分析

在Arp $\mathrm { D } ^ { [ 3 3 ] }$ 的DREBIN中，研究人员结合SVM（支持向量机）算法和Android应用程序的大量特征来区分恶意和良性应用程序。因为本文的恶意应用均来自DREBIN 数据集当中，所以本文将该方法与本文提出的方法进行比较，并从时间效率

![](images/24699a675ca8794667b897fef51f0351c5ee989e407fc2bb57eb867b77c13ccf.jpg)  
和准确率方面进行对比，其结果如图6和7所示。  
图6时间效率比较  
图7准确率比较

1.2 1   
0.8   
0.6 L   
0.4   
0.2 0 Drebin Dex模型 Smali模型 ■准确率 ■假阳性率 ■真阳性率

从图6可知，使用相同的测试样本，使用模型1显着减少了检测时间，而图7显示在模型2中获得了最高的准确度。

# 4讨论

以上介绍了本文工作的创新性，实验分析以及数据结果对比分析。相比于之前的相关工作，本文能在检测效率和精度上占居一定优势，但是该方法仍然存在不足。下面简要介绍本文方法的局限性和下一步工作的方向。

本文提出的基于统计学特征的Android恶意应用检测方法通过提取样本中的特征进行模型训练和检测，所提取的特征维度还较低，只有四个维度。不能充分地反映统计学特征在Android恶意应用检测中的价值。另一方面，由于目前研究中并没有合适的良性样本集，所以本文在选取良性样本时没有做到完全的适合，而是采取其他办法解决。最后整体的样本容量也需要扩充才能进一步提高检测精度。

# 5 结束语

现有的工作已经提取了来自Android应用程序的多个方面的数据作为特征进行Android恶意应用检测，其中包括权限、组件、动态日志、网络流量等。但是目前的研究只是分析了特征背后所具有的实际意义，比如权限代表应用能够完成的操作，而忽视了这些特征的统计学意义，并且几乎所有的检测方法在检测时间上都有所欠缺。在本文的工作中利用聚类算法来最小化个体差异性的影响，并结合多种机器学习算法训练模型。结果显示，所提出的模型需要较少的时间来检测应用程序集，并且具有较高的检测精度。在未来的工作中，将进一步探索特征与个体之间相关性的影响，以及从不同角度提取特征，以提高Android 恶意应用的检测准确性。

参考文献：   
[1]Simon B,Melissa C,Peggy C,et al. Smartphone OS [EB/OL]. (2018-04- 20).https://www.idc.com/promo/smartphone-market-sh are/os.   
[2] 360 烽火实验室,360互联网安全中心.2017年Android 恶意软件年度专 题报告[EB/OL].(2018-03-02）http://zt.360.cn/11010 61855. php?dtd101061451&did=491056914.   
[3]Liang Shuang,Du Xiaojiang. Permision-combination-based scheme for Android mobile malware detection [C]// Proc of IEEE International Conference on Communications.2014: 2301-2306.   
[4]LiLi, Bartel A,Bissyandé TF,et al. IccTA: detecting inter-component privacy leaks in Android apps [C]/ Proc of IEEE//ACM Intermational Conference on Software Engineering.2015: 280-291.   
[5]MaiorcaD,Mercaldo F,Giacinto G,et al.R-PackDroid:API package-based characterization and detection of mobile ransomware [Cl// Proc of Symposium on Applied Computing. 2017: 1718-1723.   
[6]Tang Junjie,Cui Xingmin,Zhao Ziming,et al.NIVAnalyzer:a tool for automatically detecting and verifying next-intent vulnerabilities in Android apps [C]/ Proc of IEEE International Conference on Software Testing, Verification and Validation. 2017: 492-499.   
[7]Bhattacharya A,Goswami R T.DMDAM: data mining based detection of Android malware[C]// Proc of Icic2 Inteligent Computingand Communication. 2017.   
[8]NarayananA,Liu Yang, Chen Lihui,et al. Adaptive and scalable Android malware detection through online learning [C]//Proc of International Joint Conference on Neural Networks. 2016: 157-175.   
[9]Feizollah A,Anuar NB, Salleh R,et al.AndroDialysis: analysis of Android intent effectiveness in malware detection [J]. Computers & Security,2017, 65 (C): 121-134.   
[10] IdreesF,Rajarajan M,Conti M,etal.PIndroid: a novel android malware detection system using ensemble learning methods [J]. Computers & Security, 2017,68: 36-46.   
[11] Xu Ke, Li Yingjiu, Deng R H. ICCDetector: ICC-based malware detection on Android [J].IEEE Trans on Information Forensics& Security,2016,11 (6): 1252-1264.   
[12] Yan Jinpei,Qi Yong,Rao Qifan.LSTM-based hierarchical denoising network for Android malware detection[J].Security& Communication Networks,2018,2018: 1-18.   
[13] Saracino A, Sgandurra D, Dini G,et al. MADAM: effective and efficient behavior-based Android malware detection and prevention [J]. IEEE Trans on Dependable& Secure Computing,2018,PP(99):1-1.   
[14] Tam K,Khan SJ,Fattori A,et al. CopperDroid: automatic reconstruction of Android malware behaviors [C]//Proc of Network and Distributed System Security Symposium.2015.   
[15] Chen Li,Zhang Mingwei,Yang CY,et al.POSTER:semi-supervised classification for dynamic Android malware detection [C]//Proc of ACM Sigsac Conference on Computer and Communications Security.2017: 2479- 2481.   
[16] ZulkifliA,HamidIRA,ShahWM,etal.Android malware detection based on network traffic using decision tree algorithm [C]//Proc of International Conference on Soft Computing and Data Mining.Cham: Springer,2018: 485-494.   
[17] Salehi M,Amini M.Android malware detection using Markov chain model of application behaviors in requesting system services [EB//OL].(2017). arXiv preprint arXiv: 1711. 05731.   
[18] Narayanan A,Chandramohan M, Chen L,et al.A multi-view context-aware approach to Android malware detection and malicious code localization [J]. Empirical Software Engineering,2017(6):1-53.   
[19]Arp D,Spreitzenbarth M,Hübner M,et al.DREBIN:effective and explainable detection of Android malware in your pocket [C]// Proc of Network and Distributed System Security Symposium.2014.   
[20] Connor T,Ryszard W.A tool for reverse engineering Android apk files [EB/OL].(2017-09-21) . https://ibotpeaches.github.io/Apktool/.   
[21]Ed G,Christian S,Mike W,et al.Info-ZIP[EB/OL].(2008-07-07）. http://www. info-zip.org/.   
[22] Google company. dalvik executable format [EB/OL].(2017-06-20）. https://source.android.com/devices/tech/dalvik/dex-format.