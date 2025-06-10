# 纳米孔测序技术应用于食品微生物检测的可行性分析

曹必溥1，缪丽华1，贺丽苹 2\*(1．广州广检质量检测研究院有限公司，广东广州)(2．华南农业大学测试中心，广东广州510642)

摘要：近些年来DNA测序技术发展迅速，已经从第一代生化测序发展到第三代单分子测序。作为第三代测序技术中的一种，纳米孔测序技术是基于电信号的一种物理方法测序，不同于当前流行的其他测序技术。许多研究者通常将高通量测序技术应用于食品微生物的研究，但是将纳米孔测序技术应用于食品中微生物的检测却鲜有报道。OxfordNanopore Technologies（牛津纳米孔科技公司）研发的DNA 测序仪MinION，是世界首例用于商业测序的纳米孔测序仪，经过不断完善，近年来MinION在DNA 测序中被广泛应用。MinION 测序一次需要的 DNA量约 $1 \mu \ g$ ，其标准识别速度为一秒钟识别250个碱基，平均读长可至 $1 3 \mathrm { k b } { \sim } 2 0 \mathrm { k b }$ 测序准确率可以达到 $98 \%$ 。纳米孔测序的高识别速度和高准确率，完全满足快速检测的要求，将其应用于食品中微生物检测是完全可行的。

关键词：纳米孔测序；DNA 测序技术；食品微生物

# The feasibility analysis that Nanopore sequencing technology is applied to food microbiological detection

CAO Bi-pu1，MIAO Li-hual，HE Li-ping2\* (1. Guangzhou Guangjian Quality Testing and Research Institute Co.,Ltd.,Guangzhou, China) (2. Testing Center of South China Agricultural University, Guangzhou, 510642, China)

Absrtact: DNA sequencing technology has developed rapidly in recent years and has evolved from the first generation of biochemical sequencing to the third generation of single molecule sequencing. As one of the third-generation sequencing technologies, nanopore sequencing is a physical method that based on electrical signals, different

from other current popular sequencing technologies. Many researchers usually apply high-throughput sequencing techniques to the study of food microorganisms, but there are few reports of the application of nanopore sequencing technology to the detection of microorganisms in food. Oxford Nanopore Technologies successfully developed DNA sequencing instrument of MinION, the world's first commercial instrument for the nanopore sequencing. After continuous improvement in recent years, MinION has been widely used in the DNA sequencing. The amount of DNA required for the sequencing of MinION is about $1 \mu \ g$ DNA. The standard recognition speed of one second for 250 bases, the average reading length of 13kb to 20kb and sequencing accuracy to $98 \%$ . Its high recognition speed and high accuracy meet the requirements of rapid detection, feasible to be applied to microbiological detection in food. Keywords: nanopore sequencing; DNA sequencing technology; food microorganism

随着人民生活质量的日益提高，消费者对食品的质量安全十分关注。微生物污染作为食品污染的主要来源，对食品质量安全具有重大隐患，危害消费者的健康，需要有效的检测方法对其进行监测。食品中微生物的检测方法目前主要采用传统的培养方法，传统的检测方法虽然有效，但存在操作过程复杂、培养时间久等问题，难以满足快速检测的要求。近年来，为了提高检测效率，研究者将分子生物学技术应用于食品微生物的检测，尤其是食源性致病菌的检测。常用的分子生物学技术有：PCR 技术（聚合酶链式反应）[1,2]，LAMP 技术（环介导恒温扩增法）[3-5]，核酸探针技术[6,7]，基因芯片技术[8]，DNA序列分析技术[9-11]等。其中 DNA序列分析技术是在基因水平上对食品中微生物进行分析和鉴定，可有效排除检测过程中假阳性和假阴性的干扰[10]。DNA 测序是DNA序列分析技术不可缺少的一环，只有通过测序获得DNA序列才能进行后续的分析。随着科技的不断进步，DNA测序技术也得到了极大的发展，从第一代化学测序发展到第三代的单分子测序。

纳米孔测序技术是一种新型的第三代DNA 测序技术[12],本文对纳米孔DNA测序技术的原理及其在DNA测序中的应用进行了综述，并对其应用于食品微生物检测的可行性进行了探讨。

# 1.DNA测序技术发展

1944 年，Avery 等[13]通过肺炎双球菌转化实验证明了DNA是遗传信息的载体。Watson 和Crick[14]于1953年提出了著名的DNA双螺旋结构模型，开启了DNA 测序的时代。关于DNA 测序技术较早的报道，是Whitfeld 等人[15]于1954年采用化学降解法测定多聚核糖核苷酸序列。1977年 Sanger[16]发明DNA双脱氧核苷酸末端终止测序法（chain terminator sequencing），同年 Maxam 和 Gilbert[17]发明DNA 化学降解测序法(chemical degradation sequencing),这两项技术的出现,标志着第一代测序技术的诞生。相比化学降解测序法，Sanger 测序技术由于操作快速、简单，准确率高等优点，被应用于人类基因组的测序[18]。

