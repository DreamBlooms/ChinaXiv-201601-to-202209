# Calorimetric Power Measurements in the EAST ECRH System

Weiye Xu,a) Handong Xu, Fukun Liu, Jian Wang, Xiaojie Wang, Yongzhong Hou Institute of plasma physics,Chinese academy of sciences,Hefei23oo31,China

Abstract: In this paper, the calorimetric power measurement method for electron cyclotron resonance heating system on EAST are presented.This method requires measurement of the water flow through the cooling circuits and the input and output water temperatures in each cooling circuit. Usually, the inlet water temperature is controlled to be stable to get more accurate results.The influence of the inlet water temperature change on the measurement results is analyzed for the first time in this paper.A novel temperature calibration method is proposed also.This kind of calibration method is accurate and effective, and can be easily implemented.

Keywords: Power measurement; Calorimetric method; Data acquisition; EAST tokamak; ECRH.

# I.INTRODUCTION

A 140GHz electron cyclotron resonance heating system for EAST (Experimental Advanced Superconducting Tokamak) is being built in ASIPP (Institute of Plasma Physics,Chinese Academy of Sciences)[1]. This project is designed to inject 4MW/140GHz/10Os RF power to EAST.The first two gyrotrons have ben established already.The two gyrotrons are produced by Gycom and CPIrespectively, and they have been tested in ASIPP.To get an accurate interpretation of the energy balance of the plasma and its response to heating during electron cyclotron resonance heating (ECRH) experiments,a reliable estimate of the RF power delivered to the plasma is needed[2].

There are many methods to measure the millmeter wave power,such as calorimetric method (which may use thermistor sensors,thermoelectric transducers[3],etc.),detection method (which may use diode sensors),etc.These methods which use thermistor sensors,thermoelectric sensors and diode sensors can only measure small power. They can not be used to measure the output power of the gyrotrons directly because the output power is in MW-level. We can use the couplers to couple small amounts of microwave energy from the high power to measure the real power. In addition, we can make big dummy loads which are cooling by water flow for gyrotrons,then we can measure the output power of the gyrotrons by measuring the calories of the dummy load.This method is called the flow calorimetric method,or calorimetric method for short in this paper.The calorimetric method is used to measure the output power of gyrotrons in EAST ECRH system. This method is accurate only when the inlet water temperature is stable.The influence of the inlet water temperature change on the measurement results is analyzed for the first time in this paper.

In this paper, we begin by discussng the calorimetric power measurements. Next, we analyze the calorimetric method when the inlet water temperature is variable.Then, some test results are given. Finally, we give the conclusion.

# II.CALORIMETRICPOWERMEASUREMENTS

The calorimetric measurements require the measurements of the water flow through each cooling circuit and the input and output water temperature in each cooled circuit. We have established a stable data acquisition system to acquire the water flows and the temperatures in each circuit[4]. It is based on the PXI platform. PXI is a rugged PC-based platform for measurement and automation systems [5]. It is widely used in the area of measurement[6,7],data acquisition[8],control[9,1O],etc.In our system,the data is being acquired when the gyrotron is working,being displayed on the monitor in real time, and being saved to the data storage server which are ready to be used for successive analysis procedures.

