# 浅析水电厂AVC控制策略

凌胜军 马景浩

（国投甘肃小三峡发电有限公司兰州 730050)

![](images/ab238efa979acdbb3f324679b8aafcbad79230fc769eadf1f8553abd0a237733.jpg)

凌胜军男1974年生，高级工程师，从事水电厂自动化工作。

摘要：电压是电能质量的重要指标，自动电压控制（AVC）是以系统中各条母线电压合格为约束条件，进行无功-电压优化，并向设备下发控制命令的调节过程。水电厂AVC是按照预定的策略自动控制电厂母线电压或全厂无功功率，通过调节电厂的无功功率使得母线电压稳定在可靠的区间。分析了水电厂AVC设定方式、控制模式、无功分配、安全及注意事项等控制策略，包括系统状况、变压器运行方式、机组振动区等，提出AVC在调节滞后、调节容量、设定区间几方面的优化策略，合理地制定AVC控制策略，既满足了系统的要求，也保证了水电厂设备的安全可靠运行。

关键词：水电厂AVC 控制策略中图分类号：TM622

# Analysis of Control Strategy for AVC in Hydropower Station

Ling ShengjunMa Jinghao(SDIC Gansu Xiaosanxia Power Co.Ltd. Lanzhou730050 China）

![](images/3309940cc1ab647bbfd819af4d580e1b0f65e3d0082418e178cbe85eacd1c2c4.jpg)

马景浩男 1972年生，高级工程师，从事水电厂生产、技术、运行管理工作。

Abstract: Voltage is an important indicator of power quality. Automatic voltage control (AVC) to the busbar voltage of the system qualified for the restraint conditions, Reactive power and voltage optimization, distributed to the equipment control command of the adjustment process. Hydropower plant AVC is in accordance with the predetermined strategy to automatically control the power plant bus voltage or the whole plant reactive power,Adjusting the reactive power of the bus voltage stability in a reliable range. The AVC setting way, control mode, reactive power distribution， safety and precautions control strategies of hydropower plant are analyzed, including system status, operation mode,and unit vibration. Making AVC a reasonable control strategy, not only to meet the requirements of the system,but also to ensure the safe and reliable operation of hydropower equipment.

Keywords: Hydropower station, automatic voltage control (AVC), control strategy

# 1 引言

电压是电能质量的重要指标，电压偏差大会给用电设备带来较大的危害甚至影响到电网的安全。电网规模越来越大，对电压的要求也越来越高，电压的控制方式不再能满足电网安全、可靠的要求。自动电压控制（AutomaticVoltageControl，AVC）是以系统中各条母线电压合格为约束条件，以电网功率损耗最小为目标，进行无功－电压优化，并向设备下发控制命令的调节过程。

水电厂AVC是按照预定的条件和要求自动控制电厂母线电压或全厂无功功率，通过调节电厂的无功功率使得母线电压稳定在可靠的区间，根据母线电压设定值及当前值得出电压偏差或无功功率偏差，按照调压系数计算出需要调节的无功功率值，在满足电厂及机组的安全条件下，以预定的控制策略调节机组的无功功率，使电厂母线电压符合电网的要求，提高电力系统的稳定性。水电厂AVC控制策略有AVC设定方式、控制模式、无功分配策略、安全策略及注意事项，还包括系统状况、变压器运行方式、机组振动区等多个策略，最后提出AVC在调节滞后、调节容量、设定区间几方面的优化策略。

# 2 AVC控制方式

# 2.1水电厂AVC系统结构

图1为水电厂AVC系统结构图，包括调度端主站、广站端子站监控系统、机组现地控制单元、机组励磁系统、发电机组等。调度端主站通过远动通信与厂站端子站监控系统传输四遥数据，即遥测、遥信、遥控、遥调，厂站端子站监控系统向调度端主站上传的遥测量有机组有功功率、无功功率、母线电压等，遥信量有机组出口断路器状态、机组及全厂AVC状态、机组各刀开关状态等；调度端主站向厂站端子站监控系统下发的遥调量为母线电压设定值、全厂有功功率设定值，遥控量有机组开机、停机，增励磁、减励磁。

![](images/2850e05f2a08bb56ce1823973dbe6c6dbde9871e5e470acf040b53fd61835d4e.jpg)  
图水电厂AVC系统结构图  
Fig.1 Structure ofAVC system in hydropower station

# 2.2AVC设定方式

发电机无功功率、机端电压与励磁电流有关，当励磁电流变化时，发电机的无功功率和机端电压也相应变化，进而影响母线电压，通过励磁系统的励磁调节器可以增减励磁电流，最终调节和改变母线电压，因此，AVC可以选择电厂母线电压或无功功率作为设定值来调节、控制，AVC的设定方式有无功功率设定和母线电压设定。

（1）无功功率方式。AVC调度端主站或子站电厂监控系统可直接将无功功率设定在电厂AVC系统中，设定值为全厂无功功率减去未参加AVC的机组无功值，在其他参加AVC的机组间分配，即

$$
\mathcal { Q } _ { \mathrm { A V C } } = \mathcal { Q } _ { \mathrm { S E T } } - \overline { { \mathcal { Q } } } _ { \mathrm { A V C } }
$$

式中， $\varrho _ { \mathrm { A V C } }$ 为全厂无功分配值； $\scriptstyle Q _ { \mathrm { S E T } }$ 为全厂无功设定值； $\bar { Q } _ { \mathrm { A V C } }$ 为不参加AVC 机组无功值。

(2）母线电压方式。AVC主站或电厂监控系统可直接将母线电压设定在AVC系统中，设定值为电厂母线电压，母线电压根据调压系数（即电压与无功功率的关系）设定电压值与当前实际母线电压值的差值，差值按照调压系数转换为需要改变的无功功率值，将此无功功率值与当前实际无功值及不参加AVC机组无功值计算后分配到参加AVC的机组，母线电压设定为大部分AVC电厂的设定方式，母线电压设定还分为曲线方式和定值方式，当设定为曲线方式时，设置AVC的运行区间，即母线电压的上限、下限范围，AVC实时检测母线电压是否在设定值范围内，当母线电压超过设定的上限、下限时，AVC即进行调节控制；当母线电压设定为定值方式时，AVC根据设定值进行分配，AVC死区按照不同电网或机组容量设置，当全厂母线电压实际值超过死区时，AVC按照设定值与实际值的差值分配，当全厂母线电压实际值与设定值在死区内时，AVC不做分配。调压系数计算式为

$$
\begin{array} { r } { \boldsymbol { \mathcal { Q } } _ { \mathrm { A V C } } = \boldsymbol { \mathcal { Q } } _ { \mathrm { A C T } } + \Delta V \boldsymbol { K } _ { \mathrm { V N O R } } - \boldsymbol { \bar { \mathcal { Q } } } _ { \mathrm { A V C } } } \end{array}
$$

式中， $\varrho _ { \mathrm { A V C } }$ 为全厂无功分配值； $\varrho _ { \mathrm { A C T } }$ 为当前实发无功值； $\Delta V$ 为实际母线电压与设定电压值偏差； $K _ { \mathrm { V N O R } }$ 为调压系数； $\bar { Q } _ { \mathrm { A V C } }$ 为不参加AVC机组无功值。

# 2.3控制模式

（1）调度端主站模式。电厂AVC调度端主站控制模式有两种：全厂控制模式和单机控制模式。全厂控制模式时，电厂AVC子站接收AVC调度端主站下发的电厂侧母线电压设定值并计算得出电厂需要承担的无功功率，将无功功率合理分配给参加AVC的机组，通过现地控制单元向发电机的励磁系统发送增减磁信号以调节发电机无功功率，使母线电压达到控制设定，实现全厂AVC。单机控制模式下，电厂AVC子站直接接收AVC调度端主站下发的每台机组的无功功率设定值，通过现地控制单元向发电机的励磁系统发送增减磁信号以调节发电机无功功率，使各机组无功功率达到设定值。水电厂AVC主站控制模式一般都采用全厂控制模式。

(2）控制端模式。AVC控制端模式一般有现地和远方两种。当控制端为远方时，由主站计算AVC设定值，依据预定和要求的分配策略将设定值分配到各台参加AVC的机组。当控制端为现地时，由电厂监控系统计算AVC的设定值，依据预定和要求的分配策略将设定值分配到各台参加AVC的机组。

# 3 AVC负荷分配策略

AVC按照机组无功功率变化实现母线电压的控制。AVC无功功率分配策略主要有无功成比例分配策略、等功率因数分配策略、相似调整裕度分配策略等。无功功率的调整首先由调相运行的机组承担，剩余的部分由参加无功调节的机组分担。

# 3.1无功成比例策略

无功成比例分配策略计算式为

$$
\mathcal { Q } _ { \mathrm { i A V C } } = \mathcal { Q } _ { \mathrm { S E T } } \times \frac { \mathcal { Q } _ { \mathrm { i M a x } } } { \sum _ { i = 1 } ^ { n } \mathcal { Q } _ { \mathrm { i M a x } } } \qquad i = 1 , 2 , \cdots , n
$$

式中， $n$ 为参加AVC的机组数量； $\scriptstyle Q _ { \mathrm { S E T } }$ 为AVC无功设定值； $\boldsymbol { Q } _ { i \mathrm { M a x } }$ 为参加 AVC的第 $i$ 台机组的最大无功容量； $\sum _ { i = 1 } ^ { n } { Q _ { i { \mathrm { M a x } } } }$ 为参加AVC 机组的最大无功容量之和； $\boldsymbol { \mathcal { Q } } _ { \mathrm { { i A V C } } }$ 为AVC分配到第 $i$ 台参加AVC 机组的无功。

# 3.2等功率因数策略

等功率因数分配策略计算式为

$$
\mathcal { Q } _ { \mathrm { i A V C } } = \mathcal { Q } _ { \mathrm { S E T } } \times \frac { P _ { i } } { \sum _ { i = 1 } ^ { n } P _ { i } } \qquad i = 1 , 2 , \cdots , n
$$

式中， $n$ 为参加AVC的机组数； $\boldsymbol { \mathcal { Q } } _ { \mathrm { S E T } }$ 为AVC无功设定值； $P _ { i }$ 为参加AVC的第 $i$ 台机组的当前有功实发值； $\sum _ { i = 1 } ^ { n } P _ { i }$ 为参加 AVC 机组的当前有功实发值

之和； $\boldsymbol { Q } _ { \mathrm { { i A V C } } }$ 为AVC分配到第 $i$ 台参加AVC 机组的无功。

# 3.3相似调整裕度策略

相似调整裕度分配策略计算式为

$$
\mathcal { Q } _ { i \mathrm { A V C } } = \mathcal { Q } _ { \mathrm { S E T } } \times \frac { \mathcal { Q } _ { i \mathrm { M a x } } - \mathcal { Q } _ { i } } { \sum _ { i = 1 } ^ { n } ( \mathcal { Q } _ { i \mathrm { M a x } } - \mathcal { Q } _ { i } ) }
$$

式中， $n$ 为参加AVC的机组数； $\boldsymbol { \mathcal { Q } } _ { \mathrm { s E T } }$ 为AVC无功设定值； $Q _ { i \mathrm { M a x } } - Q _ { i }$ 为参加AVC的第 $i$ 台机组的无功调整裕度； $\sum _ { i = 1 } ^ { n } ( { Q _ { i } } _ { \mathrm { M a x } } - { Q _ { i } } )$ 为参加AVC 机组的当前无功调整裕度之和； $\textstyle Q _ { i \mathrm { A V C } }$ 为AVC分配到第 $i$ 台参加AVC机组的无功。

# 4 AVC安全控制策略

电厂AVC在运行中应具有可靠的安全控制策略，以保证发电机组及系统的安全，AVC安全控制策略主要有以下几点。

# 4.1自动退出策略

(1）母线电压故障，包括电压测量通道故障、电压越限，退出全厂AVC。(2）机组无功功率测值故障，故障时无法确定机组无功功率测值是否准确，为了避免全厂无功功率设定值受影响退出全厂AVC。(3）发电状态时机组LCU故障，由于发电状态时机组LCU故障上送机组无功功率值可能为零或AVC不能判断运行机组台数，为避免此台机组无功功率为零或AVC数据错误，影响AVC分配而退出全厂AVC。(4）如机组由发电状态突变为其他状态，且机组无功功率大于机组最大无功值的 $10 \%$ ，判断数据错误退出全厂AVC。(5）电厂水位信号故障，根据水电厂情况不同，在高水头及流量变化较大的电厂退出全厂AVC，在低水头及流量变化较小的电厂可不退出全厂AVC。(6）机组强励限制动作，退出全厂AVC。（7）系统出现同步、异步或设备故障等引起继电保护动作或通过计算判断系统振荡，退出全厂AVC。

# 4.2增励磁闭锁策略

在无功增加时，如机组的条件达到增励磁闭锁策略之一，则停止增加无功，包括母线电压最大值、定子电流最大值、励磁电流最大值、机端电压高限限制值和厂用电母线电压高限限制值，并将增励磁闭锁信号送主站AVC，主站不再进行AVC增加设置，电厂AVC闭锁增加动作，只能向减少方向动作，直到闭锁信号消失。

# 4.3减励磁闭锁策略

在无功减少时，如机组的条件达到减励磁闭锁策略之一，则停止减少无功，包括母线电压最小值、定子电流最小值、励磁电流最小值、机端电压低限限制值和厂用电母线电压低限限制值，并将减励磁闭锁信号送主站AVC，主站不再进行AVC减少设置，电厂AVC闭锁减少动作，只能向增加方向动作，直到闭锁信号消失。

# 5 AVC注意事项

（1）调压系数的准确性。调压系数是AVC的重要参数，是无功功率和母线电压的对应关系，以保证AVC能够准确控制，可以根据励磁参数取得，并通过多次试验来验证调压系数的准确性。

(2）AVC安全控制策略。一般厂用电母线电压若达到其电压限制条件会闭锁增减励磁，影响AVC动作，电厂部分异步电动机容量较大，起动时可能引起厂用电电压的变化，因此，在AVC策略厂用电母线电压闭锁时需考虑对大电动机的影响。

(3）当电厂的升压变压器带有有载调压抽头时，机组无功功率的调整要与变压器的抽头调节相配合，一般在调整变压器抽头之前，应最大限度地利用发电机的电压调整。

(4）机组振动区。水轮发电机穿越振动区会引起无功功率的波动，当波动超过AVC的死区值时，AVC会进行分配调节，可能引起更大的波动，因此，机组因尽量少地穿越振动区或穿越振动区时短时间退出AVC。

(5）母线电压选择策略，电厂AVC将各段母线按编号作为优先级顺序进行选择，正常情况下，选择I母作为接收判断的受控母线，如I母故障或停电检修，选择Ⅱ母作为判断的受控母线，合母运行时，I母和Ⅱ母相差不应过大。

# 6 其他控制策略

（1）数据处理。水电厂AVC应具备实时数据处理，具备数字滤波功能，对所有数据进行数字滤波，保证无功功率、母线电压等控制数据源的准确性，防止数据突变引起误控，对采集系统的数据进行辨识，检查错误测量源、开关状态等。

（2）保护处理。水电厂AVC应具备保护处理策略，支持处理瞬动或自保持、自动复归等各类保护信号，包括主变压器差动保护、主变压器重瓦斯保护、高压侧断路器非全相保护、高压侧后备保护等各类保护信号，形成AVC分析、判断、闭锁、退出等策略。

（3）事件与告警。水电厂AVC具备各种异常情况下的事件告警功能，可以定义、记录、监视、确认、查询AVC运行过程中产生的各种事件与告警内容。

(4）记录、统计与查询。水电厂AVC具备记录、统计、查询策略，能够记录所有控制方案、控制命令以及控制设备动作情况，实现设备相关控制信息的统计与分析功能；能够记录设备的控制次数、动作次数、正确动作次数、拒动次数，并可分时段统计查询；记录AVC设备的运行状态，统计和评估AVC各项性能指标，对所有AVC数据进行查询、制作曲线图及生成报表。

# 7 AVC的优化策略

AVC在水电厂实际运行中也出现多种问题，包括AVC调节滞后、不能满足电网调节容量的要求等，还应对AVC进行优化，包括下面几项。

(1）调节滞后优化。水电厂按照上图方式与调度端主站通信获得AVC调度侧的设定值，一般一段时间设定值下发一次，调节较为滞后。水电厂AVC设定值是根据系统内重要中枢母线的电压，水电厂与调度的远动通信数据较多，而设定值是间隔一段时间下发，如在远动通信数据中加入中枢母线电压，即调度侧下发水电厂AVC设定值的依据，水电厂能够实时获取到中枢母线电压数据，将中枢母线电压的条件加入水电厂AVC算法中，AVC能够根据系统内的中枢母线电压进行调节，做到实时调节、实时响应。

(2）调节容量优化。水电厂AVC都有确定的调节容量，一般根据发电机组的无功功率给出，即发电机组的励磁系统，当励磁电流过高或过低时励磁系统报出过励限制或欠励限制动作，此时闭锁无功功率及AVC的调节，励磁电流过励限制或欠励限制动作的设定值根据经验值或机组容量设置，一般较为保守，往往发电机组还有较大潜力时励磁电流过励限制或欠励限制已经动作，实际运行中不能充分发挥发电机组的作用，因此，应该通过试验得到励磁电流过励限制或欠励限制动作的可靠数据，既保证发电机组的安全，也能充分发挥发电机组及AVC的作用。

(3）设定区间优化。水电厂母线电压一般是根据电网的要求区间运行的，区间运行的时间每个电网也不相同，这样每隔一段时间就需要修改母线电压的区间，而水电厂AVC的参数基本不能修改，大部分参数也不会变化，实际运行中母线电压的运行区间会变化，AVC不能满足电网的调节要求，可以优化AVC运行区间，实时设定AVC运行区间值，选择具备资格的操作人员实施，满足电网对水电厂AVC的要求。

# 8 结束语

实现水电厂AVC，有利于精简调度控制对象，简化电厂运行操作，提高电能质量，水电厂AVC的控制策略考虑诸多因素，包括设定方式、控制模式、无功分配策略等，还应考虑安全控制、系统状况、变压器运行方式、机组振动区等，合理地制定和优化AVC控制策略，既满足系统的要求，也保证水电厂设备的安全可靠运行。

# 参考文献

[1] 李长胜，刘光明，蒋春钢．最优发电和抽水联

合控制在抽水蓄能电厂的应用[J]．科技与生活，2010(17): 114-115.Li Changsheng, Liu Guangming, Jiang Chungang.Applicttion of optimal power generation andpumping combined control in a pumped storagepower plant[J]. Technology andLife,2010(17):114-115.  
[2] 于汀，蒲天骄，刘广一，等．电网AGC与AVC协调控制方法[J]．电力系统保护与控制，2015，43(15):42-47.Yu Ting,Pu Tianjiao,Liu Guangyi, et al. Coordinatedcontrol method of AGC and AVC in power grid[J].Power System Protection and Control, 2015,43(15):42-47.  
[3] 中国电力企业联合会．DL/T5065—2009水力发电厂计算机监控系统设计规范[S]．北京：中国电力出版社，2009.  
[4] 中国电力企业联合会．DL/T578—2008水电厂计算机监控系统基本技术条件[S]．北京：中国电力出版社，2008.  
[5] 中国南方电网公司．Q/CSG110008—2012中国南方电网自动电压控制(AVC)技术规范[S]．2012.