第二代测序技术又被称为下一代测序技术（next generation sequencing，NGS）[19]。由于其测序速度快、读长较长、一次性能测出多条序列，也被称为高通量测序技术。2004 年Roche 公司推出 454 测序平台,2006 年 Illumina 公司推出 Solexa测序平台，2007年 ABI公司推出 SOLiD 测序平台[20]，这些测序平台为第二代测序的主流平台。与第一代测序技术的化学反应方法不同，第二代测序技术采用荧光标记脱氧核糖核苷酸（dNTP），以测序仪捕捉荧光信号，从而确定被测 DNA的序列。

在第二代测序平台不断完善和广泛使用的同时，对单分子DNA进行测序的技术也开始逐步发展起来。2003年，Braslavsky 等人的研究验证了单分子测序的可行性[21]。2008 年，Harris 等人[22]开发出 tSMS（true single molecular sequencing)测序技术，Helicos Biosciences 公司基于该技术推出 HeliScope 单分子测序平台，该平台被认为是第一个商品化的第三代测序仪。2008 年Clarke等人[23]将α -溶血素与核酸酶结合，核酸酶将单链DNA分子的碱基按顺序剪切，在电场作用下依次通过α-溶血素，发现α-溶血素可连续识别通过的碱基，为蛋白纳米孔应用于DNA 测序奠定了技术基础。2010 年 Stoddart等人[24]对α-溶血素的氨基酸位点进行修饰，进一步加强了蛋白纳米孔对碱基的识别能力，使得研发稳定可靠的纳米孔测序仪成为可能。基于以上技术，2014 年Oxford Nanopore Technologies（牛津纳米孔科技公司）成功研发了世界上首例且唯一的纳米孔DNA 测序仪—MinION，并于 2015 年开始销售[25]。2009 年Pacific Biosciences 公司推出一种单分子实时测序方法—SMRT(single-molecule,real-time sequencing)测序技术[26]。

目前，Helicos 公司的tSMS，Pacific公司的SMRT和牛津纳米孔测序技术是主流的第三代测序技术。

# 2.纳米孔测序原理

纳米孔(nanopore)，可以简单地定义为内径为 $1 \sim 1 0 0 \mathrm { n m }$ 的微小洞孔，一般孔径应大于洞孔深度，或者处于同一量级[27]。纳米孔测序不同于其他测序方法，其原理是基于电信号的测序技术。DNA序列由碱基组成，组成DNA的四种碱基腺嘌呤(A)、鸟嘌呤(G)、胞嘧啶(C)和胸腺嘧啶(T)，其分子结构不同、体积大小不同，当单个核苷酸分子在电场驱使下，穿过纳米孔时，会引起电信号的变化，不同碱基引起的变化不同，因而可通过监测电信号的变化测定不同片段单链DNA的碱基序列，从而最终确认基因序列[27]。

由此可见，纳米孔测序基于电信号，是物理方法的测序，这与第一代的化学方法测序，以及第二代的生化方法测序有很大区别。化学方法测序，需要通过化学反应来终止测序，通过凝胶电泳和同位素放射性自显影等获得DNA序列，测序过程相对繁琐[28]。生化方法测序，需要构建测序文库，PCR扩增，荧光标记等[29]，耗时长，且PCR扩增时会发生一定的差错。而纳米孔测序无需使用酶进行样品扩增，具有长读长、低成本、高通量、非标记等优势[30]。

# 3.纳米孔测序分类

按照纳米孔的来源不同，目前用于DNA测序的纳米孔大致可分为2类：生物纳米孔和固态纳米孔。生物纳米孔是利用生物体内天然存在的通道蛋白作为纳米孔来源，而固态纳米孔主要利用硅及其衍生物，通过人工制造而成，而非天然存在的。

# 3.1生物纳米孔

生物纳米孔工作原理如图1所示，检测池内加入高盐溶液，在纳米孔两端施加一个外加电场后，当纳米孔中没有单链DNA分子通过时，产生的电流是恒定的。当单链DNA分子进入并穿过纳米孔时，引起电流的减小，产生阻断电流信号，通过将电流信号放大，再转换成数字信号[31]。由于不同碱基产生的阻断电流信号大小不同，从而可以通过阻断电流信号的大小来识别DNA的碱基序列。

![](images/dbd0e16ae39d3b95ae14e3121a1005b80eea3c7e06bae858813fd84ab9975e67.jpg)  
图1生物纳米孔测序原理图[31]