The architecture of the calorimetric measurement is presented in Fig.1. In EAST ECRH system, temperatures are measured using platinum resistance temperature transmiters to an accuracy of about $\pm$ $0 . 3 ^ { \circ } \mathrm { C }$ ( $\mathrm { 0 \mathrm { { } ^ { \circ } C } }$ to $1 0 0 ^ { \circ } \mathrm { C }$ ）and a resolution of $0 . 0 2 ^ { \circ } \mathrm { C }$ ，water flow is measured using vortex meters to an accuracy of about $1 \%$ F.S.. These measured data then be send to PXI 6229 data acquisition cards [11] through the isolators. PXI 6229 DAQ cards have an accuracy of $3 . 1 \mathrm { m V }$ when the range is -10V to $1 0 \mathrm { V }$ and having a sensitivity of $9 7 . 6 \mu \mathrm { V }$ when the range is $- 1 0 \mathrm { V }$ to 10V. The isolators have an accuracy of $1 0 \mathrm { m V }$ . So,when we set the range of DAQ cards to be $- 1 0 \mathrm { V }$ to $1 0 \mathrm { v }$ , the voltages from OV to $1 0 \mathrm { v }$ are proportional to the temperatures from $0 ^ { \circ } \mathrm { C }$ to $1 0 0 ^ { \circ } \mathrm { C }$ . So, the relative error of temperature measurement is,

$$
\begin{array} { r } { \left| \frac { \Delta T } { T } \right| = \sqrt { \left( \left| \frac { 0 . 3 } { T } \right| ^ { 2 } + \left| \frac { 0 . 1 } { T } \right| ^ { 2 } + \left| \frac { 0 . 0 3 1 } { T } \right| ^ { 2 } \right) } \approx \left| \frac { 0 . 3 1 7 7 } { T } \right| } \end{array}
$$

where $\left| { \frac { 0 . 3 } { T } } \right|$ is caused by temperature transmitters, .01=|| is caused by the isolators, $\begin{array} { r l r } { \left| \frac { 0 . 0 0 3 1 } { T / 1 0 } \right| = } & { { } } & { } \end{array}$ $\left| \frac { 0 . 0 3 1 } { T } \right|$ is caused by the DAQ cards.

Similarly,therelative errorof flowmeasurementis,

$$
\begin{array} { r } { \left| \frac { \Delta F } { F } \right| = \sqrt { \left( \left| \frac { 0 . 0 1 F _ { f u l l } } { F } \right| ^ { 2 } + \left| \frac { 0 . 0 0 1 F _ { f u l l } } { F } \right| ^ { 2 } + \left| \frac { 0 . 0 0 0 3 1 F _ { f u l l } } { F } \right| ^ { 2 } \right) } \approx \left| \frac { F _ { f u l l } } { 1 0 0 F } \right| } \end{array}
$$

where $F _ { f u l l }$ is the preset maximum flow.For instance, $F _ { f u l l }$ is set as $1 0 0 ~ \mathrm { m } ^ { 3 } / \mathrm { h }$ for Gycom Dummy load

The microwave output power generated by a specific gyrotron can be measured by directing the beam to dummy load which is cooled by deionized water. By measuring the inlet water temperatures and the outlet water temperatures of dummy load, we can calculate the power absorbed by dummy load [2,12, 13]. We can use the same way to get the power absorbed by main window[14], MOU, waveguides, waveguide switch, miter bends,and bellows which can be used to estimate the gyrotron output power when the rf power is directed to tokamak. The generated power of gyrotron is the sum of those power data mentioned above. We also use the same way to get the power absorbed by relief load,and relief window.

![](images/36ba69dfcdbd031a5d89489ba57649bf0a32c20d9354a6f9f3b0032e4d08396b.jpg)  
FIG.1.Architecture of calorimetric measurements.

As shown in Fig. 2, $\mathfrak { t } _ { 0 }$ is the initial time. The water,whose temperature is $T i n ( \mathrm { { t } _ { 0 } ) }$ , run through cross section A at time $\mathbf { t } _ { 0 }$ to point B after time St. The temperature of the water is $T o u t ( \mathrm { t } _ { 0 } + \delta \mathrm { t } )$ at the point of B.

![](images/5a03309f2e5c87b9c91a92a8d3a0c5a504397e85b44505557b927dafe424e0b4.jpg)  
FIG .2.Schematic of calorimetric measurements.

We know that the energy rise of the water can be calculated from

$$
W = { \mathsf { C } } \cdot m \cdot \Delta T
$$

where $\mathrm { ^ c }$ is the specific heat capacity of water,m is the mass of the water, $\Delta \mathrm { T }$ is the temperature rise. So, from time $\mathfrak { t } _ { 0 } + \delta \mathfrak { t }$ to time $\mathrm { t } _ { 0 } + \delta \mathrm { t } + \Delta \mathrm { t }$ at point B,the energy rise from point A to point $\mathbf { B }$ is,

$$
W _ { t 0 + \delta { \sf t } + \Delta { \sf t } } = \mathsf C \cdot m \cdot [ T o u t ( { \sf t } _ { 0 } + \delta { \sf t } + \Delta { \sf t } ) - T i n ( { \sf t } _ { 0 } ) ]
$$

where $m = { \boldsymbol { F } } \cdot \Delta \mathrm { t } , { \boldsymbol { F } }$ is the mass flow of water in this circuit, it is controlled to be stable in experiments. So, $F$ can be seen as a constant here. Similarly, from time $\mathbf { t } _ { 0 }$ to time $\mathfrak { t } _ { 0 } + \Delta \mathfrak { t }$ at point $\mathbf { B }$ ,the energy rise is,

$$
W _ { 0 } = \mathsf C \cdot m \cdot [ T o u t ( \mathfrak t _ { 0 } + \Delta \mathfrak t ) - T i n ( \mathfrak t _ { 0 } - \delta \mathfrak t ) ]
$$

So, from time $\mathbf { t } _ { 0 }$ to time $\mathbf { t } _ { \mathrm { n } }$ ,all energy rise from point $\mathbf { A }$ to point $\mathbf { B }$ is,

$$
\begin{array} { r } { W = \sum _ { i = 0 } ^ { n } W _ { i } = \sum _ { i = 0 } ^ { n } \mathsf { C } \cdot F \cdot \Delta \mathsf { t } \cdot \left[ T o u t ( t _ { i } + \Delta \mathsf { t } ) - T i n ( t _ { i } - \delta \mathsf { t } ) \right] } \end{array}
$$

where $t _ { i + 1 } - t _ { i } = \Delta \mathrm { t }$

When $\Delta \mathfrak { t } \to 0$

$$
\begin{array} { r l } & { W = \underset { \Delta \mathrm { t } \to 0 } { \operatorname* { l i m } } \sum _ { i = 0 } ^ { n } \mathsf { C } \cdot F \cdot \Delta \mathsf { t } \cdot [ T o u t ( t _ { i } + \Delta \mathsf { t } ) - T i n ( t _ { i } - \delta \mathsf { t } ) ] = \underset { \Delta \mathrm { t } \to 0 } { \operatorname* { l i m } } \sum _ { i = 0 } ^ { n } \mathsf { C } \cdot F \cdot \Delta \mathsf { t } \cdot [ T o u t ( t _ { i } ) - T i n ( \mathsf { C } \cdot \Delta \mathsf { t } ) ] , } \\ & { T i n ( t _ { i } - \delta \mathsf { t } ) ] = \mathsf { C } \cdot F \cdot \int _ { t _ { 0 } } ^ { t _ { n } } [ T o u t ( t ) - T i n ( \mathsf { t } - \delta \mathsf { t } ) ] d t } \end{array}
$$

