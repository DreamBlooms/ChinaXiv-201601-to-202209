# 肿瘤精准医学知识数据库的设计与构建

汪凌1，陈新2=（1浙江大学化学工程与生物工程学院杭州310027）（2浙江大学药物生物技术研究所杭州310058）

摘要目的：整合现有前沿的大量而分散的精准医学知识以形成系统完整的知识数据库，为个体组学数据的临床应用提供依据，旨在最终实现基于组学特征的精准用药推荐。方法：采用MySQL数据库管理系统构建数据库，从FDA伴随诊断、NCCN指南、My Cancer Genome、GDSC 四大权威医学资源中手动收集精准用药知识，并将原始数据标准化、结构化后以统一的格式存储。结果：成功设计并构建了肿瘤精准医学知识库，目前共收录1940条精准用药指导，涵盖了基因突变等14种不同类型的组学特征。结论：精准医学知识数据库收录了肿瘤分子组学特征和治疗策略的关联信息，可为临床上个体化治疗方案的制定提供参考依据。数据库的建立为精准医疗临床决策支持系统的开发奠定了基础。

关键词肿瘤；精准医学；数据库；组学数据

# Design and construction of tumor precision medicine knowledge database

WANGLingl, CHEN Xin²

(1 College of chemical and biological engineering,Zhejiang University Hangzhou 31oo27,China) (2 Institute of pharmaceutical biotechnology,Zhejiang University Hangzhou 31oo58,China)

Abstract Objective: To integrate substantial but scattered state-of-the-art precision medicine knowledge and form a systematic knowledge network, to support clinical application of individual omics data,aiming at precision medication recommendations.Methods: The database was constructed using MySQL. Precision medicine knowledge from FDA companion diagnosis, NCCN guidelines,My Cancer Genome and GDSC was manually colected in a unified format after being standardized and structured. Results: The tumor precision medicine knowledge base (PMKB) was successfully designed and constructed and has already collected 1940 clinical directives,covering 14 kinds of variations.Conclusion: PMKB collcts information relating tumor mutations and therapeutic strategies, which can provide personalized treatments of reference. PMKB is also the base of constructing a clinical decision support system of precision medicine.

Keywords Tumor; Precision medicine;Database; Omics data

恶性肿瘤已成为目前威胁人类生存健康的最主要因素之一，因癌症死亡的人数占据全球死亡总人数的八分之一[]。然而通过手术、化疗、放疗等传统癌症疗法治疗时，由于缺少对影像、病理学检查可及范围外的肿瘤生理状态的认识，医生无法预测患者对于特定干预的疗效，无法判断肿瘤的复发和转移，导致疗效欠佳，毒副作用明显，易耐药复发，预后较差[2]。而精准医疗作为新兴的个体化医疗模式，可从组学水平更全面地表征个体肿瘤的分子特征，通过包括组学分析、分子检测、分子病理及大数据分析等一系列综合技术手段，帮助临床选择药物响应良好的患者（包括放化疗和靶向药物），指导临床用药的准确性和安全性，提高癌症诊治效果[3]。下一代测序(Next-Generation Sequencing,NGS)技术的发展使多重基因分型和高通量基因组分析变得更为便捷，从而使临床医生能够及时获取治疗相关的分子信息以选择合适的靶向药物。目前，美国食品药品监督管理局(Food and Drug Administration,FDA)已批准如 ExtendedRAS Panel[4-5]、F1CDx[6-8]等多项基于 NGS 的伴随诊断(Companion diagnostics)检测产品,可通过检测多达数百个的特定基因指导临床精准用药。其他国际权威医学或研究机构也积极推动着精准医疗的临床实践应用，如美国国立综合癌症网络(NationalComprehensive CancerNetwork,NCCN)已将精准治疗相关用药策略纳入临床路径指南，My CancerGenome整合了精准医学知识以提供肿瘤突变与药物响应性的关系[9-10],Sanger研究所与麻省总医院癌症中心合作建立了基于癌症基因组的药物敏感性预测模型(Genomics of Drug Sensitivity in Cancer, GDSC)[11]等。

