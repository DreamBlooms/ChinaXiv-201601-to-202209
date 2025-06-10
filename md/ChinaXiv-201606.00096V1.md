# 保存元数据的发展趋势研究

# 刘建华，张智雄 (中国科学院文献情报中心）

摘要：数字资源长期保存中，保存元数据是支持数字资源长期可生存能力、可呈现能力、可理解能力、真实性、一致性的重要信息。为了全面了解保存元数据的最新发展，为国内从事长期保存的机构制定长期保存元数据的实施策略、建设方案提供参考，笔者综合分析了长期保存领域核心理论标准、重要会议和重要项目的研究进展，总结归纳了保存元数据在权利元数据，重要属性元数据，特殊类型数字资源及学科化特色的保存元数据、保存元数据的语义化、起源元数据等方面的重要发展趋势。

关键词：保存元数据PREMIS权利元数据重要属性起源元数据

# Study on the Trend of Preservation Metadata

Liu Jianhua, Zhang Zhixiong（National Science Library， Chinese Academy of Sciences ）

ABSTRACT：Preservation Metadata is a kind of important information to support the viability,renderability, understandability，authenticityand identityofdigitalresources.Tooverviewthestate-of-art of preservation metadata and provide a reference for domestic agencies that engaged in digital preservation,the authors analysis the core standards,proceedings of important conference and outcomes of important projects about preservation metadta.They summary the important development in right metadata, significant properties, preservation metadata about special digital resources, semantic of preservation metadata and Provenance Metadata.

KEY WORDS:Preservation Metadata,PREMIS,Right Metadata,Significant Properties,Provenance Metadata

# 1保存元数据的概述