Assume the wave-output duration is $\tau$ ,the average power of the gyrotron over the time span $\boldsymbol { \tau }$ can be got by

$$
\begin{array} { r } { P = \frac { W } { \tau } = \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 1 } } ^ { t _ { n } } [ T o u t ( t ) - T i n ( t - \delta { \mathfrak { t } } ) ] d t } \end{array}
$$

We found that when gyrotron ceases generating rf power, the difference between outlet water temperature and inlet water temperature rises still,itcomes to the maximal value after a while,then it descends slowly to zero within 6O seconds after the pulse is ended,as shown inFig.3.This means that energy is absorbed and temporarily stored in structural material with possble thermal loss to the outside.The thermal loss is assumed to be little enough to be ignored. So,

$$
\begin{array} { r } { P = \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { + \infty } [ T o u t ( t ) - T i n ( t - \delta \mathfrak { t } ) ] d t \approx \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - T i n ( t - \delta \mathfrak { t } ) ] d t } \end{array}
$$

![](images/df1590d6b851707b176fde9fce9969ce159efb15c485d0fc0272769ae7ea30a9.jpg)  
FIG.3.The typical signal of temperature difference between output water and input water.The pulse duration is $\tau$ ：

In the measurement,the water temperature at the inlet is kept as an approximate constant, thus,formula

(9) can be simplified to,

$$
\begin{array} { r } { P = \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - \mathrm { T i n } ] d t = \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - T i n ( t ) ] d t } \end{array}
$$

As mentioned before,the absolute error of the measured temperature is about $\pm 0 . 3 1 7 7 ^ { \circ } \mathrm { C }$ ，so，the maximum power error is

$$
\begin{array} { r } { P _ { e r r o r } = \frac { \mathbf { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } \pm 0 . 6 3 5 4 d t = \pm \frac { \mathbf { C } \cdot F } { \tau } \cdot 0 . 6 3 5 4 \cdot ( \tau + 6 0 ) } \end{array}
$$

But when the pulse is very short, the maximum of $T o u t ( t ) - T i n ( t )$ is smaller than $0 . 6 3 5 4 ^ { \circ } \mathrm { C }$ in some circuits. So, the real power,

$$
\begin{array} { r } { P _ { r e a l } = \frac { \large C \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - T i n ( t ) ] d t < \frac { \large C \cdot F } { \tau } \cdot 0 . 6 3 5 4 \cdot ( \tau + 6 0 ) } \end{array}
$$

That is,the relative error of the power can be up to $\pm 1 0 0 \%$ . In order to solve this problem, we must calibrate the temperature difference first. The real temperature difference equals the measured temperature difference plus a base temperature,an example is shown in Fig. 4.

![](images/743943ead8efd836a10f745f41631c8e0ee4970ce3627d6aedfbf33a2abdb1bf.jpg)  
FIG.4.The temperature is influenced by calibration.The relative temperature is more accurate than the absolute temperature,it is influenced by the resolution of the temperature sensor only.

In the case of no RF power transmitted to the load,the inlet water temperature should be equal to the outlet water temperature.But due to the existence of the measurement error of the temperature sensors, the difference between the inlet temperature and the outlet temperature is not zero but an approximate fixed value. So we need to calibrate the temperature measurement to eliminate the error.That is, we need to find the difference value between the outlet water temperature and the inlet water temperature in the absence of RF power.

There are two methods to get the compensation value. One method is using the digital low pas filter to filter out the noise signals of the temperature signals. Then we can get the inlet temperature $T _ { i n }$ and outlet temperature $T _ { o u t }$ . So, the compensation value is,

$$
T _ { c } = T _ { i n } - T _ { o u t }
$$

In the ideal case, the temperature difference after calibration becomes,

$$
\Delta T _ { a c } = T _ { o u t } - T _ { i n } + T _ { c } = 0
$$

So,ideally, when no RF power is transmited to dummy load,the measured power will be approximately equal to zero.In fact, the ambient temperature is not a constant. Even if the water temperature is completely constant, the temperature measured by sensors will always be a litte jitter. So，the compensation value is not particularly accurate using the method of low pass filter.

The other method to get the compensation value is using integral formula (1O). We give a test pulse signal with duration $\tau$ (taking into account the time measurement error, $1 0 \mathrm { s } > \tau > 5 0 0 \mathrm { m s }$ is appropriate) to start the power integral program. Because no RF power transmited to dummy load, the measured power should be zero.But due to the temperature difference between the outlet water and the inlet water, the measured power using formula (1O) is not zero, but is,

$$
\begin{array} { r } { P _ { c a l } = \frac { \mathbb { C } \cdot F } { \tau } \cdot \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - T i n ( t ) ] d t = \frac { \mathbb { C } \cdot F } { \tau } \cdot \Delta  { \boldsymbol \Upsilon } \cdot ( \tau + 6 0 ) } \end{array}
$$

Where, $\varDelta T$ is the average temperature difference between the inlet and the outlet. An example of the waveforms of the calorimetric power measurements in the absence of RF power is shown in Fig. 5.The test pulse duration is O.896s. As we can see,the measured dummy load power is gradually increasing with an approximately constant slope. Using the measured power value, the compensation value can be calculated by,

