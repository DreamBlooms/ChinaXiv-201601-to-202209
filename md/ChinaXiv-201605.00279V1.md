# PRELIMINARYANALYSISOFHY-2ACMRDATA

Dehai Zhang，Zhenzhan Wang，Yun Li，Jin Zhao and YalongLiu

CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences

# ABSTRACT

Water vapor and cloud liquid water can influence the accuracy of sea surface height that spaceborne altimeter measures. Atmospheric correction microwave radiometer (ACMR) can be used to retrieve the amount of water vapor and cloud liquid water by measuring radiation from atmosphere and earth's surface.HY-2 satellite is a Chinese satellite for ocean dynamic environmental monitoring ACMR is one payload ofHY-2 satellite.Up to now,ACMR has been in operation for more than three years.In-orbit system stability of three years is assessed.The data of ACMR brightness temperature are matched to that of ECMWF wet tropospheric path delay in same space and time.The water vapor and cloud liquid water retrieval algorithm is derived The wet tropospheric path delay deviations are less than $1 . 5 \mathrm { c m }$ . Brightness temperatures and path delay of ACMR were compared with that of AMR.The average and standard deviations of wet tropospheric path delayare $1 . 2 7 \mathrm { m m }$ and $0 . 6 8 \mathrm { m m }$

Index Terms— HY-2 Satellite，ACMR,Path Delay, Cross-calibration

# 1.INTRODUCTION

HY-2 satellite is a Chinese satellite for ocean dynamic environmental monitoring. It was launched on Aug.l6,2011 ACMR on board of HY-2 is a nadir viewing three-band microwave radiometer which measures radiation from atmosphere and earth's surface at frequencies of $1 8 . 7 \mathrm { G H z }$ $2 3 . 8 \mathrm { G H z }$ and 37GHz.It is used to retrieve the amount of water vapor and cloud liquid water so as to correct the path delay that altimeter's signals travel from satellite to the oceansurfaceandback.

ACMR is a full power microwave radiometer. System calibration uses matched loads and cold space background. Unlike other spaceborne path delay correction microwave radiometer,ACMR measurement antenna is a deployable offset parabolic antenna with three feeds.The reflector is fixed on the base before launch.When ACMR is in orbit, the reflector is spread by hinges and the three beams distribute in the nadir direction within 2.5 degree along the satelliteflight direction. The measurement antenna beamwidth at different frequency is $1 . 4 ^ { \circ } , \ 1 . 1 ^ { \circ }$ and $0 . 6 ^ { \circ }$ respectively.

# 2.SYSTEMSTABILITYASSESSMENT

ACMR has been working from Sep.1,2011. In order to assess in-orbit performance,the system sensitivity should be calculated at different timefirstly. Because of the fluctuation of target radiation,some cold space and hot source data was randomly selected to calculate in-orbit system sensitivity about every six months.The results demonstrate that the in-orbit system sensitivity is less than 0.25K.

In order to further monitor ACMR system stability,the system gain fluctuation is assessed for more than three years. The microwave receiver temperature influences system gain When ACMR is in orbit, microwave receiver temperature of each channel changes with time. The temperatureof microwave receivers shows a periodical variation. ACMR measurement data of hot source and cold space at certain temperature was analyzed so as to further eliminate the impact of receiver temperature variation. The temperature should be that the receiver experienced the most times from beginning to now.The selected temperature is 293K.The databetween 292.9 and 293.1 are found out to calculate system gain. Table 1 to table 3 show each channel gain at 293K.The gain is defined as V/T.

Table118.7GHz channel gainat 293K   

