# 具有双向身份认证功能的量子密钥分发协议

郑涛，张仕斌，李雪杨，熊金鑫，昌燕(成都信息工程大学 网络空间安全学院，成都 610225)

摘要：提出了一种具有身份认证功能的量子密钥分发协议，该协议利用Bell态纠缠交换特性、Bell基测量和按位异或运算，可以高效完成通信双方的身份认证；身份认证完成后，通信双方对手中粒子进行 Pauli操作，能得到与对方拥有一样的Bell态粒子；通信双方按照约定的编码规则，得到相同二进制字符串作为密钥。分析表明，提出的密钥分发协议过程简单，操作容易实现，协议的安全性也能得到保证。

关键词：双向身份认证；纠缠交换；量子密钥分发 中图分类号：TP393.08 doi:10.19734/j.issn.1001-3695.2018.09.0750

Quantum key distribution protocol with two-way authentication

Zheng Tao, Zhang Shibin,Li Xueyang,Xiong Jinxin, Chang Yan (Schoolof Cybersecurity,Chengdu University of Information Technology,Chengdu 610225,China)

Abstract: This paper proposedaquantum keydistribution protocol with identityauthenticationfunction,whichutilized the Bell state entanglement switching feature,Bel-based measurement and bitwise XORoperation to efcientlycomplete identity authenticationof both parties.After identityauthentication was completed,communicationwascompleted.The Pauli operation of the particles in both opponents could obtain the same Bell state particleas the other party；the communicating partied obtain the same binarystringas the keyaccording to the agreed encoding rules.Theanalysis shows thatthe keydistributionprotocol proposedinthis paper is simple,easyto implement,andthe securityofthe protocolcan be guaranteed.

Key words: two-way authentication; entanglement swapping; quantum key distribution

# 0 引言

