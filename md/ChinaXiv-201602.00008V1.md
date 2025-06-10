# Technology Analysis & Strategic Management

Publication details,including instructions for authors and   
subscription information:   
http://www.tandfonline.com/loi/ctas20

# Profiling science and innovation policy by object-based computing

Zhixiong Zhang²， Jianhua Liua，Yimin Zoub, Jing Xieä & Li Qian a National Science Library, Chinese Academy of Sciences, Beijing, China   
b College of Economics and Management, Zhejiang Normal University, Jinhua，Zhejiang 321004,China   
Published online:05 Feb 2014.

I cite this article: Zhixiong Zhang, Jianhua Liu, Yimin Zou, Jing Xie& Li Qian (2014) Profiling science and innovation policy by object-based computing, Technology Analysis & Strategic Management，26:5,581-593,DOI: 10.1080/09537325.2014.881992

!Xei

link to this article: http://dx.doi.0rg/10.1080/09537325.2014.881992

# EASE SCROLL DOWNFOR ARTICLE

Taylor & Francis makes every effort to ensure the accuracy of allthe information (the "Content") contained in the publications on our platform. However, Taylor & Francis, our agents, and our licensors make no representations or warranties whatsoever as to the accuracy, completeness, or suitability for any purpose of the Content. Any opinions and views expressed in this publication are the opinions and views of the authors, and are not the views of or endorsed by Taylor & Francis. The accuracy of the Content should not be relied upon and should be independently verified with primary sources of information. Taylor and Francis shall not be liable for any losses, actions,claims, proceedings, demands,costs, expenses, damages,and other liabilities whatsoever or howsoever caused arising directly or indirectly in connection with, in relation to or arisin out of the use of the Content.

This article may be used for research, teaching, and private study purposes. Any substantial or systematic reproduction, redistribution, reseling, loan, sub-licensing, systematic supply, or distribution in any form to anyone is expressly forbidden. Terms &

# Profiling science and innovation policy by object-based computing

Zhixiong Zhanga\*, Jianhua Liua, Yimin Zou $^ \mathrm { b }$ , Jing Xiea,Li Qiana

National Science Library,Chinese Academy ofSciences,Beijing,China; $b$ College of Economics and Management, Zhejiang Normal University,Jinhua,Zhejiang 32l004,China

Named entities,such as key initiatives,research programmes,scientific strategies and policies, are research objects or objects that are embedded in many web pages of science and innovation institutes.These objects provide important information that can be extracted intelligently from those pages.This paper brings forward an object-based computing method by using objects and their semantic information for profiling science and innovation policies.After extracting the objects and the relationships between them, we proposed an object grid to represent web pages. Objects were transferred into machine-readable knowledge units with rich semantic information.By using computational objects,we judged the intelligence value of web resources and classified policies into more detailed categories,such as strategic plan,research and development,and budget.To test the effectiveness of profiling science and innovation policies by using the object-based computing method,this paper conducted a research profiling experiment system.

Keywords:research profiling; science and innovation policy; research objects; object grid; object-based computing

# 1．Introduction

Research profiling (RP) is an analysis method based on bibliometrics and text extraction tools. These tools could be used to broadly scan the contextual literature information and depict the research context and research efforts wisely (Johanna et al. 2OO7; Porter, Kongthon and Lu 2002). RP tools help researchers easily identify related topics within the research domain, sketch out a ‘big picture' perspective on research activities,understand the research community,acquire insight on how innovation is progressing, and map (graphically represent) topical interrelationships of an entire research area.