<html><body><table><tr><td></td><td>Gmean</td><td>Gstd</td><td>Gmax-Gmin</td><td>Gmax-Gmin/Gmean</td></tr><tr><td>All the data(Ts=293)</td><td>0.01641</td><td>0.000044</td><td>0.000250</td><td>0.015</td></tr><tr><td>1</td><td>0.01629</td><td>0.000012</td><td>0.000085</td><td>0.005</td></tr><tr><td>2</td><td>0.01634</td><td>0.000010</td><td>0.000067</td><td>0.004</td></tr><tr><td>3</td><td>0.01633</td><td>0.000009</td><td>0.000060</td><td>0.004</td></tr><tr><td>4</td><td>0.01635</td><td>0.000010</td><td>0.000076</td><td>0.005</td></tr><tr><td>5</td><td>0.01636</td><td>0.000009</td><td>0.000076</td><td>0.005</td></tr><tr><td>6</td><td>0.01638</td><td>0.000010</td><td>0.000058</td><td>0.004</td></tr><tr><td>7</td><td>0.01640</td><td>0.000009</td><td>0.000071</td><td>0.004</td></tr><tr><td>8</td><td>0.01638</td><td>0.000009</td><td>0.000065</td><td>0.004</td></tr><tr><td>9</td><td>0.01642</td><td>0.000009</td><td>0.000053</td><td>0.003</td></tr><tr><td>10</td><td>0.01644</td><td>0.000010</td><td>0.000076</td><td>0.005</td></tr><tr><td></td><td>0.01643</td><td>0.000010</td><td>0.000073</td><td>0.004</td></tr><tr><td>12</td><td>0.01645</td><td>0.000010</td><td>0.000084</td><td>0.005</td></tr><tr><td>13</td><td>0.01644</td><td>0.000010</td><td>0.000073</td><td>0.004</td></tr><tr><td>14</td><td>0.01645</td><td>0.000010</td><td>0.000073</td><td>0.004</td></tr><tr><td>15</td><td>0.01643</td><td>0.000011</td><td>0.000079</td><td>0.005</td></tr><tr><td>16</td><td>0.01641</td><td>0.000010</td><td>0.000054</td><td>0.003</td></tr><tr><td>17</td><td>0.01644</td><td>0.000010</td><td>0.000091</td><td>0.006</td></tr><tr><td>18</td><td>0.01647</td><td>0.000010</td><td>0.000047</td><td>0.003</td></tr></table></body></html>

Table2 23.8GHz channel gain at 293K   

<html><body><table><tr><td></td><td>Gmean</td><td>Gstd</td><td>Gmax-Gmin</td><td>Gmax-Gmin/Gmean</td></tr><tr><td>All the data(Ts=293)</td><td>0.01663</td><td>0.000035</td><td>0.000220</td><td>0.013</td></tr><tr><td>1</td><td>0.01661</td><td>0.000011</td><td>0.000087</td><td>0.005</td></tr><tr><td>2</td><td>0.01666</td><td>0.000011</td><td>0.000075</td><td>0.005</td></tr><tr><td>3</td><td>0.01668</td><td>0.000011</td><td>0.000077</td><td>0.005</td></tr><tr><td>4</td><td>0.01668</td><td>0.000011</td><td>0.000082</td><td>0.005</td></tr><tr><td>5</td><td>0.01666</td><td>0.000011</td><td>0.000085</td><td>0.005</td></tr><tr><td>6</td><td>0.01666</td><td>0.000011</td><td>0.000071</td><td>0.004</td></tr><tr><td>7</td><td>0.01666</td><td>0.000012</td><td>0.000092</td><td>0.006</td></tr><tr><td>8</td><td>0.01665</td><td>0.000011</td><td>0.000091</td><td>0.005</td></tr><tr><td>9</td><td>0.01666</td><td>0.000011</td><td>0.000061</td><td>0.004</td></tr><tr><td>10</td><td>0.01667</td><td>0.000011</td><td>0.000092</td><td>0.006</td></tr><tr><td></td><td>0.01665</td><td>0.000012</td><td>0.000080</td><td>0.005</td></tr><tr><td>12</td><td>0.01664</td><td>0.000011</td><td>0.000081</td><td>0.005</td></tr><tr><td>13</td><td>0.01662</td><td>0.000011</td><td>0.000082</td><td>0.005</td></tr><tr><td>14</td><td>0.01661</td><td>0.000011</td><td>0.000089</td><td>0.005</td></tr><tr><td>15</td><td>0.01658</td><td>0.000012</td><td>0.000086</td><td>0.005</td></tr><tr><td>16</td><td>0.01652</td><td>0.000010</td><td>0.000054</td><td>0.003</td></tr><tr><td>17</td><td>0.01656</td><td>0.000012</td><td>0.000099</td><td>0.006</td></tr><tr><td>18</td><td>0.01657</td><td>0.000011</td><td>0.000064</td><td>0.004</td></tr></table></body></html>

Table337GHz channel gainat293K   