自第一个量子密钥分配(QKD)协议[被提出后，近年来量子密码学得到了巨大的发展。与经典密码学相比，量子密码学结合经典密码学和量子力学，利用量子效应实现了无条件安全的信息交互。为了满足社会对各种实际安全的需要，科研人员提出了大量的量子密码协议，主要包括量子密钥分配协议 $( \mathrm { Q K D } ) ^ { [ 2 - 4 ] }$ 、量子直接安全通信[5\~8](QSDC)、量子秘密共享[9,10](QSS)、量子数字签名及量子身份认证[1I\~14](QIA)等。QIA是以量子态为载体，利用量子力学原理使得通信一方的身份被另一方确认。QKD是通过量子信道，同时以经典信道作为辅助，给通信双方分配密钥。随着对量子技术研究的不断进步，在实际应用中量子隐私比较[15,16](QPC)、量子隐私数据库查询[17,18] (QPQ)等也在快速发展。量子通信是量子领域中最重要的应用之一，量子身份认证(QIA)是量子密钥分发(QKD)系统获取可靠密钥的前提，为通信双方的身份合法性提供重要依据。QIA利用量子不可克隆及量子测不准原理对输入者个人信息进行处理并与系统中预先存储的个人信息进行比较，从而对个人身份进行肯定或者否定的判断。1999 年，Dusek等人[13]首先提出利用经典信息认证算法对量子密钥系统经典消息进行认证的方案，从而达到抗干扰信道的效果。

2000 年，曾贵华[19]利用量子的物理特性，提出了可信赖中心的QIA，在此基础上进一步研究了无可信赖中心的量子身份认证方案，此方案采用认证密钥加密认证量子信息，以实现对认证方的动态认证，并且改进了认证的顺序，代替了经典公钥认证方案。到目前为止，QIA共分为如下三类：第一类为点对点的QIA，第二类是网络中的QIA，第三类是QIA与QKD 相结合。本文属于第三类的QIA方案。

本文提出了一个结合身份认证的量子密钥分配协议，通信参与者利用代表用户身份的二进制字符串进行BelI态的制备，双方对手中的粒子按照同一约定进行编码，随后进行粒子交换，完成Bell基测量以实现对Bell态粒子的纠缠交换，按编码规则对测量前后的粒子进行按位异或运算，就可以实现对通信双方的身份认证。待身份认证完成后，通信双方的任意一方进行Pauli门操作，可以使手中的粒子转换成和对方手中的粒子一样的Bel1态粒子。按照同样的编码规则，通信双方可以获得一串相同二进制字符串，此时完成了密钥的分配。

# 1 准备知识

# 1.1Bell态纠缠交换

本协议用到的四种Bel1态粒子可以表示为

$$
\left| \phi ^ { \pm } \right. = \frac { 1 } { \sqrt { 2 } } \left( \left| 0 0 \right. \pm \left| 1 1 \right. \right) , \left| \psi ^ { \pm } \right. = \frac { 1 } { \sqrt { 2 } } \left( \left| 0 1 \right. \pm \left| 1 0 \right. \right)
$$

两个Bell态粒子若处于 $\left| \phi ^ { + } \right.$ 态，对它们进行Bell态纠缠交换，则有下面等式成立：

$$
\begin{array} { l } { { \displaystyle \left| \phi ^ { + } > _ { 1 2 } \right| \phi ^ { + } > _ { 3 4 } = \frac { 1 } { \sqrt { 2 } } \left( \left| 0 0 \right. + \left| 0 0 \right. \right) _ { 1 2 } \otimes \frac { 1 } { \sqrt { 2 } } ( \left| 0 0 \right. + \left| 0 0 \right. ) _ { 3 4 } } } \\ { { \displaystyle = \frac { 1 } { \sqrt { 2 } } \left( \left| \phi ^ { + } > _ { 1 3 } \right| \phi ^ { + } > _ { 2 4 } + \left| \phi ^ { - } > _ { 1 3 } \right| \phi ^ { - } > _ { 2 4 } \right. } } \\ { { \displaystyle \left. + \left| \psi ^ { + } > _ { 1 3 } \right| \psi ^ { + } > _ { 2 4 } + \left| \psi ^ { - } > _ { 1 3 } \right| \psi ^ { - } > _ { 2 4 } \right) } } \end{array}
$$

如果对1、3粒子进行Bel1基测量，2、4粒子则会纠缠到对应的状态。例如，对1、3粒子测量的结果为 $\left| \psi ^ { + } \right. _ { 1 3 }$ ，2、4粒子的状态为 $\left| \psi ^ { + } \right. _ { 2 4 }$ 。若不考虑其相位问题，任意两个Bell态的纠缠情况如表1所示。

Table 1Entanglement swapping of arbitrary two Bell States   

<html><body><table><tr><td>1+12</td><td>1+734</td><td>1+>3l+>24,1->1->24, ly+>3l4+>24,l->3l->24</td></tr><tr><td>1+12</td><td>1-734</td><td>1+>l->24,1->31+>24, lv+>3ly->24,ly->3ly+>24</td></tr><tr><td>1+12</td><td>l +734</td><td>1φ+)13l4+)24,l4+>13|Φ+)24, |-)3l4->24,l4->3l->24</td></tr><tr><td>1+12</td><td>ly-734</td><td>|Φ+)13l4-)24,l4->3lΦ+)24, 1->3l+>4,4+lΦ->4</td></tr><tr><td>|-12</td><td>14+734</td><td>1->3l+>24,1Φ+>3l-724, l4+)3l4->24,4->13l4+>24 1->3l->24,1+>3l+724,</td></tr><tr><td>1-12</td><td>1-734</td><td>ly+>3l+)24,-13->24 1->l4+>24,l+3l->24,</td></tr><tr><td>1-)12</td><td>l+734</td><td>1+>3l4->24,l4->13l+>24 1-)3l4->24,l4-)3l->24,</td></tr><tr><td>1-12</td><td>|4-734</td><td>1Φ+)13l4+>24,l+>13lΦ+>24 |++24,+4,</td></tr><tr><td>|+)12</td><td>1+734</td><td>1->3l4->24,l->3l->4 ly+}3lΦ->4,l->3l4+724,</td></tr><tr><td>|+)12</td><td>1-734</td><td>1+>3l4->24l->3l+>24 |y+)3ly+>24,l4->3l4->24,</td></tr><tr><td>|+12</td><td>l+734</td><td>1->lΦ->4,1+>3l+>24 lv+)3lγ->24,ly->3l+724,</td></tr><tr><td>|+12</td><td>|y-734</td><td>1+3l->24,1->3l+>24 1->3l+>24,1+>l4->24,</td></tr><tr><td>1->12</td><td>1+734</td><td>1Φ->3l+)24,14+>3l->4 l-)3lΦ->24,1Φ->3l-724,</td></tr><tr><td>|->12</td><td>10-734</td><td>1+>3ly+>24,l4+>13l+>24 |y-)3ly+>24,l+>3l->24,</td></tr><tr><td>1->12</td><td>l+734</td><td>1φ+>l->4,->l+>24 ly-)3l4->24,l4+3ly+>24,</td></tr><tr><td>|->12</td><td>l4-734</td><td>1+>l+>24,1->l->24</td></tr></table></body></html>

