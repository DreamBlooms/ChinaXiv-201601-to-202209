# GPS数据处理策略对成果精度的影响及可靠性分析

邓标」郭若成² 李晓明」王靖」邓岳川'

（1.滁州学院 地理信息与旅游学院滁州239000；2.武汉地震计量检定与测量工程研究院有限公司 武汉 430000）

摘要：高精度GPS 数据处理的成果精度往往受海潮模型、卫星轨道约束模式设置、精密星历产品等数据类型及处理策略的制约。文中在考虑上述影响因素的前提下进行相关实验，并基于误差理论提出一种增加基线解算回数组合平差的方法，以提高基线解算精度。实验结果表明，数据处理中置入海潮模型较未采用海潮模型精度更好，FES2004模型的内外符合精度整体最优，近海区NAO99b外符合精度占优，其它海潮模型基本相当；松弛轨道模式内符合精度较固定轨道模式内符合精度好，但外符合精度较轨道固定精度稍差；不同的精密轨道产品对最终解算结果影响较小；增加基线解算回数组合平差的方法对数据处理成果精度的提高具有明显效果，且在几种精密星历下均表现良好的收敛性。

关键词：海潮模型；轨道模式；星历产品；基线解算回数【中图分类号】P288.4 【文献标识码】A

# The Influence of GPS Data Processing Strategy on the Accuracy of Results and Reliability Analysis

Deng Biao,Guo Ruocheng,LI Xiaoming ,Wang Jing,Deng Yuechuan,   
(1.School of Geographic Information and Tourism,Chuzhou University,Chuzhou 239ooo,China   
2.Wuhan Seismic Metrological Verification & Surveying Engineering Institute CO.,LTD, Wuhan,430000,China)

Abstract: In the high-precision GPS data processing，the precision of resolution are often restricted by the data processing strategies such as the the ocean tide models,the constraint mode settings of satelite orbital，and types of precise ephemeris products. In this paper, relevant experiments are carried out under the considering the above influencing factors,a method which grow in number of baseline solution and combination adjustment is proposed to improve the accuracy of baseline solution based on the error theory. the experimental results indicate that the accuracy of the results of the ocean tide model inserted in the data processing is beter than that of the unused ocean tide model;the FES2OO4 model has the best internal and external coincidence accuracy; the NAO99b external coincidence accuracy is much better in the offshore area, and the effect of other tide models is basically the same level on the accuracy of the results; The inner coincidence precision of relaxed orbit method is beter than that of fixed orbit method,but the outer coincidence precision is lower; Diferent precision orbital products have slight diference on the final solution; The method proposed this paper has significant efect on improving the precision of the GNsS data processing,and it also has rapid convergence rate with different precise ephemeris.

Keywords: ocean tide model; orbital mode; ephemeris products; number of baseline solution 0引言

随着精密工程测量学、地球动力学、气象学等领域对GPS数据处理的精度要求的提高，众多科研工作者及工程技术人员对静态定位数据处理方法做了大量的研究。文献[1]基于快速星历研究其基线解算精度，得出不同长度的基线在固定轨道模式和松弛轨道模式下，其精度有所不同的结论；文献[2]研究了有无气象数据参与GPS 数据处理对基线解算精度和降水量估计值的影响；文献[3]实验了小区域GPS网GAMIT解算结果与IGS站选取的关系；文献[4]讨论了陆态网测站分区的方案；文献[5]基于GAMIT软件研究了不同对流层延迟参数估计时间间隔长短的选择对不同长度基线解算的影响。以上研究表明不同的参数设置会对解算精度有一定影响。因此，研究不同的数据处理策略在解算高精度GPS 定位中具有重要意义。