生物纳米孔大多是生物体内天然存在的固有纳米器件，具有特有的孔径结构、生物活性和功能，由于可进行自由的分子设计和灵活的化学或生物修饰而受到科学家的青睐[32]。目前常用的生物纳米孔有 ${ \mathfrak { a } } .$ 溶血素（ $\scriptstyle \mathbf { a - H L }$ ）和耻垢分枝杆菌孔蛋白 A(Mycobacterium smegmatis porinA，MspA)[33](图 2)。

![](images/51ebd232e0ab797de130c20e20138c61e5597c2aba14469e43063a3caa6f072d.jpg)  
Fig.1The principle of biological nanopore sequencing[31]   
图 $2 \ { \mathfrak { a } } .$ 溶血素(a)和耻垢分枝杆菌孔蛋白A(MspA)(b)三维模型[33] Fig.2Three-dimensional model of $\mathfrak { a }$ -hemolysin (a)and Mycobacterium smegmatis porinA(b)[33]

$\mathfrak { a }$ -溶血素是一种七聚体孔蛋白，主要由帽型区(Cap)、边缘区(Rim)和主干区(Stem)三部分构成，主干区是由 $\beta \cdot$ -桶状结构折叠而成，该桶状结构插入到脂双分子层中形成了跨膜通道，长度约 $5 \mathrm { n m }$ ，中间收缩区直径为 $1 . 4 \ : \mathrm { n m } ^ { [ 3 4 ] }$ 。1996年Kasianowicz等人[35]采用 ${ \mathfrak { a } } .$ -溶血素构建了第一个生物纳米孔测序模型，检测到单链DNA和RNA分子通过纳米孔所造成的电流变化。该模型可以检测到核苷酸通过纳米孔的电流信号，但是核苷酸通过纳米孔的速度太快，每个核苷酸通过纳米孔时间约为 $_ { 1 \sim 2 0 }$ 微秒[30]，不利于准确识别单个碱基。在Clarke[23]和 Stoddart等人[24]对 ${ \mathfrak { a } } \cdot$ -溶血素的研究基础上，Cherf等人[36]将 ${ \mathfrak { a } } .$ -溶血素与phi29DNA聚合酶相结合，降低了DNA分子通过 ${ \mathfrak { a } } .$ -溶血素纳米孔的速度，实现了对DNA分子的实时测序(图3)。2014 年牛津纳米孔科技公司以 ${ \mathfrak { a } } .$ -溶血素为纳米孔通道，成功研发了纳米孔DNA 测序仪—MinION。

![](images/7ab8471f849818b8d1b521643b5092525e47a85b324e6cfd7466aea8573c6b0d.jpg)  
图3 $\mathfrak { a }$ -溶血素与phi29DNA聚合酶的测序组合体[36]   
Fig.3Sequencing combination of $\mathfrak { a }$ -hemolysin and phi29 DNA polymerase[36]

耻垢分枝杆菌中的孔蛋白(Mycobacter iumsmegmatis porinA,MspA)是适合研究 DNA 测序的另一种纳米孔蛋白。MspA呈圆锥状，是一种八聚体孔蛋白，有一个宽约 $1 . 2 \mathrm { n m }$ ，长约 $0 . 5 \mathrm { n m }$ 的收缩区[37]。与 5nm 长的 $\mathfrak { a }$ -溶血素蛋白孔相比，更有利于对单碱基的测定。2008 年Butler等人利用 MspA 纳米孔进行单链DNA 分子的检测，采用单链DNA分子的发夹结构来控制转移速度，得到较好的测序效果[38]。Manrao 等人[39]将MspA 纳米孔与phi29DNA 聚合酶相结合进行 DNA测序，将单链DNA进入MspA 纳米孔的速度控制在一个碱基约28 毫秒，获得了极易分辨的阻断电流信号，4种脱氧核苷酸之间的阻断电流差异高达 $4 0 \mathrm { p A }$ 图4)。

![](images/2992e410a380fe8cb97695198fbac7cf92c745a3ce1671680c3dca360a7b05e2.jpg)  
图4MspA与phi29DNA 聚合酶的测序组合体[39]

Fig.4Sequencing combination of MspA and phi29 DNA polymerase[39]

# 3.2固态纳米孔

固态纳米孔主要利用硅及其衍生物制造而成，一般使用离子束或电子束在硅或其他材料薄膜表面钻出纳米尺度的孔洞，再进一步对孔的形状和大小进行修饰而成[40]。采用固态纳米孔检测DNA序列，目前处于探索阶段，许多研究者正在研究不同的测序方法，以完善固态纳米孔的测序技术。Hall等人将α-溶血素的${ \mathfrak { \beta } } .$ -桶状结构上链接一段DNA分子，通过电泳的方式将其装载在固态纳米孔上，组成一种混合的测序模型，该方法需要保证固态纳米孔的孔径在 $2 . 4 \sim 3 . 6 ~ \mathrm { n m }$ 孔径太大或太小都不利于α -溶血素的固定[41]。Garaj 等人利用石墨烯纳米孔进行单分子探测器的研究，发现DNA分子通过石墨烯纳米孔所花时间比其他离子要长，表明DNA分子与石墨烯纳米孔存在某种相互作用，从而延长了转移时间[42]。