若约定用00表示 $\left| \phi ^ { + } \right.$ 态，01表示 $\left| \phi ^ { - } \right.$ 态，10表示 $\left| \psi ^ { + } \right.$ 态，11表示 $\left| \psi ^ { - } \right.$ 态，且假设纠缠交换前的两个Bel1态粒子的二进制表示为 $P _ { 1 2 }$ 和 $P _ { 3 4 }$ ，纠缠交换后的两个Bell态粒子的二进制表示为 $P _ { 1 3 }$ 和 $P _ { 2 4 }$ 。若两个Bell态粒子均处于 $\left| \phi ^ { + } \right.$ 态，则纠缠交换后的两个 Bell态粒子以 $\frac { 1 } { 4 }$ 的概率处于 $\mid \phi ^ { + } > _ { 1 3 } \mid \phi ^ { + } > _ { 2 4 }$ ，以 $\frac { 1 } { 4 }$ 的概率处于 $\mid \phi ^ { - } > _ { 1 3 } \mid \phi ^ { - } > _ { 2 4 }$ ，以 $\frac { 1 } { 4 }$ 的概率处于 $\left| \psi ^ { + } > _ { 1 3 } \right| \psi ^ { + } > _ { 2 4 }$ ，以 $\frac { 1 } { 4 }$ 的概率处于 $\left| \psi ^ { - } > _ { 1 3 } \right| \psi ^ { - } > _ { 2 4 }$ 。如果纠缠交换后两个Bell态粒子处于$\mid \phi ^ { + } > _ { 1 3 } \mid \phi ^ { + } > _ { 2 4 }$ ，则有 $P _ { 1 2 } \oplus P _ { 3 4 } = P _ { 1 3 } \oplus P _ { 2 4 } = 0 0 \oplus 0 0 = 0 0$ 。如果纠缠交换后两个Bell态粒子处于 $\mid \phi ^ { - } > _ { 1 3 } \mid \phi ^ { - } > _ { 2 4 }$ ，则有$P _ { 1 2 } \oplus P _ { 3 4 } = P _ { 1 3 } \oplus P _ { 2 4 } = 0 1 \oplus 0 1 = 0 0$ 。如果纠缠交换后两个Bell态粒子处于 $\left| \psi ^ { - } > _ { 1 3 } \right| \psi ^ { - } > _ { 2 4 }$ ，则有 $P _ { 1 2 } \oplus P _ { 3 4 } = P _ { 1 3 } \oplus P _ { 2 4 } = 1 1 @ 1 1 = 0 0$ 。如果纠缠交换后两个Bell态粒子处于 $\left| \psi ^ { + } > _ { 1 3 } \right| \psi ^ { + } > _ { 2 4 }$ ，则有$P _ { 1 2 } \oplus P _ { 3 4 } = P _ { 1 3 } \oplus P _ { 2 4 } = 1 0 \oplus 1 0 = 0 0$ 。经过推导发现，任意两种bell态纠缠交换后，都满足式（3)。

$$
P _ { 1 2 } \oplus P _ { 3 4 } = P _ { 1 3 } \oplus P _ { 2 4 }
$$

且任意两种bel1态纠缠交换对应的二进制关系如表2所示。

表2两个bell态纠缠交换二进制表示关系