上述文献研究GPS数据处理时，多采用基线成果的均方根（RMS）作为精度指标进行评价，该指标在一定程度上能够反应基线成果的精度，然而基线的RMS 是一个内部精度（内符合精度）的指标。RMS与成果质量有一定关系，成果质量不好时，RMS会较大，但反过来却不一定成立。鉴于大多数文献研究未对数据处理的外部可靠性进行分析或分析的较少，故本文在GPS 数据处理时兼顾成果的内外精度进行分析，分别研究了海潮模型、轨道模式设置、星历产品等因素对基线解算精度的影响，并采用基线RMS值、坐标分量偏差等作为精度评定指标。在上述实验基础上，基于误差理论，提出对同一组观测数据基线进行多回的解算，进而将多回基线组合平差的方法，设计专门实验验证该方法对提高GPS 数据处理质量的有效性。

# 1数据处理策略及精度分析

文中选用全球分布的 IGS(international GPS service,IGS)跟踪站的 ULAB、CHAN、GMSD、TWTF、KUMN、BJFS及 SHAO共7个站点数据为基础，计算数据的点位分布如图1所示。计算数据资料为2013年01月01日单日数据，借助高精度GPS数据处理软件GAMIT10.71进行基线解算。在各项指标合格的基础上进行平差计算。因IGS站站点坐标精度极高(IGS网站公布以上站点精度在 $2 \mathrm { m m }$ 以内)，因此可以看作真值，平差成果直接和IGS站公布成果进行比较，并结合基线解算的RMS评定精度。为防止计算成果因已知点位网型对成果解算产生不利影响，后续实验均选择CHAN、TWTF、GMSD、ULAB及KUMN为已知点，BJFS和SHAO两IGS站为待定点进行对比验证。

![](images/3ac824b1a7f7ebcd6ceb58b3bd7a653e3b6a60debdd63daeb5e3b11035d96bdd.jpg)  
图1IGS站点位分布图 Fig.1Location Map of IGS stations

# 1.1海潮模型对成果解算的影响

海洋受到日、月等天体引力影响致使海洋潮汐引起的地表周期性负荷形变在沿海地区垂直方向最大可达dm级8，对水平方向也有不同程度的影响[9]。目前国际上的主要海潮模型十多种，本文选用FES2004、NAO99b、CSR4.0及GOT00 海潮模型进行实验。实验选用的海洋潮模型涵盖范围、分辨率及获取方法如表1所示[10-13]。

表1全球海洋潮汐模型  
Tab.1 Global Ocean Tide Loading Models   

<html><body><table><tr><td>Model</td><td>Coverage area</td><td>Methods</td><td>Resolutio/()</td><td>Method of data acquisition</td></tr><tr><td>FES2004</td><td>global</td><td>Blending assimilation</td><td>0.125x0.125</td><td>T/P +ERS1/2 Tide gauge station + hydrodynamic model</td></tr><tr><td>NAO99b</td><td>global</td><td>Representerssimilation</td><td>0.5x0.5</td><td>T/P+ Hydrodynamic model</td></tr><tr><td>CSR4.0</td><td>66S°~66N°</td><td>Response and empirical method</td><td>0.5x0.5</td><td>T/P Inversion</td></tr></table></body></html>

为分析海潮模型对解算成果的影响，数据处理过程设计了以下5种方案进行实验： $\textcircled{1}$ 不加海潮模型改正； $\textcircled{2}$ 加入FES2004海潮模型改正； $\textcircled{3}$ 加入NAO99b 海潮模型改正； $\textcircled{4}$ 加入CSR4 海潮模型改正; $\textcircled{5}$ 加入GOT00海潮模型改正。实验参数设置为：卫星截止高度角 $1 5 ^ { \circ }$ 、已知站点约束为 $0 . 0 5 0 \mathrm { m } \cdot$ 、待定点 $5 0 \mathrm { m }$ 、观测值选项（Choiceofobservable）设定为LC_HELP,轨道模式选用固定（BASELINE）的模式，GAMIT软件参数设置项除了海潮模型设置不同，其它设置完全相同。实验结果列于表2。为更直观的体现模型解算结果的影响，将解算的BJFS和SHAO两IGS站的坐标分量的偏差分别绘制于图2和图3。

表2基线解算及成果统计 （mm）  
  

