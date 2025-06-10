# Small Private Online Judge: A New Tool for Empirical Education Research

ZHU Yun-chi School of Biological Sciences & Medical Engineering Southeast University Nanjing, China 213170096@seu.edu.cn

ZHAO Zuo-han School of Biological Sciences & Medical Engineering Southeast University Nanjing, China 213170440@seu.edu.cn

Abstract—Thispaperputs forward the concept of SmallPrivate Online Judge (SPOJ).Compared with Massive Open Online Judge(MOOJ)， SPOJ has advantagesin structured data acquisition of students' virtual behavior for its specific function and tight coupling with the classroom.SPOJ-based empirical education research can be conducted within"AcquisitionAnalysis-Application" (3A） Framework.The case study of a SPOJ program clarifies the standard pattern of SPOJ-based 3A research and highlights the emergence of education-intelligence concept. The challenges of SPOJ-based empirical education research and implications of SPOJare also discussed.

Keywords-Small Private Online Judge (SPOJ)；Empirical EducationResearch;Virtual Behavior;3AFramework;Education Intelligence

# I. BACKGROUND

Online Judge (OJ） is a tool of task arrangement and learning-status-checking effective in today's programming competitions and courses.Through black-box testing on the cloud,it can make immediate judgments about the codes submitted by users and give corresponding scores and rankings, hence it has been applicated in programming education and algorithm competitions for a long time [1].

OJ is not only a high-performance evaluation service platform,but also a valuable educational data acquisition tool [2]. The development of Internet technology has led to the rise of online learning and relevant educational data mining. Compared with those in traditional classrooms, students' various online learning behaviors are virtualized and structured, consequently easier to be acquired in a high-throughput way. Under such background,we propose the role of small private online judge（SPOJ) in empirical education research related to programming courses.

TONG Cheng-da School of Biological Sciences & Medical Engineering Southeast University Nanjing, China 213170761@seu.edu.cn

XIA Xiao-jun School of Biological Sciences & Medical Engineering Southeast University Nanjing, China xxj.rcls@seu.edu.cn

II. BASIC CONCEPTS OF SPOJ

# A．Classification:MOOJ and SPOJ

Similar to Online Course, OJ can be classified into massive open online judge (MOOJ) and small private online judge (SPOJ) according to their different attributes (Table I).

TABLEI. TABLE TYPE STYLES   

<html><body><table><tr><td></td><td>MOOJ</td><td>SPOJ</td></tr><tr><td>Accessibility</td><td>Public</td><td>Private</td></tr><tr><td>Administrator</td><td>University/Business</td><td>Teacher</td></tr><tr><td>Orientation</td><td>Algorithm competition</td><td>Programming course</td></tr><tr><td>Knowledge coverage</td><td>Board</td><td>Specific</td></tr><tr><td>Target user</td><td>Self-learner</td><td>Student</td></tr><tr><td>User& problem scale</td><td>Large & Growing</td><td>Small& Stable</td></tr><tr><td>Scoring rule [3]</td><td>ACM/OI</td><td>ACM</td></tr></table></body></html>

Just like SPOC derives from the booming MOOC,SPOJ emerges with the development and improvement of MOOJ. The launch of the early competition-oriented MOOJs such as UVa,POJ and Codeforces laid the foundation for the development framework and service pattern of OJ system. Jointed by the growing application of recent high-quality opensource projects，such as HUSTOJ and QDUOJ,the present technology allowsSPOJsto be quickly deployed and applicated to programming teaching.

Different from the MOOJs listed above,SPOJs are“Small" and “Private"，for they are course-oriented OJs built by teachers aiming to provide more efficient programming task assessment for their specific classes. SPOJs are usually deployed in the campus network which cannot be accessed publicly, thus they exist in a numerous-unknown status.

# B. The data-acquisition of SPOJ

The database structure of most OJs includes the following four main parts (Figure 1):

![](images/6a6b0fa5994f9ed7ee36b9f87662151374872ef095a622d14fa79b0a715b2aa1.jpg)  
Figure1．OJData Association View.

i)LOG:Log data is the most important data in OJ's database.It reflects all the behavior of a user at a certain time on OJ,and is stored in a table named "Solution " or“Status". The basic structure of log data is illustrated in Table II:

TABLE II. BASIC STRUCTURE OFLOG TABLE   

<html><body><table><tr><td>Name</td><td>Description</td><td>Sample</td></tr><tr><td>ID</td><td>Auto increment</td><td>1</td></tr><tr><td>ProblemID</td><td rowspan="3"></td><td>1</td></tr><tr><td>TestID</td><td>1</td></tr><tr><td>UserID</td><td>D-4282</td></tr><tr><td>InTime</td><td>User's submission time,usually accurate to the second</td><td>2020-02-03 09:00:00</td></tr><tr><td>Language</td><td>1</td><td>C++</td></tr><tr><td>Result</td><td>Based on the scoring rules</td><td>True</td></tr><tr><td>Time</td><td rowspan="4">Details</td><td>10ms</td></tr><tr><td>Memory</td><td>1M</td></tr><tr><td>CodeLength</td><td>428</td></tr><tr><td>Code</td><td>#include<iostream>…</td></tr><tr><td>IP</td><td>User's IP when submitting</td><td>47.98.171.106</td></tr><tr><td>…</td><td colspan="2"></td></tr></table></body></html>

Compared with other online systems,OJ is more functionspecific in that users only submit code and view results there while specific programming operations are done locally. Although unable to capture the detailed programming behavior, OJ's log runs as an efficient programming snapshot system recording a user's continuous submission towards a problem until it is passed or abandoned. In addition, it provides teachers access to students'usage habits from the log，such as their usage time, places of study\*, etc.

ii) PROBLEM: The problem data mainly includes ID, title, description,sample input,sample output,etc.Each problem requires at least one set of test data which is not usually written to the database yet.

The quantity of SPOJ's problems, compared with that of MOOJ,is much smaller and relevantly stable,and tends to be adjusted more frequently due to teaching reform.

iii) TEST:Test refers to the set of time-limited problems released by teacher on SPOJs in the form of exams or assignments for students.The test data includes ID,start and end time, etc.

Different from the public problem list of MOOJ, problems on SPOJ are usually posted in tests.To some extents, problems released from teachers are SPOJ's input signals while logs generated by students' virtual behavior are its output signals,so teachers tend to utilize tests to keep all signals in order and bounded.

iv）USER:The user data usually includes only the most basic information such as ID and user name when students detailed information has been registered on the campus authentication platform.

Whilesharingsimilardatabasestructureand task schedulingmechanism withMOOJ, SPOJ hasmany advantages over it in data acquisition.Firstly, SPOJ's deployer and administrator have a closer relationship (often even the same person),thus richer types of data can be exported directly from the database instead of using web crawlers or API. Secondly, SPOJ is closely integrated with classroom-teaching where teachers' assignment release and student task completion are periodic,contributing to more regular data generation. Finally,the scale of SPOJ users is small and stable,and user behavior is much easier to control, which improves the security of SPOJ and reduces the dificulty of data cleaning.

SPOJ researchers concentrate on log data rather than problem data. For one thing， due to users’ elementary programming skill and syllabus regulations for limited sphere ofknowledgepoints, thedegreeofdifficultyand discrimination of course-oriented OJ problems is lower and more uniformly-distributed than competition-oriented problems Therefore,there islessneed for SPOJ researchersto focuson problem data to build applications such as learning topic and difficulty level recommendation system [4]. For another, SPOJ researchersusually have a closerrelationship withits administrator as well as users, so they may pay more attention to students'virtual behavior pattern to be mined from log data.

# C.3AFramework Based on SPOJ

