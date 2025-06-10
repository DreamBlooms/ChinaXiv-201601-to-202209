饲料添加剂 $L$ -赖氨酸硫酸盐中 $L$ -赖氨酸含量近红外速测方法研究]李守学1,²　陈玉艳³贾　铮」 肖志明」 王燕妮」 刘成新」　樊　霞1\*（1.中国农业科学院农业质量标准与检测技术研究所，北京 100081；2.中国农业大学工学院，北京 100083;3.辽宁省兽药饲料畜产品质量安全检测中心，沈阳 110016)

摘要：为了探讨利用近红外漫反射光谱技术（NIDRS）快速定量分析饲料添加剂 $L$ 赖氨酸硫酸盐中 $L$ -赖氨酸含量的可行性，本试验在全国范围内收集了具有代表性的 $L .$ -赖氨酸硫酸盐添加剂76个，采用国家标准方法对样品中的 $L$ -赖氨酸含量进行化学赋值；用光栅型近红外光谱仪扫描 $L .$ -赖氨酸硫酸盐样品，获取了不同物理状态下样品的近红外光谱图。依据L-赖氨酸含量将样品分为定标集和验证集，运用适当的光谱预处理方法，采用竞争性自适应重加权（CARS）算法结合偏最小二乘法（PLS）建立了 $L$ -赖氨酸硫酸盐的近红外定标分析模型，并将该模型与全波长模型进行了比较。结果表明：用烘干、60 目粉碎后的样品结合CARS 算法建立的定标模型最优，定标集校正决定系数 $( \boldsymbol { R } _ { \mathrm { ~ C ~ } } ^ { 2 }$ )为0.954，校正集标准偏差（SEC）为0.510，交互验证标准偏差为（SECV）为0.659；验证集预测决定系数（ $\cdot R _ { \mathrm { ~ P ~ } } ^ { 2 }$ ）为0.952,预测标准偏差（SEP）为0.554，相对分析误差（RPD）值为3.83。由此可见，NIDRS 定量分析 $L$ -赖氨酸硫酸盐具有一定可行性，对于丰富我国氨基酸盐及其他氨基酸制品的快速检测方法具有实际的应用意义。

关键词：赖氨酸；近红外漫反射光谱技术；速测模型；竞争性自适应重加权算法中图分类号：Q517；0433.1 文献标志码： 文章编号：

