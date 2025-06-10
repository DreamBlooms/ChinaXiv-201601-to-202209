# 基于Drupal的中文古籍书目关联数据发布研究

白林林1祝忠明2

1中国科学院文献情报中心北京 100190

²中国科学院兰州文献情报中心兰州 730000

摘要：［目的/意义］对我国特有的以CNMARC格式编目的中文古籍书目数据进行关联数据化发布研究，促进中文古籍的开放利用。「方法/过程］利用Drupal平台从数据建模、数据映射、数据链接、外部查看几方面进行了对中文古籍书目数据发布为关联数据的过程进行了实现。［结果/结论」通过Drupal平台可以方便地进行中文古籍书目数据的关联化发布，但是也存在链接不完善情况，还需Drupal功能的进一步提升和与其他链接工具的使用。

关键词：中文古籍；书目数据；关联数据；Drupal；CNMARC

分类号：G254

在五千多年的社会发展过程中，我国形成了成千上万卷的古籍，但是目前我国图书馆所收藏的中文古籍在著录时，系统所采用的仅在图书馆领域通用的著录格式CNMARC和对外的基于 Z39.50协议的OPAC检索模式严重限制了古籍的利用，且检索到的书目数据是无法与外部数据进行链接的，只是一个封闭的数据集。因此如何使CNMARC编目的中文古籍书目数据对外开放、实现书目数据之间的语义链接成为保存古籍的图书馆亟待解决的问题。