<html><body><table><tr><td></td><td>Gmean</td><td>Gstd</td><td>Gmax-Gmin</td><td>Gmax-Gmin/Gmean</td></tr><tr><td>All the data(Ts=293)</td><td>0.01453</td><td>0.000045</td><td>0.000265</td><td>0.018</td></tr><tr><td>1</td><td>0.01461</td><td>0.000013</td><td>0.000103</td><td>0.007</td></tr><tr><td>2</td><td>0.01457</td><td>0.000012</td><td>0.000088</td><td>0.006</td></tr><tr><td>3</td><td>0.01459</td><td>0.000012</td><td>0.000080</td><td>0.005</td></tr><tr><td>4</td><td>0.01458</td><td>0.000015</td><td>0.000094</td><td>0.006</td></tr><tr><td>5</td><td>0.01457</td><td>0.000012</td><td>0.000087</td><td>0.006</td></tr><tr><td>6</td><td>0.01457</td><td>0.000012</td><td>0.000092</td><td>0.006</td></tr><tr><td>7</td><td>0.01455</td><td>0.000012</td><td>0.000086</td><td>0.006</td></tr><tr><td>8</td><td>0.01457</td><td>0.000012</td><td>0.000092</td><td>0.006</td></tr><tr><td>9</td><td>0.01451</td><td>0.000012</td><td>0.000103</td><td>0.007</td></tr><tr><td>10</td><td>0.01450</td><td>0.000012</td><td>0.000103</td><td>0.007</td></tr><tr><td>11</td><td>0.01447</td><td>0.000012</td><td>0.000085</td><td>0.006</td></tr><tr><td>12</td><td>0.01448</td><td>0.000011</td><td>0.000100</td><td>0.007</td></tr><tr><td>13</td><td>0.01450</td><td>0.000013</td><td>0.000074</td><td>0.005</td></tr><tr><td>14</td><td>0.01448</td><td>0.000012</td><td>0.000075</td><td>0.005</td></tr><tr><td>15</td><td>0.01447</td><td>0.000012</td><td>0.000080</td><td>0.006</td></tr><tr><td>16</td><td>0.01443</td><td>0.000011</td><td>0.000075</td><td>0.005</td></tr></table></body></html>

The variation of microwave receiver gain of each channel is very small.

# 3.PATHDELAYRETRIEVALALGORITHM

ACMR on board of HY-2 has been working for more than three years.The data of ACMR brightness temperature are matched to that of ECMWF wet tropospheric path delay in 2012.The latitude range of data is between $6 0 ^ { \circ } \mathrm { S }$ and ${ 6 0 ^ { \circ } \mathrm { N } }$ The time and space window are 3O minutes and $0 . 2 5 ^ { \circ }$ in latitudeandlongitude， respectively.ECMWFwet tropospheric path delay data as reference are bilinear interpolated in time and space.All land data and the data within $5 0 ~ \mathrm { k m }$ off land were removed from the matched dataset. One half of the matched data is randomly selected and used to derive retrieval algorithm. The other half is used to validate the algorithm.

The algorithm formula is shown as the following equation : $P D _ { \nu } = \mathrm { a _ { 0 } } + \mathrm { a _ { 1 } } \cdot \ln ( 2 8 0 - \mathrm { T v 1 9 } ) + \mathrm { a _ { 2 } } \cdot \ln ( 2 8 0 - \mathrm { T v 2 3 } ) + \mathrm { a _ { 3 } } \cdot \ln ( 2 8 0 - \mathrm { T v 3 7 } )$

Where

$_ { \mathrm { a 0 = 0 } . 2 5 7 8 }$ ， $_ { \mathrm { a l } = - 0 . 6 5 1 9 }$ ， $_ { \mathrm { a 2 = 0 . 8 5 8 4 } }$ 5 $a 3 \mathrm { = } \mathrm { - } 0 . 2 6 0 9$

Figure 1 shows the wet tropospheric path delay of HY-2 ACMR versus ECMWF.In figure 1,the first half brightness temperature matched data are used to derive retrieval algorithm with ECMWF path delay data.The atmospheric wet path delay of HY-2 is calculated by the algorithm formula.Figure 2 shows histogram of wet tropospheric path delay deviation between HY-2 ACMR and ECMWF.The data are used to validate the algorithm. The wet troposphericpath delay deviationsof algorithmand validation are $1 . 4 6 \mathrm { c m }$ and $1 . 4 7 \mathrm { c m }$ ,respectively.