# 4.纳米孔测序应用于食品微生物检测的展望

4.1DNA测序技术在食品微生物研究的应用

随着DNA测序对分子生物学发展的影响，食品微生物学的研究发生了巨大的改变，功能基因组学、转录组学、蛋白质组学和代谢组学等不依赖于微生物培养的技术都已经被应用到食品微生物研究中[43]。高通量测序技术（NGS）也被广泛应用在食品中微生物菌株的测序和微生物多样性的研究，为研究人员探索食品，尤其是发酵食品中的一些功能作用机制提供了一种新的研究方法[44]。

DNA 测序技术除了用于食品微生物基因组学和微生物多样性的研究外，同时也被应用到单个基因的DNA序列分析中，单个基因的DNA序列分析主要是应用于食品中微生物种类鉴定。徐保红等人采用PCR-焦磷酸测序法，对特定基因进行测序，准确鉴定了56株副溶血性弧菌[9]。曹冬梅等人采用同样的方法对食品中的肠炎沙门菌进行快速鉴定，准确鉴定了16株肠炎沙门菌[]。徐保红和曹冬梅等人使用PCR-焦磷酸测序法，将测序所得的DNA序列经过NCBI的BLAST分析（https://blast.ncbi.nlm.nih.gov/Blast.cgi），与目标菌的基因组序列进行比对，最终确定是否存在目标菌。

BLAST分析是以微生物基因组作为数据基础，只有越来越多的微生物基因组被测序，该分析方法的适用范围才会涵盖越来越多的微生物种类。随着食品微生物基因组学的研究迅速发展，已完成或正在进行基因组测序的食品微生物数量迅速增加[45]。

# 4.2生物纳米孔在DNA 测序中的应用

可用于DNA测序的纳米孔有生物纳米孔和固态纳米孔。但是目前只有生物纳米孔用于商业的测序，固态纳米孔处于研究阶段，没有实现商业化量产。牛津纳米孔科技公司的MinION 测序仪是第一款正式量产的纳米孔测序仪，是以α-溶血素作为纳米孔材料的测序平台，自2015年开始销售以来，在生物分子学领域被广泛使用。Deschamps 等人[46]使用MinION 测序平台对农杆菌的基因组进行测序，获得了高准确度的DNA序列。2016年宇航员KateRubins在国际空间站上使用MinION 进行DNA 测序实验，并取得成功，这是DNA在太空微重力环境中第一次被成功测序[47]。Quick 等人使用MinION 测序平台建立了一套便携式的DNA测序系统，该系统在几内亚被用于对埃博拉病人的样本进行检测，可实时监测埃博拉病毒的变异情况，为埃博拉疫情的控制提供了良好的技术支撑[48]。Menegon 等人[49]采用MinION对热带雨林中野生蛙类的血液样品进行测序，快速鉴定了该野生蛙的具体种类。纳米孔测序技术在分子生物学领域已经被广泛应用，将其应用于食品微生物研究是非常可行的。

4.3纳米孔测序技术应用于食品微生物检测的可行性

DNA测序技术在不断的发展，测序所需要的时间越来越短，花费的成本也越来越低。1990年启动的人类基因组计划使用第一代测序技术，历时13年，花费约30 亿美元[50]。2008 年使用第二代测序技术，对诺贝尔获得者JamesWatson的个人基因组的测序，历时2个月，花费约100 万美元[51,52]。对于哺乳动物的基因组，纳米孔测序技术具有将测序成本降低至1000美元且在24小时内完成测序的潜力[30]。

MinION作为第一款正式量产的纳米孔测序仪，其体积比普通U盘稍大，重量约90克可以装进口袋中，携带十分方便[53](图5)。1000美元就能购买的MinION，使用USB数据线和电脑相连接，由电脑提供电源，同时进行数据的传输[25]。MinION 测序一次需要的DNA量约 $1 \mu \ g$ ，上样量为 $7 5 \mu 1 ^ { \left[ 5 4 \right] }$ 。采用常用的 DNA提取方法，从食品微生物中提取的总DNA是可以满足MinION的测序要求。吴坤等人[55]采用 SDS 法和 SDS/CTAB法分别提取小麦表面微生物总DNA，得到的总DNA 浓度分别为 $3 3 1 7 . 5  { \mu \mathrm { \ g / m l } }$ 和 $3 8 2 0 \mu \mathrm { g / m l }$ 。秦丹[56]采用5种常用的提取方法提取发酵肉制品中微生物总DNA，得到的总DNA 浓度在 $2 6 0 { \sim } 4 1 0 ~ \mu$ g/ml。