$$
\begin{array} { r } { T _ { c } = - \Delta T = - \frac { P _ { c a l } \tau } { C F ( \tau + 6 0 ) } } \end{array}
$$

All variables in formula (16) are in the International System of Units.If we change the unit offlow signal $F$ from $\mathrm { \hbar \tilde { \cdot } k g / s ^ { \prime } }$ to the commonly used unit $\cdot \mathrm { m } ^ { 3 } / \mathrm { h } ^ { \prime }$ , the compensation value can be calculated by,

$$
\begin{array} { r } { T _ { c } = - \Delta T = - \frac { 3 . 6 P _ { c a l } \tau } { C F ( \tau + 6 0 ) } } \end{array}
$$

This method is equivalent to find the average temperature difference between the inlet and the outlet. This method is more accurate than the first method of low passfilter. And it is easy to implement because this calibration method is using power measurement principle to calculate the compensation value. We choose this approach to calibrate the temperature measurement. As the ambient temperature and water flow are not constant, we need to calibrate the calorimetric power measurement system periodically to calculate the latest calibration value to get more accurate measurement results.

![](images/6208443f3a0ba1118c2dee1fde6029ac8f676097dc0bafac4b7804a89c3c02e2.jpg)  
FIG.5.An example of the waveforms of the calorimetric power measurements of the dummy load.The dummy load power was measured in the absence of RF power.

The temperature diference error is effectively corrected by calibration.But the resolution of temperature transmittr can cause measurement error also. Actually,after temperature calibration, the power measurement error is caused mostly by the resolution of temperature transmitter and the accuracy of the flow meter. Assume,

$$
\begin{array} { r } { T _ { i n t } = \int _ { t _ { 0 } } ^ { t _ { n } = t _ { 0 } + \tau + 6 0 } [ T o u t ( t ) - T i n ( t ) ] d t } \end{array}
$$

Then, we have,

$$
P _ { r e a l } = \frac { \mathbf { C } \cdot F } { \tau } \cdot T _ { i n t }
$$

In the worst case,the relative error of measured power is,

$\begin{array} { r } { \delta _ { p o w e r } \approx \pm \left[ \left| \frac { \partial \ln ( P _ { r e a l } ) } { \partial F } \Delta F \right| + \left| \frac { \partial \ln ( P _ { r e a l } ) } { \partial T _ { i n t } } \Delta T _ { i n t } \right| + \left| \frac { \partial \ln ( P _ { r e a l } ) } { \partial \tau } \Delta \tau \right| + \left| \frac { \partial \ln ( P _ { r e a l } ) } { \partial C } \Delta C \right| \right] = \pm \left( \left| \frac { \Delta F } { F } \right| + \left| \frac { \Delta T _ { i n t } } { T _ { i n t } } \right| + \left| \frac { \partial \ln ( P _ { r e a l } ) } { \partial \tau } \Delta \tau \right| \right) . } \end{array}$ 亚+) (20)

where $\Delta F , \Delta T _ { i n t } , \Delta \tau$ is the absolute error of flow, temperature integral，wave-output duration respectively.In our system,as see in formula (2),

$$
\begin{array} { r } { \left| \frac { \Delta F } { F } \right| \approx \left| \frac { F _ { f u l l } } { 1 0 0 F } \right| } \end{array}
$$

In our system, the duration measurement error is about lms,and less than $2 \mathrm { m s }$ in the worst case,

$$
\Delta \tau < 2 m s = 0 . 0 0 2 s
$$

We set the specific heat capacity of water as,

$$
\mathrm { C } = 4 . 1 8 \mathrm { k J / ( k g \cdot ^ { \circ } C ) }
$$

But actually, the specific heat capacity will change along with the temperature and the pressure,as shown in Table 1.And the water temperature is between O and $1 0 0 ~ \mathrm { { ^ \circ C } }$ and the water pressure is between O.1 MPa and 1 MPa. So,the maximum relative error of the specific heat capacity is,

$$
\begin{array} { r } { \left| \frac { \Delta \mathrm { C } } { \mathrm { C } } \right| = \frac { 4 . 2 1 7 - 4 . 1 8 } { 4 . 2 1 7 } \times 1 0 0 \% \approx 0 . 8 8 \% } \end{array}
$$

TABLE1. Liquid water specific heat capacity at constant pressure along with the temperature and the pressure. The unit is $\mathrm { k J / ( k g \cdot ^ { \circ } C ) }$   

<html><body><table><tr><td rowspan="2">Pressure (MPa)</td><td colspan="4">Temperature (℃)</td></tr><tr><td>0</td><td>20</td><td>50</td><td>100</td></tr><tr><td>0.1</td><td>4.217</td><td>4.182</td><td>4.181</td><td></td></tr><tr><td>0.5</td><td>4.215</td><td>4.181</td><td>4.180</td><td>4.215</td></tr><tr><td>1.0</td><td>4.212</td><td>4.179</td><td>4.179</td><td>4.214</td></tr></table></body></html>

The typical temperature difference curves are shown in Fig. 6. Assume $T _ { m a x }$ is the maximum of the diference between final and initial water temperatures in each circuit, $t _ { r }$ is the duration when temperature difference rise from zero to maximum (It is related to the response time of temperature transmitter,the character of load,and the gyrotron pulse duration). As we can see,