<html><body><table><tr><td colspan="6">Tab.2 BaselineCalculationandResultsstatistics (mm)</td></tr><tr><td>Types</td><td>Baseline/RMS</td><td>Station</td><td>X-bias</td><td>Y-bias</td><td>Z-bias</td></tr><tr><td>Model-Free</td><td>0.21260</td><td>BJFS</td><td>-2.9</td><td>5.1</td><td>5.4</td></tr><tr><td rowspan="2">FES2004</td><td></td><td>SHAO</td><td>-8.3</td><td>3.6</td><td>-2.8</td></tr><tr><td>0.18783</td><td>BJFS</td><td>-2.7</td><td>4.3</td><td>4.4</td></tr><tr><td></td><td></td><td>SHAO</td><td>-7.4</td><td>1.5</td><td>-4.4</td></tr><tr><td>NAO99b</td><td>0.19418</td><td>BJFS SHAO</td><td>-3.5</td><td>4.8</td><td>6.0</td></tr><tr><td rowspan="2">CSR4</td><td></td><td></td><td>-7.1</td><td>1.4</td><td>-3.0</td></tr><tr><td>0.20738</td><td>BJFS</td><td>-2.9</td><td>4.6</td><td>4.7</td></tr><tr><td rowspan="2">GOT00</td><td></td><td>SHAO</td><td>-7.7</td><td>1.7</td><td>-4.2</td></tr><tr><td>0.21244</td><td>BJFS SHAO</td><td>-2.8 -7.6</td><td>4.5 1.9</td><td>4.5 -4.2</td></tr></table></body></html>

oiri) erreeeieiteeeerettm X-bias Y-bias Z-bias   
6   
4- mm 2   
0   
2 1 Model-Free FES2004 NA099b CSR4 GOT00 Ocean Tide Models   
iri) erreieietrtereretrm 4 X-bias Y-bias Z-bias   
2 20 TPrm   
-4   
-6   
8   
Model-Free FES2004 NA099b CSR4 GOT00 Ocean Tide Models

由表2可以得知：加入FES2004 海潮模型解算的基线 RMS 值最低、NAO99b 其次、其它模型较未加海潮模型的基线RMS 稍优。实验结果显示加入海潮模型后，整网基线解算获得的内符合精度均比未加入海洋模型的成果更优。

由图2、图3可知，将基线解算置入海潮模型后，BJFS站X、Y及Z方向偏差与无模型解算结果对比占优，对SHAO站的Y方向精度提升明显，对X方向精度也有一定程度提升，Z方向偏差则稍有增加。FES2004 海潮模型对BJFS站X、Y、Z任何方向的精度提升都是最优,对 SHAO站提升不如NAO99b 模型,基本与其它模型相当。NAO99b 模型对 SHAO站精度的提升最优，对BJFS 站精度的提升上表现较差。主要原因是BJFS站在内陆地区，受海潮影响较小，而 SHAO站距东海较近，受海潮影响较大。一方面原因是海潮模型依据一定时期内观测数据建模而成，模型本身有一定的误差；另一方面则是每日的海潮是不确定的，由模型计算具体年积日时也有一定的误差。

综合基线RMS及坐标偏差两项指标，上述几种方案中：加入FES2004 海潮模型改正的成果内外符合度最佳，又因其模型分辨率高，在一般点位测量时，内插模型数据精度理论上比其它模型高，因此在利用海潮模型解算成果时应优先考虑FES2004 海潮模型。

# 1.2轨道模式设置的影响

目前基线解算模式常用的有三种，为分析长距离基线解算模式及成果可靠性，分别设置轨道固定和轨道松弛两种解算模式进行实验。实验参数设置同前文，仅轨道模式分别选择轨道固定和轨道松弛两种解算模式，其约束采用软件默认值。限于篇幅，文中仅列出了前文验证的FES2004作为海潮模型参数，实验其它设置完全相同。基线解算及网平差成果统计见表3。为更直观的比较两种轨道模式设置对解算成果的影响,图4、图5给出了BJFS 和 SHAO两IGS 站两种模式设置获得的坐标分量与IGS站公布的坐标分量的偏差对比图。

Tab.3Baseline Calculation and Outcome Statistics

![](images/f20b07d9627d0907a1d6d246245991e8ab9c778c2a144393b0422f228eced9de.jpg)