SPOJ-based empirical education research fits the research framework of "Acquisition-Analysis-Application" (3A）[5] illustrated in Figure 2. SPOJ is the infrastructure supporting these researches where the raw data is generated and stored. Researchers can acquire smaller-scale structured data directly from the database and use relatively few computing resources for analysis.

Different from those under traditional “hypothesis-testing" research framework [6],empirical education researches under 3A Framework aim to mine patterns from the unknown so as to develop applications to solve practical problems.Within 3A Framework,the research can lead to both pedagogical and technological improvement. The pedagogical application may include student virtual behavior norm,early-warning model fused OJ data with exam scores,and various educationintellgence reports,while the technological application may be SPOJ'smanagementoptimization, classroom-teaching improvement,etc.A complete 3A research is equivalent to the construction of an ETL pipeline connecting SPOJ with the applications from this perspective.

![](images/f7e9fcba8d704f8f2fd1a4267707801be2024d2f7162c30e3e7f9fc369e4c023.jpg)  
Figure2.3AFramework Based on SPOJ.

# III. CASE STUDY

# A．Introduction

In 2017, the course leader deployed HUSTOJ on Alibaba Cloud (http://oj.bmeonline.cn) for release and inspection of programming assignments.Every assignment was released in the form of a test of 4 to 8 problems with a deadline of 1-2 weeks.User registration was done by the students themselves, and they were allowed to complete the tests off-class or during on-machine classes scheduled by the school.76 problems were released on the OJ via 11 tests during 3 months,and 10,491 logs were generated from 96 students [7].

In 2018, the teacher still allowed students to register and complete autonomously. The 2O17 tests were reused,only with the start date reset to keep pace with teaching progress. What's more,no deadline was reset. This semester,only 8493 valid logs were generated on the OJ from the lO4 recruited students, a year-on-year decrease of $1 9 \%$ [8].

In 2019，SEU adopted large-categories enrollment and small-class teaching. The original OJ was replaced with QDUOJ (http://www.bmeonline.cn/oj) deployed in the campus LAN,and the user-scale was reduced to 26 students from the electronic-information category. OJ's registration was changed to unified certification while the supervision of on-machine classes became much stricter.This semester,12 tests with 68 problems were posted on the OJ, generating 2609 logs [9].

# B.Acquisition and Analysis

The school's teaching researcher,a data engineer rather than a learning scientist, began exporting and analyzing data from the SPOJ's database at the end of 2018.

Fordimensionality reduction， most of the irrelevant variables were removed, including the $\mathrm { T I M E } ( t )$ andMEMORY $( m )$ ，which have been the criteria for judging algorithm competition problems for a long time.These variables either lacked statistical significance(Table III, taking t and $m$ as examples),or had nothing to do with empirical education research.

TABLE III. RESULTS OF Z-TEST   

<html><body><table><tr><td>Year</td><td>Variable</td><td>H</td><td>μ0</td><td>Pvalue</td><td>Result</td></tr><tr><td rowspan="2">2017</td><td>t</td><td rowspan="4">μ=μo</td><td>22.89</td><td>0.6936</td><td rowspan="4">Accept Ho</td></tr><tr><td>m</td><td>2032</td><td>0.9712</td></tr><tr><td rowspan="2">2018</td><td>t</td><td>22.89</td><td>0.6741</td></tr><tr><td>m</td><td>2032</td><td>0.9692</td></tr></table></body></html>

For sample size reduction, when searching for logs unrelated to studentsin $2 0 1 8 ^ { \circ } \mathrm { s }$ data,a large number of subsidiary accounts (alt) were found.It pushed the researcher to spend much time combining accounts or deleting relevant records directly,causing samples lost beyond prediction.No other abnormal user behavior was found during data cleaning.

![](images/d181ececeda988cfb1e1d225286c433b0ca326cad15e12d0b590844ed8de44c8.jpg)  
Figure 3．Participation Curve.

The 2017-2018 students' involvement with OJ problems reveals the number of participants declined exponentially over time (Figure 3 A and B). The gradually increasing difficulty of OJ problems along with classroom-teaching progress may accountfortheparticipantsdecreaseandintra-test discrimination increase.However, the decline in 2O18 appears to be too large.

The attempt to establish a correlation between students' completion of OJ problems and final course grades does not lead to positive result. The researcher defined the $A C$ index according to the ACM judging rule [2],and calculated the Pearson Correlation Coefficient between each student's $A C$ and their exam scores (MSC&WSC).All results only meet the criteria for moderate correlation (Table IV).Such moderate correlation may be caused by the difference between the capability to be examined and the capability to be trained, for students trained their practical programming skills on the OJ while the final exam focused on theoretical knowledge.

TABLEIV. CORRELATIONCOEFFICIENTBETWEENACANDGRADES   

<html><body><table><tr><td>Year</td><td>P AC.MSC</td><td>P AC.WSC</td></tr><tr><td>2017</td><td>0.7131</td><td>0.6074</td></tr><tr><td>2018</td><td>0.5440</td><td>0.7265</td></tr><tr><td>2019</td><td>0.6697</td><td>0.6922</td></tr></table></body></html>

The prominent high AC&MSC correlation in 2017 may be caused by a rare set of students in this school who already have a solid programming foundation before entering university. Their role as teaching assistants during on-machine classes actually multiplied the teaching resources to programming practice of 2O17 course,which consequently increase the $M S C$ and $A C$ correlation to some extents.

Except for 2017, the correlation between $A C$ and MSC is not even as good as WSC,particularly significant in 2O18.The survey of the students shows majority of them have received 12 years of exam-oriented education and tend to have formed typical learning habit, and the assumption goes that the grasp of theoretical knowledge be more correlated to learning habit than practical skill.Therefore, the representation method of students' learning habits reflected in their virtual behavior on OJ is furtherobserved.

![](images/efe2bab940334352d3775ee24b558ea0d8cc4085a980e5c531951a74d7d12df9.jpg)  
Figure 4. Submit Line Model.

Several models were established,among which Submit Line (Figure 4, samples from two students in 2017)[2] tends to be more interpretative.It is determined with linear regression model fittingcorrected cumulativesubmissionsagainst logarithmic date series of a student. This model can reflect both a student's effort in each test $\cdot \kappa _ { b }$ ，slopeofSubmitLine) and his or her time arrangement habits for completing them( $\dot { S } t _ { b } , \mathrm { R } ^ { 2 }$ of the fit).The submit-lines in Figure 4 demonstrates that Student 2 is more devoted in OJ problems along with more timely completion than Student1， which matches their daily submission curves below.

# C. Application

Findings from above analysis are applied to two types of practice:

i) Strengthening management of OJ: Contrast between data from last two years made the course leader realized the necessity for stricter management, hence he took measures as mentioned in introduction (III.A).Asa result, the downward trendof Participation Curveof 2O19 (Figure $3 \textrm { C }$ ）becomes much gentler than that of 2O18,not as gentle as that of 2O17 yet

ii） Building education-intelligence (EI) system: In the analysis process，inspired by theconcept of business intelligence[1O]，theresearcherproposed"education intelligence",which means utilizing advanced data technology to build ETL pipelines within schools in a gesture to promote the 3A-cycle-flow of education data, the rationalityof educational decision-making， and theimprovementin education effectiveness.Guided by this concept, the researcher "employed" one of the three "teaching assistants" (II.B） to transform his analysis methods into software assisting the cleaning,visualization and analysis of OJ data. The software has been developed since the summer of 2O19 and now is opensource under the MIT license [11], representing the completion of the first OJ data ETL pipeline aiding programming teaching.

# $D$ Disccusion

The empirical education research within 3A Framework reported above has exerted a positive effect on programming teaching practice.It also revealed challenges in SPOJ-based education research:

i)Special behavior influence:SPOJ's user relationship is usually very close,for they are students learning in the same classroom and even living in the same apartment. Therefore, special behavior of individual users may have a significant impact on the user group whether positive or negative. While strong measures must be taken to eliminate the effects of negative behavior, positive behavior contributing to a virtuous circle in SPOJ user ecology is more worthy of attention, recording and researching.

ii)Black-box attribute: There is sort of "deception" in any virtual behavior. A student with a good programming foundation may not take the basic problems seriously while another student who always completes assignments in a timely and efficient manner may be a cheater actually.More data is required to accurately represent such behavior,among which source code data from SPOJ has great potential due to developmentofagainst-cheatingsystems.Teachers' understanding of student information and behavior-based cluster analysis also help capture such “deceptive”behavior.

iii)Internalization effect: The requirement forstrict management of SPOJ makes it inaccessible to the public and restricted in user scale.This guarantees the operating efficiency and data quality of SPOJ, but isnot conduciveto communication between peer teachers as well as the expansion of education-intelligence.A solution for this dilemma is to establish a public database and open SPOJ data in accordance with a recognized OJ data standard.At present, Xia et al in SEU has begun to explore in this field [12].

iv） Theoretical basis:Application-oriented as it is,SPOJbased education research still demands theoretical support from learning science， which may explain the more complex cognitive mechanisms and emotional activities behind virtual behaviors on SPOJ, making up for the "dead zone" cause by its black-box attribute from another perspective.

# IV. IMPLICATIONS

SPOJ is the combination of technology innovation and course improvement.It can be defined as“OJ + Classroom", while its implication is far beyond the classroom.First,the education-data-miners on SPOJ may do class-useful empirical education research under the guidance of 3A Framework,and take appropriate measures to share their findings and expand education-intelligence.Second, course teachers or leader can utilize other technologies such as SPOC and "Rain Classroom" to enrich classroom teaching while providing more data for teaching researchers. Last but not least, in nowadays information age, disciplines relevant to learning science should attach more importance to student virtual behavior on online platforms such as SPOJ,in a gesture to provide theoretical justification for the analysis and application of education data.

# REFERENCES

[1]Wasik S,Antczak M,Badura J,Laskowski A, Sternal T.A Survey on O nline Judge Systems and Their Applications[J]. ACM Computing Survey s. 2018;51(1):31-34.doi:10.1145/3143560.

[2] ZHU Yun-chi, ZHAO Zuo-han, TONG Cheng-da,XIA Xiao-jun. Online Judge Based Programming-practice Data Mining[J].Journal ofElectrica 1& Electronic Education.2020,42(1): $9 4 - 9 8 \substack { + 1 4 1 }$ ：   
[3] Li Yang.Documents[EB/OL].https://docs.onlinejudge.me/#/onlinejudge /guide/contest_rule_type,2019-09-22.   
[4] Wayne Xin Zhao,Wenhui Zhang,YulanHe,XingXie,and Ji-RongWe n.2017.Automatically Learning Topics and Difficulty Levels of Proble ms in Online Judge Systems.ACMTrans.Inf. Syst.36,3,Article 27 (M arch 2018),33 pages. doi:10.1145/3158670   
[5] ZHU Yun-chi, ZHAO Zuo-han,TONG Cheng-da,XIA Xiao-jun.A Rev iewofMultimodal Education Evaluation Research under the 3AFramew ork[J]. Journal of Bio-education: To be published   
[6] Dr Robyn Smyth.Introduction to research methods in education-By Ke ithFPunch[J].British Journal of Educational Technology,2Oo9,Vol.40 (6):1149-1150   
[7] ZHU Yun-chi.Releases NEDB/oj-001[EB/OL].http://share.bmeonline.c n/nedb/oj-001/releases,2020-01-30.   
[8] ZHU Yun-chi.Releases NEDB/oj-003[EB/OL].http://share.bmeonline.c n/nedb/oj-003/releases,2020-01-30.   
[9] ZHU Yun-chi.Releases NEDB/oj-0o5[EB/OL].http://share.bmeonline.c n/nedb/oj-005/releases,2020-01-30.   
[10]D.J.Power.A Brief History of Decision Support Systems[EB/OL]. http: //dssresources.com/history/dsshistory.html,20o7-03-10.   
[11]TONG Cheng-da,ZHU Yun-chi.(2020). SPOJ Analyzer (Version 1.0.0. 0)[Software].http://share.bmeonline.cn/admin-and-development/spoj-an alyzer/releases   
[12]ZHU Yun-chi,XIA Xiao-jun.Release of Virtual Behavior Metadata - O nline Judge [EB/OL].http://www.bmeonline.cn/2020/02/04/%e4%b8%a d%e5%9b%bd%e6%9c%ac%e7%a7%91%e7%94%9f%e5%9c%a8%e 7%ba%bf%e6%b5%8b%e8%af%84%e7%b3%bb%e7%bb%9f%e6%9 5%99%e8%82%b2%e6%95%b0%e6%8d%ae%e6%a0%87%e5%87%8 6v0-1/,2020-02-04.