$$
T _ { i n t } \approx \mathrm { m a x } ( \tau , t _ { r } ~ ) \cdot T _ { m a x }
$$

Because the temperature resolution eror is $\pm 0 . 0 2 \mathrm { ~ } ^ { \circ } \mathrm { C }$ , in the worst case,

$$
\Delta T _ { i n t } \approx 0 . 0 4 \cdot ( \tau + 6 0 )
$$

Hence,

$$
\begin{array} { r } { \left| \frac { \Delta T _ { i n t } } { T _ { i n t } } \right| \approx \frac { 0 . 0 4 \cdot ( \tau + 6 0 ) } { \operatorname* { m a x } ( \tau , t _ { r } ~ ) \cdot T _ { m a x } } } \end{array}
$$

But due to the randomness of the temperature resolution error, usually, we have,

$$
\Delta T _ { i n t } \approx 0
$$

So,the maximum calorimetric measurement error is,

$$
\begin{array} { r } { \delta _ { p o w e r } \approx \pm \left( \frac { F _ { f u l l } } { F } + \frac { 4 \cdot ( \tau + 6 0 ) } { \operatorname* { m a x } ( \tau , t _ { r } \ ) \cdot T _ { m a x } } + \frac { 0 . 2 } { \tau } + 0 . 8 8 \right) \% } \end{array}
$$

The probable calorimetric measurement error is,

$$
\begin{array} { r } { \delta _ { p o w e r } \approx \pm \left( \frac { F _ { f u l l } } { F } + \frac { 0 . 2 } { \tau } + 0 . 8 8 \right) \% } \end{array}
$$

where $F$ is the mass flow of water in each circuit; $T _ { m a x }$ is the maximum of the difference between final and initial water temperature in each circuit; $\tau$ is wave-output duration; $t _ { r }$ is the duration when temperature difference rise from zero to maximum,for instance, $t _ { r } \approx 3 s$ for waveguide dummy load of CPI gyrotron when the pulse duration is $2 \ \mathrm { s } , t _ { r } \approx 1 4 \ s$ for aluminum tank dummy load of CPI gyrotron when the pulse duration is $2 \mathrm { ~ s ~ }$ $t _ { r } \approx 1 3 s$ for dummy load of Gycom gyrotron when the pulse duration is 5 s. And allparameters are in standard international unit. When the gyrotron pulse duration is bigger than 1 s,the relative error of calorimetric measurement is less than $10 \%$ and less than $5 \%$ in most cases.

![](images/4aa8ba100e264123beb2de75e4a345c245149f17c8522064588a0c10daa3576e.jpg)

FIG.6.The temperature difference between outlet and inletof dummy load cooling circuit.The figure above shows the situation when tr is bigger than t.The figure below shows the situation when tr is smaller than $\tau$

# III. CALORIMETRIC MEASUREMENTS WHENTHE INLETWATER TEMPERATURE ISVARIABLE

When the water temperature at the inlet is variable,the power measurement can be got by formula (9). Firstly,the parameter St should be measured.Assume the water flow is $\mathrm { F }$ ，the water volume of the dummy load is $\mathrm { \Delta V }$ ,then, we have,

$$
\begin{array} { r } { \delta t = \frac { V } { F } } \end{array}
$$

where $\mathrm { ~ F ~ }$ is volume flow in the unit of $\mathrm { m } ^ { 3 } / \mathrm { h }$ . We can get the volume $\mathrm { \Delta V }$ by injecting water to the empty dummy load,assume the volume flow of water is $\mathrm { F } _ { 0 }$ ,the spend time from beginning to inject the water to the time when the outlet flow out water is Sto. So,

$$
\begin{array} { r } { V =  { \mathrm { F } _ { 0 } } \cdot \delta  { \mathrm { t } _ { 0 } } } \\ { \delta t = \frac {  { \mathrm { F } _ { 0 } } \cdot \delta  { \mathrm { t } _ { 0 } } } { F } } \end{array}
$$

In theory,the power can be measured by formula (9)and(33) when the inlet water temperature is variable. But in fact, the real-time measurement of the water temperature is difficult. In our system, the maximum response time ofthe temperature transmitter is about 18s. So,this measurement method is not so accurate because the temperature measurement delay. Usually, we measure the power by keeping the inlet water temperature as a constant. But for verifying this measurement theory is correct, we do some experiments.

As shown in Fig.7,the inlet water temperature increases gradually at a constant slope.Wecan get the correct power using formula (9). The definite integral is calculated as the green rectangle shown. The temperature difference at time t should be the outlet water temperature at time t minus the inlet water temperature at time $t \mathrm { - } \delta t$ 、But if we use formula (1O) to calculate the power,the definite integral is calculated as the brown rectangle shown, the temperature difference is $\varDelta T$ less than the correct value in every moment. So, the measurement result using formula (1O) will be smaler than the correct result.

![](images/56c05f3dc3e72fb84f8c31d7980431d58d0d42bf3b895b509800610fe78242a6.jpg)  
FIG.7. The temperature of the outlet water and the inlet water along with the time when the inlet water temperature is gradually increasing.The black curve indicates the outlet water temperature and the blue curve indicates the inlet water temperature.