表1任意两个Bell态的纠缠交换  
[able 2The binary representation relation of two Bell states   

<html><body><table><tr><td colspan="3">entanglementswapping</td></tr><tr><td>P2</td><td>P4</td><td>纠缠交换后PP24</td></tr><tr><td>00</td><td>00</td><td>00+00=00， 0101=00， 10+10=00， 1111=00</td></tr><tr><td>00</td><td>01</td><td>0001=01，01+00=01， 10④11=01，1110=01</td></tr><tr><td>00</td><td>10</td><td>0010=10，1000=10， 0111=10，1101=10</td></tr><tr><td>00</td><td>11</td><td>0011=11，1100=11， 0110=11，1001=11</td></tr><tr><td>01</td><td>00</td><td>01+00=01， 0001=01， 1011=01，1110=01</td></tr><tr><td>01</td><td>01</td><td>0101-00， 0000-00， 1010=00， 1111=00</td></tr><tr><td>01</td><td>10</td><td>0110=11，1001=11， 00+11=11， 1100=11</td></tr><tr><td>01</td><td>11</td><td>0111=10，1101=10， 0010=10， 1000=10</td></tr><tr><td>10</td><td>00</td><td>10④00=10， 0010=10, 0111=10， 1101=10</td></tr><tr><td>10</td><td>01</td><td>1001=11， 0110=11, 0011=11， 1100=11</td></tr><tr><td>10</td><td>10</td><td>10④10=00， 00+00=00， 01+01=00， 1010=00</td></tr><tr><td>10</td><td>11</td><td>1011=01，1110=01， 0001=01， 01+00=01</td></tr><tr><td>11</td><td>00</td><td>1100=11， 0011=11, 0110=11， 1001=11</td></tr><tr><td>11</td><td>01</td><td>1101=10， 0111=10, 0010=10， 10+00=10</td></tr><tr><td>11</td><td>10</td><td>1110=01，1011=01, 0100=01， 00+01=01</td></tr><tr><td>11</td><td>11</td><td>1111=00，1010=00， 0000=00， 01+01=00</td></tr></table></body></html>

# 1.2Pauli矩阵变换

Pauli矩阵可以表示如下：

$$
\begin{array}{c} X = { \binom { 0 } { 1 } } \quad 1 \atop 0 \int Y = { \binom { 0 } { i } } \quad 0 \end{array}
$$

$$
\begin{array}{c} Z = { \binom { 1 } { 0 } } \quad { \binom { 0 } { - 1 } } \quad I = { \binom { 1 } { 0 } } \quad 0 \\ { 0 } \quad - 1 \end{array}
$$

其中：X和Z分别称为比特翻转和相位翻转操作符。如果对一个量子比特进行 $\mathrm { \Delta } X$ 操作，有 $\ X \left| 0 \right. = \left| 1 \right.$ ， $\scriptstyle { \big | } X | 1 \rangle = | 0 \rangle$ 。对其进行Z操作，有 $\scriptstyle { Z | + \rangle = | - \rangle }$ ， $\scriptstyle { Z | - \rangle = | + \rangle }$ 。对其进行 $i Y$ 操作，同时产生比特翻转和相位翻转效果。

$$
\begin{array}{c} i Y = Z X = { \binom { 1 } { 0 } } \quad 0  \\ { 0 \quad - 1 } \end{array} \textstyle { \binom { 0 } { 1 } } { \binom { 0 } { 0 } } = { \binom { 0 } { - 1 } } = i { \binom { 0 } { i } } = i { \binom { 0 } { i } } \quad 0
$$

# 四个Bell态粒子状态经过Pauli矩阵转换结果如表3所示。

表3四种Bell态粒子经过Pauli矩阵转换结果  
Table 3.Results of transformation of four Bell state particles through Pauli matrix   

<html><body><table><tr><td>Bell态</td><td></td><td>-</td><td>l+></td><td>lw-></td></tr><tr><td>+></td><td>1</td><td>0</td><td>Ox</td><td>iσy</td></tr><tr><td>-></td><td></td><td>I</td><td>igy</td><td>Ox</td></tr><tr><td>lv+></td><td>x</td><td>iσy</td><td>I</td><td></td></tr><tr><td>lv-></td><td>iσy</td><td>Ox</td><td></td><td>1</td></tr></table></body></html>

# 2 协议描述

a)Alice的二进制身份字符串为 $I D _ { \mathrm { A } } { = } \{ \mathrm { P } _ { 1 2 } ^ { 1 } , \mathrm { P } _ { 1 2 } ^ { 2 } \ldots \mathrm { P } _ { 1 2 } ^ { 2 n } \}$ ，Bob的二进制身份字符串为 $I D _ { B } { = } \{ { \bf P } _ { 3 4 } ^ { 1 } , { \bf P } _ { 3 4 } ^ { 2 } \ldots { \bf P } _ { 3 4 } ^ { 2 n } \}$ 。Alice 和Bob 秘密共享 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 。Alice根据 $I D _ { A }$ 制备Bell态粒子序列 $S _ { I D _ { A } }$ ，Bob根据 $I D _ { \scriptscriptstyle B }$ 制备Bell态粒子序列 $S _ { I D _ { B } }$ 。双方约定制备规则为：如果身份字符串的当前位是00，则制备的粒子态处于 $| \phi > ^ { + }$ 。如果身份字符串的当前位是01，则制备的粒子态处于 $| \phi > ^ { - }$ 如果身份字符串的当前位是10，则制备的粒子态处于 $| \psi > ^ { + }$ 。如果身份字符串的当前位是11，则制备的粒子态处于 $| \psi > ^ { - }$ 。

b）Alice抽取所有 $S _ { I D _ { A } }$ 粒子序列的第二个粒子，并随机插入足量的Bel1态粒子作为诱骗粒子，记录其位置信息后Alice将这段粒子序列 $\boldsymbol { S } _ { \iota D _ { A } } ^ { \prime }$ ，发送给Bob，Bob抽取所有 $S _ { I D _ { B } }$ 粒子序列的第一个粒子，插入足量的处于Bel1态的诱骗粒子，并记录位置信息后记为 $\boldsymbol { S } _ { \ I D _ { B } } ^ { \prime }$ ，发送给Alice。双方同样按照约定的编码规则，对诱骗粒子进行编码： $\left| \phi ^ { + } \right.$ 编码为00， $\left| \phi ^ { - } \right.$ 编码为01， $\left| \psi ^ { + } \right.$ 编码为10， $\left| \psi ^ { - } \right.$ 编码为11。

c）双方都接收到粒子序列 $\boldsymbol { S } _ { \iota D _ { A } } ^ { \prime }$ 和 $\boldsymbol { S } _ { \ I D _ { B } } ^ { * }$ 后，公布诱骗粒子的位置和诱骗粒子的二进制编码字符串。各自抽取出诱骗粒子后进行测量，并比较误码率。若误码率高于规定的阈值，协议终止。