![](images/c4b432c01af981e8a5012fd8a28fc3a87c5495e6a9bdbe81c0813d7e98f3be52.jpg)  
图4 轨道模式设置对BJFS站成果的影响Fig.4TheEffectof Settingof TrackMode on TheAchievementsofBJFSStation

图5轨道模式设置对SHAO站成果的影响Fig.5 The Effect of Setting of Track Mode on TheAchievementsof SHAOStation

由表3可知：轨道松弛模式比轨道固定模式解算出的基线RMS小，且全网最弱边相对中误差轨道松弛模式计算结果更优，说明此模式解算出的基线内符合精度较高，主要原因是轨道松弛模式解算时把星历误差同时作为未知数进行求解，相当于在进行基线网平差前把基线进行一次误差调整，因而内符合精度表现良好；而轨道固定模式则相当于忽略了星历误差，虽然解算的基线RMS值较轨道松弛解精度稍差，但其坐标成果对比IGS站公布的坐标偏差较小，说明轨道固定模式的外符合精度较高，特别是在Z方向上，轨道固定解优势更为明显。这主要是轨道松弛解算时，尽管把卫星轨道误差纳入整体解算,获得较高的内符合精度，但也使得误差分配时把轨道误差引到了基线中，使得基线、卫星间的误差整体符合度较好，实际计算时，基线间可靠性未必是最有利的，特别是基线的Z方向偏差更为突出，导致平差成果整体较轨道固定模式可靠性差。

# 1.3星历产品对成果精度的影响

人所共知，星历也是影响基线解算的一个重要因素，特别是长基线解算，一般的广播星历难以满足要求，需采用精密星历进行处理。目前IGS 提供的精密星历产品包括最终精密星历产品(IGS)、快速精密星历(IGR)、超快速精密星历(IGU)。不同的星历产品在精度、滞后时间、更新率和采样率方面的差异如表4所示[14-15]。

表3基线解算及成果统计（mm）  
表4IGS提供的精密卫星星历产品  
Tab.4Precision Satellite Ephemeris Products of IGS   

<html><body><table><tr><td>Satellite Ephemerides</td><td>Accuracy/cm</td><td>Latency</td><td>Updates</td><td>Sample Interval/min</td></tr><tr><td>IGS</td><td>2.5</td><td>12～18 days</td><td>every Thursday</td><td>15</td></tr><tr><td>IGR</td><td>2.5</td><td>17～41 hours</td><td>at 17 UTC daily</td><td>15</td></tr><tr><td>IGU</td><td>3.0</td><td>3～9hours</td><td>at 03,09,12，21UTC</td><td>15</td></tr></table></body></html>

在上述星历产品中，IGS 精度最高，滞后时间为13d；IGR 精度与IGU 精度相当，时延为17h；IGU每天更新4次，更新时间为每天03：00：00，09：00：00，15：00：00和21：00: 00(UTC)。

为了分析不同精密星历产品对成果精度的影响，实验选取了IGS、IGR及IGU3种星历产品解算IGS站的空间直角坐标。实验时除采用的星历产品不同，其它参数设置完全相同。

<html><body><table><tr><td>Station</td><td>Satellite Ephemerides</td><td>X-bias</td><td>Y-bias</td><td>Z-bias</td></tr><tr><td rowspan="3">BJFS</td><td>IGU</td><td>-2.8</td><td>4.6</td><td>5.5</td></tr><tr><td>IGR</td><td>-3.0</td><td>4.6</td><td>4.7</td></tr><tr><td>IGS</td><td>-2.9</td><td>4.6</td><td>4.7</td></tr><tr><td rowspan="3">SHAO</td><td>IGU</td><td>-4.2</td><td>-0.9</td><td>-6.1</td></tr><tr><td>IGR</td><td>-7.4</td><td>1.6</td><td>-4.4</td></tr><tr><td>IGS</td><td>-7.3</td><td>1.4</td><td>-4.5</td></tr></table></body></html>