![](images/3e316d77206a0d8ed4faf1f8cc0aed49acc765cb6544c73ebcbfad3f5df4d21c.jpg)  
Fig.1 wet tropospheric path delay of HY-2 ACMR vsECMWF

![](images/5a3e95d3ef6de11e981f9a949eb7946201ac7eb3c487f7a5626ff628c733e184.jpg)  
Fig.2 histogram of wet tropospheric path delay deviation betweenHY-2ACMRand ECMWF

# 4.CROSS-CALIBRATIONWITHAMR

AMR on board of Jason-2 operates at 18.7GHz,23.8GHz and $3 4 ~ \mathrm { G H z }$ with nadir viewing of wet tropospheric path delay for correcting the altimeter on the same satellite.The frequency channel of ACMR is similar to that of AMR.

Cross-calibration wasdone bycomparing brightness temperatures of ACMR with that of AMR from Oct.14, 2011 to Oct.30，2013.The interval of space is $0 . 5 ^ { \circ }$ in latitude and longitude.The interval of time is 3O minutes. Some data were removed from the matched database:

(1) Data whose central pixels between the AMR and the $3 7 \mathrm { G H z }$ channel of ACMR were more than $0 . 1 ^ { \circ }$ apart; (2) All land data; (3) All cloud data with a liquid water content greater than O in the Jason-2data product; (4) Data within $5 0 \mathrm { k m }$ off land; (5) Data with a brightness temperature greater than $1 6 0 \mathrm { K }$ at $1 8 . 7 \ \mathrm { G H z }$ and $1 7 5 \mathrm { ~ K ~ }$ in the Ka bands when considering rain in the pixels; (6)Data with the latitude greater than 6O considering the path delay algorithm. In total, 8821 pixels of ACMR were matched with that of AMR. Wet tropospheric path delay of ACMR was calculated with the brightness temperature data matched with thatof AMRby the algorithm formula derived in the last chapter. Figure 3 to figure 5 show brightness temperatures of ACMR versus AMR at different channels. Figure 6 shows wet tropospheric path delay of ACMR versus AMR.

Brightness temperatures of AMR are very similar to that of ACMR.The biases are 0.39K, 0.26K,and $- 3 . 6 7 \mathrm { ~ K ~ }$ at 18.7GHz, 23.8GHz and Ka band, respectively. The standard deviationsare1.21K，1.93K and1.56K.InAMR,theKa band frequency is 34GHz. In ACMR，the Ka band frequency is 37GHz.That is why the bias of brightness temperatures is much more in Ka band channel. The average deviation of wet tropospheric path delay is $1 . 2 7 \mathrm { c m }$ The standard deviation is $0 . 6 8 \mathrm { c m }$ Usually, the average deviation can be corrected as a constant. The difference of wet tropospheric path delay retrieved by ACMR and AMR is small.

![](images/00ac887c04caebd9f33cfb907011d54b707609d4d6966f744ae1d4829e9d704d.jpg)  
Fig.3brightness temperaturesofACMRvs AMR at 18.7GHz

![](images/50ab6f6b0f4b679b027e3974b0e6aca4295efe4cc59c9173f05da1d456f9110d.jpg)  
Fig.4brightness temperaturesofACMRvsAMR at 23.8GHz

![](images/7be893f7326230ed6374da39d89c752ae21bf213df2c7c8771ef02fdfea54997.jpg)  
Fig.5 brightness temperatures of ACMR vs AMR at Ka band

![](images/c3d07a8dac719dc59844b28f14f5ba05d201c6fa1c78725c5af0317e375e679f.jpg)  
Fig.6 wet tropospheric path delay of ACMR vs AMR

# 5.CONCLUSION

ACMR on board of HY-2 has been working for more than three years. The data of ACMR brightness temperature are matched to that of ECMWF wet tropospheric path delay in same space and time. The path delay retrieval algorithm is derived and validated. The wet tropospheric path delay deviations of algorithm and validation are $1 . 4 6 \mathrm { c m }$ and $1 . 4 7 \mathrm { c m }$ ，respectively. Cross-calibration wasdoneby comparing brightness temperatures and path delayof ACMR with that of AMR.The standard deviations are 1.21K,1.93K and1.56K at18.7GHz, $2 3 . 8 \mathrm { G H z }$ and Ka band respectively. The average and standard deviations of wet tropospheric path delay are $1 . 2 7 \mathrm { m m }$ and $0 . 6 8 \mathrm { m m }$