We make the inlet water temperature increase gradually in the gyrotron pulse,and use formula (10) to calculate the power.Some test results are shown in Table 2.Especially,shot number lis measured when the inlet water temperature is gradually increasing in the pulse duration. Obviously,the power test results (506kW,812 kW) are smaller than the real value (546 kW,849 kW). The temperature difference of the dummy load circuit is shown in Fig. 8.The inlet water temperature rose $0 . 0 9 \mathrm { ~ } ^ { \circ } \mathrm { C }$ after $6 0 \mathrm { ~ s ~ }$

When we use formula (1O) to calculate the power, the temperature difference is $\Delta \mathrm { T }$ less than the correct value in every moment,and,

$$
\begin{array} { r } { \delta t = \frac { \Delta T } { 0 . 0 9 } \times 6 0 } \end{array}
$$

By formula (1O), we can get,

$$
{ \frac { F _ { V } { \cdot } { } ^ { \mathsf { C } } { \cdot } { \mathsf { A } } T { \cdot } 6 0 } { 3 . 6 \cdot { } \tau } } = { \frac { 4 2 { \times } 4 1 8 0 { \times } \Delta T { \times } 6 0 } { 3 . 6 \times 1 } } = 2 9 2 6 \times 1 0 ^ { 3 } \cdot \Delta T = 5 4 6 \times 1 0 ^ { 3 } - 5 0 6 \times 1 0 ^ { 3 } = 4 0 \times 1 0 ^ { 3 }
$$

where, $F _ { V }$ is the volume flow with the unit of $\mathrm { m } ^ { 3 } / \mathrm { h }$ , change it to the mass flow $F$ with the unit of $\mathrm { k g / s }$

$$
\begin{array} { r } { F = \frac { F \cdot 1 0 0 0 } { 3 6 0 0 } = \frac { F _ { V } } { 3 . 6 } \ ( { \mathrm { k g } } / { s } ) } \end{array}
$$

So,

$$
\Delta T \approx 0 . 0 1 3 7 ^ { \circ } \mathrm { C }
$$

$$
\begin{array} { r } { \delta t = \frac { \Delta T } { 0 . 0 9 } \times 6 0 \approx 9 . 1 s } \end{array}
$$

Similarly, for the collector power, we have,

$$
{ \frac { F _ { Y } \cdot { } ^ { \mathsf { C } } \cdot { \mathsf { A } } T \cdot 6 0 } { 3 . 6 \cdot \tau } } = { \frac { 3 9 . 1 \times 4 1 8 0 \times \Delta T \times 6 0 } { 3 . 6 \times 1 } } = 2 7 2 4 \times 1 0 ^ { 3 } \cdot \Delta T = 8 4 9 \times 1 0 ^ { 3 } - 8 1 2 \times 1 0 ^ { 3 } = 3 7 \times 1 0 ^ { 3 }
$$

So,

$$
\Delta T \approx 0 . 0 1 3 6 ^ { \circ } \mathrm { C }
$$

Because the inlet water temperature of collctor is same as that of dummy load, the inlet water temperature rose $0 . 0 9 \mathrm { ~ \textdegree C }$ after $6 0 ~ \mathrm { s }$

$$
\begin{array} { r } { \delta t = \frac { \Delta T } { 0 . 0 9 } \times 6 0 \approx 9 . 1 s } \end{array}
$$

The analysis above is not very accurate because the temperature measurement is not exactly accurate, and the inlet water temperature increased gradually at just a nearly constant slope,but not a real constant slope.

TABLE 2.Power measurement results when the inlet water temperature is graduall increasing (No.1),and results when the inlet water temperature is a constant ( $\mathrm { N o } . 2 \sim \mathrm { N o } . 6 )$ . All these data are measured when the pulse duration is ls with the cathode voltage is $- 4 4 \mathrm { k V }$ ,the anode voltage is $2 1 \mathrm { k V }$ ,the main magnetic current is $5 0 . 4 \mathrm { A }$ ,the filament voltage is $3 3 . 4 \mathrm { V }$ ,and the filament current is $3 4 \mathrm { A }$   

<html><body><table><tr><td>No.</td><td>Dummy Load Power/kW</td><td>Probable Error / %</td><td>Average Dummy Load Power/kW</td><td>Collector Power/kW</td><td>Average Collector Power/kW</td><td>Probable Error / %</td></tr><tr><td>1</td><td>506</td><td></td><td>506</td><td>812</td><td>812</td><td></td></tr><tr><td>2</td><td>544</td><td></td><td></td><td>847</td><td></td><td rowspan="4"></td></tr><tr><td>3</td><td>531</td><td></td><td></td><td>841</td><td></td></tr><tr><td>4</td><td>560</td><td>3.5</td><td>546</td><td>855</td><td>849 3.6</td></tr><tr><td>5</td><td>538</td><td></td><td></td><td>849</td><td></td></tr><tr><td>6</td><td>557</td><td></td><td></td><td>851</td><td></td><td></td></tr></table></body></html>

![](images/e5d5771e78e456f9d558d47bf69912573b742046f44a0082ef7de72df8ee6943.jpg)  
FIG.8.The temperature of the dummy load outlet water and the inlet water along with the time in shot number 1. The blue curve indicates the outlet water temperature and the red curve indicates the inlet water temperature.

As shown in Fig.9, when the inlet water temperature is decreasing gradually,the analysis is similar with that when the inlet water temperature increased gradually. We can get the correct power use formula (9), the definite integralis calculated as the green rectangle shown. But if we use formula (1O) to calculate the power, the definite integral is calculated as the brown rectangle shown,the temperature difference is 4Tbigger than the correct value in every moment. So, the measurement result using formula (lO) will be bigger than the correct result.

