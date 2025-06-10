# Enhanced management of personal astronomical data with FITSManager

Chenzhou Cuia\*, Dongwei Fana, Yongheng Zhaoa, Ajit Kembhavib, Boliang Hea, Zihuang Caoa, Jian Lia, Deoyani Nandrekar b.c

NationalAstronomicalObservatories,ChineseAcademyfSciences,ADatunRoad,Chaoyangistrict,BjingChin b Inter University Centre for Astronomyand Astrophysics,Post Bag 4,Ganeshkhind,Pune 411oo7,ndia DepartmentofysicsandAstronomy,TheJohnsHopkins University3701SanMartinDrive,Baltimore,MD1218,Unitedtate

# ARTICLE INFO

# ABSTRACT

Article history:   
Received 6 February 2011   
Received in revised form9 May 2011   
Accepted 17 June 2011   
Available online 25 June 2011

Communicated by G.F.Gilmore

Keywords: Methods:data management Techniques:Virtual Observatory Astronomical data bases

Although the roles of data centers and computing centers are becoming more and more important,and on-lineresearch is becoming the mainstream for astronomy,individual research based on locally hosted data is still very common.With the increase of personal storage capacity,it is easy to find hundreds to thousands of FITS files in the personal computer of an astrophysicist. Because Flexible Image Transport System (FITS) is a professional data format initiated by astronomers and used mainly in the small community,data management toolkits for FITS files are very few.Astronomers need a powerful tool to help them manage their local astronomical data.Although Virtual Observatory(VO) is a network oriented astronomical research environment,its applications and related technologies provide useful solutions to enhance the management and utilization of astronomical data hosted in an astronomer's personal computer.FITSManager is such a tool to provide astronomers an eficient management and utilization of their local data,bringing VO to astronomers inaseamless and transparent way.FITSManager provides fruitful functions for FITS file management,like thumbnail,preview,type dependent icons,header keyword indexing and search,collaborated working with other tools and on-line services,and so on.The development of the FITSManager is an effort to fill the gap between management and analysis of astronomical data.

$\circledcirc$ 2011Elsevier B.V.All rightsreserved.

# 1. Introduction

Astronomy depends upon observations,which are recorded with naked eyes,films or modern digital detectors.Scientific data, including observational data and other kinds of data,for example simulation results,are basic resources for astronomy research. During the last few decades,with the development of detectors and information technologies,astronomers'data harvesting abilities have increased sharply.Astronomy is facing a data deluge, and traditional data processing and analysis are facing big challenges (Szalay and Gray,2001;Bell et al.,2009;Hey et al., 2009). As one of the solutions for these challenges,Virtual Observatory (VO) was initiated around 2ooo and later an international working environment (IVOA,the International Virtual Observatory Alliance)1 was established in 2002.

AVirtual Observatory isa data-intensive on-line astronomical research and education environment, taking advantages of advanced information technologies to achieve seamless,global access to astronomical information(Cui and Zhao,2oo8).The power of the World Wide Web is its transparency. It is as if all the documents in the world are inside your PC.The idea of the Virtual Observatory is to achieve the same transparency for astronomical dataand other related information (Quinn et al.,2004).

Scientific data available for the whole community are increasing sharply.At the same time,takingadvantages of fast network and cheap storage devices,personal collections are also increasing rapidly.For an astronomer working on observational astronomy,it is very common to find hundreds or thousands of FITS files in his personal laptop.These astronomers often feel it is difficult or very hardto look fora specific file from large number of directories and files,and what is worse is that they can hardly find any tool to help them.

During the last decades,several popular data processingand analyzing packages, i.e. IRAF,² ESO-MIDAS, SAOImage DS9,4 Aladin,5 fv, et al.,have been developed to meet astronomers'requirements, but none of them provides powerful data management functions.

![](images/2fc0b6dc51f429afdc18e56f3c7c0d2917cd799dd822158f4698f398841671bc.jpg)  
Fig.1.Main interface of FITSManager.

FITS is the most common data format for astronomers(Wells etal., 1981;Hanisch et al.,2oo1),but it is used only inastronomyand a very fewclose related fields.Itsuserbase isa very small community. For general image formats,i.e.JPG,GIF,TIF,etc.there are quitea few image management applications,freeware or commercial ones,for example ACD see, Google Picasa, and so on. Unfortunately, none of these supports files in FITS format very well.