由表5可知：采用不同的精密星历，计算IGS站的坐标成果精度都在毫米级，三维坐标分量IGU产品成果在 $7 \mathrm { m m }$ 范围内波动、IGR和IGS产品成果在 $8 \mathrm { m m }$ 内波动，在Z方向IGU 成果偏差稍大。表明三种星历产品计算结果基本相当，这和各星历产品标注的精度基本一致。表明在相同的观测时间段内，相同的数据处理条件下，几种精密星历产品对成果的解算精度影响基本相当。在一定的条件下，可用超快或快速星历替代精密星历进行基本等效精度的数据处理。

# 1.4基线解算回数及影响

GPS 基线解算过程中受到多种因素的影响，既存在软件模型误差的影响，也存在基线处理过程中人为因素的干扰，如根据基线残差调整卫星截止高度角、删除错误卫星、调整卫星采样间隔等情况。相当于基线解算过程既包含了系统误差又包含了偶然误差。为提高测量成果的精度及可靠性，若采用外业多次观测的处理方式，将导致外业工作量大大的增加，同时作业成本也将进一步的提高。众所周知，在一定观测条件下，通过多测回观测可以提高观测精度。基于此理论，本文提出观测数据基线多回解算并组合平差的方法，即通过对观测数据进行多回基线解算，并对各回基线成果组合平差。

为验证基线解算回数的影响，文中设计了本次实验。实验中基线解算回数共6回，每回基线独立解算后和前几回基线解算后进行组合平差。实验开始前首先利用TEQC软件对观测数据进行了预处理。实验参数设置为FES2004海潮模型、轨道固定模式，其它参数同前。在实验过程中会根据成果残差图情况对部分卫星、部分时段及卫星截止高度角作相应处理，各回基线解算合格后，组合平差坐标与IGS公布坐标的偏差列于表6。为更直观的比较基线解算回数间的关系，图6和图7给出了BJFS和 SHAO站点的坐标偏差与解算成果回数间的关系图。

表6不同基线处理回数的成果对比（mm)  
Tab.6 Comparison of the Results of Different Baseline Processing times   

<html><body><table><tr><td>Station</td><td>Number of baseline solution</td><td>X-bias</td><td>Y- bias</td><td>Z-bias</td></tr><tr><td rowspan="6">BJFS</td><td>1</td><td>-2.7</td><td>4.3</td><td>4.4</td></tr><tr><td>2</td><td>-2.9</td><td>4.2</td><td>4.3</td></tr><tr><td>3</td><td>-2.1</td><td>2.9</td><td>4.1</td></tr><tr><td>4</td><td>-0.8</td><td>0.5</td><td>2.4</td></tr><tr><td>5</td><td>-0.1</td><td>-0.5</td><td>1.5</td></tr><tr><td>6</td><td>0.6</td><td>-0.4</td><td>0.8</td></tr><tr><td rowspan="5">SHAO</td><td>1</td><td>-7.4</td><td>1.5</td><td>-4.4</td></tr><tr><td>2</td><td>-7.3</td><td>1.4</td><td>-3.7</td></tr><tr><td>3</td><td>-6.9</td><td>1.2</td><td>-3.6</td></tr><tr><td>4</td><td>-6.1</td><td>0.3</td><td>-3.2</td></tr><tr><td>5</td><td>-5.7</td><td>0.0</td><td>-27</td></tr></table></body></html>

![](images/7126309296145c5ac62d4204971045ac134c8a8928be82570ba471625cf2f025.jpg)  
图6BJFS站基线解算回数与坐标分量偏差关系 Fig.6 Diagram of the Relationship Between the Number of Baseline Solutions of BJFS Station and the Deviation of Coordinate Components

![](images/b131c64087d660fe1c3237db2c551a0474a92cb92765dbd0b6138e49070443b8.jpg)  
图7SHAO站基线解算回数与坐标分量偏差关系 Fig.7Diagram of the Relationship Between the Number of Baseline Solutions of SHAO Station and the Deviation of Coordinate Components