![](images/ad45c0eb1cf97567e6514ae0b42599dafc5dcdff633abb439b9b2c7162a8844b.jpg)  
图5 MinION测序仪[25]  
Fig.5MinION sequencing machine[25]

MinION默认运行时间为48小时，运行2分钟产生的数据就可以用于相关分析，其标准识别速度为一秒钟识别 250 个碱基（250bps）[54]，平均读长可以达到 $1 3 \mathrm { k b } { \sim } 2 0 \mathrm { k b } ^ { \left[ 5 7 \right] }$ 。徐保红[9]和曹冬梅[1]等人对食品中致病菌的鉴定采用了几十个碱基序列，甚至十几个碱基序列。Menegon 等人[49]采用约 600 个碱基(600bp)的DNA序列快速鉴定了热带雨林中一种野生蛙类的具体种类。MinION测序的错误率为 $5 \mathrm { { \sim } 1 0 \% ^ { [ 5 8 ] } }$ ，比目前流行测序仪 Illumina MiSeq 和 HiSeq 的错误率还要低[59]。通过提高测序深度，MinION测序的准确率可以达到 $9 8 \% [ 6 0 ]$

尽管MinION具有测序速度快，准确率高等优点，但是生物纳米孔使用的脂基质，其机械稳定性较弱[61]，反复洗涤会降低测序芯片的使用寿命。MinION 运行一次需要99 美元，测序芯片（Flowcell）使用寿命约为72小时，一块测序芯片的费用为500\~900 美元[54]。使用成本高将会限制MinION在食品微生物检测领域的广泛应用。2018年牛津纳米孔科技公司将推出更便携的 SmidgION，其测序芯片和MinION相同，该设备是针对智能手机开发出的DNA 测序仪，通过智能手机提供电源并进行操作，具体售价没有对外公布[25]。

相比生物纳米孔，固态纳米孔具有优良的机械稳定性、化学稳定性和热稳定性[61,62]，同时还可以对纳米孔的尺寸和形状进行亚纳米级的调整[63]，可以制造高密度的纳米孔阵列[64]。但是DNA通过固态纳米孔的速度过快以及固态纳米孔对DNA的识别率较低[61]，这限制了固态纳米孔用于DNA测序。如果能够突破这些缺点，以固态纳米孔作为测序芯片，将提高测序芯片的使用寿命，降低DNA测序成本，使得纳米孔测序更容易被应用于食品微生物的检测领域。

相信研究人员的不断努力，可以开发出更稳定的生物纳米孔，可以克服DNA通过固态纳米孔的速度过快和固态纳米孔对DNA低识别率的问题，不断完善纳米孔测序技术，提高检测的稳定性，降低检测成本，纳米孔测序将会广泛应用于食品微生物的检测。

# 参考文献

[1] 刘仲敏,郑鸣,王永芬,等.食源性沙门氏菌实时定量PCR 检测研究[J].食品工业 科技,2007,28(8):233-236.   
LIU Zhong-Min,ZHENG Ming,WANG Yong-Fen,et al.The detection of salmonella in food by real-time quantitative PCR[J].Science and Technology of Food   
Indust,2007,28(8):233-236.   
[2] 蔡亦红,姚余有.3种食源性致病菌的多重PCR 快速检测方法的建立[J].中国卫 生检验杂志,2007,17(11):1959-1962.   
Cai Yi-hong,Yao Yu-you.Establishment and application of multiple PCR for   
diagnosing three food-borne bacterial pathogens[J].Chinese Journal of Health   
Laboratory Technology,2007,17(11):1959-1962.

[3]王敏雅,徐明汉,潘宏伟,等.沙门菌 invA基因LAMP 快速检测法的建立和初步应用[J]．中国卫生检验杂志,2008,18(10):1971-1981.