但是我国中文古籍书目数据的语义化研究方面的研究目前主要集中在通过本体对古籍知识概念、知识元的语义网络构建、古籍文献语义标注的细粒度语义理论研究方面，如安欢[1]对中医养生古籍的知识概念的语义网络构建进行了研究，高明月[2基于本体构建原则对《备急千金要方》的语义网络构建进行了研究。但是古籍书目数据本身的语义化研究迄今为止一直没有实践性进展。

2006 年，关联数据[3的提出以及随后在国外图书馆和各个机构、企业的成功实践应用（如美国国会图书馆标题表的关联数据发布[4、德国国家图书馆书目数据和规范数据的关联数据发布[5]、BBC 的关联数据发布[6]等）为实现我国中文古籍书目数据的发现与丰富语义链接提供了一种思路。

关联数据作为语义网的一个简单应用，主要利用 RDF 和URI技术进行数据的发布、共享和链接，其中RDF以“主-谓-宾”三元组的模型对数据进行描述，因此发布关联数据最为关键的一步是如何将CNMARC格式的数据转换为RDF格式，本文对关联数据发布方式进行分析后，选取Drupal平台作为中文古籍书目关联化发布的技术平台，以《关联数据中CNMARC到MARC21的映射实现》［7]和《关联数据中CNMARC 到RDF的映射实现》「8]研究的语义映射为基

础，进行了中文古籍书目数据的关联化研究。

# 1关联数据发布方式研究

2006 年7月Tim Berners-Lee提出的关联数据的四个发布原则[1]：

（1）用URI作为任何事物的名称；  
（2）用HTTPURI使任何人都可以访问这些名称；  
（3）有人访问某个标识名称时，以标准的形式(如RDF，SPARQL)提供有用的信息；  
（4）尽量给出相关的URI，方便人们可以找到更多的相关的事物。

遵循关联数据发布四原则，根据发布数据量的大小、数据的保存方式、数据的更新频率，目前主要有一系列发布方式[9]：静态RDF 发布，适用于数据量比较小的情况，数据创建者自己制作 RDF文档上传至网络上；RDF三元组批量存储的发布，适用于数据量大各种类型的数据的发布应用；关系数据库的发布，适用于将关系数据库存储的数据内容发布成关联数据，可利用的工具有D2R、OpenLink Virtuoso 或Triplify；基于现有应用程序或WebAPI(Application Program Interface，应用程序界面）进行封装的数据发布等，目前发布关联数据的发布方式也一直在更新。但是在发布过程中，考虑到所用发布工具的难易度和版权，本文利用了最流行的内容管理系统Drupal，无需掌握过多的语义技术且为开源软件，通过内容模型对数据进行结构化表示，利用所包含的RDF 相关模块与其他模块实现数据的RDF 化和RDF 链接，最后通过 SPARQL模块对外开放以便于其他网络应用实现查询。

2基于Drupal实现中文古籍书目数据关联化的原理机制

Drupal[10]是基于网络的开源的一套内容管理系统，是一个在PHP 语言、Apache 服务器支撑下的内容管理平台，具有强大的网站开发能力，可以说是网站开发的操作系统。主要由内核、模块、主题三部分架构而成，而Drupal的关联数据支持功能也正是通过这些模块得以实现的。Drupal在当初创建的时候，考虑到当时已经存在的语义网技术，就在其核心代码中植入了rdf.php 的源文件，在关联数据这个概念提出以后，马上成立了语义网组，用于研究关联数据技术。终于在 2008年开始陆续发布了Drupal6中支持关联数据的模块，经过一年的时间，在 2009年时，Drupal6 通过这些模块已经可以支持关联数据的发布了。并且在2011年发布的 Drupal7中，关联数据支持模块中的许多模块作为Drupal的核心模块被内化。在2015年11月发布的Drupal8 版本中，更进一步并入了原来属于扩展模块的部分为核心模块。具体而言，Drupal与关联数据发布相关的模块具体包括：（1）RDF 模块[11]：可以把 Drupal 站点上的内容模型转化为RDF数据模型。

（2）SESMOL-ARC2（Archive2）[12]是一个RDF数据存储器。（3）RDFx[13]（RDF CCK、evoc模块）：是RDF Extention的简称，定义内容类型和字段、与RDF的Class 和property 映射。evoc 模块是 External RDF vocabulary Importer的简称，用于导入外部元数据元素词汇集。（4） SPARQL 模块[14]：为查询生成的RDF数据提供接口。（5）Feeds 模块[15]的功能是实现数据的批量导入。（6）Reference 模块[16]、Link 模块[17]：分别实现 RDF 数据的内部链接和外部链接。（7）RESTful web services 模块[18];系统默认的数据格式是嵌套在 HTML 中的 RDFa格式，这个模块提供除了HTML 格式之外的RDF/XML、N3、JSON 等格式的数据。

3基于Drupal的中文古籍书目数据的关联数据发布

遵循关联数据发布流程和 Drupal实现关联数据的原理机制利用 Drupal平台，本文通过三步实现中文古籍书目数据的关联化发布：数据建模、数据 RDF化、数据的WEB发布与开放查询。

# 3.1数据建模

数据建模，在这一步囊括了对将要发布为关联数据的中文古籍进行实体、属性的选择与分析、词汇表的选择与创建、数据模型的建立。

# 3.1.1实体与属性的选择、分析

在发布关联数据之前，需要详细分析所发布的中文古籍书目数据中哪些可以作为实体，以及实体的属性和实体之间的关系。从CNMARC依据的古籍编目规则所组成的书目记录的扁平的层次看，可分成中文古籍本身、与中文古籍相关的责任者、版本、地点、主题等。中文古籍本身的属性有题名（正题名、其他题名）、责任者、版本、出版地、出版商、出版时间、册数、尺寸、主题、附注等；责任者实体的属性有姓名、字、号、籍贯、朝代、成就、思想、流派、以及作品等；版本实体的属性有版本名称、版本简介、版本出处、其他名称、源流等；出版地实体的属性名称、有经度、纬度、简介、特点等；主题的属性包括上下位词、入口词、优选词、主题词对应的分类号等。

# 3.1.2词汇表的选择

词汇表的选择要根据所描述实体的属性进行选择，其中Drupal站点上被内化的元数据元素词汇集有content，dc，foaf，og，rdfs，sioc，sioct，skos，xsd 等，除了这些基础词汇集，本文还选用bibo 本体、mods 本体、ISBD 本体、RDA，通过evoc 模块把这些外部词汇集进行导入，其中BIBO 本体和ISBD 本体较全面地包含了适合于描述中文古籍书目数据的类和属性。

BIBO 本体[19]，称为书目本体，是由Giasson F和D'Arcus B两人利用本体构建工具

Protégé构建的一个本体，BIB0本体通过定义各个类及类之间的上下位关系，每个类有对应的属性，这种属性在上下位类之间是可以传递的，所以类中最上位的类为Owl:Thing，所有下位类有81个，所包含属性中适合描述中文古籍的也比较全面。

ISBD 词汇集[20]，国家标准书目著录，对各类信息可以进行描述的国家标准，，包括：普通图书、连续性资源、古籍、电子资源、非书资料、印刷乐谱、析出文献、地图资料。在2011年由Saur DG在开放元数据注册系统（Open Metadata Registry，OMR）[21中进行了ISBD元素和属性的关联数据注册服务。我国的古籍著录规则就是在参考国际标准书目著录（古籍）规则的基础上编制而成的，所以采用ISBD词汇集中的元素和属性更加能准确地描述中文古籍书目数据。

# 3.1.3数据模型的创建

数据模型主要以比较直观的方式显示对中文古籍所涉及的实体及属性以及之间的关系。中文古籍除了选择责任者、出版地判定其来源、真实性之外，把版本作为一个链接，是考虑到其不同于现代书籍的特殊性，古籍版本对中文古籍的鉴别、评价至关重要，所以在Drupal站点上也对古籍版本的关联数据发布作了研究，出版地可以与已发布为关联数据的GEO 本体[22]（地理本体）进行链接；中文古籍主题信息是来源于中国分类汉语主题词表或汉语主题词表，深圳大学图书馆提供了中国分类汉语主题词表的关联数据试用系统[23]，所以与这个系统进行了链接，但是该系统目前处于试用状态，外部并不能与之进行链接，所以中文古籍主题词属性选择了字符串（URI以后用来扩展）责任者、出版地与外部数据进行了链接，在图1的中文古籍数据模型中用URI标记，版本部分是在Drupal站点内部进行的链接，用节点node 标记。

![](images/ff3d37bdc9ce0550f2d3c9a2287cac1c794223d0898d99f45c114db35c9312e1.jpg)  
图1中文

# 古籍数据模型

3.2中文古籍书目数据RDF化

中文古籍书目数据的RDF 化通过CNMARC 与RDF 的映射分析、内容类型的创建和 RDF 映射、数据的批量导入三步实现。

# 3.2.1中文古籍书目数据CNMARC字段与RDF映射的分析

关联数据实践中，国外图书馆机构在MARC21到RDF的映射层面，积累了较丰富的经验，考虑到CNMARC与MARC21的记录结构相似，仅在字段描述方面存在一些差异，CNMARC元数据到 RDF 的映射可以首先考虑CNMARC到MARC21的映射，再参照 MARC21到RDF 的映射，最终构建CNMARC到RDF 的映射。其中CNMARC到MARC21的映射和CNMARC 到到RDF 的映射分别在《关联数据中的CNMARC到MARC21的映射实现》和《关联数据中的CNMARC到RDF 的映射实现》文中已进行了探讨，所以在此不再进行详述。

# 3.2.2内容类型的创建和RDF映射

基于上述中文古籍书目数据实体属性的分析、选择，各字段、子字段等与RDF映射分析的基础上，在Drupal站点上通过CCK模块添加名称为“AncientBook”的内容类型，同时添加CNMARC中描述中文古籍的字段名称作为该内容类型的字段，由于站点有默认的Title 题名字段，所以把这个字段作为中文古籍的正题名字段，本文在站点添加的字段有其他题名、合刻题名、等同责任者、次要责任者、版本、出版地、出版商、出版时间、册数、尺寸、主题、四库分类号等23个字段（图2）。

通过 RDF CCK 模块对创建的内容类型、字段名、字段类型与RDF三元组中的主谓宾进行一一映射。其中内容类型对应RDF 主语，通过 RDF types 对其进行类型的描述；字段集中的字段各自对应RDF 谓语，与Drupal站点所包括的元数据词汇表和通过evoc模块从外部导入的元数据词汇表对应；字段类型对应宾语属性类型，Drupal站点规定了三种属性类型，property、rel、rev。其中property 代表属性类型是文本值（比如数字、text文本、html文本等），并且可以通过 XML Schema datatypes进一步说明该文本值是什么数据类型，比如字符串、布尔值、日期等；rel代表属性类型是URLS；rev代表属性类型是节点参照，是站点内另一个节点。每一种属性可以有多个取值。当利用RDFCCK 映射完成之后，系统就会利用 RDF 模块自动生成该新建内容模型的本地RDFS 词汇表。

考虑到责任者对考察古籍的重要性和中文名称规范文档还未发布为关联数据，新建了一个内容类型“person”，建立姓名、简介、朝代、生卒、作品、朋友等字段，利用foaf 本体和time 本体[24进行RDF MAPPINGS。

中文古籍版本对考证古籍价值和真伪的重要性，我国目前缺乏古籍版本本体，所以在Drupal站点上新建了一个名称为“edition”古籍版本内容类型，按照中国分类主题词表第二版的“版本”主题词间的关系，选取属性题名、摘要、上位词、下位词、中图法分类号、参见、来源词表、源流、入口词（非优选词）、族首词、优选词作为字段。

Ancientbook EDITMANAGEFIELDSMANAGEDISPLAYRDFMAPPINGSCOMMENTFIELDSCOMMENTDISPLAY Home>Administration>Structure >Content types>Ancientbook Show row weights LABEL MACHINE NAME FIELDTYPE WIDGET OPERATIONS ÷ Title tite Nodemodule element ↑ 其他题名 field_altnative Text Textfield edit delete . 合刻/合订题名 field_relation Text Textfield edit delete bs 等同责任者 field_creator Nodereference Check boxes/radio buttons edit delete 4。 次要责任者 field_contributor Nodereference Check boxes/radio buttons edit delete + 版本 field_edition Nodereference Check boxes/radio buttons edit delete 0。 出版地 field_publicationplace Link Link edit delete · 出版商 field_publisher Text Text field edit delete →。 出版时间 field_date Text Text field edit delete . 册数 field_volume Text Text field edit delete ： 尺 field_extent Text Textfield edit delete 主题 field_subject Text Textfield edit delete i。 四部分类号 field_classification Text Text field edit delete +· 丛编 field_is_part_of Nodereference Check boxes/radio buttons edit delete 中 附属丛编题名 field_has_part_of Nodereference Check boxes/radio buttons edit. delete 中· 一般性附注 field_note Text Textfield edit delete ： 装订形式 field_binding Text Textfield edit delete

# 3.2.3节点数据的批量导入

完成内容类型创建和RDF映射之后，就可以根据建立的这个数据模型为每一条中文古籍书目数据创建实例，生成节点。创建节点时，可以单个节点的创建，也可以通过Drupal的Feeds 模块[9批量导入数据。可以导入数据的格式有 txt、csv、tsv、xml、opml五种格式。但又以CSV格式的数据导入最为应用的比较多，本文选取了从CALIS联合公共目录检索系统的“古籍四部类目浏览”[25]下载了100条文本格式的UTF-8 编码的中文古籍书目数据进行处理成CSV文件进行导入。具体实现过程如下：

（1）Feeds的设置

在Feedsimporters页面进行基本设置、提取器、解析器、处理器的设置。

基本设置不用修改，按系统默认的方式；提取器有文件上传和网络抓取两种，选择Fileupload（文件上传）；解析器有Common syndication parser、CSV parser、OPML parser、Sitemap parser 四种，选择CSV parser；处理器 Node processor、Taxonomy termprocessor、User processor三种，选择Node processor，并对 Node processor 进行设置Bundle 设置（绑定对象，选择 AncientBook）和映射，这里的映射是 source与Target之间的映射，指所上传的CSV文件的字段名和Bundle绑定的对象AncientBook内容类型所创建的字段之间的映射，映射过程如图3。所以需要事先对从CALIS下载的数据进行处理。

importancientbooks bibliographydata EDITEXPORTCLONEDELETETAMPER   
Home>Administration>Structure>Feeds importers   
Basicsettings Mapping for Nodeprocessor Help Attached Settings Definehicheemetofineedsoteinupalgeakeseataeastfn to: targetAuniquetagetmeansthtavalefotargetcanonlyoccronce.E.gnlyoneitemwiththeULhtp/examplecom/ontent/canexis. [none] Show row weights   
Perdicimiort: SOURCE TARGET TANFIGURATION Importson i 题名2005a Title (title) Notused as unique. Remove   
Fetcher Change   
File Settings 其他题名5175a 其他题名(field_altnative) Remove upload 合刻题名4235a 合刻/合订题名(field_relation） Remove   
Upload content   
from a local file. 等同责任者7015a 等同责任者(Nodereferencebynodetitle)(field_creator.title) Remove   
Parser Change ： 次要责任7025a 次要责任者(Nodereferencebynodetitle)(field_contributor:title) Remove   
csv Settings . 版本（205Sa） 版本（Nodereference by node title)(field_edition:title) Remove   
Parsedata in = 出版地（2105a） 出版地：URL (field_publicationplace:url) Remove Comma Separated 出版商2105c 出版商（field_publisher) Remove Valueformat. 出版时间2105d 出版时间(field_date) Remove Change T 册数215Sa 册数（field_volume） Remove   
Processor Node Settings 尺寸2155d 尺寸(field_extent) Remove Mapping 主题606Sa 主题(field_subject) Remove processor ： 四部分米号6965a 四部分米号(fieldclassifiratinn) Remnve

（2）数据预处理

将数据处理成符合格式的CSV文件。以Excel格式打开下载的数据，由于每一条数据的字段不尽相同，所以在EXCEL表格中将下载的数据分解与提取成与Drupal所建的“AncientBook”内容类型下创建的相同的字段，并保存为CSV文件。成与Drupal生成CSV文件，除了以上字段的处理，还有数据内部的处理，主要针对多值字段和链接处理。针对多值问题可以通过Feeds Tamper 模块[2来处理，这个模块有许多插件，通过图3中右上角的Temper 给多值字段添加“Explode”插件，这个插件默认的多个值之间用英文半角的逗号隔开，需要安装此插件的字段有：“其他题名 $5 1 7 \mathfrak { S } \mathrm { a }$ ->其他题名、次要责任者 $7 0 2 \mathfrak { s a }$ ->次要责任者、附属丛编 $4 1 1 \ S \mathrm { a \ - } \lambda$ 附属丛编题名”三个字段。

针对链接问题，如果是节点参照（nodereference）内部链接，只需在CSV文件中填写字符串，在映射时映射为(Node reference by node title）（field-X），只要在导入文件前导入被参照的节点即可；如果是外部链接，需要在映射时同时映射为title和URI两种，在CSV文件中设置两列相应的字段，一列为取值为title，一列取值为对应的URI，如本文的出版地就是如此设置，两列字段名都取为出版地 $2 1 0 \ S \mathrm { a }$ ，一个取值为具体的地名，另一列取值为从GEO本体中对应的URI。

（3）数据的批量导入

经过Feeds设置和数据预处理之后就可以导入数据了，在导入数据时，需要自定义代码，在 wamp/www/drupal7/sites/all/modules 下定义一个文件夹，本文命名为 sem,在其中创建sem.module 和 sem.info两个文件，在sem.module编写代图4的代码；在图3右上角点击EXPORT，复制Feeds 映射生成的代码，在图4中进行粘贴。在Feedsimporter页面点击中间的import即可选择“import ancient books bibliography data”进行CSV格式的数据导入。

functionsem feeds importer_defaultO{   
此处粘贴生成的代码   
t 在上图代码之外添加以下两行   
Sexport['import_ancient_books_bibliography_data'] $\begin{array} { r } { = { } } \\ { { } } \end{array}$ Sfeeds_importer,t   
retumSexport;t   
}   
functionsem_ctools_plugin_api(Sowner.Sapi){ if (Sowner $= ^ { . }$ feeds'&& $S _ { \Delta } D C =$ feeds_importer_default){t retun array('version'=>1） $: 4 1$   
}

# 3.3数据的Web发布与开放查询

通过上述中文古籍书目数据的RDF化和RDF 链接，系统会自动为创建的中文古籍节点生成各种格式（N3、RDF/XML、Turtle等）的三元组RDF 数据。通过 SPARQL endpoint终端的SPARQL查询语句查询用户所需要的数据或选用安装了Tabulator Extension插件的Firefox浏览器直接查看RDF数据。

# 3.3.1数据的SPARQL查询

第一种通过 SPARQL查询语法对生成的RDF数据进行查看，Drupal站点安装了SPARQLendpoint 模块，同时必须配合 SESMOL-ARC2 模块存储三元组来使用，图5为Drupal站点提供的 SPARQL endpoint查询页面查询所得的数据。查询时必须先对查询用到的词汇表进行实现声明，查询语句格式必须与RDF语句一致。右侧可选择查询结果的输出方式，包括XML、JSON、Plain、Serialized PHP、Turtle、RDF/XML、Query Struture、HTMLTable、TSV格式。

![](images/f2b3425dfd27a49305a36a77ea1b64f31855b4af2039b0abf2326bca9f790fbc.jpg)  
图5SPARQL查询图

# 3.3.2语义浏览器查看RDF数据

第二种通过语义浏览器查看生成的RDF数据。本文下载了Firefox3.6.18中文版，Tabulator Extension 0.87版本；通过设置火狐浏览器“工具---Data browser---makeFirefox request RDF”。如果是通过Firefox直接查看，只需在每个节点的后面添加“.rdf”即可得到所需要的RDF数据，输出的数据格式包括N3 格式、RDF/XML格式等。图6、图7分别为对Drupal站点上节点“本草述：三十二卷,卷首，［一卷」”所生成的RDF/XML、N3格式的数据。

<rdf:RDF   
xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:isbd="http://iflastandards.info/ns/isbd/elements/"   
xmlns:terms="http://purl.org/dc/terms/"   
xmlns:bibo="http://purl.org/ontology/bibo/" xmlns:sioc="http://rdfs.org/sioc/ns#"> <rdf:Description rdf:about="http://localhost/drupal7/node/27"> <isbd:P1037>有墨筆眉批附注 內封鐫：潛江劉雲密先生著。本艸述。嘉慶庚午還讀山房校瑟；內封B面鐫：光緒丙 <isbd:P1040>板框19.1x14，10行20字，小字雙行同大字，白口，單黑魚尾，左右雙邊</isbd:P1040> <isbd:P1068></isbd:P1068> <isbd:P1078>线装</isbd:P1078> <isbd:P1087></isbd:P1087> <terms:created>2016-03-03T16:42:20+08:00</terms:created> <terms:creator rdf:resource="http://localhost/drupal7/node/26"/> <terms:date>2016-03-03T16:42:20+08:00</terms:date> <terms:extent>25cm</terms:extent> <terms:issued>清光緒丙子[二年,1876]</terns:issued> <terms:modified>2016-03-03T16:42:20+08:00</terms:modified> <terms:publisher>来青閣</terns:publisher> <terms:subject>中藥學-- 本草-- 中國</terms:subject> <terms:subject>子部,医家類,本草之屬</terms:subject> <terms:title>本草述：三十二卷,卷首,[一卷]</terms:title> <bibo:annotates>卷七至九分上、下卷.</bibo:annotates> <bibo:annotates>有墨筆眉批</bibo:annotates> <bibo:edition rdf:resource="http://localhost/drupal7/content/%E5%88%BB%E6%9C%AC"/> <bibo:volume>24册</bibo:volume> <sioc:num replies>0</sioc:num replies>

# 图6RDF/XML数据查看

![](images/6b454413bce1c7240f54663962d655207bdd029d2df69b4a1b3e769a0af4fb3f.jpg)  
图7N3格式的数据查看

4结语

本文对我国特有的以CNMARC格式编目的中文古籍书目数据的关联数据化进行了研究，通过Drupal软件实现了中文古籍数据书目数据的关联化发布，但是也存在着一些问题：

（1）本文所建的Drupal站点只是一个基于本地位置的小型试验站点，不能对外开放。

（2）链接方面：Drupal站点上所创建的节点与外部的链接过少，这是由于我国目前发布为关联数据的资源过少，只能在本地站点通过自建别的内容类型来创建节点用以实现节点之间的关联。所以应该发布更多的与中文古籍相关的资源为关联数据，比如对鉴定古籍源流非常重要的古籍版本本体的发布、中文名称规范档的发布、中国历史元纪年（朝代）关联数据的发布等。并且在进行链接时也是进行的手动链接，这种情况针对的是小部分数据，针对大量数据，必须配合其他链接工具或软件实现数据之间的自动链接。

（3）RDF三元组存储方面：SESMOL-ARC2这个模块不适用于大型站点，因为RDF索引比较耗时。所以在RDF三元组存储方面，针对大量的数据，选用内存较大的三元组存储器比较合适。

（4）如何把所发布的数据进行可视化是一个关联数据的一个研究热点，而如何把Drupal平台上发布的数据通过可视化进行直观的显示，方便用户更好的理解，进而实现基于Drupal平台发布关联数据的可视化，

参考文献

2[]高明月．基于本体的《备急千金要方》语义网络构建研究[D]．北京中医药大学，2016. 3[] BERNERS-LEET. Linked Data [EB/OL]． [2016-10-11].   
http://www. w3.org/DesignIssues/LinkedData. html.   
4[] SUMMERS E, ISAAC A， REDDING C et al． LCSH， SKOS and Linked Data[C/OL]. [2016-10-11]. http://dcpapers.dublincore.org/index. php/pubs/article/view/916. 5[] Deutsche Nationalbibliothek - Linked Data Service. [EB/OL]. [2016-10-29]. http://www. dnb.de/EN/Service/DigitaleDienste/LinkedData/linkeddata_node.html. 6[] Linked Data on the BBC [EB/OL]． [2016-10-29].   
http://www. slideshare.net/moustaki/linked-data-on-the-bbc-2638734.   
7[]贾君枝，白林林．关联数据中CNMARC到MARC21的映射实现\*［J]．国家图书馆学刊, 2015(4) :80-93.   
8[]白林林，贾君枝．关联数据中CNMARC 到 RDF 的映射实现\*[J]．国家图书馆学刊, 2015(4) :94-102.   
9[] BIZER C， CYGANIAK R， HEALTH T. How to Publish Linked Data on the Web   
[EB/OL]. [2017-01-27]. http://wifo5-03.informatik.uni  
mannheim. de/bizer/pub/LinkedDataTutorial/.   
10[] Drupal - Open Source CMS [EB/OL]. [2016-09-23]． https://www.drupal.org/. 11[] RDF modules [EB/OL]． [2016-09-24]． https://www.drupal.org/node/222788. 12[] ARC2 store [EB/0L]. [2016-09-24]. https://www.drupal.org/project/arc2_store 13[] RDF Extensions [EB/OL]. [2016-09-24]. https://www.drupal.org/project/rdfx. 14[] SPARQL [EB/OL]. [2016-09-25]. https://www.drupal.org/project/sparql. 15[] Feeds [EB/OL]. [2016-09-27]. https://www.drupal.org/project/feeds.   
16[] Entity reference [EB/OL]. [2016-09-24].   
https://www. drupal.org/project/entityreference.   
17[] Link [EB/OL]. [2016-09-28].https://www.drupal.org/project/link.   
18[] RESTful Web Services[EB/OL]. [2016-09-   
29].https://www. drupal.org/pro ject/restws.   
19[] Bibliographic Ontology Specification 丨 The Bibliographic Ontology [EB/OL]. [2016-09-30]. http://bibliontology.com/.   
20[] The Registry! :: ISBD elements :: Show Detail [EB/OL]. [2016-09-30] http://metadataregistry.org/schema/show/id/25.html.   
21[] http://metadataregistry.org/   
22[] GeoNames [EB/OL]. [2016-09-30]. http://www.geonames.org/.   
23[]中文知识组织系统形式化语义描述标准体系研究[EB/OL]．［2016-09-30].   
http://nkos.lib.szu.edu.cn/.   
24[] Time Ontology in OWL [EB/OL]. [2016-09-30]. https://www.w3.org/TR/owl-time/ 25[]古籍四部分类浏览[EB/0L].[2016-09-   
30].http://opac.calis.edu. cn/opac/classNumber. do?subact $=$ enterpage&type $\circleddash$ sklm. 26[] Feeds Tamper. [EB/OL].[2016-09-30]. https://www.drupal.org/node/2614786.

# 作者贡献说明：

白林林：负责论文的数据获取、提纲、撰写；祝忠明：负责论文的修订。

# Research on Publishing Chinese ancient books bibliographic data to Linked

# Data

Bai Linlin1 Zhu Zhongming²

lNational Science Library， Chinese Academy of Sciences， Beijing， 100190 ²Lanzhou Library， Chinese Academy of Sciences，Lanzhou， 730000 Abstract: [Purpose/significance] This article did a research on publishing Chinese ancient bibliographic data cataloged in CNMARC format to linked data in order to promote open utilization of Chinese ancient books. [Method/process] The process of publishing ancient Chinese bibliographic data as Linked Data is realized by using Drupal platform from data modeling， data mapping， data linking and external querying. [Result/conclusion] Publishing ancient Chinese bibliographic data as Linked Data can be easily realized through Drupal platform, but there also exists imperfection linking so that further improvement of Drupal functions and use of other link tools.

Keywords : Chinese ancient books; bibliographic data; linked data; Drupal; CNMARC