赖氨酸添加剂是目前动物生产中应用最为广泛的氨基酸添加剂之一，其不仅可以提高饲料中蛋白质的利用率，还能提高动物饲料转化率，为动物生长提供更加全面均衡的营养。在实际的生产应用中，由于游离的 $L .$ -赖氨酸非常容易潮解，易发黄变质，且具有刺激性的腥味，因此除特殊需要，常把 $L$ -赖氨酸制成 $L$ -赖氨酸盐酸盐或 $L$ -赖氨酸硫酸盐[( $\mathrm { C _ { 6 } H _ { 1 4 } N _ { 2 } O _ { 2 } }$ ））$\phantom { } _ { 2 } { \cdot } \mathrm { n H } _ { 2 } \mathrm { S O } _ { 4 } ]$ 的颗粒状物料进行使用[1]。 $L .$ -赖氨酸硫酸盐是 2010 年前开发的一种新型赖氨酸添加剂产品，市场上应用较广的是 $L .$ -赖氨酸含量 $6 5 \%$ 和 $70 \%$ 的2种规格的产品， $L .$ -赖氨酸平均含量在 $5 5 . 4 \%$ 左右[2]。与 $L$ -赖氨酸盐酸盐相比，虽然二者前期发酵工艺相同，但 $L .$ 赖氨酸硫酸盐后续处理方法成本更低且更环保。 $L$ -赖氨酸硫酸盐工业生产中多以玉米淀粉浆、废糖蜜等为原料，利用 $L$ -赖氨酸生产菌株进行厌氧发酵，发酵后培养液用硫酸处理并加热，最后喷雾干燥制成颗粒，其成品呈褐色粒状或粉末状， $L$ -赖氨酸含量 $9 5 1 \%$ ，另外含有不少于10%的其他氨基酸[3]。目前，关于 $L$ -赖氨酸硫酸盐添加剂中 $L$ -赖氨酸含量的测定还没有统一的国家标准或行业标准，企业多采用《饲料中氨基酸的测定》（GB/T18246-2000）中的酸水解法[3]测定产品中 $L$ -赖氨酸含量，该方法虽然精密度相对较高，平行检测样相对偏差 $< 5 \%$ 但检测过程中样品水解时间长，仪器成本昂贵且对检测员操作水平要求高，分析速度慢，单样检测耗时大约需要2d的时间，不适用于大批量样品的快速检测分析。

近红外漫反射光谱技术（near infrared diffuse reflectance spectroscopy，NIDRS）是一种新型的快速检测分析技术，其原理主要是分子中含氢基团X-H（如C-H、N-H、O-H等）对近红外光的吸收。该技术在分析过程中待检样品不需要繁琐的前处理,不需要任何化学试剂，无污染，是一种环境友好型技术。同时仪器成本低，检测限低，通常含量在 $0 . 1 \%$ 以上的组分都可进行分析[4]。目前，NIDRS已经在饲料、石油、食品、药品、烟草、茶叶等领域得到了广泛的应用[5-11]。 $L$ -赖氨酸属于有机物，制成盐是为了维持物质的稳定，便于运输使用，L-赖氨酸硫酸盐分子中的无机成分不会破坏物质的有机结构，因此可以用NIDRS 对 $L$ -赖氨酸硫酸盐进行检测分析。由于各企业生产工艺不同，产品质量标准不统一，容易造成出厂产品在组成成分、 $L .$ -赖氨酸含量、颗粒大小、产品颜色等方面参差不齐，同时 $L .$ -赖氨酸硫酸盐添加剂在运输、储藏过程中容易潮解结块，甚至变质。这些都会成为利用NIDRS 进行分析时的影响因素。近年来，国内外专家应用 NIDRS 对食品、饲料中氨基酸成分的检测进行了较为广泛的研究[12-15]，但氨基酸盐及其制品的相关研究还未见报道。

本研究以饲料级 $L$ -赖氨酸硫酸盐添加剂为研究对象，分析了样品不同状态对近红外光谱分析的影响，并比较了全光谱与特征波长2种定标模型的预测效果，探讨了基于 NIDRS快速定量分析 $L$ -赖氨酸硫酸盐添加剂中 $L$ -赖氨酸含量的可行性。

# 1材料与方法

# 1.1样品的收集及制备

本试验于2013—2016 年期间，从不同生产厂家和产品用户处分批次采集了生产日期、产品规格各不相同的 $L .$ -赖氨酸硫酸盐产品，所有样品的来源均不相同，具有较强的代表性。第1阶段分批次采集了不同来源样品59个，用作校正集；第2阶段采集不同来源样品17个，用作验证集。将各样品平均分成2份，一份用旋风磨 $0 . 5 ~ \mathrm { m m }$ 标准筛粉碎至样品粒度在$0 . 2 8 ~ \mathrm { m m }$ 以下（60目)制备成粉碎样，一份留作原始样品。样品密封包装后均置于冰柜中 $4 \mathrm { { ^ \circ C } }$ 条件下保存。

# 1.2 $L$ -赖氨酸含量的测定

按照《饲料中氨基酸的测定》（GB/T18246—2000）中的酸水解法对烘干基样品（烘干基，于 $1 0 5 \mathrm { ~ } ^ { \circ } \mathrm { C } |$ 洪箱中烘 $^ { \scriptsize 5 \mathrm { ~ h ~ } }$ ）进行赋值。样品过60目筛粉碎后，称样（ $5 0 \sim 1 0 0 ~ \mathrm { m g }$ ，加入$1 0 ~ \mathrm { m L }$ 的 $6 \mathrm { m o l / L }$ 盐酸溶液后真空封口，置于 $1 0 5 \mathrm { ^ \circ C }$ 烘箱中水解 $2 2 \mathrm { ~ h ~ }$ 以上。取出水解液冷却至室温，先过滤，再稀释50倍后过 $0 . 4 5 ~ { \mu \mathrm { m } }$ 滤膜，之后用氨基酸分析仪测定样品中 $L$ -赖氨酸的含量。按照《饲料中水分的测定》（GB/T6435—2014）的方法测定收到基样品中水分的含量，然后根据烘干基样品中 $L$ -赖氨酸的含量换算得出收到基样品中 $L$ -赖氨酸的含量。