然而，目前我国精准医疗的临床应用尚未成熟，主要原因是组学数据未得到有效解读和利用，难以与相关精准医学知识进行关联匹配形成明确的治疗策略参考。为解决以上问题，亟待开发一个精准医学知识搜索匹配系统作为临床决策支持(clinicaldecision support,CDS)工具[12]，以准确联结患者的组学数据与相应的精准用药指导，为个体化治疗方案的制定提供参考依据。但现有的精准医学知识来源分散且在不断更新中，因此建立一个系统整合前沿精准医学知识的数据库成为构建上述搜索系统的必要基础之一。本文将具体阐述肿瘤精准医学知识数据库(Precision Medicine KnowledgeBase,PMKB)的数据来源、结构设计及原理、构建方法。PMKB主要解决了临床用药指征中包含的组学特征数据类型不同、逻辑关系复杂等实际问题，实现了不同数据源的精准医学知识的结构化存储与快捷搜索调用，同时确保数据的完整性与准确性。

# 1数据库的设计

# 1.1数据来源

目前，本数据库收录了来自四大权威机构的精准医学知识数据资源，分别为FDA含伴随诊断的药物标签(label)、NCCN临床实践指南、My Cancer Genome 精准用药知识以及Sanger研究所等提供的GDSC 精准用药预测资源。

FDA的伴随诊断是一种与靶向药物相关联的体外诊断技术，主要通过检测人体内蛋白、突变基因的表达水平，在不同类型的疾病人群中筛选出最佳用药人群，有针对性地进行个体化医疗[13-14]。如最早的伴随诊断始于1988年FDA 批准的靶向药物赫赛汀(Herceptin)，只有通过免疫组化检测确认HER2蛋白过表达或通过原位杂交法检测出 HER2基因扩增的乳腺癌患者才被允许使用赫赛汀治疗。FDA药物标签全面涵盖了该药的适应证、伴随诊断、用药剂量、注意事项等信息，是肿瘤精准用药指南的权威可靠来源之一。

NCCN临床实践指南是由27个美国知名癌症中心联合制订的癌症临床治疗路径规范[15]，并且指南内容会根据医学进展不断更新以确保其时效性，具有高度临床参考价值。NCCN指南覆盖的癌症种类全面，尤其是对于非小细胞肺癌这类靶向药物应用较多的适应证而言，指南中会给出不同分子分型对应的可选治疗方案，并标注其证据等级以区分推荐优先级[16]。

My CancerGenome 是为医护人员、患者、研究人员提供癌症精准医学知识的一站式工具，主要提供了肿瘤突变与其对应治疗药物的关联信息[9-10]。My Cancer Genome依据癌种分类，分别给出癌症相关的突变及其亚型、可用药物及其响应性、对应证据、可参与临床试验等信息[17]，可作为FDA和NCCN两个临床指南级精准用药指导的详细说明与补充资源。

GDSC 资源是英国 Sanger研究所和美国麻省总医院癌症中心合作建立的基于癌症基因组的药物敏感性数据库，整合收录了大量生物标志物与药物敏感性之间的关系，旨在发掘具有临床意义的治疗标志物用以判断不同患者对治疗的响应性[18]。该项目在超过1000个癌细胞系中对265种药物进行敏感性测试，并建立了高精度的药物响应预测模型[1]。该资源可为组学特征无明确临床指南匹配(FDA、NCCN)的患者提供细胞系水平的精准用药参考证据。

# 1.2数据库结构设计

精准医学知识库的结构设计主要解决以下三个问题：一，PMKB整合了四大来源的数据资源，如何实现不同来源数据的统一结构化存储，并保证数据的完整性和准确性；二，精准医学知识中的用药指征通常较为复杂，包括多个分子组学特征或其他临床指征，如何准确表征不同类型的组学特征并保存其相互间复杂的逻辑关系；三，如何设计数据表间的关系从而实现数据的快捷搜索调用，即在后续搜索匹配过程中可一次性读取一条用药指导相关的所有用药指征和治疗策略信息。

为实现上述数据结构化存储和快捷搜索调用的目的，本数据库设计了21张数据表，其实体关系如图1。其中，临床用药指导表作为数据库的核心表主要关联了患者基于肿瘤分子水平的用药指征和治疗策略，而注释表存储了每条用药指导的相应文本描述以保证其原始性。

