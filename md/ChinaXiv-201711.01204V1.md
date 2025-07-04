# 构建面向WARC文档的全文索引系统

胡吉颖吴振新谢靖张智雄(中国科学院文献情报中心 北京 100190)

摘要：【目的】开发网络信息存档WARC文件的解析与索引系统，充分挖掘科技网站存档资源价值。【应用背景】在网络资源采集存档领域，WARC文件格式获得了广泛的应用。随着网络信息的多样化，已有的WARC文件索引工具越来越难以满足用户多样性的查询需求。【方法】采用模块化方案解析WARC 文件。分析比较常用的索引工具，选择Solr平台开发全文索引系统。【结果】实现对WARC文件基于内容的检索访问服务，并在WARC的索引中增加了学科分类、资源类型和存档时间等分面检索内容，从多维度对WARC文件内容进行揭示。【结论】向用户提供了丰富的科技网站存档数据信息，提高了用户检索访问效率。

关键词:网络存档WARC 文件模块化解析Solr 索引分类号：G352

# 1引言

随着互联网在社会生活中的深度扩展，网络信息的更新速度不断加快，网络资源的生命周期变得更加短暂。采集并保存具有价值的Web资源信息，以满足当前和未来的访问和使用，已成为国内外许多保存机构的重要工作，一些重要在线资源的存档，如科研和商业信息，已经上升到国家战略层面。

国际网络保存联盟(IIPC)[1]自成立以来，一直致力于推动全球网络存档(WebArchive)活动，其成员包括全球40多个国家图书馆、档案馆等，在网络信息保存领域占有十分重要的地位。为了更好地支持采集和访问，以及存档机构之间的交流，IIPC提出了标准化的网络文件存档格式WARC(Web Archive)，并于2009 年成为ISO 国际标准[2]。WARC文件格式具有记录信息量大、支持扩展和压缩以及易于管理的特点，已在许多WebArchive项目中得到广泛应用[3]。

随着参与保存的科研机构数量增多，存档资源数据量的迅速上升，存档资源信息的利用与共享成为WebArchive活动中越来越重要的方面。如何提升用户体验，满足用户多样性的查询需求；如何利用先进的技术有效重用存档资源，充分发挥存档资源的价值，这些都成为存档项目开发面临的挑战。WARC文件解析和索引技术的提高，成为解决这些问题的关键环节。本文将详细介绍中国科学院文献情报中心WebArchive团队在国际重要科研机构网络资源存档实践中，如何有效地实施WARC的解析及构建全文索引系统。

# 2WARC索引工具现状及需求分析