# 1.3样品近红外光谱采集

本研究中采用SupNIR-2700 型光栅近红外光谱仪（聚光科技股份有限公司生产）进行光谱采集，仪器波长为 $4 ~ 0 0 0 { \sim } 1 0 ~ 0 0 0 ~ \mathrm { c m } ^ { - 1 }$ ，数据采样间隔为 $1 \ \mathrm { n m }$ ，光谱分辨率为 $1 0 \ \mathrm { n m }$ 。因温度会影响样品的吸光度、波长位移，从而影响样品光谱质量[16，因此，在光谱采集前需将待扫描样品从冰柜取出置于实验室环境中进行回温处理 $^ { 7 2 \mathrm { ~ h ~ } }$ 以上，使样品温度回至室温后进行光谱扫描。装样时，每个样品的高度要与样品池的边缘持平，以保证装样量一致。每个样品重复装样3次，扫描后取平均光谱，得到收到基样品光谱。之后再将所有样品放于105℃烘箱中5h，取出冷却至室温后再重复上述步骤获得烘干基样品光谱。

# 1.4数据处理

# 1.4.1 定标模型的建立

本试验运用偏最小二乘法（partial least square method，PLS）建立定标模型，PLS 能将光谱矩阵（ $( X )$ 和浓度矩阵（Y）同时分解。在计算每一个新主成分前，将 $X$ 的得分（T）和Y的得分（U）进行交换，使得到的主成分直接与Y关联，使主成分与Y最大程度的相关，从而保证获得最佳校正模型。

利用学生残差与杠杆值[17相结合来判定建模过程中出现的异常样本。为了消除光谱信号的基线漂移、提高光谱分辨率，使用导数（Derivate)数学处理方法，表示为0-2-21、1-2-15、1-2-21、2-2-15、2-2-21。其中第1个数值代表微分处理，0代表不求导，1代表求一阶导，2代表求二阶导；第2个数值代表求导的多项式数；第3个数值代表导数求导的间隔数。为了消除样本粒度分布不均匀引起的散射，使用了变量标准化处理和去散射处理（SNVDT）、变量标准化处理（SNV）、散射校正（MSC）、去趋势（Detrend）等光谱预处理方法。

试验中通过独立的验证集对近红外定标模型进行检验，评价模型性能的统计学指标主要包括：校正决定系数 $( \boldsymbol { R } _ { \mathrm { ~ C ~ } } ^ { 2 }$ 、验证决定系数 $( \boldsymbol { R } _ { \mathrm { ~ V ~ } } ^ { 2 }$ ）、预测决定系数 $( R _ { \mathrm { ~ P ~ } } ^ { 2 }$ ）、校正标准偏差（SEC）、交互验证标准偏差（SECV）、预测标准偏差（SEP）和相对分析误差（RPD）值[验证集L-赖氨酸含量的标准偏差（SD）与 SEP 的比值]。通常 SEP与 SEC 越小，模型精确度越高;SECV与 SEC 越接近，定标模型越稳定。

# 1.4.2 特征波长筛选方法

与食品、饲料相比， $L$ -赖氨酸硫酸盐添加剂组成成分相对简单且 $L .$ -赖氨酸含量高，因此样品近红外光谱中与氨基酸相关的光谱峰较为明显。为了降低建模数据量，提高建模效率，增加定标模型的精度和稳定性，需要提取光谱中与 $L$ -赖氨酸相关的特征波长。本研究选用竞争性自适应重加权（competitive adaptive reweighted sampling，CARS）算法[18]筛选光谱中的特征波长。CARS算法采用“适者生存”原则，将每个变量看成1个个体，通过自适应加权采样技术筛选出 PLS 模型中回归系数绝对值较大的波长，去掉权重较小的波长，并通过交互校验优选出模型交互交验均方根误差最小时所对应的波长组合。此算法中引入了指数衰减函数来控制变量的保留率，具有很高的计算效率。论文中所有光谱数据处理和建模均在Mat lab 20l3b（Math works，美国）和PLS-Toolbox 8.0（Eigenvector Research，美国）软件中进行。

# 2结果

本试验分批次获取了具有较强代表性的 $L$ -赖氨酸硫酸盐样品，结果如表1。所选样品$L .$ -赖氨酸含量范围较广，变异性较大。

表1样品 $L$ -赖氨酸含量统计结果  
Table1 Statistic result of samples $L$ -lysine content   

<html><body><table><tr><td>项目 Items</td><td>样品量 Sample number/个</td><td>平均值 Mean/%</td><td>范围 Range/%</td><td>标准偏差 SD/%</td></tr><tr><td>收到基样品 Wet basis sample</td><td>76</td><td>56.57</td><td>50.11~59.52</td><td>2.26</td></tr><tr><td>烘干基样品 Dry basis sample</td><td>76</td><td>55.27</td><td>50.91～60.68</td><td>2.40</td></tr><tr><td>校正集（烘干基）Calibration （dry basis）</td><td>59</td><td>56.72</td><td>50.91～60.68</td><td>2.43</td></tr><tr><td>验证集（烘干基）Validation （dry basis）</td><td>17</td><td>56.77</td><td>52.51~59.81</td><td>2.12</td></tr></table></body></html>

样品未经处理（未粉碎收到基）、粉碎干燥（60目烘干基）、未粉碎干燥（未粉碎烘干基）、粉碎未干燥（60目收到基）4种不同预处理后获取近红外光谱，并搭配不同组合的光谱预处理方法，用PLS建立了校正模型，结果如表2。从表2中可以看出，利用未粉碎样品建立的模型效果远差于粉碎后的样品， $R _ { \mathrm { ~ V ~ } } ^ { 2 } ~ R _ { \mathrm { ~ C ~ } } ^ { 2 }$ 均小于后者，且 SECV与 SEC 更大。

Table 2NIDRS model results of different physical states samples   

<html><body><table><tr><td rowspan="2">项目 Items</td><td rowspan="2">样品量 Sample</td><td colspan="5">主因子数</td><td rowspan="2">交互 验证</td></tr><tr><td>预处理 number/ Preprocessing</td><td>Principal factor</td><td>校正 决定 系数</td><td>验证 决定 系数</td><td>校正 标准 偏差</td></tr><tr><td>未粉碎收到基 Wet basis not</td><td>个</td><td>Derivate （2-2-15)</td><td>number</td><td>RC</td><td>R²</td><td>SEC</td><td>偏差 SECV</td></tr><tr><td>crushed 60 目收到基 Wet basis at 60</td><td>59</td><td>+MSC Derivate（1-2-15)</td><td>3</td><td>0.313</td><td>0.231</td><td>1.789</td><td>1.901</td></tr><tr><td>mesh 未粉碎烘干基 Dry basis not</td><td>59</td><td>+MSC Derivate （2-2-15)</td><td>6</td><td>0.885</td><td>0.814</td><td>0.733</td><td>0.931</td></tr><tr><td>crushed 60 目烘干基 Dry basis at 60</td><td>59</td><td>+SNV+Detrend Derivate （2-2-21)</td><td>6</td><td>0.569</td><td>0.124</td><td>1.460</td><td>2.330</td></tr><tr><td>mesh</td><td>59</td><td>+MSC</td><td>6</td><td>0.925</td><td>0.834</td><td>0.663</td><td>0.992</td></tr></table></body></html>