d）完成误码率检测后，双方对手中的粒子进行Bell基测量，测量的结果按如下规则编码： $\left| \phi ^ { + } \right.$ 编码为00， $\left| \phi ^ { - } \right.$ 编码为01， $\left| \psi ^ { + } \right.$ 编码为10， $\left| \psi ^ { - } \right.$ 编码为11。得到 $I D _ { A } ^ { \phantom { \dagger } }$ 和 ${ I D } _ { B } ^ { \prime }$ ，此时完成纠缠交换。双方公布 $I D _ { A } ^ { ' }$ 和 $\left| I D _ { B } \right|$ ，各自判断$I D _ { A } \oplus I D _ { B } = I D _ { A } ^ { ^ { \prime } } \oplus I D _ { B } ^ { ^ { \prime } }$ 是否成立，根据式(2)，若成立，则完成对通信另一方的身份认证。

e)完成身份认证后，Alice根据 ${ I D } _ { B } ^ { \prime }$ 和纠缠交换的性质，由表1可以推出Bob手中Bell态序列的信息。根据表3所示的Pauli操作，Alice将手中的粒子执行相应的操作，即可得到与Bob相同的粒子序列。双方按照1)的编码规则对得到的粒子序列进行编码，可以得到相同的二进制字符串作为密钥序列。

# 3 协议举例

a）假设 Alice 的二进制身份字符串 $I D _ { \scriptscriptstyle A } = 1 1 0 1 0 1 0 0$ ，Bob的二进制身份字符串 $I D _ { B } { = } 1 0 0 1 1 1 0 0$ 。Alice 和 Bob 共享 $I D _ { A }$ 和$I D _ { { _ B } }$ 。Alice 根据 $I D _ { A }$ 制备粒子序列 $S _ { I D _ { A } } = \{ | \psi ^ { - } \rangle , | \phi ^ { - } \rangle , | \phi ^ { - } \rangle , | \phi ^ { + } \rangle \}$ ，Bob根据 $I D _ { \scriptscriptstyle B }$ 制备粒子序列为 $S _ { I D _ { B } } = \{ | \psi ^ { + } \rangle , | \phi ^ { - } \rangle , | \psi ^ { - } \rangle , | \phi ^ { + } \rangle \}$ 。制备规则为：如果身份字符串当前位为00制备处于 $\left| \phi ^ { + } \right.$ 态的粒子，当前位为01制备处于 $\left| \phi ^ { - } \right.$ 态的粒子，当前位为10 制备处于 $\left| \psi ^ { + } \right.$ 态的粒子，当前位为11制备处于 $\left| \psi ^ { - } \right.$ 态的粒子。

b）Alice抽取所有 $S _ { I D _ { A } }$ 粒子序列的第二个粒子，并随机插入足量的Bell态粒子作为诱骗粒子，记录其位置信息后Alice 将这段粒子序列 $\boldsymbol { S } _ { \ I D _ { A } } ^ { * }$ ，发送给Bob,Bob 抽取所有 $S _ { m _ { B } }$ 粒子序列的第一个粒子，插入足量的处于Bel1态的诱骗粒子，并记录位置信息后记为 $\boldsymbol { S } _ { \ I D _ { B } } ^ { \prime }$ ，发送给Alice。双方同样按照约定的编码规则，对诱骗粒子进行编码： $\vert \phi ^ { + } \rangle$ 编码为00， $\left| \phi ^ { - } \right.$ 编码为01， $\left| \psi ^ { + } \right.$ 编码为10， $\left| \psi ^ { - } \right.$ 编码为11。假设 $\boldsymbol { S } _ { \mathit { I D } _ { A } } ^ { \prime }$ 中诱骗粒子位置信息为 $L _ { \mathrm { } A } = \{ 2 , 3 , 5 , 7 \}$ ， $L _ { \mathrm { } _ { A } }$ 表示诱骗粒子在 $\boldsymbol { S } _ { \ I D _ { A } } ^ { * }$ 序列中的第2,3,5,7位。状态信息为 $\{ | \psi ^ { - } \rangle , | \phi ^ { - } \rangle , | \phi ^ { + } \rangle , | \psi ^ { + } \rangle \}$ ，编码为$E _ { \scriptscriptstyle A } = \{ 1 1 , 0 1 , 0 0 , 1 0 \}$ 。 $L _ { \scriptscriptstyle B } = \{ 1 , 3 , 4 , 6 \}$ 表示诱骗粒子在 $\boldsymbol { S } _ { \ I D _ { B } } ^ { \prime }$ 序列中的第1,3,4,6位。状态信息为 $\{ | \phi ^ { + } \rangle , | \psi ^ { - } \rangle , | \phi ^ { - } \rangle , | \phi ^ { + } \rangle \}$ ，编码为$E _ { B } = \{ 0 0 , 1 1 , 0 1 , 0 0 \}$ 。

c）双方都接收到粒子序列 $\boldsymbol { S } _ { \ I D _ { A } } ^ { \prime }$ 和 $\boldsymbol { S } _ { \ I D _ { B } } ^ { * }$ 后，公布诱骗粒子的位置和诱骗粒子的二进制编码字符串。各自抽取出诱骗粒子后进行测量，并比较误码率。若误码率高于规定的阈值，协议终止。