由表6可见：随着基线解算回数的增加，BJFS 和 SHAO两站点的坐标偏差明显减少，图6及图7显示，基线解算4回后成果的精度随基线解算回数的增加便不再明显的提高。这表明基线解算回数增加到一定程度后，点位精度的提升不再显著。实验结论符合偶然误差传播定律中提高测回数可以提高精度，但当测回数达到一定的程度后，精度提高就不再明显的规律。

为更进一步的分析多回解算基线组合平差的效果，分别采用前文实验中3种不同的精密星历独立解算6次。本次实验除星历不同，其他参数设置完全相同，为了不受人为因素的干扰，基线解算仅仅改变卫星高度角，6回卫星截止高度角设置分别为 $1 5 ^ { \circ }$ 、 $1 6 ^ { \circ }$ 、 $1 7 ^ { \circ }$ 、 $1 8 ^ { \circ }$ 、$1 9 ^ { \circ }$ 和 $2 0 ^ { \circ }$ ，这样便于检核多回基线解算组合平差的可靠性。限于篇幅，实验结果直接给出BJFS 和 SHAO两IGS站中解算回数计算结果与IGS站公布成果比较的关系图。不同星历及解算回数关系图见图 $8 \sim$ 图13。

![](images/2eecc0926df2d4f3feb3dd76b92e3014d10dce58be41798a3c8decbf33de5fda.jpg)  
图8BJFS站IGU星历基线解算回数与坐标分量偏 差关系 Fig.8 Diagram of the Relationship Between the Number of IGU Ephemeris Baseline Solutions of BJFS Station and the Deviation of Coordinate

![](images/bc05b4dd041a7f99a91a5e3346e03a32cb9c74616d7f8e41b6e6a716c0b78ba7.jpg)

Fig.9Diagram of the Relationship Between the Number ofIGR Ephemeris Baseline Solutions of BJFS Station and the Deviation of Coordinate Components

![](images/e0b21aeb4936971ccccb85808874c64ce1d35e9e18e1e1adba809958f77b9efd.jpg)  
图10BJFS站IGS星历基线解算回数与坐标分量 偏差关系 Fig.1O Diagram of the Relationship Between the Number ofIGSEphemeris Baseline Solutions of BJFS Station and the Deviation of Coordinate

![](images/4428fae275ad9b4140a96eeefd458e3fd5daad5d877b7efb4907c7ad95f6b77e.jpg)  
图9BJFS站IGR星历基线解算回数与坐标分量偏差关系  
图11SHAO站IGU星历基线解算回数与坐标分量偏差关系  
Fig.11Diagram of the Relationship Between the Number ofIGUEphemeris Baseline Solutions of SHAO Station and the Deviation of Coordinate Components

![](images/633662fd279cd001c131dc5aac4a37ab110523224b7a4734d3b7779a146a2d89.jpg)  
图12SHAO站IGR星历基线解算回数与坐标分量偏差关系

![](images/204c52d5da26ee88521cc7dc98810dbbd847254c828f273b0ea1696ec5401fe4.jpg)  
Fig.12 Diagram of the Relationship Between the Number ofIGREphemeris Baseline Solutions of SHAO Station and the Deviation of Coordinate Components   
图13 SHAO站IGS星历基线解算回数与坐标分量 偏差关系 Fig.13Diagram of the Relationship Between the Number ofIGUEphemeris Baseline Solutions of SHAO Station and the Deviation of Coordinate Components

由图 $8 \sim$ 图13可知：采用3种精密星历中任意一种星历，随着基线解算回数的增加，BJFS 站的精度明显提高，X、Y及Z坐标分量的偏差均随着基线解算回数的增加而降低。表现良好的收敛性；而SHAO站各坐标分量随着基线解算回数的增加有收敛也有发散的现象，整体有所收敛。一方面说明增加基线解算回数进行组合平差可以提高成果的精度及可靠性，另一方面表明，仅靠设置卫星截止高度角解算基线不尽完美，在实际工作中应结合基线残差图、卫星截止高度角、变换卫星采样间隔及过滤几何因子不理想的时段等方式，进一步的提升基线多回组合解算的效果。

# 2结论