Derivate：导数；MSC：散射校正；SNV；变量标准化处理；Detrend：去趋势。

试验数据显示样品在经过60 目粉碎烘干后获取光谱，结合Derivate、MSC 建立的模型效果最佳， $R _ { \mathrm { ~ C ~ } } ^ { 2 }$ 为0.925，明显优于样品经其他预处理建立的模型。为了进一步提高模型的预测效果，本试验选用CARS算法选取了光谱中与 $L$ -赖氨酸相关的特殊波段，相关参数包括：主成分个数选择5个，交互验证个数为10，预处理方法为自动扩展（autoscaling），迭代次数为50，建立校正模型后与全光谱模型比较，不同光谱区域对模型效果的影响如表3。CARS算法模型预测效果优于全光谱模型， $R _ { \mathrm { ~ C ~ } } ^ { 2 }$ 为0.954，高于全光谱模型的 $R _ { \mathrm { ~ C ~ } } ^ { 2 } 0 . 9 2 5$ 。并且CARS模型的外部验证效果也高于全光谱模型， $R _ { \mathrm { ~ P ~ } } ^ { 2 }$ 为0.952，高于全光谱模型的 $R _ { \mathrm { ~ P ~ } } ^ { 2 } 0 . 9 2 4$ 号

表2不同物理状态样品的NIDRS 模型结果  
表3不同光谱区域对模型效果的影响  
Table 3Effects of different spectrum region on model effect   