d）完成误码率检测后，双方对手中的粒子进行Bell基测量，此时Alice手中的粒子序列为 $N \mathrm { e w } _ { I D _ { A } } = \{ | \psi ^ { + } \rangle , | \phi ^ { + } \rangle , | \psi ^ { - } \rangle , | \phi ^ { - } \rangle \}$ ，Bob 手中的粒子序列为 $N \mathrm { e w } _ { I D _ { B } } = \{ | \psi ^ { - } \rangle , | \phi ^ { + } \rangle , | \phi ^ { - } \rangle , | \phi ^ { - } \rangle \}$ 。按如下规则编码： $\left| \phi ^ { + } \right.$ 编码为00， $\left| \phi ^ { - } \right.$ 编码为01， $\left| \psi ^ { + } \right.$ 编码为10， $\left| \psi ^ { - } \right.$ 编码为11。得到 $I D _ { A } ^ { ' } = \{ 1 0 , 0 0 , 1 1 , 0 1 \}$ 和 $I D _ { B } ^ { ' = \{ 1 1 , 0 0 , 0 1 , 0 1 \} }$ ，此时完成纠缠交换。双方公布 $I D _ { A } ^ { \phantom { \dagger } }$ 和 ${ I D } _ { B } ^ { \mathrm { ~ . ~ } }$ ，根据公式$I D _ { A } \oplus I D _ { B } = I D _ { A } ^ { \prime } \oplus I D _ { B } ^ { \prime }$ ，因为

$$
I D _ { A } \oplus I D _ { B } = 1 1 0 1 0 1 0 0 @ 1 0 0 1 1 1 0 0 = 0 1 0 0 1 0 0 0
$$

$$
I D _ { A } ^ { ' } \oplus I D _ { B } ^ { ' } = 1 0 0 0 1 1 0 1 @ 1 1 0 0 0 1 0 1 = 0 1 0 0 1 0 0 0
$$

所以该公式满足，证明通信双方的身份合法。

e)此时Alice 手中的粒子序列为 $\{ | \psi ^ { + } \rangle , | \phi ^ { + } \rangle , | \psi ^ { - } \rangle , | \phi ^ { - } \rangle \}$ ，Bob手中的粒子序列为 $\{ | \psi ^ { - } \rangle , | \phi ^ { + } \rangle , | \phi ^ { - } \rangle , | \phi ^ { - } \rangle \}$ 。根据表1和3，Alice对手中的粒子进行Pauli操作的顺序为 $\{ \sigma _ { z } , I , , \sigma _ { \mathrm { x } } , I \}$ ，此时Alice手中的粒子状态变为 $\{ | \psi ^ { - } \rangle , | \phi ^ { + } \rangle , | \phi ^ { - } \rangle , | \phi ^ { - } \rangle \}$ ，按照a）中的编码规则，双方得到相同的二进制字符串 $k e y = 1 1 0 0 0 1 0 1$ 。此时完成了密钥分配。身份认证和密钥分配过程如图1所示。

# 4 安全性分析

根据协议步骤可知，当身份认证完成后，密钥分配的过程不会有安全隐患。所以本协议的安全性分析主要分析身份认证过程。

# 4.1冒充攻击

假设Alice 被Eve 冒充，Bob是合法的。Eve在不知道 $I D _ { A }$ 的情况下和 Bob 通信。Eve 随机制备 Bell态粒子序列 $S _ { I D _ { E } }$ ，并发送所有 $S _ { I D _ { E } }$ 的第一个粒子给Bob，Bob发送所有 $S _ { I D _ { B } }$ 的第一个粒子给Eve。接收完成后，Eve 拥有的粒子序列记为 $\boldsymbol { S } _ { \iota D _ { E } } ^ { \prime }$ ，Bob 拥有的粒子序列记为 $\boldsymbol { S } _ { \ I D _ { B } } ^ { \prime }$ 。Eve 和Bob 对手中的粒子进行Bell基测量，完成纠缠交换。Eve对测量后的粒子状态用约定的编码方式编码成二进制字符串，记为 $\boldsymbol { I D } _ { E } ^ { * }$ ，Bob手中的粒子也经过同样的操作后，记为 $\boldsymbol { I D } _ { \ B } ^ { * }$ 。当Bob 对Alice 进行身份认证时，Eve公布 $\boldsymbol { I D } _ { E } ^ { \prime }$ ，根据式(2)，由于$I D _ { A } \oplus I D _ { B } \ne I D _ { E } \oplus I D _ { B } ^ { \prime }$ ，Eve不能通过身份认证。同理，Eve 冒充Bob也不能通过身份认证。

# 4.2截获/重发攻击和中间人攻击