本文在实验海潮模型对基线及坐标成果影响的基础上，分析了轨道模式及不同精密星历对成果精度的影响，验证了轨道松弛和轨道固定解算模式的内外可靠性。在此基础上，提出了基线多回解算组合平差的方法，通过不同海潮模型、轨道设置模式、不同星历产品及基线多回数解算的实验分析，得出以下结论：

1）使用海潮模型比未用海潮模型解算获得的基线及坐标偏差等精度指标更优，FES2004海潮模型解算结果的内外符合度整体较优，且FES2004模型的分辨率较其它模型更高，因而可以更好地减少模型内插的误差影响，在使用海潮模型计算时，应优先考虑该模型。

2）使用轨道松弛模式解算时，解算结果往往内符合精度较高，外部可靠性在空间直角坐标系中较轨道固定模式差。主要原因是该模式把星历误差作为未知数进行联合求解时，易把相关误差调整到基线中去，造成基线内符合精度高，外符合精度较轨道固定解差的现象，在一般工程中建议使用轨道固定解算进行基线解算。

3）精密星历、快速星历及超快星历解算成果精度基本相当，几种星历产品公布精度也基本相当，说明在数据处理过程中，可以使用快速星历或超快星历替代精密星历，获得基本等效精度的数据成果。

4）同一组观测数据，经合理增加基线解算回数组合平差的方法，较单一次基线计算成果精度高，说明增加基线解算回数进行组合平差，能有效的提高数据解算精度和可靠性，值得在GPS数据处理过程中推广及进一步验证。

# 参考文献

[1]高旺,高成发,潘树国,等.基于快速星历的GAMIT 高精度基线解算研究[J].测绘科学,2015,40(2):22-25,38.  
[2]李星光,郑南山.参数设置对高精度 GPS 数据解算的影响探讨[J].测绘科学,2015,40(1):33-37,51.  
[3] 邬熙娟,高俊强,黄燕．小区域GPS 网GAMIT 解算结果与IGS 站选取的关系[J].南京工业大学学报（自然科学版），2010,32(4):96-99  
[4] 万军,成英燕,党亚民,等，陆态网测站高精度解算分区方案[J].测绘科学,2016，41(4):1-4.  
[5] 黄祖登,梅连辉.高精度GPS 数据处理中对流层参数估计研究[J].测绘地理信息,2013,38(5):12-15.  
[6] 曹艳丰,陈宝献,陈秀万,等.基于GPS 数据的 MODIS 大气可降水量反演精度提高模型[J].遥感信息,2014(12).  
[7] 张光茹，秘金钟．不同数据处理策略对PPP收敛精度的影响[J].测绘科学,2018,3(43):77-81  
[8] 曹炳强，成英燕，许长辉．海潮模型对连续跟踪参考站数据解算的影响—以福建省为例[J]．测绘科学,2015,40(12):108-111.  
[9] UrschI C,Dach R, Hugentobler U,et al, Validating Ocean Tide Loading Models Using GPS[J].JGeod,2005,78(10):616-625.  
[10] Matsumoto K,Takanezawa T,Ooe M.OceanTide Models Developed by AssimilatingTopex/Poseidon Altimeter Data into Hydrodynamical Model:A Global Model and a RegionalModel around Japan[J].J Oceanogr,2000,56(5):567-581.  
[11] Lyard F,Lefevre F,Letellier T,et al.Modelling the Global Ocean Tides:Insights from FES2004[J].Ocean Dynamics,2006,56(5-6):394-415.  
[12] Wang Yihang,Fang Guohong,Wei Zexun,et al. Accuracy assessment of global ocean tidemodels base on satelite altimetry[J].ADVANCES IN EARTH SCIENCE,2010,25(4):353-359.  
[13] 孙佳龙,郭金运,郭淑艳,刘新.基于验潮资料的CSR4.0模型和NAO.99b 模型在中国海域的精度分析,2013,28(5):2787-2795.  
[14] 刘盼,刘智敏,张明敏,郭金.不同IGS 星历产品对地基GPS 反演水汽的影响[J].测绘科学,2018,12(43):17-22.  
[15] http://www.igs.org/products/data