<html><body><table><tr><td colspan="8">定标集</td></tr><tr><td></td><td></td><td colspan="3">Calibration</td><td colspan="3"></td></tr><tr><td>建模方法</td><td>数据点</td><td>校正</td><td>校正标</td><td></td><td>交互</td><td>交互验证标 预测</td><td>Validation</td><td>相对</td></tr><tr><td>Modeling</td><td>Data</td><td>决定</td><td>准偏差</td><td>验证决</td><td>验证 准偏差/校</td><td>决定</td><td>预测标 准偏差</td><td>分析</td></tr><tr><td>approach</td><td>marker</td><td>系数</td><td></td><td>定系数</td><td>标准</td><td>正标准偏差</td><td>系数</td><td>误差</td></tr><tr><td></td><td></td><td>RC</td><td>SEC</td><td>R²v</td><td>偏差 SECV/SEC</td><td>R</td><td>SEP</td><td>RPD</td></tr></table></body></html>

<html><body><table><tr><td colspan="3"></td><td colspan="5">SECV</td></tr><tr><td>偏最小二乘法</td><td>1 499</td><td>0.925</td><td>0.663</td><td>0.834</td><td>0.992</td><td>1.496 0.924</td><td>0.634</td><td>3.34</td></tr><tr><td>PLS 竞争性自适应</td><td rowspan="3"></td><td rowspan="3"></td><td rowspan="3"></td><td rowspan="3"></td><td>1.292</td><td></td><td></td><td rowspan="3"></td></tr><tr><td>0.954</td><td></td><td></td></tr><tr><td>重加权-偏最 31</td><td>0.659</td><td>0.952</td></tr><tr><td>小二乘法 CARS-PLS</td><td></td><td></td><td>0.510</td><td>0.924</td><td></td><td></td><td>0.554</td><td>3.83</td></tr></table></body></html>

# 3讨论

# 3.1 $L$ -赖氨酸含量分析

本试验中按照GB/T 18246—2000、GB/T 6435—2014方法测量了样品中的 $L .$ -赖氨酸含量并进行了比较，结果如表1。表1中的数据表明本研究中所选样品 $L$ -赖氨酸含量范围较广，变异性较大，具有较强的代表性。

# 3.2 $L$ -赖氨酸硫酸盐NIDRS