临床用药指导表，存储精准用药指导关联信息，包含3个字段：临床用药指导ID（主键）、综合指征ID（外键）和治疗策略ID（表1）。临床用药指导ID同时作为注释表的外键。其他数据表均为此表的扩展表，通过连接查询形成一条完整的临床用药指导。默认情况下所有表均使用自增ID作为主键。

由于临床路径或治疗指南中相应的用药指征往往不是单一的，通常包含多个分子病理特征或其他临床指征，因此我们通过综合指征、综合指征成分、分子指征三张数据表将复杂用药指征拆分为多个分子指征并表征其逻辑关系。

综合指征表包含逻辑运算符，该字段值限定范围为and、or、not、is。

综合指征成分表是综合指征表的扩展表，包含综合指征ID（外键）、成分类型、组合顺序、分子指征ID（外键）或综合指征ID（外键）。其中，“成分类型”字段值限定为综合(complex)或分子(atomic)指征。若成分类型为综合指征，则通过综合指征ID外接到综合指征表；若成分类型为分子指征，则通过分子指征ID外接到分子指征表。

分子指征表包含特征类型，存储肿瘤分子变异特征的不同类型。特征类型包括高甲基化、拷贝数变异、基因融合、基因表达异常、蛋白表达异常、信号通路激活状态、基因突变、外显子突变、单核苷酸多态性、其他临床指征（如肿瘤分期、治疗史）等14种类型。由于不同类型变异所含信息存在较大差异，因此我们创建了14张组学特征(feature)表以存储不同特征类型的具体变异信息。每张表包含的字段根据其特征类型专门设计，如外显子突变表包含字段：分子指征表ID（外键）、基因名gene symbol、外显子号、突变类型（包括突变mutation、插入insertion、缺失deletion、跳跃skipping等），而信号通路激活状态表包含字段：分子指征表ID（外键）、通路、状态类型（包括上调、下调）。

![](images/40b82445b7334b58f6848cdf843ee1e032d0559b1436c7a40096ccd2233053c9.jpg)  
图1精准医学知识数据库实体关系图  
Fig1. Entity relationship diagram of PMKB

表1临床用药指导表 Table1 Clinical directive table   

<html><body><table><tr><td>临床用药指导ID Clinical directive ID</td><td>综合指征ID Indication Complex ID</td><td>治疗策略ID Therapeutic Strategy ID</td></tr><tr><td>CD1</td><td>CI1</td><td>TS1</td></tr><tr><td>CD2</td><td>CI2</td><td>TS2</td></tr></table></body></html>

用药指征的复杂逻辑拆分方法具体举例如下：某条临床路径为“当患者肿瘤组织同时发生A基因突变和B基因突变而无C基因突变时，推荐使用xx治疗策略”，则此用药指征可结构化为逻辑组合(Aand B)or not(C)(图2)。所有逻辑运算符都被记录在综合指征表中（表2），逻辑运算符关联的对象（即综合指征或分子指征）被记录在综合指征成分表中（表3）。逻辑运算符or的操作对象是综合指征CI2和CI3，and的操作对象是分子指征AI1和AI2，not的操作对象是分子指征AI3，以上逻辑拆分的顺序记录在综合指征成分表中的“组合顺序”字段。在分子指征表中记录特征类型（表4），分子指征表的ID作为外键与不同组学特征表（如基因突变表）相关联。具体变异的特征信息（如A基因突变）记录在组学特征表中。

![](images/87d1f0fecfc5c59b0889dc6e304284bdd88223dadb92c9d9b36598c353fe78cd.jpg)  
图2用药指征逻辑拆分示意图  
Fig 2.Logic decomposition illustration of complex indication

表2综合指征表Table 2 Indication complex table  
表3综合指征成分表  

<html><body><table><tr><td>综合指征ID Indication Complex ID</td><td>逻辑运算符 Operator</td></tr><tr><td>CI1</td><td>or</td></tr><tr><td>CI2</td><td> and</td></tr><tr><td>CI3</td><td>not</td></tr></table></body></html>

Table 3 Complex indication components table   