假设Eve 截获Alice发送给Bob 的粒子序列 $\boldsymbol { S } _ { \iota D _ { A } } ^ { \prime }$ ，由于此时Bob没有接收到Alice发来的粒子序列，Alice不会宣布在 $\boldsymbol { S } _ { \mathit { I D } _ { A } } ^ { ' }$ 序列中诱骗粒子的二进制字符串和位置信息。Eve 不论采取什么手段对 $\boldsymbol { S } _ { \ I D _ { A } } ^ { \prime }$ 进行测量，当Eve测量完成并发给Bob后，都会使得Bob对诱骗粒子测量得到的结果与Alice公布的状态完全不同。执行窃听检测时，Eve会被Bob发现。协议随即终止。假设由于疏忽或其他原因Alice公布了 $\boldsymbol { S } _ { \ I D _ { A } } ^ { * }$ 中诱骗粒子的二进制字符串和位置信息，由于Eve无法得知通信双方约定的对诱骗粒子的编码规则，Eve仍旧无法正确的对诱骗粒子进行正确的测量，从而导致通信双方的窃听检测不通过。

![](images/9c4ec0e2501d00ffc5008d1fab23c06c36d66906be4eb1d417acfcc95a2d8da7.jpg)  
图1身份认证和密钥分配过程  
Fig.1Identity authentication and key distribution process

# 4.3 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 的安全性

由于 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 是双方在开始通信之前秘密共享的，非法用户无法得知 $I D _ { A }$ 和 $I D _ { { } _ { B } }$ 。如果Eve 采取穷举法猜测 $I D _ { A }$ 和，当 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 的长度为2n时,Eve 能正确猜出的概率 $I D _ { \scriptscriptstyle B }$ 为 $\frac { 1 } { 4 ^ { n } }$ （204号（20当 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 的长度足够长时，Eve 能猜出的概率趋近于零。如果Eve采取截获/重发攻击来得到 $I D _ { A }$ 和 $I D _ { { } _ { B } }$ ,Eve 截取Alice发送给Bob的粒子序列 $\boldsymbol { S } _ { \ I D _ { A } } ^ { \prime }$ ，由于Eve 的测量无法推测Alice手中粒子序列的详情，且会导致Alice手中粒子的塌缩。使得通信双方无法完成纠缠交换，进而无法通过式（2)，身份认证无法通过。如果Eve试图通过通信双方公布的 $I D _ { A } ^ { \phantom { \dagger } }$ 和 $\left| I D _ { B } \right|$ 来猜测 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ ，由于 $I D _ { A } ^ { \phantom { \dagger } }$ 和 ${ I D } _ { B } ^ { \mathrm { ~ . ~ } }$ 是两个Bell态粒子纠缠交换后四个混合态的二进制表示，所以 ${ I D } _ { A } ^ { \prime }$ 和 ${ I D } _ { B } ^ { \prime }$ 都以 $p = \frac { 1 } { 4 }$ 的概率处于 $\{ 0 0 , 0 1 , 1 0 , 1 1 \}$ ,Eve 无法得到 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 的有效信息。故$I D _ { A } ^ { \phantom { \dagger } }$ 和 ${ I D } _ { B } ^ { \mathrm { ~ . ~ } }$ 的公布不会导致 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 的泄露。且 $I D _ { A }$ 和 $I D _ { \scriptscriptstyle B }$ 是可以重复利用的。

# 5 性能分析

首先分析身份认证过程，在已有的身份认证协议中，大部分协议都是抽取用于通信的粒子进行窃听检测，这种方法在一定程度上减小了协议认证复杂性，但是对于身份认证过程，由于有相当一部分粒子用于窃听检测，导致身份认证的效率下降。在本协议中，由于通信双方按照各自公开的 ID进行Bel1态粒子制备，完成粒子制备后，双方均对粒子序列插入额外的窃听粒子，且窃听粒子的二进制编码信息与ID编码信息一致，在同样减小了协议的复杂度基础上，较好了提高了用于身份认证的粒子使用效率。

分析密钥生成效率，根据协议描述，Alice与Bob完成身份认证（QIA）后，双方根据公开的ID'信息，结合简单的Pauli门操作，就可以得到与对方手中相同的粒子序列。经过粒子编码后，Alice和Bob得到相同二进制密钥串。由于本协议在QKD步骤前，已经完成了对通信参与双方对身份认证，此时Alice 和Bob 都是合法的参与者，故他们不再对手中的粒子进一步的进行窃听检测等容易造成粒子损失的操作这即是说，QIA完成后，双方手中的全部粒子都将用作密钥建立过程。与经典的BB84、B92等协议做对比，本协议有较好的密钥生成效率。

如安全性分析部分描述的，本协议的安全性分析主要聚焦在身份认证过程中。结合经典的非对称加密思想，本协议提出通信双方用公开的ID进行粒子的制备，身份的验证等步骤。通信双方在发送的粒子序列中插入了足量的窃听检测粒子，这使得本协议能抵抗绝大部分的攻击策略，使得本协议有较好的安全性能来满足身份认证和密钥建立两个过程。

# 6 结束语

本文提出了一种基于BelI态粒子纠缠交换特性的具有身份认证功能的量子密钥分发协议。通信双方只需按照代表