Wang Min-ya, Xu Ming-han, Pan Hong-wei,et al.Establishment and preliminary application of LAMP inv Ageneassay for rapid detection of Salmonella[J].Chinese Journal of Health Laboratory Technology,2008,18(10):1971-1981.   
[4] 李永刚,王德国,吴建刚,等.环介导恒温扩增法(LAMP)检测金黄色葡萄球菌[J]. 食品工业科技,2010,31(1):388-391.   
LI Yong-gang, WANG De-guo, WU Jian-gang,et al.Detecting of Staphylococcus aureus by loop-mediated isotherma lamp lification (LAMP) method[J].Science and Technology of Food Industry,2010,31(1): 388-391.   
[5] 姜侃,吕沁风,汪新,等.三重LAMP 法检测食品中沙门氏菌、单增李斯特菌和金 黄色葡萄球菌[J].食品科学,2013,34(24):182-187.   
JIANG Kan,LU Qin-feng,WANG Xin,et al.Development of Multiplex LAMP Method for the Detection of Salmonella spp.,Staphylococcus aureus and Listeria   
monocytogenes in Foods[J].Food Science,2013,34(24): 182-187.   
[6] Rudi K,Flateland S L,Hanssen J F,et al.Development and evaluation of a 16S ribosomal DNA array based approach for describing complex microbial communities in ready-to-eat vegetable salads packed in a modified atmosphere [J].Appl Environ Microbiol,2002,68:1146-1156.   
[7] 周凤丽,简纪常,吴灶.地高辛标记的DNA探针制备及其应用于溶藻弧菌的检 测[J].华中农业大学学报,2009,28(4):459-462.   
ZHOU Feng-li,JIAN Ji-chang,WU Zao-he.Preparation and Application of   
Digoxigenin Labeled DNA Probe for Detection of Vibrio alginoly ticus[J].Journal of Huazhong Agricultural University,2009,28(4):459-462.   
[8] 何冬梅，王洪敏，柯昌文,等．单增李斯特菌检测基因芯片的研制与评价[J]. 中华微生物学和免疫学杂志,2011,31(10):916-921.   
HE Dong-mei,WANG Hong-min,KE Chang-wen,et al.Development and evaluation of a DNA microarray for Listeria monocyiogenes detection[J].Chinese Journal of Microbiology and Immunology,2011, 31(10):916-921.

[9] 徐保红,李秀娟,杨芳,等.PCR-焦磷酸测序法快速鉴定副溶血性弧菌[J].预防医学情报杂志,2011,27(01):78-80.

XU Bao-hong,LI Xiu-juan,YANG Fang,et al.Detection of Vibrio parahaemolyticus by PCR and Pyrosequencing[J].Journal of Preventive Medicine   
Information,2011,27(01):78-80.   
[10]朱珠,王永,兰青阔,等.应用焦磷酸测序技术快速检测食品中沙门氏菌[J].食品 科学,2013,34(2):182-186.   
ZHU Zhu,WANG Yong,LAN Qing-kuo,et al.Application of Pyrosequencing   
Technology for Rapid Detection of Sallmonella spp. in Foods[J].Food   
Science,2013,34(2):182-186.   
[11] 曹冬梅,倪长鹏,刘宇,等.PCR-焦磷酸测序法快速鉴定食品中肠炎沙门菌[J]. 大连工业大学学报,2015,34(01):29-33.   
CAO Dongmei,NI Changpeng,LIU Yu,et al.Rapid detection of Salmonella enteritidis in food by PCR-pyrosequencing[J].Journal of Dalian Polytechnic   
University,2015,34(01):29-33.   
[12] Feng Liang ,Peiming Zhang. Nanopore DNA sequencing: Are we there   
yet?[J].Science Bulletin.2015,60(3):296-303.   
[13] Avery, O.T., MacLeod, C.M. & McCarty, M. Studies on the chemical nature of the substance inducing transformation of pneumococcal types.[J].Journal of   
Experimental Medicine， 1944， 79(2):137-158.   
[14] Watson, J.D.; Crick, F.H. Molecular structure of nucleic acids; a structure for deoxyribose nucleic acid[J].Nature. 1953 ,171(4356):737-738.   
[15] Whitfeld P. R..A method for the determination of nucleotide sequence in polyribonucleotides[J]. Biochem J,1954, 58(3):390-396.   
[16] Sanger F., S. Nicklen, A., R.. Coulson. DNA sequencing with chain-terminating inhibitors[J]. Proc Natl Acad Sci USA, 1977,74(12):5463-5467.   
[17] Maxam A. M. W.. Gilbert. A new method for sequencing DNA[J].Proc Natl Acad Sci USA, 1977,74(2):560-564.   
[18] International Human Genome Sequencing Consortium. Finishing the   
euchromatic sequence of the human genome[J]. Nature,2004, 431(7011):931-945.

[19] Schuster S C. Next-generation sequencing transforms today's biology[J]. Nature Methods,2008,5(1):16-18.