<html><body><table><tr><td>综合指征ID Indication Complex ID</td><td>成分类型 Indication Type</td><td>组合顺序 Component Order</td><td>综合指征ID Indication Complex ID</td><td>分子指征ID Indication Atomic ID</td></tr><tr><td>CI1</td><td>complex</td><td>1</td><td>C12</td><td></td></tr><tr><td>CI1</td><td>complex</td><td>2</td><td>CI3</td><td></td></tr><tr><td>CI2</td><td>atomic</td><td>1</td><td></td><td>AI1</td></tr></table></body></html>

<html><body><table><tr><td>C12</td><td>atomic</td><td>2</td></tr><tr><td>C13</td><td>atomic 1</td><td>A12 AI3</td></tr></table></body></html>

Table 4Indication atomic table   

<html><body><table><tr><td>分子指征ID Indication Atomic ID</td><td>特征类型 Indication Atomic Type</td></tr><tr><td>AI1</td><td>基因突变</td></tr><tr><td>A12</td><td>基因突变</td></tr><tr><td>AI3</td><td>基因突变</td></tr></table></body></html>

治疗策略表包含治疗策略ID、治疗策略成分ID两个字段（表5），后者作为外键可外接到其扩展表治疗策略成分表。治疗策略成分表存储具体药物或治疗方法信息，包括治疗策略类型和治疗策略内容（表6）。其中，治疗策略类型包括化疗、靶向治疗、免疫治疗等多种常见疗法。

治疗策略通常包含不止一种药物，故其所涉及到的药物清单将被展示，目前没有进行逻辑拆分。事实上，如果治疗策略中包含多种药物，可能意味着是药物A和B联合用药(即 DrugAand Drug B)，也可能是可以使用药物A或 B(即 Drug Aor Drug B)。为了最大化数据准确性，存在逻辑关系的原始治疗策略信息被储存在注释中以备查询。

表4分子指征表  
表6治疗策略成分表  

<html><body><table><tr><td>治疗策略ID Therapeutic Strategy ID</td><td>治疗策略成分ID Therapeutic Strategy Components ID</td></tr><tr><td>TS1</td><td>TSC1</td></tr><tr><td>TS1</td><td>TSC2</td></tr></table></body></html>

表5治疗策略表Table 5 Therapeutic strategy table  
Table 6 Therapeutic strategy Components table   

<html><body><table><tr><td>治疗策略成分ID Therapeutic Strategy Components ID</td><td>治疗策略成分类型 Components Type</td><td>治疗策略内容 Therapeutic Strategy Components</td></tr><tr><td>TSC1</td><td>靶向治疗</td><td>Drug A</td></tr><tr><td>TSC2</td><td>化疗</td><td>Drug B</td></tr></table></body></html>

# 2数据库的构建方法

本数据库采用MySQL 数据库管理系统构建。相比于大中型数据库 SQL server 和Oracle，MySQL具有功能丰富、使用简便、运行速度快、安全可靠等优势。

由于各来源的精准医学知识大多使用非结构化的自然语言描述，难以准确有效地进行自动化知识抽提与转换，因此PMKB采用手动方式进行数据采集以保证数据的真实有效性。人工收集的FDA伴随诊断、NCCN指南、MyCancer Genome 资源、GDSC

精准用药预测资源，通过数据库开发工具Navicat手动加入PMKB，同时建立各数据表之间的外键联系，从而完成精准医学知识数据的结构化、标准化存储。

# 3结果与讨论

精准医学知识库整合了FDA、NCCN、MyCancerGenome 和GDSC 四大权威精准用药资源，并以标准化、可计算的结构存储，以实现肿瘤分子病理特征和治疗策略信息的关联。目前，PMKB共收录了1940条临床用药指导（表7）、21张数据表（表8），涵盖了临床信息、高甲基化、拷贝数变异、基因融合、基因表达异常、蛋白表达异常、信号通路激活状态、基因突变、外显子突变、单核苷酸多态性、染色体变异等14种不同类型的分子组学特征。

由于PMKB的结构设计具有广泛的通用性与可扩展性，可使不同来源的医学知识数据以结构化的方式统一、完整、准确地存储于数据库中。其中，综合指征表、综合指征成分表、分子指征表的设计可有效表征用药指征中的复杂逻辑关系，便于进一步实现患者的真实肿瘤分子组学特征与PMKB精准用药知识之间的快速匹配；各组学特征表的字段设计可使不同变异类型的数据在结构化存储（抽提、编码）过程中最大化保留其原始性；各数据表之间的外键关联设计可实现数据的快捷搜索调用，即在后续搜索匹配过程中可一次性读取一条用药指导相关的所有用药指征和治疗策略信息。