保存元数据一直是数字资源长期保存领域长期关注的重点与热点问题，作为支持数字资源长期保存过程的信息[1，它是支持数字资源在长期保存过程中保有长期可生存能力、长期可呈现能力以及长期可理解能力等的必要信息。因为保存元数据的存在，数字对象的自我记录成为可能，即便是所有权、保管、技术、法律限制、用户全体发生了变化，也可以确保数字对象的长期保存和访问。

经过数十年的研究，保存元数据目前已经经历了概念发展、理论发展、实践论证三个阶段，国外已经形成了不少成型的保存元数据体系、保存元数据使用方法、保存元数据相应的工具等成果，国内虽然以应用为主，但也陆续形成了一些标准规范应用指南[2]。

随着保存环境的不断变化，保存资源类型的不断丰富，保存要求的不断调整，保存元数据也不断发生着变化，本文希望从探索保存元数据的发展入手，结合当前保存元数据理论、实践研究的进展，分析保存元数据的发展趋势，以便为长期保存元数据的实施策略、建设方案提供参考。

# 2保存元数据的发展

长期保存领域对保存元数据的研究兴起于20世纪90年代。随着长期保存活动的不断开展，研究人员意识到要实现数字资源在长期保存过程中保有长期的可生存能力、可呈现能力、可理解能力、真实性、一致性等特征，需要记录很多有关资源本身、资源的硬件和软件环境、变动历史等相关信息。基于此，他们开始探索针对保存的元数据集合。

1998年，MichaelDay[3]首次在其报告中采用了“Preservation Metadata”(保存元数据)的概念。同年，Research Library Group(研究图书馆组织，简称RLG)针对数字图像保存探索了相应的长期保存元数据集合[4]。随后，Consultative Committee for Space Data Systems(美国空间数据系统咨询委员会，CCSDS)公布了Reference Model for an Open Archival InformationSystem(开放存档信息系统参考模型，OAIS)，为各类长期保存活动提供了参考模型和基本概念框架。OAIS制定的信息模型，提出一个数字保存系统中的信息对象由数据对象本身和它的呈现信息组成，数据对象由一个或多个比特序列组成，而呈现信息将这些比特序列转换成为更有意义的信息。呈现信息又可以分为结构呈现信息和语义呈现信息两种，其中前者指出数据对象的组成结构，而后者表现数据对象的语义含义。某一呈现信息可以引用已经定义好的呈现信息。通常情况下，为了让被保存的某一信息对象能够被“独立理解”，这一信息对象需要一系列具有引用关系的呈现信息组成呈现网络来进行表述。根据信息对象内容和功能的不同，OAIS又将数字保存系统中信息对象分为内容信息对象、保存描述信息对象、打包信息对象和描述信息对象4种类型[5]，其中明确了描述信息对象包括指引信息、环境信息、来源信息、稳固性信息、访问权限信息(2009年新版的OAIS中才增加了访问权限信息)。英国CURL Exemplars in Digital ARchiveS(CEDARS)[]项目在充分吸收OAIS参考模型和其它领域的元数据研究成果基础上，考虑了多种数字格式，开发出其对应的保存元数据框架。此外，还有澳大利亚国家图书馆[7]和欧洲Networked European Deposit Library[8](NetLib)也在这一阶段提出了针对保存需求的元数据框架。OAIS、CEDARS、NetLib等保存元数据的出版标志着保存元数据从概念到理论标准的跨越。

2000年，Online Computer Library Center(联机计算机图书馆中心，简称OCLC)和RLG共同发起了一个对数字保存元数据的基础架构进行研究的行动计划[I，他们继续沿用了Preservation Metadata的说法，开发了一个广泛适用的、综合性元数据框架，并在此基础上发布了可应用于实践操作的数据字典。2005年PREMIS1.0[9]正式发布，并在随后的10年中先后发布了PREMIS2.0、PREMIS2.1、PREMIS2.2[10]和PREMIS2.3，目前PREMIS3.0正在筹备中,尚未正式发布。PREMIS的正式发布使保存元数据实现了从理论标准到实践操作的升级。自PREMIS之后，针对保存元数据的研究越来越贴近实际应用，在具体的应用策略、相应的元数据获取工具等方面都取得了不少成果。

除国外的研究成果外，国内比较有代表性的主要是国家图书馆、清华大学和军队院校在保存元数据框架方面做出了一些探索。清华大学的程变爱等人在“国家数字图书馆工程长期保存规范”项目支持下，发布了《国家数字图书馆长期保存元数据标准规范应用指南》[2]，指南基于规范和PREMIS数据字典，列出了一些必备语义单元，需要保存系统开发的标识符命名域、受控词表等内容，并介绍了一些可用于自动提取元数据的工具及几个实用情景，为具体的实施提供了很好的指导建议。

# 3保存元数据的发展趋势及实施建议

伴随着数字保存理论研究和实践活动的不断深入，考虑到实际使用的便利性、合作保存及分布式保存环境下明晰的权力信息需求、保存内容多元化的需求、多重保存策略的需求、动态保存的需要等因素，不少从事长期保存研究的机构、项目也针对保存元数据从理论、实践等方面开拓了新的发展。综合分析长期保存领域核心标准、重要会议和重要项目的研究进展，笔者认为，保存元数据在权利元数据，重要属性元数据，特殊类型数字资源及学科化特色的保存元数据、保存元数据的语义化、起源元数据等方面有比较明显的发展，并结合分析的内容给出了一些实施的建议。下文将从上述几个方面逐一进行阐述。

# 3.1权利信息日趋受到重视

在分布式保存、合作保存逐步成为长期保存主流的今天，版权专有权可能会限制甚至完全阻碍通过复制和传播来保存作品，同时，在保存后的一些操作中也可能需要越来越多的权利信息。因此，权利元数据成为保存元数据体系中一大重点。

2009年出版的OAIS在其原有的Preservation Description Information（保存描述信息,PDI）下明确区分出了一类访问权限信息，该信息主要用于确定内容信息相关的访问约束，包括法律框架、许可条款及访问控制等。该信息中包含了遵从提交协议（Submission Agreement）前提下的访问和分发条件，同时还包含了应用权利强制措施的说明。这标志着权利类型元数据作为保存元数据的一个重要组成部分，有了明确的理论基础。2013年，DigitalPreservationCoalition(数字保存联盟，DPC)中心出版的《Preservation Metadata(2nd edition)》[11]明确将保存元数据划分为起源元数据、权利元数据、技术与环境说明元数据三类。这些都从概念和理论上强调了权利元数据对保存元数据的重要。

从保存元数据实践上看，PREMIS[9-10]在其最近新出版的三个版本元数据字典中，有关权利元数据的调整和变动占据了绝对主要的地位，包括扩展权利元数据语义单元，将原先单一的“许可声明”扩展到三种明确形式的知识产权：版权、许可、法规，还为无法归类到这三种明确形式的知识产权提供了一个可扩展的语义单元。同时，新版的PREMIS中为扩展后的权利声明容器都提供了通用的元数据和各自专有的元数据，如标示符、特性、范畴、授予仓储的权利特征等，极大地丰富了权利元数据的定义，此外，PREMIS还进一步丰富化定义了权利元数据与其它实体之间的关系等。牛津大学和曼彻斯特大学合作完成的PersonalArchives Accessible in Digital Media (Paradigm)[12]项目将权利信息作为长期保存元数据的一个重要组成部分，重点关注其中的知识产权元数据，他们认为知识产权元数据对保存和获取都有重要的意义，在重点考察了各类权利元数据的基础上，Paradigm确定了在个人档案存储中的权力保存方案。由ExLibris和新西兰国家图书馆共同研发的长期保存方案Rosetta[13]中,权利管理作为核心保存元数据之一，一方面用于保存权利元数据，另一方面也用于控制对保存对象的访问。欧盟第七框架资助的视听资料长期保存项目PrestoPRIME[14]在充分调研了现有的MPEG-21、Open digital Rights language、PREMIS等权利表达语言与格式，以及MediaStreaming MAF、MPEG Extensible Middleware等权利管理系统的基础上，基于Media ValueChain Ontology(ISO/IEC 21000-19)设计了详细的权利管理元数据本体模型，支撑视听资源的长期保存[15]。

总体上看，不论是独立的权利元数据方案还是嵌入保存元数据体系中的权利元数据，目前针对权利元数据的定义已经趋于成熟，国内保存机构在实施保存活动时至少要记录下保存系统对其所保存的数字对象可采取的被授权的保存行为，至于更多的面向资源服务的权利描述信息，则需要参照实际的需要遴选合适的语义单元进行记录。

# 3.2数字资源重要属性元数据越来越具体清晰

在保存元数据中，重要属性(Significant Properties)的概念是数字保存元数据界争论的焦点内容之一，它对保存仓储的保存策略选择有着直接的影响。研究者们普遍认为重要属性并不是数字对象固有的，而是随着时间的流逝，由保存活动发生的环境所决定，必须维护的关于数字对象的关键特征（如外观、观感、知识内容等）。但是之前，“重要属性”被给予了各式各样的定义且以很多不同的方式被使用，对于重要属性怎样归类和使用缺乏一致的认同。2009年， Cultural, Artistic and Scientific knowledge for Preservation,Access and Retrieval(CASPAR)项目组的David Giaretta[16]在iPres 2009会议上，在讨论OAIS的新版本中提出的定义的基础上，对重要属性、可靠性、出处、表现信息和OAIS进行了探讨，明确了重要属性与可靠性、出处、表现信息的关系，并给出了相应的应用示例，为重要属性的使用提供了有力的理论依据。2008年正式出版的PREMIS2.0数据字典为重要属性创建了结构化语义单元集合，通过这些语义单元有助于保存对象重要属性的管理，同时还可确保这些属性不会受到保存活动的损害而长久存在，这为重要属性的实施提供了可操作的元数据支持。为了深入调查重要属性的完整概念，确定对各种类型保存对象重要的属性，并评价每一个属性对对象未来呈现的重要性，Joint Information Systems Commitee(英国联合信息系统委员会，JISC)专门资助了Investigating the Significant Properties of Electronic Content Over Time(InSPECT)项目[17]。根据研究目标，InSPECT项目收集整理了有关重要属性的各种版本定义、观点，分析并发展出了一个清晰一致的概念[18]，在此基础上还形成了一个完整的重要属性数据字典[19]，清晰地定义了重要属性相关的语义单元。该项目的研究成果为JISC资助的相关长期保存项目提供了有关重要属性的重要参考。此外，还有Simone Sacchi[20]等人针对科学数据集长期保存中的重要属性，提出了一个逻辑模型，该模型提供了为适当的实体确定和分配重要属性的必要抽象。

尽管目前为止，还尚未有一个长期保存项目开发出针对该元数据的词表，但是已经有一些机构在实践中开始运用此元数据来记录保存信息。如英国的SHERPA人文数据服务数字保存项目针对电子预印本这一类保存资源构造重要属性元数据，以记录电子预印本资源中的一些特殊属性，如语义内容（文本或图片）、文档布局等，以便于日后对资源的维护[2]。我国相关机构在实施长期保存过程中，也需要逐步重视该类元数据，参照OAIS、PREMIS、InSPECT等项目，从资源利用的角度出发，扩展出尽可能完整描述对象属性的语义单元，在存储过程中记录相应的重要属性元数据。

# 3.3特殊类型数字资源、学科化的保存元数据受到越来越多的关注

随着长期保存的不断发展，原先主要针对数字文本资源的长期保存工作逐步扩展到了对更多类型资源的保存上，如音频/文件、互动多媒体资源、科学数据（如地球科学的卫星遥感数据等）、网络内容（网页、blog等）、互动内容、应用程序和进程等。同时，原先主要集中在图书馆、档案馆、博物馆等文化机构对传统文化资源开展的长期保存工作也逐步扩展到了各个学科领域。在这种情况下，单独一种保存元数据体系无法满足多种类型的数字资源的保存需求。因此，不少研究者结合所需要保存的数字资源本身的特点和学科特色需求，利用已有的各类元数据和领域知识结构，为有学科化特色的或特殊类型的数字资源设计了相应的保存元数据模型。

Ruth Duerr等人[21]在PREMIS、ISO 1115、Content Standard for Digital Geospatial Metadata(CSDGM)等元数据体系基础上，设计了针对地球科学领域科学数据的长期保存元数据模型。Kia Ng等人[2-23]参考并重用OAIS、CIDOC Conceptual Reference Model (CIDOC-CRM)和FRBR model，提出了可有效描述互动多媒体资源的CASPAR本体元数据框架。GunterR.Fuhr等人[24]针对医疗机构与临床研究数据，利用领域已有的一些正式本体来定义和描述数字对象的保存元数据。由欧盟第七框架资助项目PrestoPRIME项目[14]主要关注视听资料的长期保存，并需要解决原生数字化视频资料的长期保存问题，为了实现这一目标，该项目在OAIS、PREMIS和Rosetta保存元数据基础上，扩展了保存元数据的范围，将起源元数据、技术元数据、权利元数据作为重要组成部分纳入了保存元数据中。欧盟的BlogForever项目[25]集中针对博客这一类的社会网络数据，设计了包括博客内容、博客种子、网络与关联数据、分类内容、内容语义信息、垃圾检测信息、采集信息、外部插件、排序等内容在内的保存元数据模型，为博客资源的长期保存、管理和使用提供了很好的参考意见。

随着国内保存活动的逐步开展，当前以数字文本资源为主的长期保存工作必然会逐步向其它类型扩展，同时，针对特定学科的学科化保存也必然会逐渐增多。针对此，各机构有条件的可以在现有一些较为成熟的元数据体系基础上，重新制定对应的完整的长期保存元数据模型，但更多机构可以充分利用现有元数据体系中提供的扩展机制，如PREMIS提供的扩展语义单元机制，在相应的语义组建容器中嵌入外部定义好的特殊格式的元数据，如针对数字静止图像的NISO Z39.87MIX scheama，这样即可快速地实现对于不同类型、不同学科的元数据的扩展。

# 3.4保存元数据的语义日趋丰富

随着语义技术的发展，保存元数据也越来越重视语义技术的融合与应用，与传统简单的元数据描述相比，语义技术的引入可促进保存元数据对数字资源内容的深层揭示，提升内容挖掘的深度，同时，语义技术也进一步提高了保存元数据在细粒度和交互操作方面的性能。

保存元数据语义的丰富是从其自身和实施操作过程两个方面实现的。在自身的发展中，保存元数据主要是通过应用OWL语言、采用RDF格式存储和管理元数据，如PREMIS于2013年6月发布的OWL语言的本体，提供了可兼容关联数据、支持PREMIS有序化的数据词典[26]。在具体的实施操作中，语义化的丰富主要体现在不同环节对语义化技术的应用。具体来讲，包括利用RDF三元组描述保存元数据记录、关联数据用于数字资源的组织等。欧盟资助的Memories[27]在保存元数据之间建立RDF三元组，描述类、从属类、属性、术语与关系，构成基于本体的保存结构，实现音频资源的长期保存。法国SPAR项目[28]利用METS标准，在METS与RDF三元组之间建立联系，例如通过<infor:bnf/spar/provenance# hasEvent>对应来源本体中的“hasEvent”属性。除了应用RDF三元组外，SPAR项目还尝试通过关联数据技术，将整个数据仓储整合成一个关联数据。SCIence Data Infrastructure for Preservation-EarthScience(欧盟FP7框架计划资助的地球数据保存项目，SCIDIP-ES)[29]对地球数据保存元数据的相关技术问题进行调查和分析，认为“GeoNames”本体、TheGeneralMultilingual Environmental Thesaurus(通用多语种环境叙词，GEMET）等本体资源的应用，完善了保存元数据对地理数据的描述和保存。Kia $\mathrm { N g }$ 等人[22-23]参考并重用了现有的相关标准模型，如CIDOC-CRM和FRBRmodel，提出了CASPAR的本体元数据框架，其中描述了互动多媒体资源各种概念之间存在的复杂关系，实现了互动多媒体资源的本体驱动保存方法。通过这一框架，他们更全面、有效地描述了所需要保存的元数据之间的关系和依赖性。基于这一研究，他们认为本体与保存元数据在长期保存应用中的结合对数字仓储系统的互操作、数字对象之间关系的自动推理等有很大用处。GunterR.Fuhr等人[24针对医疗机构与临床研究数据，在现有的一些领域本体基础上提出了数字对象的保存元数据体系，该元数据体系也以本体形式表达，本体中主要描述了数据对象的基本特征（如类型、格式、尺寸、保存描述信息等）和一些领域特有的信息，借助这一领域本体可以实现对象的索引和元数据的管理，从而解决由于格式过时、医学术语变动等为医学领域用户带来的使用问题。欧盟的SustainingHeritage Access(SHAMAN)语境模型提供了一个用本体表示数字对象属性和他们之间关联的独立基础设施[30]，推动了长期保存中语义技术的应用。

从上述已有的研究可以看到，目前在具体实施操作中语义化的实现主要依靠的是RDF三元组、关联数据和本体框架三种技术，其中又以本体为主。因此，我国的一些存储机构在开展相关存储工作时，可以充分借鉴和应用现有的一些通用或学科本体框架，采用本体的方式来描述、存储和管理元数据。

# 3.5起源元数据日渐丰富和完善

起源元数据是保存元数据中的一类重要元数据，它负责记录数字对象创建、保存过程中系列动作的信息及相应的结果，同时还包括一些验证的信息，此类元数据对确保保存对象的真实性有重要的意义[31]。随着数字保存实践活动和语义网的不断发展，起源元数据在内容、表达模型方面不断丰富和完善。在内容方面，有些保存仓储认为数字起源应该包括自对象创建之后的所有变化的历史记录，包括迁移、标准化和其他的一些操作。在PREMIS中，对象是不可变更的，所有的修改操作会产生的一个新的对象记录，该新对象与其来源对象之间建立关系。对所有的对象而言，数字起源相关的元数据均包括对象的创建者、所有者、权力拥有者、影响对象的事件或过程操作以及操作的时间等。这些元数据元素分别以PREMIS事件实体与代理者实体下相应的语义单元表示，在对象实体中也提供了包括对象特征或重要属性的扩展元素（包括来源某个领域的特定起源此表）。National LibraryofNew Zealand(新西兰国家图书馆，NLNZ)定义的起源元数据包括了对过程的描述，这些元素据类似于PREMIS中的事件，但NLNZ中涉及更长时间范围内的多个步骤，同时NLNZ中还提供了记录过程实施的原因的元数据。ExLibris的Rosetta明确将起源元数据作为其保存元数据方案中的核心元素之一，该元数据用于记录数字对象的来源、所有发生在该数字对象上的变动，即系列事件、行为以及相关行为者的记录。METS在其管理元数据部分也提供了名为digiProvMD的特定元素，用于描述任何与数字对象相关的任何保存活动。在起源元数据的表达模型上，2007年发布的Open Provenance Model(开放起源模型，OPM)[32]最具典型，OPM旨在定义一套不同系统间可交互的起源信息模型，允许开发人员创建并共享操作该模型的工具。OPM从技术的角度定义了起源，支持对多种事物的起源描述，允许多级描述同时存在。该模型中定义了Artifact、Process和Agent三个核心概念以及六种关系和角色，在该模型中，时间也可被标注用于参考。其它还有如Provenir Ontology[33、Provenance Vocabulary[34]等，也从不同的角度提出了起源元数据的表示模型。

基于这种发展趋势，在实施数字资源保存过程中，尤其是针对科学数据的保存中，保存实施机构要充分考虑对起源信息的记录。在目前尚无统一通用的模型前提下，实施中可以从OPM、Provenir、Provenance等现有表达模型中选择一个作为通用模型的基础，然后在此基础上，根据本机构保存策略或针对保存内容的学科领域，构造个性化的起源模型并定义适合自己的起源信息描述细粒度，便于记录相应的起源信息。

# 4结语

作为支持数字资源长期保存过程的重要信息，保存元数据是支持数字资源在长期保存过程中保有长期可生存能力、长期可呈现能力以及长期可理解能力等的必要信息。随着保存环境的不断变化，保存资源类型的不断丰富，保存要求的不断调整，保存元数据也不断发生着变化，本文结合当前保存元数据理论、实践研究的进展，重点分析保存元数据的发展趋势，一方面可以全面了解保存元数据的最新发展，另一方面也可为国内相关机构制定长期保存元数据的实施策略、建设方案提供参考，支持国内机构结合各自的保存特色设计适合自己的保存元数据集合。

# 参考文献

[1]Preservation Metadata for Digital Objects: A Review of the State of the Art, A White Paper by the OCLC/RLG Working Group on Preservation Metadata[OL].[2014-10-13].   
http://www.oclc.org/research/projects/pmwg/presmeta_wp.pdf   
[2]程变爱，郑小惠，童庆钧，等.国家数字图书馆长期保存元数据标准规范应用指南[K]. [2014-10-13].htp://www.nlc.gov.cn/newstgc/gjsztsggc/bzgf/201101/W020120412526555524627. pdf   
[3]Michael Day.Issues and Approaches to Preservation Metadata[C].In: Guidelines for digital maging: papers given at tne joint Nauonal Preservauon Uiice and Kesearcn Lioraries Group preservation conference in Warwick, 1998. National Preservation Office, London, pp. 73-84. [4]RLG Working Group on Preservation Issues of Metadata[OL].[2014-12-13].   
http://www.rlg.org/preserv/presmeta.html   
[5]Consultative Committee for Space Data Systems: Reference Model for an Open Archival Information System (OAIS) [OL]. CCSDS 650.0-B-1 BLUE BOOK.Washington, DC.   
[2014-10-13]. http://public.ccsds.org/publications/archive/650x0b1s.pdf   
[6]Michael Day.CEDARS:Digital Preservation and Metadata[C]. In: 6th DELOS Workshp: Preservation of Digital Information, 1998, Tomar   
[7]National Library of Australia.Preservation Metadata for Digital Collections-Exposure Draft [OL].[2014-12-13].http:/pandora.nla.gov.au/pan/25498/20020625-0000/www.nla.gov.au/preserve /pmeta.html   
[8]Titia van der Werf-Davelaar. Long-term Preservation of Electronic Publications-The NEDLIB projec[J].D-Lib Magazine,1999(5):9   
[9]Data Dictionary for Preservation Metadata: Final Report of the PREMIS Working Group [OL]. [2014-12-13]. htp://www.oclc.org/research/projects/pmwg/premis-final.pdf   
[10]PREMIS Data Dictionary Version 2.2: Hierarchical Listing of Semantic   
Units[OL].[2014-10-13].http://www.loc.gov/standards/premis/v2/premis-dd-Hierarchical-Listing2-2.html   
[11]Brian Lavoie，Richard Gartner. Preservation Metadata(2nd Edition)[OL].[2014-12-13]. http://dx.doi.org/10.7207/twr13-03   
[12]Rights metadata for personal archives. [OL].[2014-12-13].   
http://www.paradigm.ac.uk/workbook/metadata/rights-metadata.html   
[13]Nir Sherwinter,Richard Wright. Strategy for use of preservation metadata within a digital library[OL].[2014-12-13].https://www.prestocentre.org/system/files/library/resource/strategy_for use_v1.02.pdf   
[14]Guus Schreiber.Metadata Models, Interoperability Gaps and Extensions to Preservation Metadata Standards[OL].[2014-12-13].   
https://prestoprimews.ina.fr/public/deliverables/PP_WP2_D2.2.2_MetadataModels_Interoperabilit yGaps_v1.50.pdf   
[15]Annarita Di Carlo.Internal Deliverable ID4.0.5b-Common Rights Ontology[OL].   
[2014-12-13] .   
https:/prestoprimews.ina.fr/public/deliverables/PP_WP4_ID4.0.5b_RightsOntology_R0_v1.11.pd f   
[16]Giaretta David, Matthews Brian, Bicarregui Juan, Lambert Simon,et al. Significant Properties, Authenticity, Provenance, Representation Information and OAIS Information[OL].   
[2014-12-13].2009. http://escholarship.org/uc/item/0wf3j9cw   
[17]The significant properties of digital objects. [OL].[2014-12-13].   
http://www.jisc.ac.uk/whatwedo/programmes/preservation/2008sigprops.aspx   
[18]Andrew Wilson.Significant Properties Report[OL]. [2014-12-13].   
http://www.significantproperties.org.uk/wp22_significant_properties.pdf   
[19]Gareth Knight, Digital Curation Specialist .InSPECT Significant Properties Data   
Dictionary[OL]. [2014-12-14]. htp://www.significantproperties.org.uk/sigprop-dictionary.pdf [20]Simone Sacchi, Karen Wickett Allen Renear, et al.Framework for Applying the Concept of Significant Properties to Datasets[C]. In: Proceedings of ASIST 2011 ,October 9-13,2011, New Orleans, LA, USA.   
[21]Ruth Duerr, Ron Weaver, Mark A. Parsons. Chapter 7-A New Approach to Preservation Metadata for Scientific Data -A RealWorld Example[M],Springer-Verlag Berlin   
Heidelberg,2010,pp:113-125   
[22]Kia Ng, Eleni Mikroyannidi, Bee Ong. An Ontology based Framework for the Preservation of Interactive Multimedia Performances[C].In: Proceedings of 2O09 Fifth IEEE International Conference on e-Science,pp:40-44   
[23]Tran Vu Pham & Kia Ng. Preservation of Interactive Multimedia Performances: Ontologies and OAIS[OL].[2014-12-13].   
http://www.casparpreserves.eu/Members/metaware/Presentations/preservation-of-interactive-multi media-performances-ontologies-and-oais/at_download/file.ppt   
[24]Günter R. Fuhr,. Heiko Zimmermann. An Ontology Framework for Long-term Digital Preserv ation and beyond[OL].[2014-12-13].   
http://www.ibmt.fraunhofer.de/content/dam/ibmt/en/documents/PDFs/ibmt-product-information-s heets/telematics-intelligent-health-systems/MT_ENSURE_en.pdf   
[25]K. Stepanyan, M. Joy, A. Cristea， et al.D2.2 Report:BlogForever Data Model[OL].   
[2014-12-13]. https://zenodo.org/record/7488/files/BlogForever_D2_2WeblogDataModel.pdf [26]PREMIS OWL ontology 2.2 now available[OL].[2014-12-13].   
http://www.loc.gov/standards/premis/ontology-announcement.html   
[27]Jean-Francois Cosandier, Per Dahl. The European Project MEMORIES: Management, Description, Retrieval of Audio Archives[OL].[2014-12-13].   
http://www.memories-project.eu/documents/Presentation_MEMORIES_Amsterdam.ppt   
[28]Linked data and preservation metadata[OL].[2014-12-13].   
http://www.dpconline.org/component/docman/doc_download/773-linksthatlast2012peyrard [29]Report on the survey of technologies, polices,metadata,semantics and   
ontologies[OL].[2014-10-13].   
http://www.scidip-es.eu/assets/Deliverables/SCIDIP-ES-DEL-WP15-D15-1.pdf   
[30]Kun Qian, Maik Schott Christian Kraetzer, et al.A Security Contextualisation Framework for Digital Long-Term Preservation. In: Proceedings of the International Workshop on Semantic Digital Archives, (part of the 15th International Conference on Theory and Practice of Digital Libraries (TPDL)), September 29th, 2011, Berlin, Germany.   
[31]Priscilla Caplan.DCC Digital Curation Manual: Instalment on Preservation Metadata [OL]. [2014-12-13]. http://hdl.handle.net/1842/3356   
[32]The OPM Provenance Model （OPM） [OL].[2014-12-13].http://openprovenance.org [33]Provenir Ontology[OL].[2014-10-13].http://wiki.knoesis.org/index.php/Provenir_ontology [34]Hertig O.Provenance Information in the web of Data[C]. In: Proceedings of the Linked Data on the web (LDOW) workshop at WWW, 2009,Madrid, Spain.

# 作者简介：

刘建华女，中国科学院文献情报中心，馆员，长期保存，信息抽取与文本挖掘,E-mail:liujh@mail.las.ac.cn，北京市海淀区，邮编：100190。张智雄男，中国科学院文献情报中心，研究馆员，博士生导师，信息系统和智能信息处理。地址同上。

联络方式：  
通讯地址：北京市海淀区北四环西路33号文献情报中心3D联系电话：010-82628382；13426465118.