[20] Mardis E. R.. The impact of next-generation sequencing technology on genetics [J]. Trends in Genetics,2008,24(3):133-141.   
[21] Braslavsky I, Hebert B, Kartalov E, et al. Sequence information can be obtained from single DNA molecules [J]. Proc Natl Acad SciUSA,2003,100(7):3960-3964. [22] Harris TD，Buzby PR，Babcock H，et al.Single-molecule DNA sequencing of a viral genome[J]. Science,2008,320(5872):106-109.   
[23] Clarke J, Wu HC, Jayasinghe L, et al. Continuous base identification for   
single-molecule nanopore DNA sequencing[J]. Nat Nanotechnol., 2009, 4(4):   
265-270.   
[24] Stoddart D, Heron A J, Klingelhoefer J, et al. Nucleobase Recognition in ssDNA at the Central Constriction of the α -Hemolysin Pore[J]. Nano Leters, 2010,   
10(9):3633-3637.   
[25] https://nanoporetech.com/cn/   
[26] Eid J, Fehr A,Gray J, et al. Real-time DNA sequencing from single polymerase molecules[J]. Science,2009,323(5910):133-138.   
[27]王凯歌,窦硕星,王鹏业,等.利用纳米孔研究DNA[J].物   
理,2004,33(08):579-586.   
WANG Kai-Ge,DOU Shuo-Xing,WANG Peng-Ye,et al.Study DNA with a   
nanopore[J].Physics,2004,33(08):579-586.   
[28] 刘振波.DNA 测序技术比较[J].生物学通报,2012,47(07):14-17.   
LIU Zhen-Bo.DNA sequencing technology comparison[J].Bulletin of   
Biology,2012,47(07):14-17.   
[29] 谢浩,赵明,胡志迪,等.DNA 测序技术方法研究及其进展[J].生命的化   
学,2015,35(06):811-816.   
XIE Hao,ZHAO Ming,HU Zhidi,et al.Research of the methods for DNA sequencing technology and its progress[J].Chemistry of Life,2015,35(06):811-816.   
[30] Branton D, Deamer D W, Marziali A, et al. The potential and challenges of nanopore sequencing.[J]. Nature Biotechnology, 2008, 26(10):1146-1153. [31] Ying Y L, Cao C,Long Y T. Single molecule analysis by biological nanopore sensors.[J]. Analyst, 2014, 139(16):3826-3835.   
[32]张春萍.a溶血素纳米孔的研究进展和应用[J].基因组学与应用生物   
学,2014,33(05):1114-1118.   
Zhang Chunping.The Research Progress and Application of α -Hemolysin   
Nanopore[J].Genomics and Applied Biology,2014,33(05):1114-1118.   
[33] Venkatesan B M, Bashir R. Nanopore sensors for nucleic acid analysis[J]. Nature Nanotechnology, 2011, 6(10):615-624.   
[34] Song L, Hobaugh M R, Shustak C, et al. Structure of staphylococcal   
alpha-hemolysin, a heptameric transmembrane pore[J]. Science, 1996,   
274(5294):1859-1866.   
[35] John J. Kasianowicz, Brandin E, Branton D,et al. Characterization of individual polynucleotide molecules using a membrane channel[J]. Proceedings of the National Academy of Sciences of the United States of America, 1996, 93(24):13770-13773. [36] Cherf G M, Lieberman K R, Rashid H, et al. Automated Forward and Reverse Ratcheting of DNA in a Nanopore at Five Angstrom Precision1[J]. Nature   
Biotechnol0gy, 2012, 30(4):344-348.   
[37] Derrington I M, Butler T Z, Collins M D, et al. Nanopore DNA sequencing With MspA.[J]. Proceedings of the National Academy of Sciences of the United States of America, 2010, 107(37):16060-16065.   
[38] Butler T Z, Pavlenok M, Derrington I M, et al. Single-molecule DNA detection with an engineered MspA protein nanopore[J]. Proceedings of the National Academy of Sciences of the United States of America, 2008,105(52):20647-20652.   
[39] Manrao E A, Derrington I M, Laszlo A H, et al. Reading DNA at   
single-nucleotide resolution with a mutant MspA nanopore and phi29 DNA   
polymerase[J]. Nature Biotechnology, 2012, 30(4):349-53.   
[40] 陈文辉,罗军,赵超.固态纳米孔:下一代 DNA 测序技术——原理、工艺与挑战 [J].中国科学:生命科学,2014,44(07):649-662.   
CHEN WenHui,LUO Jun,ZHAO Chao.Solid-state nanopore: the next-generation

sequencing technology-principles, fabrication and challenges[J]. Scientia Sinica(Vitae),2014,44(07):649-662.