In professional data centers,database management systems (DBMS) and data grid technologies are used to manage large numberof data files and their metadata.Findingand using such DBMS and professional data management technologies are difficult matters for most of astronomers.Thus,there is a gap between data analysis and data management for personal users.FITS Manager9 (FITSManager）is just the tool,aiming to provide powerful and easy-of-use management functions for individual astronomers,and at the same time leveraging these functions with dataanalysis tools and services,including not only VO-ready ones but also legacy applications.Compared to professional data analysis packages,i.e. IRAF, MIDASand IDL Astronomy User's Library,1° the role of the FITSManageris very similar to the role of Google Picasa to Adobe Photoshop.11

The mission of the FITSManager is to provide individual astronomers an efficient management and utilization of large collections of local stored FITS files,bringing VO to them in a seamless and transparent way.12 In the following sections of the paper,we first describe functions and key features of the FITSManager,and then introduce the architecture and technical highlights of the software.

In the last part,we discuss future trends of astronomy data management and utilization,and summarize the development and future plan for the application.

# 2.Key featuresand functions

Professional data analysis packages and toolkits provide powerful data processing,analyzing,and visualizing functions for FITS files,while providingat best very limited management functions. Users have to manage and locate their FITS files using directories and filenames.When the number of FITS files is small, these ways are reasonable and acceptable.When an astronomer has to manage thousands to tens of thousands ofFITS files in his computer,itwill be hard and time consuming for him to find a specific file.

FITSManager focuses on management of small and moderately large number of FITS files hosted in astronomer's personal computer, providing index,search,preview,and external linked functions.On a recently produced laptop with 2GB or more memory,it is feasible forFITSManager to take care of thousands ofFITS files.When the collection reaches to tens of thousands of files or more,data centerlevel solutions are recommended.The main interface is shown in Fig.1. Key features and functions of the current release include:

·File search based on FITS header keywordsand other metadata. Two ways are provided in the current version,general search and advanced search.For general search,a Google-like formis provided as shown in Fig.2.FITS header content and filenames in the current file list will be used to match the search phrase. Advanced search is a database based way.Before using this function,header keyword information of FITS files under a given directory orawhole file systemhas to be imported intoa database system.Graphics User Interface(GUI) wizards are provided forboth FITS headerarchivingandFITSfile search.The file search interface and back-end programs will be improved in the future versions with guidance of user's feedback.

![](images/ebd4111c473915a28dff327f67dfea7c8a3bc11ba2d8e42f692250def04acb34.jpg)  
Fig.2.File Search Dialog.

![](images/70f8e310011d83beda1363ecc26089fb34d2079dc8f9137aa7b9a529be66cf57.jpg)  
Fig.3.Relationships among core plug-in,application plug-ins and OSGi framework.

·Grouping,annotating and rating.The FITS files hosted in the user's computer can be grouped into different categories by their content,type or other characters.Annotation and 5-star rating canbeadded forselected FITS files,and these are searchable later.Being similar to functions provided by many other image management applications,all of these functions are useful for file management.

· Thumbnail and preview.FITSManager explorer provides several views for files and directories,including thumbnails,titles, icons,list and detail.In titles and icons modes,the FITSManager provides different icons to distinguish different FITS file types, i.e.image,random groups,multiple HDU (Header and Data Unit)FITS. In thumbnails mode,the software creates and displays thumbnails for several typical FITS format files.In the current release，table,2D image and 1D spectrum types are supported.In future releases,thumbnail function for more types of FITS fileswill be provided.This functionisvery helpful for rapid inspection and locating of FITS files containing image and spectra data.

· Interoperability with VO tools.IVOA VOTable1³ data format and SAMP14 messaging are supported by the FITSManager. IVOA members have recognized that building a monolithic tool that attempts to fulfill all the requirements of all users is impractical, and it is a better use of the limited resources to enable individual tools to work together effciently. SAMP is an IVOA messaging protocol that enables astronomy software tools to interoperate and communicate.As mentioned above,FITSManager focuses itself on file management,but leaves other functions,i.e. processing,visualization,analyze,statistics et al.,to other existing and new developed tools.Selected files in the FITSManager can be sent to SAMP-ready applications,for example Aladin,Topcat,15 SAOImage DS9,Worldwide Telescope16 (WWT),and so forth.

![](images/9bcfda3f5f819215efc1da30362efc5102a06b8f4203d9ba2ce887da7ffaf1fe.jpg)  
Fig.4.Logical architecture of FITSManager.

·Easy-to-use graphic user interface.FITSManager isan end user application,soa friendly user interface is very important.FITSManager explorer looks like MS Windows File Explore.An astronomer can browse his directory and file tree using the same manner as using file manager provided by his operating system (OS).Whena FITS file is selected,some specific functions will be available.For files in other formats,the navigation process is similar to usingan OS file manager.

# 3.Architecture and technical highlights

During the design and development of the FITSManager,advanced development modes were adopted and latest VO functions were considered.

# 3.1.Plug-inbasedarchitecture

Plug-in development mode is a very popular way for software development nowadays.Many well-known packages,for example

![](images/d3b18c86699fadc1778f9ed932fe61c1888ae1ebc28c91d4e456bd3714a9c9ed.jpg)  
Fig.5.FITS file grouping and rating window.

Firefox,17 Eclipse18 and many content management systems (CMS), are developed based on plug-ins.

Eclipse with Equinox19 is used as the developing environment. Open Service Gateway Initiative (OSGi) technology is the dynamic module system for Java,which enables the modularassemblyof software built with Java technology.From a code point of view, Equinox is an implementation of the $\mathrm { O S G i } ^ { 2 0 }$ framework specification,a set of bundles that implement various optional OSGi services and other infrastructure for running OSGi technology based systems. On the other hand,Eclipse provides powerful plug-in development environment for the OSGi framework,which makes plug-in coding much easier.

In the FITSManager,all of the specific functions are realized as dynamic modules,i.e.plug-ins.A core plug-in provides common interfaces for other application plug-ins,and application plug-ins provide the dedicated functions mentioned in the above section.

In the OGSi framework,plug-ins discovery,load and execute are all completed by the framework.Comparing to the framework,all the attached plug-ins have equal roles.However,for the FITSManager package,there is a plug-in to provide basic functions.We call this plug-in as core plug-in,and other plug-ins as application plugins.Although the FITSManager application plug-ins are loaded by the OSGi framework physically,their functions depend on the core plug-in. Relationships among core plug-in,application plug-ins and the OGSi framework are shown in Fig.3.

When basic control functions of application plug-ins,for example,start/stop,are integrated into the core plug-in,the backend OSGi framework can be ignored in logical.Architecture of the FITSManager will be simplified as in Fig.4,consisting of a core and a bundle of application plug-ins.

FITSManager core plug-in is the kernel for the application. It controls start and stop of application plug-ins,and provides extension interfaces to them.The main functions of the core plug-in include software configuration, $1 / 0$ interface management,database connection,different views of file system,etc.

Several basicapplication plug-inshave been provided:

·Explorer,a file manager similar to those provided by many OS distributions,for instance MS Windows and various Linux systems (Fig. 1).   
·Category,enable user to create custom groups for FITS fles, to annotate and rate these fles (Fig.5).   
·Favorites,an index view of selected file system directories (Fig.6).Header information of FITS files under these directories will be imported into databasesand indexed.And then fast FITS file search on FITS header keywords is enabled.   
·IconCreater,return different sets of icons for current fle system content to the FITSManager core plug-in according its request (Fig.7).Five types of views,thumbnails,icons,tiles,list,detail, are supported.A worthwhile point we should mention here is that the IconCreater plug-in will read and analyze header information of FITS filesand createdifferent icons for themaccordingto their FITStypes，i.e.image，multiple HDU，etc. Additionally, the plug-in also act at a FITS viewer(Fig.8).

When the core plug-in requests a thumbnail view,the IconCreater loads the first data HDU of a FITS file into memory and return a thumbnail for the file.If values ofNAXIS1and NAXIS2keywords in theFITS headerof a file are not in the same magnitude level,for example,several vs thousands,the IconCreater plug-in will assume the content of the file is a spectrum,and plot the first line as its thumbnail. If the FITS file is an image,a thumbnail will return after essential processes to the first data HDU,for example cutout,sharpen,and contrastadjustment.For table FITS files,a blank table frame with defined rows and columns by NAXIS1 and NAXIS2 keywords willbereturnedas thumbnails.

![](images/f2b112c73d0be11bf06a3f63129b14d151f914d78eda11f2e887af630c3e552e.jpg)  
Fig.6.Indexand search based on FITS header keywords.

Creating thumbnails on the fly for FITS files is a new function brought forward by the application.When an astronomer is looking for FITS files with significant characters among a number of files,this function will be very useful.

·SAMP,supports message exchange between FITSManager and other SAMP-ready tools,for example Aladin,Topcat,VOPlot, SAOImage DS9,WWT,etc.(Fig.9),which links them into an astronomical data management and utilization environment.

# 3.2.Othertechnical highlights

FITSManager is developed in Java,so operating system independence is a natural character of it.Although database systems are very important and popular for developers,theyare not so familiar to astronomers,who are the end users of the package.So in the FITSManager,an embedded Java database management system, Apache Derby,21 is adopted.For embedded database component, installation and configuration are not required.When astronomers are using flexible index and search functions,they would not notice that a database system is running at the back end.If a user needs to use a standalone database system,FITSManageralso provides interface to connect with it.

# 3.3.Performance test

Performance of two key features of the application was tested using data of one spectroscopic plate from SDSS DR7.22 The test was conducted on a Lenovo ThinkPad T41Oi laptop with Intel (R) Core(TM)i5CPU $( \mathsf { M } 4 3 0 @ 2 . 2 7 \mathsf { G } \mathsf { H z }$ ),4GBRAM,MicrosoftWindows 732 bit professional OS,Western Digital WD3200BEVT-O8A23T1 ATA hard disk.

In the plate 1529-52930 of tile 9435,there are 640 1d spectrumFITS files at“spSpec"subdirectory and 64O image FITS files at“spAtlas”subdirectory.In“thumbnail"view mode,it takes less than one second to create thumbnails for the 64O spectrum or image FITS files in one directory.

It takesa longer time to create index for FITS files ina given directory. For the instance of the SDSS spectroscopic plate 1529- 52930,it takesabout $1 0 \mathrm { m i n }$ to import FITS header content of 640 spectra files into FITSManager embedded database,which meansit takesabout1sper file.When the FITS headeris simpler, the process will be faster. Fortunately,this operation is not executed very often. Once an index is created,it can be used for a long time if there is no change in the directory.

The above results are obtained when the laptop is mainly used by the FITSManager.If there are other applications running at the same time,time needed for thumbnail creation and indexing will be longer.

# 4. Summary

With the arrival of Cloud computing,23 it seems that everything willappearasa service(XaaS),borders between local storage and remote storage,between local applications and on-line services become more and more blur,which is changing our way of data management and utilization.More and more research activities will take advantages of on-line services.On the other hand,personal computers and laptops will keep their role for quite a long timeas the dominant working platform fora scientist,and offline research should not be ignored.FITSManager is such a tool that brings VO functions and online services to today's astronomers in a seamless and transparent way,no requirement for its user to take care of the physical locations of these functions and services.

In the future versions of the software,it will be enhanced in the following manner.

·Deeper involvement with VO and on-line services.Groundbreaking applications and on-line services appear from time to time,for example “astrometry.net"(Lang et al.,201O). Taking advantages of the OSGi module developing environment,plugins can be developed for these smart services and integrated into the FITSManager seamlessly.Plug-ins for astrometry.net, VOSpace²4 and Montage25 are planned for the next release.

![](images/1ad6f469d3f3e7eabfdef56ae62f3da32d66bd4873e7ded09fdaf01e7c952209.jpg)  
Fig.7.Different views of data files,(a) shows“Icons"view and (b) shows“Thumbnails"view.

·Developer and user community.The OSGi technology provides the standardized primitives that allow applications to be constructed from small,reusable and collaborative components. These components can be composed into an application and deployed.Furthermore,dynamic module development mode enables a loose collaboration way, i.e.developer community.

![](images/9637a734e74dccf6b05a82edfe15f4afd99e878c89066601d2a83b23262d79cd.jpg)  
(a) Display content of a FITS file

![](images/fd84b23fb5f800b4ae1a2808d1b2e229b478be00d784e8ef73645086c9deaf59.jpg)  
Fig.8.View FITS file content and its thumbnail.(a) Shows the content of a selected FITS file in (b).

A FITSManager developer and user community is planned.Third party developers and end users can develop their own plug-ins and contribute to the whole community,which will enrich functions of the application rapidly.

![](images/1fa22279b9e28ff7f2c179099625cc696de781fb6eee6329ed46bbe4ccc1fc34.jpg)  
(a) Select a file and send it to other applications through SAMP

![](images/05622dbe77cd1baa4cbfb31a0571ca73561b52f7f544702c95637a411de90f32.jpg)  
(b) File received by SAOImage DS9

![](images/61a3d7bd8fb771ac1bcc47405104757bbdbd50678aa29177290f2923c890abcd.jpg)  
Fig.9.Data exchange between FITSManager and SAOImage DS9 and Aladin.

·Enhanced thumbnail and preview functions.On one hand,more types of FITS files will be supported,for example multi-fiber spectrum,data cube,etc.On the other hand,optimized thumbnailsand previews are tried to provided,which need considerationof manyaspects of the data filesand intelligent analysis for the content.

·Easy-of-use user interface.During the past few decades,many professional astronomers have been used to command line interfaces (CLI) coming with astronomical data process platforms,i.e. IRAF,ESO-MIDAS,and Unix like operating systems. Nowadays,network is stepping into service oriented and cloud computing era.Advanced graphic user interfaces,for example, the Multi-Touch screen from Apple iPad,26 have acquired dominant positions as user interfaces,and have been accepted widely by the younger generation.MSR Worldwide Telescope isa successful example on user interface design in astronomical software.For FITSManager,one of a number of astronomical tools,auser friendlyand easy-of-use GUIisvery important.In the future versions,menu layout and window theme will be redesigned.The file search dialog will be greatly improved, providing a much more friendly appearance.

· Comprehensive documentation and help system.Documentation and help system are very important for users,especially for a new application.FITSManager user manual is under preparation,and a searchable“Help"button will be implemented in the tool.

# Acknowledgement

FITSManager is a collaborated project between Chinese Virtual Observatory(China-VO) and Virtual Observatory India (VO-India). Thispaper is funded by National Natural Science Foundation of China(10820002,60920010,90912005),Ministry of Science and Technology of China (BSDN2o09-O7)，Beijing Municipal Science and technology Commission (2oo7Ao85).VO-India isa collaboration between the Inter-University Centre for Astronomy and Astrophysicsand Persistent SystemsLtd.,and is partially funded bythe Ministry of Communications and Information technology of the Government of India.The first author thanks Robert Hanisch (STScI),Alex Szalay(JHU) and Mark Allen(CDS)for their helpful discussion.

# References

Bell,G.,Hey,T., Szalay,A.,2009.Science 323 (591),1297.doi:10.1126/science.- 1170411.   
Cui,C.Z.,Zhao,Y.H.,20o8.Worldwide R&D of Virtual Observatory. In: Jin,W.J., Platais,I.,Perryman,M.A.C.(Eds.),A Giant Step: from Milli- to Micro-arcsecond Astrometry，Proceedings of the International Astronomical Union (2007) Symposium S248,3,563-564.   
Hanisch,R.J.,Farris,A.,Greisen,E.W.,Pence,W.D., Schlesinger, B.M.,Teuben,P.J., Thompson,R.W.,Warnock,A.,2001.A&A376,359.   
Hey,T.,Tansley,S.,Tolle,K.,2oo9.The Fourth-Paradigm:Data-Intensive Scientific Discovery，second ed.Microsoft Research,Redmond,WA.   
Lang,D.,Hogg,D.W.，Mierle,K.,Blanton，M.,Roweis,S.,2010.AJ 139,1782. doi:10.1088/0004-6256/139/5/1782.   
Quinn,P.J.,Barnes,D.G., Csabai,I., Cui,C., Genova,F., Hanisch,B.,Kembhavi,A.,Kim, S.C.,Lawrence,A.,Malkov, O.,Ohishi,M.,Pasian,F., Schade,D.,Voges,W.,2004. The International Virtual Observatory Alliance:recent technical developments and the road ahead.In: Oschmann,J.M.,Glasgow,Jr.(Eds.),Ground-based Telescopes,Proceedings of the SPIE,5493,137-145.   
Szalay，A.，Gray，J，2001．Science 293(5537)，2037．doi:10.1126/science.- 293,5537.2037.   
Wells,D.C., Greisen, E.W.,Harten,R.H.,1981. A&A Supplement Series 44,363.