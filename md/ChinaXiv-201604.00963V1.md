Astronomical DataAnalysisSoftwareand Systems:XXIV ASPConference Series,Vol.495   
A.R.TaylorandE.Rosolowsky,eds.   
（204号 $\wp$ 2015Astronomical Society of the Pacific

# AstroCloud, a Cyber-Infrastructure for Astronomy Research: Data Archiving and Quality Control

Boliang He,1 Chenzhou Cui,1 Dongwei Fan,1 Changhua Li,1 Jian Xiao,²   
Ce Yu,² Chuanjun Wang,³ Zihuang Cao,1 Junyi Chen,² Weimin Yi,3   
Shanshan Li,1 Linying Mi,1 and Sisi Yang1   
1 National Astronomical Observatories, Chinese Academy of Sciences (CAS),   
20ADatun Road,Beijing l000l2, China

2Tianjin University, 92 Weijin Road, Tianjin 300072, China

3 Yunnan Astronomical Observatory, CAS, P.0.Boxl10, Kunming 6500l1, China

Abstract. AstroCloud is a cyber-Infrastructure for Astronomy Research initiated by Chinese Virtual Observatory (China-VO) under funding support from NDRC (National Development and Reform commission) and CAS (Chinese Academy of Sciences)(Cui et al.2O14).To archive the astronomical data in China, we present the implementation of the astronomical data archiving system (ADAS). Data archiving and quality control are the infrastructure for the AstroCloud. Throughout the data of the entire life cycle,data archiving system standardized data, transferring data,logging observational data,archiving ambient data,And storing these data and metadata in database. Quality control covers the whole process and all aspects of data archiving.

# 1.Introduction

There are tens of telescopes running in China. Every night and day, they are producing several terabytes data. To archive these huge data and manage them,we present an implementation of an Astronomical Data Archiving System (ADAS). The data types which would be archived are the observation data and ambient data.The observation data such as image FITS,spectra FITS and observation log,are produced by telescope and data reduce pipeline.Ambient data are some environment data, such as weather, seeing data and allsky camera images.

Archived data is stored into the observatory's data center first, then data is transferred to AstroCloud data center via ADAS.In AstroCloud, we build a Data Access API For users and programs to access data. The following telescopes have been already using this archiving system to archive their data. These telescope are located in multiple sites in China: Guo Shoujing Telescope (LAMOST),Lijiang GMG $2 . 4 \mathrm { m }$ Telescope,Xinglong 2.16m Telescope,Delingha 50Bin Telescope,Huairou Solar Radio Telescope,Huairou Solar Multi-Channel Telescope and Fuxian lm New Vacuum Solar Telescope (NVST).

![](images/b0e293e9d77d5382de964fb4ed939ca27aa1f7feb0f70dd1335690feefe3e0fc.jpg)  
Figure 1. Dataarchive Framework

# 2. Data Model

The type of AIJraw data include files and tables.FITS file mainly contain the raw data. FITS can be image,can be spectral, etc. The tables are catalog tables,ambient data tables, observational logs,etc.Metadata consists of two types:

·Schema Metadata:Schema Metadata stores all the databases, schemas, tables and columns information. The database-schema is similar to the IVOA TAP schemas(IVO 2010).   
·Archive Metadata: Archive Metadata stores the FITS files’header information. The database-schema is shown in Table 1. Usually one telescope has one table in the archive database.

Table 1. ArchiveMetadatadatabase-schema   

<html><body><table><tr><td>Column Name</td><td>Definition</td><td>Description</td></tr><tr><td>id</td><td>SERIAL</td><td>Auto increasing integer, Primary Key</td></tr><tr><td>filename</td><td>VARCHAR(30)</td><td>FITS fle name</td></tr><tr><td>object</td><td>VARCHAR(30)</td><td>Observation object</td></tr><tr><td>RA</td><td>NUMERIC(12,8)</td><td>Right ascension, default J2000</td></tr><tr><td>Dec</td><td>NUMERIC(12,8)</td><td>Declination,default J2000</td></tr><tr><td>filesize</td><td>INTEGER</td><td>File size (bytes)</td></tr><tr><td>checksum</td><td>VARCHAR(64)</td><td>MD5 checksum</td></tr><tr><td>recTime</td><td>TIMESTAMP WITHOUT TIME ZONE</td><td>Recorded time</td></tr></table></body></html>

# 3. Software archiving Architecture

The system consists of four submodules (Laher et al. 2014):

![](images/d89ecca2e5bb7d763fac35aab9c9092b2b7818e35da7999daebff6dcc54a0cbd.jpg)  
Figure 2. Software Architecture