Table7ThenumberofclinicaldirectivescollectedinPMKB   

<html><body><table><tr><td>数据来源</td><td>临床用药指导 记录条数</td></tr><tr><td>FDA</td><td>44</td></tr><tr><td>NCCN</td><td>70</td></tr><tr><td>My Cancer Genome</td><td>58</td></tr><tr><td>GDSC</td><td>1768</td></tr><tr><td>总计</td><td>1940</td></tr></table></body></html>

表7PMKB临床用药指导条目统计  
表8精准医学知识数据库条目统计  
Table 8 The number of records collected in PMKB   

<html><body><table><tr><td>数据表名称</td><td>英文表名</td><td>记录条数</td></tr><tr><td>临床用药指导表</td><td>clinical_directive</td><td>1940</td></tr><tr><td>注释表</td><td>annotation</td><td>65601</td></tr><tr><td>治疗策略表</td><td>therapeutic_strategy</td><td>499</td></tr><tr><td>治疗策略成分表</td><td>therapeutic_strategy_components</td><td>351</td></tr><tr><td>综合指征表</td><td>indication_complex</td><td>2835</td></tr><tr><td>综合指征成分表</td><td>indication_complex_components</td><td>6006</td></tr><tr><td>分子指征表</td><td>indication_atomic</td><td>2301</td></tr><tr><td>高甲基化表</td><td>feature_gene_hypermethylation</td><td>501</td></tr><tr><td>拷贝数变异表</td><td>feature_gene_copy_number_variation</td><td>359</td></tr><tr><td>基因融合表</td><td>feature_gene_fusion</td><td>12</td></tr></table></body></html>

<html><body><table><tr><td>基因融合状态未知表</td><td>feature_gene_fusion_unknown</td><td>1</td></tr><tr><td>基因表达异常表</td><td>feature_gene_expression</td><td>1</td></tr><tr><td>信号通路激活状态表</td><td>feature_pathway_activity</td><td>22</td></tr><tr><td>蛋白表达异常表</td><td>feature_protein_expression</td><td>24</td></tr><tr><td>基因突变表</td><td>feature_gene_mutations</td><td>995</td></tr><tr><td>基因未突变表</td><td>feature_gene_no_mutations</td><td>5</td></tr><tr><td>基因突变状态未知表</td><td>feature_gene_status_unknown</td><td>1</td></tr><tr><td>外显子突变表</td><td>feature_gene_exon_mutation</td><td>14</td></tr><tr><td>单核苷酸多态性表</td><td>feature_gene_coding_snp</td><td>19</td></tr><tr><td>染色体变异表</td><td>feature_chromosome_mutation</td><td>1</td></tr><tr><td>其他临床指征表</td><td>feature_other_clinical_indication</td><td>94</td></tr></table></body></html>

我们设计构建的精准医学知识库从海量数据资源中整合、提炼了有效的精准用药知识，可通过匹配肿瘤患者的分子组学数据，为其提供个体化的治疗方案参考。为构建一个完整的临床决策支持系统，我们已建立了病例组学数据库用以存储患者真实的组学数据，并开发了PMKB相应的匹配算法以关联患者组学数据与精准用药指导。病例组学数据库、精准医学知识库、匹配算法三者共同构成精准医学知识搜索系统，旨在最终实现临床诊治过程中的精准用药推荐（图3）。利用此搜索系统，我们已完成20例胃癌患者的分子病理分析与精准用药推荐，并将在实际应用中持续优化参数、添加最新的精准医学知识数据。目前PMKB采用的手动数据采集方式虽然可以保证数据的准确性，但效率较低，因此我们将在后续工作中利用自然语言处理(natural languageprocessing,NLP)[19]、数据挖掘(data mining)[20]等技术建立自动化的数据采集方法，以实现高效的精准医学知识识别、抽提、编码存储。