![](images/35c2b8cfe511902c17ea130a1fc7163bf5efc8283f7d9b7ef365b7378f8eb1c8.jpg)  
FIG.9.The temperatureofthe outlet water and the inlet wateralong with the time when the inlet water temperature is gradually decreasing.The black curve indicates theoutlet water temperature and the bluecurve indicates the inlet water temperature.

# IV. TEST RESULTS

We have tested our gyrotrons and got the output power using calorimetric method. Up to now, the #1 Gycom gyrotron has demonstrated $9 0 0 \mathrm { k W }$ output power ( $8 1 3 { \mathrm { ~ k W } }$ power is absorbed by dummy load) for $1 0 ~ \mathrm { s }$ with cathode voltage of $- 4 5 . 5 \mathrm { k V }$ and anode voltage of $2 4 \mathrm { k V }$ at about $48 \%$ electrical efficiency. Some related key signals are shown in Fig. 1O.And the #1 Gycom gyrotron has demonstrated $6 4 4 \mathrm { k W }$ output power ( $5 8 5 \mathrm { k W }$ power is absorbed by dummy load) for $7 5 4 \mathrm { s } [ 1 ]$ with cathode voltage of $- 4 4 . 5 \mathrm { k V }$ and anode voltage of $2 4 \mathrm { k V }$ at about $5 3 \%$ electrical efficiency.

The $\# 2$ CPI gyrotron has got about $4 9 9 \mathrm { k W }$ output power ( $\mathbf { \Psi } _ { 4 4 9 \mathrm { k W } }$ power is absorbed by aluminum tank dummy load and waveguide dummy load) for 79.66 s with cathode voltage of $- 5 7 \ \mathrm { k V }$ and anode voltage of $2 1 \mathrm { k V }$ at about $2 7 . 1 \%$ electrical efficiency and has got about $7 2 1 \mathrm { k W }$ output power ( $\mathbf { \hbar } ^ { 6 4 9 \mathrm { k W } }$ power is absorbed by aluminum tank dummy load and waveguide dummy load) for $5 1 7 \mathrm { m s }$ with cathode voltage of $- 5 9 \mathrm { k V }$ and anode voltage of $2 2 \mathrm { k V }$ at about $3 5 . 2 \%$ electrical efficiency. Some related signals are shown in Fig.11 and Fig.12.The long-pulse and high-power test is stopped by dummy load leaking problem.

![](images/90182222d2c1de2cd17af6c45e4fb48e67c73f95ed033f5a5de655eef9d04ab2.jpg)  
FIG.10. The key signals of Gycom gyrotron at $9 0 0 \mathrm { k W }$ output power.

![](images/edb3643a2ab6b8632b369924913e52a80deebfcaaf453ed1470982f8057dc599.jpg)  
FIG.11. The key signals of CPI gyrotron at $4 9 9 \mathrm { k W }$ output power.

![](images/2b8db0a45c310d5827fe3ff023bf644b2dfb6481b34c3956adfa5e6dd6bad97c.jpg)  
FIG.12. The key signals of CPI gyrotron at $7 2 1 \mathrm { k W }$ output power.

Except the dummy load and the collctor,we measured the power of the other cooling circuits,such as Main Window, MOU etc.[15] The test results for #1 Gycom gyroton are shown in Table 3,and the probable calorimetric measurement error,water flow,and pressure drop for each cooling circuit are shown in Table 4.The power consumption is the sum of the cathode power and the anode power which are the product of voltage and current. As we can see,the sum of calorimetric power in al measured cooling circuits is approximately equal to the power consumption. It can prove that the calorimetric method is self-consistent, and the calorimetric measurement results are credible.

TABLE 3.The power of all measured cooling circuits for Gycom gyrotron.The power is in the unit of kW.   

<html><body><table><tr><td>No.</td><td>Pulse Duratio n (s)</td><td>Power Consump tion</td><td>Dummy Load Power</td><td>Collect or Power</td><td>MainW indow Power</td><td>Relief Window Power</td><td>Relief Load Power</td><td>Test Bench Power</td><td>MOU Power</td><td>Output RF Power</td><td>Sum of Calorim etric Power</td></tr><tr><td>1</td><td>99.961</td><td>1005</td><td>306</td><td>644</td><td>0.62</td><td>1.07</td><td>4.5</td><td>5.45</td><td>23.2</td><td>334.65</td><td>984.84</td></tr><tr><td>2</td><td>99.981</td><td>1114. 7</td><td>388</td><td>652.4</td><td>0.69</td><td>1. 62</td><td>6.56</td><td>8.33</td><td>30.32</td><td>426.65</td><td>1087.92</td></tr></table></body></html>

TABLE 4.The probable calorimetric measurement error, water flow,and pressure drop for each cooling circuit.   

<html><body><table><tr><td>Cooling Cuicuit</td><td>Dummy</td><td>Collector</td><td>Main Windo</td><td>ReliefWindow</td><td>Relief Load</td><td>Test Bench</td><td>M0</td></tr><tr><td>Probable Calorimetric Measurement</td><td>3.3</td><td>3.4</td><td>5.2</td><td>5.4</td><td>2.8</td><td>2.8</td><td>3.8</td></tr><tr><td>Error (%) Water Flow (m³/h)</td><td>42</td><td>39.6</td><td>2.3</td><td>2.2</td><td>5.2</td><td>5.1</td><td>3.4</td></tr><tr><td>Pressure Drop</td><td>0.3</td><td>0.3</td><td>0.3</td><td>0.5</td><td>0.3</td><td>0.3</td><td>0.5</td></tr><tr><td>(MPa)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# V.CONCLUSION