网络存档内容不仅数据量巨大，而且随着时间在非线性地动态增加。为了实现WARC存档文件的检索和访问，对WARC的解析与索引显得尤为重要，最常用的开源软件工具包括Wayback[4]、NutchWAX[5]和WERA[等。

Wayback是互联网档案馆(InternetArchive,IA)提供的一个基于URL的索引与访问工具，可以重现时间轴上不同时间点存档的页面，但不支持对文本内容的检索访问，因而难以满足用户多样化的搜索需求。NutchWAX[7可以实现基于内容的全文索引和检索,并在许多国家的网络存档项目中得到应用。目前，Nutch开发团队战略方向发生了变化[8，已很少提供

NutchWAX的后续维护和更新，而专注于网络爬虫工具的开发。此外,NutchWAX依赖于Hadoop的文件系统建立索引，不具备在本地建立索引的能力；功能扩展比较困难，需要修改大量的代码才能实现。因此NutchWAX已不再是一个合适的提供全文检索的平台。WERA也是一款比较常用的网络存档内容查询与浏览工具，它由IA和挪威国家图书馆共同开发，既可以提供类似于Wayback的URL检索功能，也具备全文检索的能力。但是，开发人员采用NutchWAX作为其搜索引擎的内核，因而WERA也没有从根本上解决NutchWAX所面临的局限性。Solr[9是应用十分广泛的开源企业级搜索软件，具备全文索引和分面检索功能。IA在对比NutchWAX和Solr性能后，发现在保存的文档数量急剧增加时，NutchWAX的检索性能明显低于Solr，因而推荐采用Solr作为未来全文检索的平台。目前，大英图书馆、荷兰视听研究所以及IA已经开始探索使用Solr解决WARC存档项目的全文检索问题。

中国科学院文献情报中心在实施国际重要科研机构网络信息存档项目[10]中，需要构建一个 Web 存档访问服务平台，为科研人员、情报人员、科技管理人员长期有效地利用存档资源提供有利的支撑。这不但需要对存档资源提供基本访问服务能力，同时需要支持用户在时间线上对相应的网络科技信息进行研究和分析，还需要为数据挖掘和再利用提供历史数据的支撑这些功能的实现需要底层索引系统提供有力的支持，而现有的WARC索引工具很难满足这些要求，因此在项目研发过程中，笔者开始探索利用Solr平台构建面向WARC文件的全文索引系统以满足用户的需求。

在网络资源长期保存与检索领域，与Solr相关的研究仍处于起步阶段，存在许多问题需要解决，尤其是Solr不具备直接索引WARC文件的能力。为了解决上述问题，并从WARC文件中提取出更多的信息，本文利用WARC文件的结构化特性，采用模块化方案实现WARC文件的解析；从解析结果中提取索引字段内容，并利用Solr平台构建面向WARC文档的全文索引系统。

# 3WARC文件模块化解析的设计与实现

# 3.1WARC文件结构样例及存储方案

WARC能在单个文件中安全地承载大量数据对象，它提供了将多个资源记录(WARCRecord)连接成单个长文件(WARC文件)的机制，按照互联网上抓取内容块的顺序存储"网络爬取的内容”。为了便于数据的保存与分享，WARC格式的文件由单个或多个WARC记录简单连接而成，第一个记录通常用于描述后续的多个记录。以采集科技网站(http://www.iahe.org/)为例，图1给出了采集该站点生成的WARC文件所包含的信息。

Warc-Type=response -Warc-Date=2014-03-27T09:15:27Z 版本号 -Warc-Record-ID $\scriptstyle 1 = <$ Kurn:uuid:602e7461- 声明 1b45-4e0a-81cd-05834c40f330> Content-Type=application/http 记录标头 多个命名 Absolute-offset=742 字段行 Content-length=32608 WARC Record 个空行 -Warc-Target-URI=http://www.iahe.org/ WARC Record -Warc-Payloa-Digest=shal:PB7UTLRONT ：· WXCXAMZON5YZYRA57WGCYL + Warc-IP-Address=213.238.130.4 单个 WARC Record -Http//1.1200 OK WARC -Cache-Control:Private Content-length:32344 WARC Record HTTP响应 头 Content- type:text/html WARCRecord -Server:Microsoft-IIS 7.5 Date:27Mar201409:04:57GMT 内容块 两个空行 -Connection:close <Html> <Head> 网络资源 内容 <Title>Welcome to the International Association for Hydrogen Energy <Body></Body></Hmtl>

一般情况下，WARC 记录的内容或者是一次检索的直接结果(网页、内嵌图片、URL转向信息、DNS主机名查询结果、独立文件等)，或者是为存档内容提供附加信息的综合资源(如元数据、转化后的内容)。每个WARCRecord由一组简单文本标头和任意数据内容块构成，其中WARC记录标头的第一行，是用于声明该记录采用给定版本号的WARC格式，然后是以空行结束的不定行数的命名字段。可以发现，WARC文件结构具有分层和结构化的特征。

由于网站内容数据量大，采集网站信息会生成大量WARC文件，其储存方案和提供的方式，取决于软件及应用程序的实现。本文使用Heritrix对站点进行采集，采集结果可以分由多个WARC文件存储，每个WARC文件的最大体量可以通过Heritrix的配置文件order.xml 进行设置和管理，即通过写组件<mapname $\varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varprojlim \varLambda$ "write-processors" $>$ 中的max-size-bytes参数进行设置，并且Heritrix会自动对一次采集任务生成的WARC文件进行编号，如在采集过程中设置的WARC文件最大为1GB，当对站点采集的数据小于1GB时，只生成一个WARC文件，WARC文件名中包含序号0000，当超过1GB时，会分为多个WARC文件进行存储，顺序采用0001,0002,0003等，如图2所示：

![](images/4cdd42d0fd59e27e73586a858658d18a2fb0c301234e59cec8ca9f6257c53340.jpg)  
图2 WARC文件顺序存储示意图

# 3.2 WARC文件模块化解析

根据WARC文件的结构化特点，本文在设计WARC文件解析方案时采用分层解析以及解析功能模块化的思路。WARC文件解析流程如图3所示，其解析过程可以分为4个功能模块：WARCRecord获取模块、标头获取模块、WARCRecord内容块获取模块和内容块解析模块。

# (1)WARCRecord获取模块

一个WARC文件由多个资源记录WARCRecord顺序连接构成，通过WARCRecord获取模块将WARC文件拆分为多个WARCRecord，这样就由解析WARC文件内容转变为解析WARCRecord的内容。

Heritrix源代码中除了网络信息采集的核心工具包之外，还提供针对 WARC 格式的IO 操作包org.archive.io.warc。本文利用该包的核心类对WARC文件进行读取，如WARCReader.java，WARCRecord.java,WARCReaderFactory.java等。在WARC文档解析的过程中，循环调用WARCReaderFactory类中的get(StringwarcFilePath)函数来获取WARCReader对象，遍历整个WARC文档，即可以获得每一个WARCRecord.

(2)WARCRecord标头获取模块

每个WARCRecord结构一致，都包括一组WARC记录标头和内容块，在获得WARCRecord后，可通过WARCRecord类中的getHeader(函数完成对记录头标区信息的解析，即获取WARCRecord标头各命名字段信息，这些信息保存在数据结构 Map中。对一个WARCRecord标头的解析结果如表1所示。

![](images/c5eeb719ce7200f40202ae8686fe83b936d440d61a68d1c353d3c2ce9b792a06.jpg)  
图3 WARC文件解析流程

表1WARCRecord 标头的解析结果样例  

<html><body><table><tr><td>序号</td><td>Key</td><td>Value</td></tr><tr><td>1</td><td>WARC-Type</td><td>response</td></tr><tr><td>2</td><td>reader-identifier</td><td>http://124.16.154.180:8066//warcs/201 403/www.iahe.0rg-20140327091515-0 0000-hadoop-master-180.warc.gz</td></tr><tr><td>3</td><td>WARC-Date</td><td>2014-03-27T09:15:27Z</td></tr><tr><td>4</td><td>absolute-offset</td><td>742</td></tr><tr><td>5</td><td>Content-Length</td><td>32608</td></tr><tr><td>6</td><td>WARC-Record-ID</td><td><urn:uuid:602e7461-1b45-4e0a-81cd-</td></tr><tr><td>7</td><td>WARC-IP-Address</td><td>05834c40f330> 213.238.130.4</td></tr><tr><td>8</td><td>WARC-Payload-</td><td>sha1:PB7UTLRONTWXCXAMZON5</td></tr><tr><td></td><td>Digest</td><td>YZYRA57WGCYL</td></tr><tr><td>9</td><td>WARC-Target-URI</td><td>http://www.iahe.org/</td></tr><tr><td>10</td><td>Content-Type</td><td>application/http;msgtype=response</td></tr></table></body></html>

(3)WARCRecord内容块获取模块

类似地，在获得WARCRecord后，利用WARCRecord类中的Warcrecord.read(读取WARCRecord内容，并以字节数组形式存储。

(4)WARCRecord内容块解析模块

前述模块利用Heritrix提供的WARC格式IO操作包中的核心类获取WARCRecord标头字段信息和内容块，而对WARCRecord内容块的解析是通过自行开发模块的 parseContent(byte[]content)完成。解析过程如下:

WARCRecord内容块是由HTTP协议头、两个空行和资源内容组成。首先通过空行分隔从WARCRecord取出HTTP协议头部分进行解析，可以获取其中包含的数据信息。一个HTTP协议头的解析结果样例如下:

HTTP/1.1 200 OK   
Cache-Control: private   
Content-Length: 32344   
Content-Type: text/html   
Server:Microsoft-IIS/7.5   
Set-Cookie:ASPSESSIONIDCCCATDCR $\underline { { \underline { { \mathbf { \Pi } } } } } =$ BGOBMIKBGEKJJO   
MFKGCDLAJB;path=/   
X-Powered-By:ASP.NET   
Date:Thu,27Mar201409:04:57GMT   
Connection: close

该步骤主要目的是通过解析 HTTP 协议头进而获知Content-Type字段内容，即明确存档页面的资源类型，然后根据资源类型调用不同的解析工具去解析：若资源类型为PDF，则调用PDFBox解析；若资源类型为Word、PPT、Excel，则调用POI解析；若资源类型为HTML，则调用HTMLParser解析等。在获得存档页面的标题和内容后，将信息保存到数据结构 Map中。最终,Map 中保存了WARCRecord的标头字段、标题和内容，完成了对单个WARCRecord的完整解析。

由于网络资源内容的多样性和复杂性，不排除某些特别资源出现无法解析或解析时间过长的情况，在实际解析过程中，为了保障WARC文件的解析效率，笔者定义了一个守护线程去执行WARC文件的解析，通过设置守护线程的执行时间来保障解析顺利进行。

从上述过程不难看出，采用模块化解析方案简化了WARC文件的解析实现，可以将WARC文件内容根据WARC结构拆分成相互独立的组成部分，有利于构建内容索引，并可以为以后做数据挖掘、元数据抽取、数据分析服务等提供方便易用的接口。

# 4基于Solr平台构建WARC文件全文索引系统

WebArchive系统不仅要实现对WARC文件的长期保存，而且要能够对WARC解析后的内容建立有效的索引，以向用户提供高效的检索和访问功能。考虑到Solr在全文索引和分面检索方面的强大优势，本文利用Solr工具开发WARC文件内容索引模块，以优化用户检索和访问效果，提升用户体验。

# 4.1自动索引系统流程设计

为了实现对WARC文件的自动化实时索引，开发了一个监测模块，能够实时监测是否有新的WARC文件生成；当有新的WARC文件生成时，自动将其加入索引队列，等待索引模块进行索引，保障了WARC文件索引和检索内容更新的实时性。

![](images/412dcd1a3252d8f8888e126882cfdb35ec5755e53dbebbde54f52fca9a514a5f.jpg)  
图4WARC文件自动索引系统方案设计

图4给出了WARC文档自动索引的方案设计，首先要实现WARC生成系统、索引模块和WARC文件解析模块的对接，达到对WARC文件自动化持续索引的目的。中国科学院文献情报中心构建的采集系统对站点进行周期性采集，采集任务完成后自动将生成的WARC上传到存储阵列进行统一存储，为了实现对采集生成的WARC文件实时索引，监测模块可以周期性对存储阵列进行轮询以查看是否有新的WARC生成，当监测到有新的WARC文件时，将新的WARC文件加入索引队列，等待索引模块实施索引。索引模块从索引队列获取索引任务，然后调用WARC获取和解析模块对WARC文件进行分层读取和解析，解析结果保存在数据结构Map中；索引模块从Map中获取要建立的索引字段的值，可以获取的索引字段包括该存档页面的URL、存档时间、资源类型、存档页面的标题、页面内容等。

# 4.2 索引字段设计

索引字段的设计除了上述WARC解析获得的字段，还包括数据库的辅助扩展字段，如学科分类、来源

的站点名称、站点类型等。每条索引对应WARC文件中的一个WARCRecord，即一个存档页面的信息。索引字段的详细设计如表2所示：

表2索引字段设计  

<html><body><table><tr><td>序号</td><td>字段名称</td><td>字段含义</td><td>字段来源</td><td>备注</td></tr><tr><td>1</td><td>WARC_Record_ID</td><td>页面唯一标识</td><td>WARCRecord头部解析</td><td></td></tr><tr><td>2</td><td>WARC_Target_URI</td><td>存档页面URL</td><td>WARCRecord头部解析</td><td></td></tr><tr><td>3</td><td>WARC_Filename</td><td>WARC文件名</td><td>WARCRecord头部解析</td><td></td></tr><tr><td>4</td><td>WARC_Type</td><td>记录类型</td><td>WARC Record头部解析</td><td></td></tr><tr><td>5</td><td>WARC_Date</td><td>存档时间</td><td>WARC Record头部解析</td><td></td></tr><tr><td>6</td><td>Datelist</td><td>存档时间列表</td><td>索引查询</td><td></td></tr><tr><td>7</td><td>year</td><td>年</td><td>WARCRecord头部解析</td><td>设为分面字段</td></tr><tr><td>8</td><td>month</td><td>月</td><td>WARC Record头部解析</td><td></td></tr><tr><td>9</td><td>day</td><td>日</td><td>WARCRecord头部解析</td><td></td></tr><tr><td>10</td><td>type</td><td>资源类型</td><td>WARC Record 内容解析</td><td>设为分面字段</td></tr><tr><td>11</td><td>formattype</td><td>规范资源类型</td><td>WARCRecord内容解析</td><td></td></tr><tr><td>12</td><td>title</td><td>存档页面标题</td><td>WARCRecord内容解析</td><td></td></tr><tr><td>13</td><td>content</td><td>存档页面内容</td><td>WARCRecord内容解析</td><td></td></tr><tr><td>14</td><td>keyword</td><td>页面关键词</td><td>WARCRecord内容解析</td><td></td></tr><tr><td>15</td><td>site_name</td><td>站点名称</td><td>数据库</td><td>设为分面字段</td></tr><tr><td>16</td><td>site_en_name</td><td>站点英文名称</td><td>数据库</td><td></td></tr><tr><td>17</td><td>site_url</td><td>站点URL</td><td>数据库</td><td></td></tr><tr><td>18</td><td>subject</td><td>站点学科分类</td><td>数据库</td><td>设为分面字段</td></tr></table></body></html>

# 4.3 索引策略设计

为了提高用户的检索效率和更好地揭示存档的WARC文件内容，笔者设计了两种不同的索引策略，即WARC记录综合索引和存档页面索引。

虽然两种索引策略的每一条记录都代表一个存档URL，但第一种索引策略是以存档页面的WARC_RecordID为唯一标识符，每一条索引都代表一个完整的WARCRecord，建立索引时需将WARC文件的解析字段和数据库读取字段依次写入索引相应字段。第二种索引策略是以存档页面的URL为唯一标识符，同时新增一个datelist索引字段；该字段为一个多值字段，用于存储该存档页面不同的存档时间，代表该存档页面自存档以来的存档次数和每次存档的时间。在为每一个WARCRecord建立索引时，首先查询索引中是否存在该URL记录；若不存在，则只需将WARC文件的解析字段和数据库读取字段依次写入索引相应字段；若索引中已存在该URL，说明该URL已经被存档过，则将此次的存档时间和以前的存档时间合并，重新写入datelist字段，而其他字段内容更新为最新存档时间的页面内容。

采取上述两种索引策略的优势在于可以满足用户多样性的查询需求，以WARCRecordID为唯一标识符的索引可以提供存档URL每一次采集的完整信息，以存档页面URL为唯一标识符的索引可以将URL多次采集信息进行归并处理，能够清晰地展示每一个URL的全部采集情况，同时大大减少索引体量，提高检索速度，并且这两种索引可以相互支撑，相互补充。

# 5 WebArchive访问平台应用效果分析

中国科学院文献情报中心已基本开发完成面向重要科研机构的WebArchive访问平台，实现了WARC文件的模块化解析，构建了基于内容的全文索引系统。与常用的开源索引工具相比，该平台具有更完善的访问和检索功能，可以从多角度向用户展示存档资源，如表3所示。

表3不同访问平台的索引工具功能对比  

<html><body><table><tr><td>功能</td><td>Wayback</td><td>NuchtWAX</td><td>WERA</td><td>Web Archive平台</td></tr><tr><td>URL 检索</td><td>：</td><td>。</td><td>：</td><td>·</td></tr><tr><td>内容检索</td><td>0</td><td>·</td><td>：</td><td></td></tr><tr><td>学科分面</td><td></td><td></td><td>0</td><td>·</td></tr><tr><td>资源类型分面</td><td>。</td><td>。</td><td>。</td><td>·</td></tr><tr><td>时间分面</td><td>0</td><td></td><td></td><td>·</td></tr><tr><td>站点浏览</td><td>。</td><td>。</td><td>。</td><td>·</td></tr></table></body></html>

(注：·具备功能，缺少功能)

截至2016年1月，WebArchive平台采集存档数据总量达到了26TB(压缩包体量)，WARC文件数总计两万多个，索引体量超过了500GB；平台能够提供URL和全文检索，同时增加了学科分类、资源类型、存档时间等分面内容，实现了从多维度对WARC文件内容进行揭示。通过首页内容检索入口输入关键词可以进行内容检索，如图5所示。检索结果给出了采集的URL，对文档类型如HTML、PDF、DOC、PPT、TXT等提取了标题和内容，从检索结果中还可以看到每个URL的存档次数、所属的学科领域、所属站点名称以及最新存档时间等，同时还可以对检索结果按相关度和日期进行排序，如图6所示。

![](images/79e692d57d9d4d9f47505476e2236147ca31bb36964d5f9f8ec9912a5e975403.jpg)  
图5WebArchive 访问平台首页的检索入口及功能分区  
图6检索结果页面

学科6 当前选择： environmental   
综合 (1,985,562)   
生物与环境（1,020,616] 共检案到3,359,888章 排序： 租关室 日期 能源 (219,429)   
食品与健康（134,281） 1, http://www.sybioprojectorg/]   
标题： What is Synthetic Biology?   
在挡谢间 学科顿域：[综合] 站点名称：合成生物学项目   
存档时间 版本个数：7 最新存档时间：2015-5-5   
2015 (2,698,634) 网顶内容：organizations, nstitutions,journalists, and others disouss the emerging field of synthetic biology with a variety of audiences. Publications > Project news • 05/29/14 An Ecological Risk Research Agenda for Synthetic 2014 (661,254) BiologyEnvironmental scientists and synthetic biologists have for the first time developed a set of key research areas to study the potential ecological impacts of synthetic biology, Project news > Project news • 10/29/14 香源炭型 PLOS Looks at theImportance of Synthetic Biology CommunicationDavid Shirinofthe Publicibrary ofScience 资源美型 (PLOS) speals with David Rejesli about the importance of properly communicating synthetic biology concepts, Project news > Inventories Products & Applications InventoryThis inventory of synthetic biology-based . html (2,891,385) Q.归档列表模式 Q归当日历楼式   
pdf (399,104)   
doc (13,448) 2, http://www.synbioproject.org/news/[html   
xml (8,135) 标题: News - Synthetic Biology Project   
gif (7,894) 学科顿域：[综合] 适点名称：合成生物学项目   
ipg (5,402) 新本个数：7 最弱存作时间： 2015-5-5   
docx (4,506) 网顶内容：Biology CommunicationDavid Shifrin of the PublicLibrary ofScience (PLOS) speaks with David Rejeski ppt (4-22)72))   
bxt (1,442) problems by using an emerging technology caled"gene drives." Project news > Project news • 05/29/14 An css (1,045) Ecological Risk Research Agenda for Synthetic BiologyEnvirenmental scientists and synthetic biologists have for

# 6结语

面向国际重要科技机构网站开展的WebArchive系统建设中，利用开源软件Heritrix实现网络内容的大规模分布式采集，以WARC文件格式进行存储，不仅实现了科技网站资源的长期保存，也有利于存档资源的可持续发展。基于Heritrix提供的WARC文件I/O操作包，实现了WARC文件的分层读取；对读取的WARC内容，开展了不同类型网络资源的模块化解析;奠定了构建 Solr索引的基础，同时为进一步的数据挖掘、元数据抽取、数据分析服务等提供相应的接口。

基于Solr平台开发的WARC文件索引和访问系统，增加了学科分类、资源类型和存档时间等分面内容，实现了从多维度对WARC文件内容进行揭示。可以提供对存档资源的URL和全文检索，同时明显提高了WARC文件内容的检索效率。此外，该平台能够实时解析和索引生成的WARC文件，跟踪网络资源的动态变化，对于WebArchive的在线实时更新具有重要意义。

WebArchive资源是一个巨大的宝库，如何深度挖掘和发挥存档资源的价值，是未来面对的主要挑战之一，也是今后研究的方向，希望笔者的探索能够为网络保存领域的同仁提供有益的参考。

# 参考文献：

[1] IIPC Members [EB/OL].[2015-12-25].http://netpreserve.org/ about-us/members.   
[2] ISO 28500:2009 WARC File Format [EB/OL].[2009-05-15]. http://www.iso.org/iso/home/store/catalogue_ics/catalogue_d etail_ics.htm?csnumber=44717.   
[3] 曲云鹏．网络存档文件格式WARC研究[J].图书馆学研究, 2014(24): 20-25，28．(Qu Yunpeng. Research on the Standardized WARC File Format [J].Researches on Library Science,2014(24):20-25,28.)   
[4] 孙志茹，吴振新，曲云鹏．基于Wayback的索引策略研究 [J]．现代图书情报技术，2009(4):14-18.(Sun Zhiru，Wu Zhenxin,Qu Yunpeng.Analysis of Index Strategies in Web Archive[J].New Technology of Library and Information Service,2009(4):14-18.)   
[5] 吴振新，曲云鹏，李成文，等．基于开源软件搭建网络信 息资源采集与保存平台[J]．现代图书情报技术，2009(7-8): 6-10.(Wu Zhenxin，Qu Yunpeng，Li Chengwen，et al. Constructing a System for Harvesting and Preserving Chinese Web Information Resources Based on Open Source Software [J].New Technology of Library and Information Service, 2009(7-8): 6-10.)   
[6] WERA 0.4.2RC1 [EB/OL].[2006-01-17].http://archiveaccess.sourceforge.net/projects/wera/.   
[7] NutchWAX 0.11.0-SNAPSHOT API [EB/OL].[2007-02-20]. http://archive-access.sourceforge.net/projects/nutchwax/apido cs/overview-summary.html.   
[8] SOLR-Nutch Report [EB/OL]. [2011-01-31]. http://archive. org/\~aaron/iipc/solr-nutch-report.html.   
[9] SolrFeatures [EB/OL].[2016-01-25].http://lucene.apache. org/solr/features.html.   
[10]吴振新，张智雄，谢靖，等．基于IIPC 开源软件拓展构建 国际重要科研机构Web 存档系统[J].现代图书情报技术, 2015(4):1-9.(Wu Zhenxin,Zhang Zhixiong,Xie Jing,et al.

Developing Web Archive System of International Institutions Based on IPC Open Source Software [J].New Technology of Library and Information Service,2015(4):1-9.)

# 作者贡献声明：

胡吉颖：设计解析和索引方案，系统开发，论文撰写;  
吴振新：设计解析和索引方案，论文撰写及最终版本修订;  
谢靖：设计索引方案，系统开发;  
张智雄：完善索引方案设计。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

收稿日期:2016-02-25  
收修改稿日期:2016-03-22

# A Full-text Indexing System for WARC Files

Hu JiyingWu ZhenxinXie JingZhang Zhixiong (National Science Library, Chinese Academy of Sciences,Beijing 10o19o, China)

Abstract: [Objective]This paper developsa parsingand indexing system for the WARC files,which fully exploits the value of Web archives from scientific institutions.[Context]The WARC files have been widely used in digitalcuration. However,the existing ful-text indexing tools cannot satisfy the diversified needs ofthe WARC searchers.[Methods] We employed a modular scheme to parse the WARC files. Upon analyzing popular indexing tools,developed a new full-text indexing system based on the Solr platform. [Results] The new system effctively indexed the Web archives. Users could search information from diferent perspective,such as the subject category,resource type,and archived time,etc.[Conclusions]The newsystem indexes rich Webarchives from international institutions,and improves the efficiency of users' information retrieval activities.

Keywords: Web archive WARC fileModular parseSolr index