未粉碎收到基、60目烘干基、未粉碎烘干基、60目收到基4种物料形态的 $L .$ -赖氨酸硫酸盐近红外光谱图如图1。 $L .$ -赖氨酸硫酸盐添加剂虽然是混合物，但物料组成成分相对简单，因此近红外光谱峰也相对清晰明显。样品中赖氨酸的吸收峰主要集中在4个特征光谱区：第1特征光谱区主要是C-H基团的二级倍频吸收峰，在 $1 \ 0 5 0 { \sim } 1 \ 2 0 0 \ \mathrm { n m }$ 附近；第2特征光谱区主要是C-H基团的组合频吸收峰，在 $1 \ 3 0 0 { \sim } 1 \ 5 0 0 \ \mathrm { n m }$ 附近；第3、4特征光谱区即 $1 6 0 0 \sim$ 1 850 nm、 $2 0 0 0 { \sim } 2 5 0 2 \mathrm { n m }$ 附近也有明显的特征吸收峰[19]。在 $1 9 4 0 \mathrm { n m }$ 波长左右处，图1-c、图1-d 中的吸光度明显低于图1-a、图1-b，说明样品中的水分对样品光谱影响较大。图1-b、图1-d 与图1-a、图1-c 相比，粉碎后的样品粒度更加均匀，降低了对光的散射作用，因此吸光度更低。

a：未粉碎收到基样品光谱图 Spectrogram of wet basis not crushed；b：60 目收到基样品光谱图 Spectrogramof wet basis at 60 mesh；c：未粉碎烘干基样品光谱图 Spectrogram of dry basis not crushed；d:60 目烘干基样品光谱图 Spectrogram of dry basis at 60 mesh。

![](images/ed972f183967eeb54ce8307891b99a960e4074a0997b1685125ac7baf2a1d2ca.jpg)  
图1不同前处理样品近红外光谱图  
Fig.1Near infrared spectrogram with different pretreatment samples

# 3.3 定标模型的建立

根据 $L$ -赖氨酸硫酸盐样品的物料状态，选取适当的光谱预处理方法（如Derivate、SNV、MSC、Detrend 等），采用PLS，用校正集59个样品建立近红外定标模型。根据表2定标模型结果可以得出，不同前处理会对定标模型质量造成较大的影响。未粉碎收到基样品颗粒较大且不均匀，在扫描光谱过程中会对光造成严重的散射，光谱发生位移，影响样品光谱的质量，从而降低了模型的准确度。

水分含量对样品的光谱影响较为严重，会直接影响到校正模型的优劣。从表2中模型效果来看，60目收到基样品在经过烘干后再建立校正模型， $R _ { \mathrm { ~ C ~ } } ^ { 2 }$ 从0.885增长到0.925， $R _ { \mathrm { ~ V ~ } } ^ { 2 }$ 由0.814 增长到0.834，模型效果改善显著。部分样品储藏时间较长，在保存过程中会发生不同程度的潮解，会影响模型的质量。在扫描样品光谱时，样品温度已与室温持平。因此，为了得到质量较好的定标模型，应将样品粉碎后烘干再获取近红外光谱，并结合适当的光谱预处理方法建立定标模型。本试验中最佳定标模型校正相关系数 $\boldsymbol { R } _ { \mathrm { ~ C ~ } } ^ { 2 }$ 为0.925，SEC与 SECV分别为0.663、0.992，均优于其他物料状态样品的定标模型。但该模型也在存在过拟合的现象，可能与数据中无关信息变量过多有关。

# 3.4特征波长筛选

运用特征波长建立定量模型，不仅可以有效去除无关信息变量，提高建模效率，还可以尽可能地降低共线性对模型的影响[20]。试验中将60 目烘干基样品光谱经上述预处理后，利用CARS 算法筛选出特征波长，共筛选出31个波长点，筛选结果如图2。从图中可以看出，CARS算法筛选出的特征波长与 $L$ -赖氨酸样品吸收峰的光谱段基本相吻合，主要是C-H键、N-H键的吸收峰。其中， $1 \ 1 0 0 { \sim } 1 \ 4 0 0 \ \mathrm { n m }$ 波段的特征波长主要是C-H基团的二级倍频与组合频的吸收峰， $1 \ 7 0 0 { \sim } 1 \ 9 0 0 \ \mathrm { n m }$ 波段的特征波长主要与N-H基团相关。

![](images/13cab44eac71d138bd2e8cb6fae37cb47397648f8747ce8ea6d1e4d79ad33ad0.jpg)  
图2CARS 算法筛选的特征波长点  
Fig.2Filter characteristic wavelength point used CARS algorithm