自身身份的二进制字符串制备Bell态序列，然后Alice抽取她手中所有Bell态的第一个粒子，插入足量的诱骗粒子后发送给Bob，Bob也对手中的粒子做同样的操作。双方均完成粒子接收后，对各自手中的粒子做Bel1基测量，并将测量结果进行二进制表示。双方公布测量结果对应的二进制就可以完成对对方的身份认证。完成身份认证后，通信的发起方对手中粒子做相应的Pauli操作，得到与另一个通信方相同的Bel1态粒子。通信双方按照相同的编码规则对手中的粒子进行二进制编码，可以使得双方拥有相同的密钥串。对本协议的安全性分析表明，只要代表通信双方身份信息的二进制字符串没有泄露，本协议就可以抵御冒充攻击和截获/重发与中间人攻击，身份认证过程就是真实有效的。在实际的应用中，本协议的实现只取决于Bell态的精确制备、Bell态的精确测量操作和Pauli门的正确实现。且代表用户身份的二进制字符串可以重复利用， $I D _ { A }$ 和 $I D _ { { } _ { B } }$ 的安全性也得到了保证

# 参考文献：

[1]Bennett C H,Brassard G.Quantum cryptography:publickey distribution and coin tossing [C]//Proc of IEEE International Conference on Computers Systems and Signal Processing. 1984: 175-179.   
[2]Bennett C H.Quantum cryptography using any two nonorthogonal states.[J].Physical Review Letters,1992,68 (68):3121-3124.   
[3]Wang Chao，Wang Shuang，Yin Zhenqian，et al.Experimental measurement-device-independent quantum key distributionwith uncharacterized encoding [J]. Optics Letters,2016,41 (23):5596-5599.   
[4]Curty M,Xu Feihu，Cui Wei，et al.Finite-key analysisfor measurement-device-independent quantum key distribution [J].Nature Communications,2014,5 (4): 643-648.   
[5]Patwardhan S,Moulick S R,Panigrahi P K.Efficient controlled quantum secure direct communication protocols [J]. International Journal of Theoretical Physics,2016,55(7):3280-3288.   
[6]Patwardhan S,Moulick S R,Panigrahi P K.Efficient controlled quantum secure direct communication protocols [J].  International Journal of Theoretical Physics,2016,55(7):3280-3288.   
[7]Chang Yan,Xu Chunxiang,Zhang Shibin,et al.Quantum secure direct communication and authentication protocol with single photons [J]. Chinese Science Bulletin,2013,58 (36):4571-4576.   
[8] Cai Qingyu,Li Baiwen.Deterministic secure communication without using entanglement [J].Chin Phys Lett,2004,21 (4): 601-603.   
[9]Qin Huawang,Dai Yuewei.Verifiable (t,n) threshold quantum secret sharing using d-dimensional Bell state [J]. Information Processing Letters,2016,116 (5):351-355.   
[10] Mishra S,Shukla C,Pathak A,et al.An integrated hierarchical dynamic quantum secret sharing protocol [J]. International Journal of Theoretical Physics,2015,54 (9): 1-12.   
[11]Wang Ding,He Debiao,Wang Ping，et al.Anonymous two-factor authentication in distributed systems: certain goals are beyond attainment[J].IEEE Trans on Dependable and Secure Computing,2015, 12 (4): 428-442.   
[12]Wang Ding，Wang Ping.Two birds with one stone: two-factor authentication with security beyond conventional bound [J]. IEEE Trans on Dependable and Secure Computing,2018,15(4): 708-722.   
[13] DuSek M,Haderka O,Hendrych M,et al. Quantum identification system[J].Physical ReviewA,1999,60(1):149-156.   
[14] Yuan Hao,Liu Yimin，Pan Guozhu，et al.Quantum identity authentication based on ping-pong technique without entanglements [J]. Quantum Information Processing,2014,13(11):2535-2549.   
[15] Gao Gan.Secure multiparty quantum secret sharing with the collective eavesdropping-check character [J].Quantum Information Processing, 2013,12(1): 55-68.   
[16] Wang Yukun，Zhang Jie,Huang Wei，et al.A quantum private comparisonprotocolwithsplittinginformationcarriers[J]. International Journal of Theoretical Physics,2015,54(1): 281-291.   
[17] Wei Chunyan,Wang Tianyin, Gao Fei. Practical quantum private query with better performance in resisting joint-measurement attack [J]. Physical ReviewA,2016,93 (4).   
[18] Gao Fei,Liu Bin,Huang Wei,et al.Postprocessing of the Oblivious Keyin Quantum Private Query[J].IEEE Journal of Selected Topics in Quantum Electronics,2014,21 (3): 98-108.   
[19]曾贵华．不依赖第三方的动态量子身份认证方案[J]．电子学报, 2004,32 (7):1148-1152.(Zeng Guihua.Dynamic quantum identity authentication scheme independent of the third party [J].Acta electronica Sinica,2004,32(7): 1148-1152.)