Much work has been carried out on RP (e.g. Porter and Newman 2O11; Choi, Le and Sung 2011; Guo, Huang and Porter 201O; Johanna and Jan 20O7; Hicks and Atlanta 2004). The data they used for analysis were mainly from science,technology and innovation databases,such as Web of Science and Chinese Science Citation Database.Few researchers utilise web resources for RP or adopt RP tools, especially for web resources. Compared with high-quality formal databases, web resources are informal, unstructured, poor in semantic meaning,and occasionally unreliable and unstable.However, web resources stillhave the advantage in terms of size,timeliness,accessibility and diversity. With the help of semantic web mining technologies (Gerd, Andreas,and Bettina 2006),we could apply the profiling application into web resources. Sehgal (2OO7） proposed a profile-based approach to explore the social networks of US senators generated from web data. The social networks were then compared with networks generated from voting data. Despite these studies,no in-depth study on web content analysis is available.

The National Science Library (NSL) is an information analysis service provider of the Chinese Academy of Sciences (CAS). Learning timely science and innovation policies and providing research reports to policy makers are very important tasks for the library.Aside from the science, technology and innovation databases,some web pages released by key science and innovation related institutes,such as the Office of Science and Technology Policy of the White House,are also important resources. Several projects have been carried out in NSL to automatically or semiautomatically support the monitoring and profiling of the science and innovation policies released on the websites of those key institutes.In this paper, we focus on the web resources of some key institutes to implement science and innovation policy RP. We have then attempted to monitor and depict the development of science and innovation policies.

Based on science, technology and innovation databases, our project is similar to RP processes that require to deal with web page mining and content extraction,analysis and visualisation. Considering the great challenges to implement RP on web resources,the authors bring forward a new approach of object-based computing to facilitate the profiling of science and innovation policies based on web resources.The rest of this paper is structured as follows. Section 2 describes the main idea of object-based computing. Section 3 discusses some key issues of object-based computing for profiling. Section 4 shows some applications of the new approach. Section 5 concludes the paper and provides recommendations for future work.

# 2.Main ideas of object-based computing

To present the main ideas of object-based computing,the meaning of object should first be explained. The named entities embedded in the web page usually contain the core information of that web page. Such entities include scientific strategies,policies,key initiatives,research programmes and key research institutes.This content is valuable for the automatic mining of inteligence from web pages. For example, in a news article titled‘President Obama Lays out Strategy for American Innovation' (Obama 2Oo9), two important named entities, namely,‘President Obama' and ‘Strategy for American Innovation',are found.These two entities could present the main topics and value of the news directly.Thus, we consider these meaningful named entities as research objects or objects. Utilisation of these objects (meaningful named entities) and their inner relationships could further accomplish the computation for knowledge discovery.Therefore, an object-based computation method is used to identify the objects and the relationships between them from web pages to determine profiling science and innovation policies.Four main ideas are identified in this method:

· Web pages on science and innovation policies from the websites of key institutes,such as the Office of Science and Technology Policy and US National Science Foundation, should be crawled continuously to monitor the changes in science communities. The institutions should be chosen correctly in view of the authority and reliability of web resources obtained. The experts in the fields would be involved in the institute filter process.

· The crawled free texts should be transformed into time-stamped objects (when objects occur, that is,objects with temporal features) through information extraction.Important objects should be identified to support object-based computation.After related web pages are crawled from the targeted institutes’ website, we need to transfer the unstructured free texts into structured and machine-readable object collections. Given the dynamicness of web resources, we should add the temporal feature of objects when labelling the extracted objects. Take ‘July 13, 2010, White House Announces National HIV/AIDS Strategy' as an example. We turn this title into the following time-stamped triple: (object type,object value, time stamp) (Strategy, National HIV/AIDS Strategy, July 13, 201O);(Object A, Object B,Relationship Type, Time Stamp) (White House,National HIV/AIDS Strategy,Announces,July 13,2O1O).Furthermore,we should record other context information of the objects,such as source,syntax and position in the text.With the information of objects extracted from the text, we could construct an object grid to identify the important objects,which will be explained in detail in the following section.   
·A large-scale knowledge base based on time-stamped objects should be built to achieve semantic mining of the related topics.The large-scale knowledge base with time-stamped objects is important for object-based computation.In our method,allextracted objects and their semantic information are preserved in relation databases. These objects and their relationship representation model can be extended to content analysis tasks with a temporal dimension,such as burst topic detection (Kleinberg 2002).   
The status of science communities should be profiled by using information visualisation.Basing on enormous objects,we identify new science and innovation policies,assess the intelligence value of those policies to support Chinese scientific policy-makers,classify the policies into more detailed categories (such as formal scientific declaration, strategic plan, research and development, budget and organisation restructure),outline the hot topics in a period of time, depict current active activities and players in the institutes,and cluster the related policies of the institutes.

Given that web crawling and information visualisation are not the key issues of object-based computation,this paper specifically focuses on object identification and object-based computation.

# 3. Key issues

As mentioned above,object identification and object-based computation are the key issues of this paper. First, we discuss identification of important objects.

# 3.1.Identification of important objects

As shown in Section 2,the named entities embedded in web pages usually carry the core information of certain web pages.These named entities could present the main topics and value of the news directly. Extracting these entities from the unstructured web pages is important. An object grid transfers the objects embedded in the web into structured and machine-readable knowledge units.An object grid is a two-dimensional array that can capture the distribution of knowledge objects across text sentences.The rows of the grid correspond to the sentences in the text, whereas the columns correspond to the extracted knowledge objects from the text. For each object in the web page, the corresponding grid cell contains information about its grammatical role (S (Subject), O(Object), X (neither subject nor object) and gap, which signals the absence of the object in a given sentence.

The object grid is an extension of the popular entity grid representation for local coherence modelling proposed by Barzilay and Lapata (2OO8). The authors mainly extended the entity grid in three aspects to capture more information about the text. First, named entities and compound nouns are treated as head nouns in the entity grid. However, individual words cannot express a definite meaning and cannot describe the topic of the text explicitly.Thus,the object grid uses objects that are composed of terms and named entities instead of words. Second, named entities are divided into eleven classes (Person,Foundation, Project, etc.). These semantic entity types play important roles in distinguishing the category of the web resource.For example, news articles are likely to be about people and organisations.Third,the entity grid treats entities independently because it cannot capture the factor of lexical cohesion between entities.We address this problem by clustering entities semantically and by using the semantic chain to connect semantically related entities.

To construct the object grid, we need to deal with two things.First, we need to extract the objects and the relationships between them from text automatically.To extract the needed objects, we define a research ontology that organises various object types and relationships useful for the construction of the object grid.This ontology shows all types of named entities that we regarded as objects for object-based computation.The named entities mentioned in web pages are considered the object instances of certain types defined in the ontology.All object instances extracted from the text will be used for the object grid construction. Figure 1 shows part of the research ontology. To identify these objects and their relationships,we bring forward a series of methods,such as tokeniser and sentence splitter, after basic nature language processes.First, the simplest method of object extraction is the dictionary-based approach. We collect some special object instances and some indication words that will pay an important role in rule construction. Limited by the dictionary size,the method is not flexible in the extraction of new objects.By contrast, some construction rules are based on object instances, such as parts of speech, syntax and structure. We filter the complete syntax phrases from a sentence for further analysis and design a rule-based model.To construct a rule,we have used two other modules that refer to the indication word identification and lexicon-syntactic pattern learning.For the objects that do not match any fixed pattern, we analyse the context feature and compute the similarity between the sentence containing the object and the sample according to the assumption that concepts that are semantically related tend to be near in terms of context as to that of plain text (Athanasios and Vangelis 2Oo8; Zhang et al. 2009).

![](images/641d18f6814cbe55bc65463fea9e88a8c388cdcede14f7ad70f90af57c24c0ad.jpg)  
Figure 1. Structure of the research ontology.

Second, we should preserve as much information of the objects as possible and construct the object grid. Basing on the lexicalised models for statistical parsing proposed by Colins (1997), we could mark the role of each extracted object in the text. During the annotation, we handled the co-reference of objects on the basis of the research of $\mathrm { N g }$ and Cardie (2002). Subsequently, we constructed the object grid to represent the positional relation, syntactic relation and semantic relation among objects.Figures 2 and 3 show the example of object role annotation and object grid.

The method used in the current study in identifying the important objects in the web page is different from that used in other related research. In the present study, the important objects are divided into global objects and local objects,which are used to represent the topic and sub-topics of

1[NASA's Voyager1 spacecraft]s has entered a [new region]。between [our solar system]xand[interstellarspace]x.   
2[Data]sobtained from[Voyager]xover the last yearreveal this [newregion]sto beakind of[cosmicpurgatory]。   
3In[it] $x _ { 1 }$ [thewind of charged particles]sstreaming out from [our sun] has calmed,[oursolarsystem'smagneticfield]shaspiledup,and[higher-energy particles],from inside our [solar system]xappearto be leakingout into [interstellarspace]..   
4"[Voyager]stells usnow that we're in [a stagnation region]xin [the outermost layerof the bubble]xaround [our solar system]x，"said [Ed Stone]s，[Voyager project scientist] $x$ at[theCalifornia InstituteofTechnology]xin [Pasadena]x   
5"[Voyager]sis showing that what is outside is pushing back.We shouldn't have longto waitto find outwhat[the space] $x$ between[stars] $x$ isreallylike."   
6Although [Voyager $1 ] _ { 5 }$ isabout[11 billionmiles(18billionkilometers)]。from [thesun] $\therefore$ it isnot yet in [interstellar space]x.   
7In the latest data,[the direction of the magnetic field lines]shas not changed indicating[Voyager] $s$ isstill within [theheliosphere]。,[thebubble of charged particlesthesun]sblowsaround itself. NASA's Voyager 1 Spacecraf CalifomiaInstituteofTechnology Organazation Device Sun Person VoyagerProje typeOr   
A InterstellarSpace Cosmic Purgatory Stagnation Region typeor Location typeOr Solar Systecn Data MagnetietFied Bubble Ed Stone jectScientist Pasadena Star Heliosphere typeof 1 S 。 X X - 1   
2 X 0 . - S X 1   
3 # X X X = · S S #   
4 S = X - = = X X S X X X   
5 S = X 1 · · ： · = · 1 1 X   
6 S = X X 1 1 8 = #   
7 S S # S = 0

the text,respectively.A fundamental assumption underlying our approach is that the distribution of entities in texts exhibits certain regularities reflected in grid topology.This assumption is not arbitrary. Some of these regularities have been recognised in centering theory (Grosz, Joshi and Weinstein 1995) and other entity-based theories of text. The global objects based on their distributed grid patterns,such as object cluster, object coherence,object density and object span, were identified.The anchor text and the ‘meta' label of the web page are useful for this task. Given that the coherence is more visible inside the sub-topic than inside the topic,the text could be split into a number of semantic blocks by using this regularity.Therefore,local core objects could be identified based on their distributed patterns in each block.

# 3.2.Object-based computation

With the important objects identified, we could now implement computations, such as judging the intellgence value of web policy resources to support scientific policy-makers and categorising web pages into detailed classification.

To compute the value of web resources automatically, we should first understand the basic process of finding useful information implemented by human beings.Before the analysis, people usually retrieve many resources,including news.These resources are retrieved by using certain key words or by browsing certain parts of websites that have a close relationship with their topics. Humans willfilter and sort these resources according to the resource type,source, title and abstract. If they find some words closely related to their target task of titles or abstracts, which are defined as intelligent sensitive words in this paper, they will decide to read these resources in depth to find more useful information. These sensitive words may refer to special persons,organisations, programmes,terms and so on.All of these sensitive words and their featured information are included in our object.Basing on the above processes,we have determined that some features could be used for automatic computation.

·Authority of source.If one piece of news is released in an offcial website,then this resource is more reliable than other resources from non-offcial websites.   
· Content type of resource. If one resource is an extensive research report writen by experts or research groups, then this report includes more valuable information than the regular news.   
· Referred objects.If many important sensitive objects are mentioned in one resource, then this resource is considered more important than other resources.

However, most processes of judging the value of resources employ qualitative reasoning. To make our process more automatic and quantitative,we define five feature dimensions and propose corresponding computable indicators for important science and innovation policy resource identification. Table 1 shows the details of those five features and their corresponding indicators. Many indicators of these five features are related to important objects.Through the object grid and its featured information,such as semantic types and other atributions,the important objects identified will be used as items in vector computation. The weights of the feature vary and will be given by information experts.

The important objects are extracted to compute the indicators. Some computation methods are presented below.

# (1）Web authority

The authority of web resources wil be computed according to the five indicators in our method Formula(1) shows the computation method.

$$
\begin{array} { l } { A u t h o r i t y ( D ) = S c o r e ( s i t e ) + S c o r e ( s i t e T y p e ) + S c o r e ( d i r ) + S c o r e ( d i r T y p e ) } \\ { + S c o r e ( c o u n t r y ) } \end{array}
$$

Here, $D$ represents the web page for computation,and Authority $( D )$ refers to its authority value.Score(site) indicates the importance score of the website where the web page came from,and Score(dir) is the score of the website directory where the web page was obtained from. Score(siteType) and $S c o r e ( d i r T y p e )$ show the type of institute corresponding to the website and the directory type,respectively. The directory type is classified by the main resource type. Score(country) is the score of the location of the institute.All scores used here are semiautomatically given through the works of information experts.The scores could be changed in terms f task.

# (2) Object relevancy

We compute the objectrelevancy of one resource through four indicators, namely,object frequency $( F ( O ) )$ , object important score $( I S ( O ) )$ , object length $( L ( O ) )$ ,and length of the main web content $( L ( D ) )$ . Different object instances with different semantic types are added together. As shown in Formula (2), $D$ represents the web page for computation. Object Relevancy $( D )$ is the object relevancy of the web page. $F i ( O )$ is the frequency that one object instance $o$ occurs in the web page,and $L i ( O )$ is the length of this object instance.Even though the features are similar,different objects have different importance scores. Thus, $I S i ( O )$ indicates the importance level of object $o$ $L ( D )$ refers to the length of the main content of a web page.In this formula, $i$ is the number of important objects with different semantic types and values.

Table 1.Details of the five features and their corresponding indicators   

<html><body><table><tr><td>Feature dimension</td><td>Corresponding indicators</td><td>Descriptions</td></tr><tr><td>Web source authority</td><td>(Different country types have different levels of importance)</td><td>Country type of source organisation. Examples include strong scientific country, BRICSa,and developed country</td></tr><tr><td></td><td>Type of source organisation. (Different organisation types have</td><td>Examples include scientific management organisation,science foundation,research</td></tr><tr><td></td><td>different levels of importance) Importance of each organisation</td><td>institute,and news site Importance marks are given by intelligent</td></tr><tr><td></td><td>Type of source directory</td><td>analysers Examples include strategy,research report,</td></tr><tr><td></td><td>Importance of each directory</td><td>publication,news,and events Importance values are given by intelligent</td></tr><tr><td>Content type of</td><td>Type of file</td><td>analysers Refers to PDF,PPT,XLS,DOC,or HTML</td></tr><tr><td>resource</td><td>Length of the main web content</td><td></td></tr><tr><td></td><td>Ratio of main content and whole web</td><td>A higher ratio implies that the resource contains more information</td></tr><tr><td></td><td>Feature words about content type in the title and full text</td><td>Some feature words could reflect the type of resources,such as‘annual report, budget,</td></tr><tr><td></td><td>Type of source directory</td><td>and research report' Examples include strategy,research report, publication, highlight, news,press release,</td></tr><tr><td>Object (narrow)</td><td>Different objects and their importance</td><td>and events Objects here do not contain terms. Objects refertopeople,organisations,conferences, programs,strategies,and so on.The importance marks are given by intelligent</td></tr><tr><td>Science and innovation</td><td>Domain-related terms</td><td>analysers first.Afterward,thesemarks are computed through the object grid Corevocabularies of science and innovation. These terms could be used to compute the</td></tr><tr><td>related terms</td><td>Domain hot terms</td><td>domain relation of resource. Hot topic of science and innovation.Resource talking about the hot topic may attract users</td></tr><tr><td>Policy related terms Common words</td><td></td><td>These words are usually used with other types</td></tr><tr><td></td><td>Scientific words</td><td>of terms or objects</td></tr></table></body></html>

aBRICS is the acronym foranassciationoffive major emerging national economies:Brazil,Rusia,India,China and South Africa.

$$
{ \mathrm { O b j e c t ~ R e l e v a n c y ~ } } ( D ) = \sum _ { i = 1 } ^ { n } F i ( O ) * L i ( O ) * I S i ( O ) / L ( D ) .
$$

Similar to object relevancy,science and innovation relevancy and policy relevancy can be computed through the corresponding types of the extracted word. To simplify computation, each indicator is computed separately and the results are normalised to the [O-1] zone.

We defined some rules, which contain several indicators from the same or diferent dimensions, with the help of information experts.These rules are separated into two groups, namely,important rules and unimportant rules.All rules and examples are related to the practical tasks of the inteligence analysis of NSL.For example,we ofer more attention to the large scientific and technological powers to monitor the trend of scientific and technological policies.Therefore, the USA is more important than Nepal in this task. However, this preference varies with the task.

Important: Important person $^ +$ sci/tech innovation terms (e.g.Barack Obama $+$ Sci&Tech|Innovation) importantsource $^ +$ important country $+$ Sci&TechlInnovation terms(e.g.OECD+ United States $+$ Sci&Tech|Innovation) Unimportant: important person $^ +$ simple event news (e.g. Barack Obama $^ +$ visiting .. ）unimportant country $+$ Sci&Techl Innovation terms (e.g.Nepal $+$ Sci&Tech|Innovation)

Basing on the computed scores for each indicator and rule,we judge the value of science and innovation policy resources both quantitatively and qualitatively. If one web page acquires high scores in all the five features,then that web page will be very significant for the science and innovation policies.The computed intelligence value of a web page corresponds to the quantity of referred objects involved with the important or unimportant rules.

In addition to intelligence value judgment, we also employed important objects to conduct further resource classification, monitor conferences and research communities in a certain period of time,and so on. Basing on the important objects and their semantic type of information, we organise the web pages of the same objects into the same semantic type.We could further combine object frequency, position of objects in a document and document frequency on the basis of the extracted objects and their time feature.This combination requires a certain period of time to find the hot objects. More details on the computation processes are reported in another paper by Zhang et al. (2011).

# 4．Application

The authors implemented an RP system that monitors the websites of 86 science and innovation authority organisations,such as Ofce of Science and Technology Policy and Research Councils UK. The effectiveness of profiling the science and innovation policies of those institutes via the object-based computing method was demonstrated.All these organisations were chosen by science and innovation policy information experts.In this application,11 information experts were involved.They are members of the scientific policy and strategy team of NSL in CAS.They chose 86 important organisations where they obtained resources for further inteligence analysis. Moreover,they provided the basic important objects with certain weight scores and rules that they have been recently concerned with most. With the help of the experts, we crawled related web resources in narrow scopes,constructed a basic gazetteer for object extraction and implemented qualitative judgment rules.

Using this system，we provided the newest important science and innovation policy web resources,automatically classified these resources,furnished important topics and objects in the most recent month,and kept track of the certain topics and objects within target organisations.

homePage browse institute Profile mySpace homePage>detail of resource Recommended resources Candidate resourcesModify Extract Standard Title:ASTRATEGYFORAMERICANINNOVATION-SeCuring OurEconomicGrowthandProsperity [original link cached] publish Time:2011-2-4 fromInstitute:Offce of Science and Technology Polcy|The White House fromDirectory:blog total resource in this directory(119) content Type:science strategy resource Type:PDF(1.25M)[download] importance： important Terms:EconomicGrowth,advancedmanufacturing,business innovation,quantumleap,breakthrough space importantObjects:SmallBusinessAssociationNationalScienceFoundationPresidentBarackObama,iomassCrop Assistance Program,RecoveryAct Broadband Awards Abstract: Translation ASTRATEGYFOR AMER ICANINNOVAT ION Securing Our Economic Growthand Prosperity NationalEconomicCouncil,CouncilofEconomicAdvisers,and OficeofScienceand Technology PolicyFEBRUARY2011TableofContents Executive Summary1New Initiatives.. /PolicyMonitor/search/search.htm?searchType=object&value=Global..

HomePage >Office of Science and Technology Policy1 The White House fulltext currentresourcedatefrom to search total resources339 items)sort:publishtime importancereadings List Mode Image Mode 1AClearer Vision for American Innovationand Jobs 2011-09-08 Office of Science and Technology Policy | The White House   
important object important subject keyTerms:costlylitigation,tomorrowmorning,miniaturevideocamera,patentreform bill,dramatic technological contrast   
conference foundation person project institute university researchLab key Objects:Quentin Palfrey Ahatrart HML65.kCached|related resource]（5readings） RickWeiss 14 RAMERICANINNOVATION-Securing Our Economic Growthand TomKalil 12 1-02-04OficeofScienceandTechnologyPolicy|TheWhiteHouse 0 1omicGrowth,advancedmanufacturing.business innovation. ace.quantum leap   
JohnP. Holdren onalScienceFoundation,President BarackObama,BiomassCrop ram,Small Business Association,Longitude Prize.TradeAdjustment   
Aneesh Chopra munity.CarnegieMellon University,BellLabs,Department of Energy Cached|related resource][（25readings)   
PresidentBaraok velopment through Science,Technology,and Innovation 2011-7 2011-9 2011-11 2012-1 2012-3 2012-5 ceof Science and Technology Policy|The White House D 20 40 2011-8 2011-10 2011-12 2012-2 2012-4 2012-6iate Change,food security,long-standingdevelopment,global affaccess frequency PresidentBarack Obama keyObjects:National Science Foundation,President Barack Obama

According to the testing token by some intelligence experts,the method presents good performance.Figure 4 shows the RP result of one important web resource identified in our system. This web resource profiles its intelligence value,which is marked by stars,content type classification, key terms,key objects,related resources with same objects,and so on. Figure 5 shows the key terms and objects of the Office of Science and Technology Policy of the White House.Moreover,this figure presents the development trend of one object in different periods of time.More information could be obtained on the following URL: http://policyMonitor.las.ac.cn.

Table 2.Check result of recall and precision   

<html><body><table><tr><td>Test amount of resource</td><td>Recall (%)</td><td>Precision (%)</td></tr><tr><td>100</td><td>65</td><td>27</td></tr><tr><td>300</td><td>89</td><td>50.2</td></tr></table></body></html>

We invited some science and innovation policy intelligence experts to check the effectiveness of our object-based computing method. They assessed the precision and recall of the important resources for the science and innovation policy identified by our method.Precision refers to the ratio of the amount of important stars marked by our system and was identified by intelligence experts from the total test resource.Recall refers to the ratio of the amount of important resources identified by intelligence experts from the total test resource.We selected the top 1OO important resources published from June 6,2011,to June 16,2011,and the top 300 important resources published from1 July 2011 to 30 July 2011.The result is shown in Table 2.

The test result shows that our method could determine the most important resources for information experts.However, the performance of the exact importance level of each resource is not satisfactory. Moreover, more test resource situations show beter performance in recall and precision.

# 5.Conclusions and future recommendations

This paper puts forward the object-based computation method for profiling science and innovation policies.According to our practice, the object-based computation method performed satisfactorily in identifying important resources.

Although we carried out some successful applications and received good evaluation results, much work needs to be done to widely apply our method in the future.Based on the test results, we will improve the method to determine a reasonable weight setting for each feature and adjust the algorithm for identifying the quality of important objects. Furthermore, we willdetermine a method of combining rules automatically on the basis of the existing important resources. All of these factors will affect the final mark and the amount of stars,which shows the importance level of the resources.

# Acknowledgements

This paper is supported bytheproject itled‘ScientificDevelopmentTrend Detection System',funded bythe Chinese Academyof Sciences (2Oo9-2Ol1)and ‘Thecomputing methodof subjectcentralityof texts basedonlanguage network' supported by National Natural Science Foundation of China (Grant No. 61O75047).

# Notes oncontributors

ZhixiongZhangisaprofessorand theAsistantDirectorof National ScienceLibraryatthe ChineseAcademyofSciences. He is also the Director of Information Systems,Library Department.He haspublished over 9O papers in journals, conferences and workshops.His currnt interest areas include information extraction,web mining,research profling scientometrics,semantic web,and digital preservation.

Jianhua Liu isaPhDcandidateof the National ScienceLibrary,Chinese Academyof Sciences.She specialises in text mining and scientometrics.   
Yimin Zou is alectureratthe CollegeofEconomics and Management,Zhejiang Normal University.He specialise in text mining and semantic web.

JingXieisalibrarianof theNational Science Library,Chinese Academyof Sciences.Hespecialises indistributed computing and semantic index.

Li Qian is aPhDcandidateof the National Science Library,Chinese Academyof Sciences.He specialises in text mining and informationvisualisation.

# References

Barzilay,R.and M.Lapata.2oo8.Modeling local coherence:anentity-basedapproach.ComputationalLinguistics 34, no. 1: 1-34.   
Choi,D.G.,H.Le,andT.Sung.20l1.Research profiling for‘standardizationand innovation'.Scientometrics 8,no.1: 259-278.   
Colins,M.1997.Three generative,lexicalised models forstatistical parsing.InProceedings ofthe ACL/EACL,Madrid, Spain,July 1997,16-23. Stroudsburg,PA: The Association for Computational Linguistics.   
Gerd,S.,H.Andreas,andB.Betina.2Oo6.Semantic web mining:stateof theartand future directions.Web Semantics: Science,Services and Agents on theWorld Wide Web 4,no.2:124-143.   
Grosz,B.J.,A.K.Joshi,and S.Weinstein.1995.Centering:Aframework formodeling thelocal coherenceof discourse. Computational Linguistics 21,no.2:203-225.   
Guo Y.,L.Huang,andA.L.Porter.2Olo.The research profiling methodapplied tonano-enhanced,thin-flmsolarcells. R&D Management 40, no.2:195-208.   
Hicks,D.,and G.Atlanta.2004. Global research competition affcts USoutput.School of Public Policy.Atlanta,GA: Georgia Institute of Technology.   
Johanna,B.and S.Jan.2Oo7.Profilingacademic research ondigital games using text extraction tools.In Proceedings ofthe Digital Games ResearchAssociation (DiGRA)Conference,24-28September 2007,Tokyo,Japan,ed.Akira Baba,714-729.Tokyo:DiGRA.   
Johanna,B.,R.Sami,S.Anne,andM.Petri.2Oo7.Enrichingliterature reviews withcomputer-asistedresearchextraction. Case: profling group support systems research.Paper presented at the proceedings of the 4Oth annual Hawaii International Conference on System Sciences,February 2Oo7,Hawaii.   
Kleinberg,Jon.2Oo2.Burstyand hierarchical structure in streams.Paper presented at the proceedings of theeighth ACM SIGKDD International Conference on Knowledge Discovery And Data Mining $( \mathrm { K D D } ^ { \prime } 0 2 ) ,$ ,Edmonton,AB, Canada.   
Lapata,Mirella and Regina Barzilay.2Oo5.Automatic evaluationof text coherence:models and representations. Paper presented at the proceedings of the19th International Joint Conference on Artificial Inteligence, Edinburgh.   
Ng,V.and C. Cardie. 2Oo2.Improving machine learning approaches to coreference resolution. Paper presented at the proceedings of the ACL, July,Philadelphia.   
Porter,A.L.and Nils C.Newman.2011.Mining external R&D.Technovation 31,no.4: 171-176.   
Porter,A.L.,A.Kongthon and J.C.Lu.2OO2. Research profling: Improving the literature review.Scientometrics 53,no. 3: 351-370.   
President Obama.2O09.President Obama lays out strategy for American innovation.htp://www.whitehouse.gov/the press_ofice/president-obama-lays-out-strategy-for-american-innovation.   
Sehgal,Aditya Kumar.2Oo7.Profiling topics on the web for knowledge discovery.PhDdiss.,Universityof Iowa.   
Staff Writers.2011. Voyager hits new region at solar system edge. Space Daily.htp://www.space-travel.com/ reports/Voyager_Hits_New_Region_at_Solar_System_Edge_999.html (accessed November 12,2012).   
Tegos,A., V. Karkaletsis,and A.Potamianos.2008.Learning of semantic relations between ontology concepts using statisticaltechniques.InProceedingsoftheworkshopon High-Level Information Extraction(HLIE2O08)atECMLPKDD 2008,Antwerp,Belgium,19 September 2008.htp://www-ai.cs.tu-dortmund.de/HLIE08/slides/03-tegosHLIE_08_Tegos.pdf.   
Zhang,Zhi-Xiong,JianXu,Jian-huaLiu,QiZhaoNaHong,Si-huWu,andDai-qingYang.2oo9.Extractionknowledge objects in scientific web resource for research profiling.Proceeding of 2OO9 International Conference on Machine Learning and Cybernetics (ICMLC),July 12-15,Baoding.   
Zhang,Zhixiong,NaHong,Ying Ding,Jian-hua Liu,Jian Xu,and Dai-ling Yang.2O11.Research profing basedon semantic web mining.Paper presented at the International Council for Scientific and Technical Information Annual Conference (ICSTI 2011), Beijing.