用CARS算法筛选的特征波长建立定标模型，并用内部交互验证与外部验证来评价模型，内部交互验证一般采用留一交互验证，即从校正集中随机选机一个样品（该样品不参与建模)验证剩余样品建立的模型优劣程度。外部验证即重新收集不同来源的样品组建验证集，检验校正集样品建立的模型效果。

与全光谱定标模型比较，结果如表3。从表中可以看出，与全光谱1499个波长相比，CARS-PLS定标模型仅使用了31个波长，极大的提高了建模效率。并且选用31个特征波长建模后，与全波长相比，模型的 $R _ { \mathrm { ~ C ~ } } ^ { 2 }$ 从0.925升高到0.954， $R _ { \mathrm { ~ V ~ } } ^ { 2 }$ 从0.834增加到0.924，模型效果改善显著。同时 $R _ { \mathrm { ~ P ~ } } ^ { 2 }$ 从0.924增加到0.952，样品预测值与原始值的相关性更高，如图3；SEC 与 SECV 更小，且比值也小于全光谱模型，说明CARS-PLS 定标模型精确度更高，且稳定性更优。同时，由于无关信息变量的减少，消除了模型的过拟合现象。最终建立的定量分析模型为：用CARS算法筛选特殊波长，定标方法为PLS，光谱预处理采用 Derivate（2-2-21）、MSC，模型 SEC与SECV分别为0.551、0.659，RPD值为3.83。

![](images/bab1a5a2b8aabb71cdf05c6e29c3d5a12ec9f1fa1ca9f92fdc73fa4a6258d714.jpg)  
图3特征彼长与全波长近红外模型外部验证结果  
Fig.3Validation results of characteristic wavelength and full wavelength of near infrared model.

# 4结论

选用60 目粉碎烘干后的样品获取近红外光谱，通过CARS算法筛选特殊波长，用 PLS建立的定标分析模型质量最优，外部验证样品的实测值与预测值的 $\boldsymbol { R } _ { \mathrm { ~ P ~ } } ^ { 2 }$ 为0.952，表明该定

标模型准确度较高、稳定性好，对于 $L$ -赖氨酸硫酸盐样的检测分析具有一定的可行性。

# 参考文献:

[1] 陈宝利,张青萍.赖氨酸生产的现状及未来的发展方向[J].辽宁化工,2011,40(8):872-873.

[2] 朱进龙,臧建军,曾祥芳,等.80赖氨酸与70赖氨酸和98赖氨酸对生长肥育猪饲喂效果的比较研究[J].中国畜牧杂志,2014,50(21):27-31.

[3]王自蕊,游金明,谯仕彦.赖氨酸硫酸盐相对于赖氨酸盐酸盐的生物学效价评定[J].动物营养学报,2008,20(1):52-57.

[4]张丽英,杨文军,李冰颖.L-赖氨酸硫酸盐的质量标准与含量检测技术[J].饲料工 业,2007,28(1):35-36.

[5]褚小立,袁洪福.近红外光谱分析技术发展和应用现状[J].现代仪器,2011,17(5):1-4.

[6] 刘波平,秦华俊,罗香,等.偏最小二乘-反向传播-近红外光谱法同时测定饲料中 4 种氨基酸[J].分析化学,2007,35(4):525-528.

[7]褚小立,陆婉珍.近红外光谱分析技术在石化领域中的应用[J].仪器仪表用户,2013,20(2):11-13.

[8] 於筱岚,何勇,徐宁.近红外分析技术在食品氨基酸检测中应用的研究进展[J].光谱学与光谱分析,2014,34(9):2377-2381.

[9] ROGGO Y,CHALUS P,MAURER L,et al.A review of near infrared spectroscopy and chemometrics in pharmaceutical technologies[J].Journal of Pharmaceutical and Biomedical Analysis,2007,44(3):683-700.

[10] 邱军,王允白,张怀宝,等.烟草中淀粉、石油醚提取物的近红外光谱分析模型研究[J].分析化学,2006,34(4):588.

[11]胡茶根,赵红霞,边文亮.近红外技术在茶叶快速无损检测方面的研究与应用[J].食品科学,2007,28(10):638-641.