![](images/65578159caf04ee62a841eec92491c5da4470ba0c1ba0ea8cbdea83a9424ab64.jpg)  
精准医学知识搜索系统  
图3精准医学知识搜索系统示意图  
Fig 3. Illustration of precision medication searching system

# 参考文献

[1] Stratton MR, Campbell PJ, Futreal PA. The cancer genome. Nature, 2009, 458:719-724.   
[2]付文华,钱海利,詹启敏.中国精准医学发展的需求和任务.中国生化药物杂志,2016,36(4):1-4. [3] Garraway LA, Verweij J, Ballman KV. Precision oncology: an overview. Journal of Clinical Oncology, 2013,31(15):1803-1805.   
[4] Sorich MJ, Wiese MD,Rowland A,et al. Extended RAS mutations and anti-EGFR monoclonal antibody survival benefit in metastatic colorectal cancer: a meta-analysis of randomized, controlled trials. Annals of Oncology,2015,26(1):13-21.   
[5] Allgra CJ, Rumble RB, Hamilton SR, et al. Extended RAS gene mutation testing in metastatic colorectal carcinoma to predict response to anti-Epidermal Growth Factor Receptor monoclonal antibody therapy: American Society of Clinical Oncology Provisional Clinical Opinion Update 2015.Journal of Clinical Oncology,2016,34(2):179-185.   
[6] Ali SM, Hensing T,Schrock AB,et al. Comprehensive genomic profiling identifies a subset ofcrizotinibresponsive ALK-rearranged non-smallcell lung cancer not detected by fluorescence in situ hybridization. Oncologist, 2016,21(6):762-770.   
[7]RankinA,Klempner SJ,Erlich R,etal. Broad Detection of Alterations Predicted to Confer Lack of Benefit From EGFR Antibodies or Sensitivity to Targeted Therapy in Advanced Colorectal Cancer. Oncologist, 2016, 21(11):1306-1314.   
[8] Boussemart et al. Hybrid-capture based genomic profiling identifies BRAF V6O0 and non-V600 alterations in melanoma samples negative by prior testing. Annals of Oncology,2017,28(suppl_5):v428-v448.   
[9] Kusnoor SV, Koonce TY,Levy MA, et al. My Cancer Genome: Evaluating an Educational Model to Introduce Patients and Caregivers to Precision Medicine Information. AMIA Joint Summits on Translational Science, 2016:112.   
[10] Levy M,Lovly C, Horn L, Naser R,Pao W.My Cancer Genome: Web-based clinical decision support for genome-directed lung cancer treatment. Journal of Clinical Oncology, 2011, 29:15_suppl, 7576.   
[11] IorioF,Knijnenburg T,Vis D,et al.ALandscape of Pharmacogenomic Interactions in Cancer. Cell2016, 166(3):740.   
[12] Castaneda C, Nalley K, Mannion C,et al. Clinical decision support systems for improving diagnostic accuracy and achieving precision medicine. Journal of Clinical Bioinformatics,2015, 5(1):4.   
[13] Fridlyand J,Simon RM,Walrath JC,et al. Considerations for the successful co-development of targeted cancer therapies and companion diagnostics. Nature Reviews Drug Discovery,2013,12(10):743.   
[14] Mansfield EA. FDA perspective on companion diagnostics: an evolving paradigm. Clinical Cancer Research,2014,20(6):1453-1457.   
[15] National Comprehensive Cancer Network. About NCCN. 2017. htps://www.nccn.org/about/default.aspx [16] National Comprehensive Cancer Network. NCCN clinical practice guidelines in oncology: non-small cell lung. 2017. htps://www.nccn.org/professionals/physician_gls/pdf/nscl.pdf   
[17] My Cancer Genome. 2017. https://www.mycancergenome.org/   
[18] Yang W, Soares J, Greninger P,et al. Genomics of Drug Sensitivity in Cancer (GDSC): a resource for therapeutic biomarker discovery in cancer cells. Nucleic Acids Research,2013,41:D955-D961.   
[19] Al-Haddad MA,Friedlin J,Kesterson J,et al. Natural language procesing for the developmentofaclinica registry: a validation study in intraductal papillary mucinous neoplasms. HPB,2010,12(10):688-695. [20] Koh HC,Tan G. Data mining applications in healthcare. Journal of Healthcare Information Management, 2005,19(2):64-72.