1 Data Transfer System (DTS). Data transferring is via network. The network transfer is scheduled. In the central data center in NAOC,we set up a Transfer Server to accept data transfer. We choose rsync tools running this service. Because it is open source and has a very good performances. (Zampieri et al. 2009)

2 Data Ingest System (DIS). DIS provides the data to database function. This procedure will parse the FITS header and choose the necessary filed to record into the database. We use the AstroPy(Astropy Collaboration et al.2013） to manipulate the FITS file, which can collect the FITS file header easily.(Dobrzycki et al. 2012)

3 Logging System (LGS). All the operation willbe logged into the database. LGS is the procedure to log the operation: data transfer, data ingest, database replication, etc.

4 Archive Backup System (BKS). BKS consists of files backup,database replication,and database backup.These operations are scheduled.

# 4.Archiving Pipeline

1 Data will be transferred to the data center in NAOC by DTS in schedule.

2 After the data is finished transferred. DIS will start running,DIS will check the files’checksum,collect the FITS files’header and insert it into the archive database.

3 All the files has been checked and record into the database,gather these information (file amount, transfer log,database log,etc) to email these information to the system administrator and telescope operator.

4 These FITS files and database will be backup by BKS in schedule.

5 Database replication: archive database is the write-only database,the SkyTools(Sky 2014) replication procedure will replicate the database to the Query Databases for other user or system to access,such as Data Publish System²(Fan et al.2014).

# 5. Quality Control

Data quality can be controlled by the data archiving process. In DTS,every file has been made a MD5 checksum, before transferred and after transferred, transfer procedure will valid the checksum.Database is been checked and valid by schedule.

# 6. Conclusions

We developed and implemented an astronomical data archiving system that can be operated automatic. When the data is produced, the procedure will be running quietly. When the procedure is finished, the operator will receive the job detail email.

Acknowledgments. This paper is funded by National Natural Science Foundation of China (U1231108),Ministry of Science and Technology of China (2012FY120500), Chinese Academy of Sciences (XXH12503-05-05). Data resources are supported by Chinese Astronomical Data Center.

# References

2010,Table Access Protocol (TAP) Version 1.O. http://www.ivoa.net/documents/TAP/ 20100327/REC-TAP-1.0.html   
2014,SkyTools.http://pgfoundry.org/projects/skytools   
Astropy Collaboration,Robitaille, T.P.,et al.2013,A&A, 558,A33.1307.6212   
Cui, C., Yu, C., Xiao,J.,He, B.,Li, C.,Fan, D., Wang, C., Hong, Z.,Li, S.,Mi,L., Wan, W., Cao,Z., Wang,J., Yin,S.,Fan, Y.,Wang, J.,& Yang, S.2O14, in ADASS XXIV, edited by A.R. Taylor,& E. Rosolowsky (San Francisco: ASP),vol. TBD of ASP Conf. Ser., TBD   
Dobrzycki,A., da Rocha, C., Vera,I., Vuong,M.-H., Bierwirth, T.,Forchi, V.,Fourniol, N., Moins,C.,& Zampieri, S.2O12,in Society of Photo-Optical Instrumentation Engineers (SPIE) Conference Series,vol. 8451 of Society of Photo-Optical Instrumentation Engineers (SPIE) Conference Series   
Fan, D., He, B., Xiao,J.,Li, S.,Li, C., Cui, C., Yu,C.,Hong, Z., Yin, S.,Wang, C., Cao, Z, Fan,Y.,Mi,L., Wan, W.,& Wang, J. 2014, in ADASS XXIV, edited by A.R. Taylor,& E.Rosolowsky (San Francisco:ASP),vol.TBD of ASP Conf. Ser., TBD   
Laher,R.R., Surace,J., Grillmair, C.J., Ofek,E.O.,Levitan,D., Sesar,B., van Eyken, J. C., Law,N. M.,Helou, G.,Hamam, N.,Masci,F.J.,Mattingly,S., Jackson,E.,Hacopeans, E.,Mi, W., Groom, S., Teplitz,H., Desai, V., Hale,D., Smith,R., Walters,R., Quimby, R.,Kasliwal,M.,Horesh,A.,Bellm,E.,Barlow,T.,Waszczak,A.,Prince,T.A.,& Kulkarni, S.R.2014,PASP,126,674.1404.1953   
Zampieri, S.,Forchi, V., Gebbinck,M.K., Moins,C.,& Padovan,M.2Oo9,in Astronomical Data Analysis Software and Systems XVII, edited by D.A. Bohlender,D.Durand,& P.Dowler, vol. 411 of Astronomical Society of the Pacific Conference Series, 540