[12] 闵顺耕,覃方丽,李宁,等.傅里叶变换近红外光谱法测定大麦中蛋白质、淀粉和赖氨酸含量[J].分析化学,2003,31(7):843-845.

[13] 李楠,许韵华,宋雯雯,等.利用近红外光谱技术快速检测大豆氨基酸含量[J].植物遗传学报,2012,13(6):1037-1044.

[14] BAGCHI T B,SHARMA S,CHATTOPADHYAY K.Development of NIRS models to predict protein and amylose content of brown rice and proximate compositions of rice bran[J].Food Chemistry,2016,19:21-27.

[15] LIN C,CHEN L,SHI C H,et al.Determination of grain protein by near-infrared spectrometry and multivariate calibration in barley[J].Food Chemistry,2014,162:10-15.

[16]李勇,魏益民,王峰.影响近红外光谱分析结果准确性的因素[J].核农学报,2005,19(3):236-240.

[17] 闵顺耕,李宁,张明祥.近红外光谱分析中异常值的判别与定量模型优化[J].光谱学与光谱分析，2004,24(10):1205-1209.

[18] 李江波,彭彦昆,陈立平,等.近红外高光谱图像结合CARS 算法对鸭梨 SSC 含量定量测定[J].光谱学与光谱分析,2014,34(5):1264-1269.

[19] 陶琳丽,黄伟,杨秀娟,等.20 种氨基酸近红外光谱及其分子结构的相关性[J].光谱学与光谱分析,2016,36(9):2766-2773.

[20] COZZOLINO D,CHREE A,SCSAIFE JR,et al.Usefulness of near-infrared reflectance (NIR) spectroscopy and chemometrics to discriminate fishmeal batches made with different fish species[J].Agricultural And Food Chemistry,2005,53(11):4459-4463.

# Near Infrared Rapid Determination Method for $L$ -Lysine Content in Feed Additive $L$ -Lysine

Sulfate

LI ShouXue1,2CHEN Yueyan³JIA Zheng'XIAO Zhiming1WANG Yanni1LIU Chenxin' FAN Xial\* (1. Institute of Quality Standards & Testing Technology for Agro-Products, Chinese Academy of Agricultural Sciences, Beijing 10oo81, China; 2. College of Engineering, China Agricultural   
University, Beijing 100083, China; 3.Animal Feed Quality and safety of Veterinary Testing Centre in Liaoning Province, Shenyang l1oo16, China)

Abstract: In order to explore the feasibility of near infra diffuse reflectance spectroscopy (NIDRS) method for rapidly quantitative determination of $L$ -lysine content in feed additive $L$ -lysine sulfate, seventy-six representative samples of $L$ -lysine sulfate were collected in China.According to the national standard method to chemical evaluated the $L$ -lysine content of samples; the near infrared spectrogram of $L$ -lysine sulfate samples at different physical states were scanned by raster near infrared diffuse reflectance spectroscopy instrument. On the basis of $L$ -lysine content samples were divided into calibration and validation sets, using appropriate spectral pretreatment method, the near infrared quantitative analysis model of $L$ -lysine sulfate was established by using competitive adaptive reweighted sampling (CARS) algorithm combined partial least square method (PLS),and compared with the full wavelength model. The results showed that the optimal calibration model was established with the sample of dry and crushed at 6O mesh,and the determination coefficient of correction calibration set $( R _ { { \mathrm { ~ C ~ } } } ^ { 2 } )$ was 0.954, the standard error of calibration（SEC） was 0.510,the standard error of cross validation（SECV） was 0.659.The determination coefficient of prediction validation set $( R _ { \mathrm { ~ P ~ } } ^ { 2 } )$ ）was 0.952, the standard error of prediction（SEP） was O.554,the relative percent deviation （RPD） value was 3.83.In conclusion,NIDRS quantitative analysis of $L$ -lysine sulfate has certain feasibility,it has practical application significance for rich other amino acids fast detection methods in our country.

Keywords: lysine; NIDRS; rapid determination model; CARS