Calorimetric measurement system has been established to measure the rf power generated by gyrotrons. The calorimetric measurements when the water temperature at the inlet is invariable or variable are discussed respectively. For getting more accurate results, we usually measure the dummy load power by keeping the inlet water temperature as a nearly constant. And the calorimetric measurement uncertainty has been discussed.The test results show that the calorimetric method is self-consistent and is credible for power measurements.

# ACKNOWLEDGMENTS

This work was supported by the National Magnetic Confinement Fusion Science Program of China (Grant No.2011GB102000,No.2015GB103000) and the Science Foundation of Institute of Plasma Physics Chinese Academy of Sciences (Grant No. Y45ETY230B). And we greatly appreciate the experts from CPI, GYCOM and GA for the cooperation in the development of ECRH project on EAST.

# REFERENCES

[1]H.Xu,X.Wang,F.Liu,J.Zhang,Y.Huang,J.Shan,D.Wu,H.Hu,B.Li,M.Li,Y.Yang,J.Feng,W.Xu,Y.Tang,W.Wei, L. Xu,Y.Liu,H.Zhao,J.Lohr,Y.A.Gorelov,JP.Anderson,W.Ma,Z.Wu,J.Wang,L.Zhang,F.Guo,H.Sun,X.Yan,T.East, Development and PreliminaryCommisioning Resultsof aLongPulse140 GHz ECRH Systemon EASTTokamak(Invited), Plasma Science and Technology,18 (2016) 442-448.   
[2]A.Bruschi,F.Gandini,V.Muzzini,N.Spinicchia,S.Cirant,G.Gitin,G.Graucc,V.Mellera,A.Nardone,A.o C.Sozzi,CalorimetricloadsforhighpowertransmissonlinesatmilimeterwavelengthsFusionEngDes,56-57(O)649-654. [3]H.Toda,K.Sasaki,Y.Nakagawa,ISugiura,AMatched-LoadTypeThermoelectricTransducerforPower Measurements in the Millimeter-Wave Region,Instrumentation and Measurement,IEEE Transactions on,23 (1974) 408-413.   
[4]W.Xu,H.Xu,F.Liu,F.Hou,Z.Wu,Data acqusitionsystemforelectroncyclotronresonance heatingonEASTtokamak, Fusion Eng Des,113 (2016) 119-125.   
[5] What Is PXI [Online]. Available: http://www.ni.com/pxi/whatis/   
[6]J.Kourunen,T.avolainen,A.Lehikonen,M.Vauhkonen,L.M.Heikinen,SuitabilityofaPXIplatformfoanlectrical impedance tomography system,Meas Sci Technol,20 (2009) 015503.   
[7]S.Ducourtieux,B.Poyet,Developmentofametrologicalatomicforcemicroscope withinimizedAbbeerroranddiferetial interferometer-based real-time position control,Meas Sci Technol,22 (2O11) 094010.   
[8]H.D.Pujara,R.Rajpal,A.K.ivastava,ASar,PXIbasedlosslessontiuousdataacqusitionystemforeadystate tokamaks,21st IEEE/NPSS Symposium on Fusion Engineering - SOFE 05,(2006) 529-531.   
[9] S.X.Ma,M.Zhang,D.H. Chen,L.L. Xia,Z. Zeng,X.L. Zhang,C.L.Wang,K.X.Yu,A Control System Basedon PXI Technology for the ECRHPower Supply of J-TEXT,Ieee TPlasma Sci,42 (2014) 1709-1713.   
[10] Z.C.Zhang,Z.S.Ji,B.J.Xiao,F.Yang,Y.Wang,Z.H.Xu,J.Liu,The upgradeof EASTcentralcontrol system inPXI platforms,Fusion Eng Des,89 (2014) 582-587.   
[11] NI PXI-6229 [Online]. Availabe: http://sine.ni.com/nips/cds/view/p/lang/en/nid/14137   
[12]L.Gorelov,J.Lohr,R.BaityJr,P.Cahalan,R.Calis,D.Ponce,H.Chiu,Gyrotronpowerbalancebasedoncalorimetric measurementsintheD-DECHsystem,in:FusionEnginering,2003.20th IEE/NPSS Symposiumon,IEEE,2003,pp.546- 548.   
[13]H.Wang,Z.H.Lu,S.Kubo,G.Y.Chen,C.Wang,J.Zhou,M. Huang,J.Rao,Power measurementsystemofECRHon HL2A,Ec18-18th Joint Workshopon Electron Cyclotron Emission and Electron Cyclotron Resonance Heating,87 (2015). [14]G.Michel,H.Laqua,W.Kasparek,Calorimetric measurementof the microwavepowertransmited throughadiamond window,Fusion Engineering&Design,s 56-57(2001) 655-660.   
[15] W.Xu,H.Xu,F.Liu,Y.Tang,Z.Wu,X.Wang,J.Wang,J.Feng,Millmeter Wave Power MonitoringinEASTECRH System,IEEE Access,4(2016) 5809-5817.