[41] Hall A R, Scott A, Rotem D, et al. Hybrid pore formation by directed insertion of α -haemolysin into solid-state nanopores.[J]. Nature Nanotechnology, 2010,   
5(12):874-877.   
[42] Garaj S, Hubbard W, Reina A, et al. Graphene as a subnanometre trans-electrode membrane.[J]. Nature, 2010, 467(7312):190-3.   
[43] Sarah O'Flaherty, Todd R.Klaenhammer. The impact of omic technologies on the study of food microbes[J]. Annual Review of Food Science and Technology,   
2011,2:353-371.   
[44] Solieri, L., Dakal, T.C., Giudici, P. Next-generation sequencing and its potential impact on food microbial genomics[J]. Annals of Microbiology,2013, 63(1): 21-37. [45]娄恺,班睿,赵学明.食品微生物基因组学的研究进展[J].食品科   
学,2002,23(09):138-140.   
LOU Kai,BAN Rui,ZHAO Xue-ming.Advances in food microbiology   
genomics[J].Food Science,2002,23(09):138-140.   
[46] Deschamps S, Mudge J, Cameron C, et al. Characterization, correction and de novo assembly of an Oxford Nanopore genomic dataset from Agrobacterium   
tumefaciens[J].Scientific Reports. 2016;6(1):28625.   
[47] NASA press release,‘First DNA Sequencing in Space a Game Changer, (29 August 2016)   
[48] J. Quick et al., Real-time, portable genome sequencing for Ebola surveillance[J]. Nature,2016,530:228-232.   
[49] Menegon M, Cantaloni C, Rodriguez-Prieto A, et al. On site DNA barcoding by nanopore sequencing[J]. PLoS ONE. 2017,12(10):e0184741.   
[50]石铁流.新技术能使 DNA 测序的成本降低多少?[J].科学通   
报,2017,62(19):2042-2046.   
SHI TieLiu.How much will new technologies lower the cost of DNA   
sequencing?[J].Chinese Science Bulletin,2017,62(19):2042-2046.   
[51] Wheeler D A, Srinivasan M, Egholm M,et al.The complete genome of an individual by massively parallel DNAsequencing[J].Nature,2008,452(7189):872-876. [52] 王兴春,杨致荣,王敏,等.高通量测序技术及其应用[J].中国生物工程杂 志,2012,32(01):109-114.   
WANG Xing-chun,YANG Zhi-rong,WANG Min,et al.High-throughput Sequencing Technology and Its Application[J].China Biotechnology,2012,32(01):109-114. [53] Miten Jain, Hugh E. Olsen, Benedict Paten， Mark Akeson.The Oxford Nanopore MinION: delivery of nanopore sequencing to the genomics community[J].Genome Biol. 2016; 17(1): 239.   
[54] https://nanoporetech.com/cn/products#comparison   
[55] 吴坤,陈红歌,刘娜,等.小麦表面微生物总DNA 提取方法的比较与改进[J].中 国粮油学报,2003,18(06):34-38.   
Wu Kun,Chen Hong-ge,Liu Na,et al.Comparation and Improvement of Methods to Extract Total DNA from Microbe on the Surface of Wheat Kernels[J].Chinese Cereals and Oils Ass0ciation,2003,18(06):34-38.   
[56] 秦丹．发酵肉制品中微生物总DNA 提取方法比较[A].Proceedings of 2010 First International Conference on Cellular,Molecular Biology, Biophysics and Bioengineering[C].International Science and Engineering Center, Hong Kong、Wuhan Institute of Technology, China,2010:5.   
Qin Dan.Comparison of Methods for Total Microbial DNA Extraction from fermented meat[A].Proceedings of 2010 First International Conference on Cellular,Molecular Biology, Biophysics and Bioengineering[C].International Science and Engineering Center, Hong Kong、Wuhan Institute of Technology, China,2010:5.   
[57] Tyson JR, O'Neil NJ, Jain M, et al. MinION-based long-read sequencing and assembly extends the Caenorhabditis elegans reference genome[J]. Genome Research, 2018,28: 266-274.   
[58] Tyson JR, O'Neil NJ, Jain M, et al.Whole genome sequencing and assembly of a Caenorhabditis elegans genome with complex genomic rearrangements using the MinION sequencing device. bioRxiv. 2017. DOI: 10.1101/099143   
[59] Batovska J,Lynch SE,Rodoni BC, et al. Metagenomic arbovirus detection using MinION nanopore sequencing[J]. J Virol Methods,2017,249:79-84. [60] Giordano Francesca, Aigrain Louise,Quail Michael A., et al. De novo yeast genome assemblies from MinION, PacBio and MiSeq platforms.Scienific   
Reports,2017,7(1):3935.   
[61] Haque, F., Li, J., Wu, HC., et al.Solid-State and Biological Nanopore for Real-Time Sensing of Single Chemical and Sequencing of DNA. Nano Today, 2013, 8(1):56-74.   
[62] Maitra RD., Kim J., Dunbar WB. Recent advances in nanopore sequencing[J]. Electrophoresis, 2012,33(23):3418-3428.   
[63] Liu S., Zhao Q., Li Q., et al. Controlled deformation of $\mathrm { S i } _ { 3 } \mathrm { N } _ { 4 }$ nanopores using focused electron beam in a transmission electron microscope[J]. Nanotechnology, 2011,22(11):115302.   
[64] Kim MJ., Wanunu M., Bell DC., et al. Rapid Fabrication of Uniformly Sized Nanopores and Nanopore Arrays for Parallel DNA Analysis[J]. Adv Mater, 2006, 18(23):3149-3153.