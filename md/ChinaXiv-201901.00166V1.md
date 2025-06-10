# 异构容器云间应用迁移模型研究

杨凯琪，赵玉龙，陈林(江南计算技术研究所，江苏 无锡 214000)

摘要：为解决基于Docker容器的应用跨异构容器云迁移的问题，针对主流的异构容器编排引擎的编排原理进行了研究，同时也研究了主流容器服务提供商之间的异构性，在此基础上提出了基于Docker容器的应用跨异构容器云迁移的三层模型。为提高基于Docker容器的应用跨异构容器云迁移的效率，提出基于镜像预同步的应用迁移技术。实验结果表明，利用三层模型能成功实现应用跨异构容器云的迁移，并且在引入镜像预同步技术前后，同构云异构容器编排引擎之间的应用迁移时间平均减少 $60 . 3 3 \%$ ，异构云Kubernetes 集群之间的应用迁移时间平均减少 $4 3 . 6 7 \%$ 。

关键词：Docker容器；应用迁移；三层模型；异构容器云 中图分类号：TP302 doi: 10.19734/j.issn.1001-3695.2018.09.0762

Study on migration of applications between Heterogeneous container clouds

Yang Kaiqi, Zhao Yulong, Chen Lin (Institute ofJiangNan Computing Technology,Wuxi Jiangsu 2140oo,China)

Abstract:Inorder tomigrate Dockercontainerbased applicationsacrossheterogeneous containerclouds,theauthorstudied the principles of mainstream heterogeneous container orchestrating engines.Meanwhile,this paper conducted a surveyon the heterogeneityofcontainer serviceof diferent providers.The author proposed the Thre-layered Model of Migrating Docker Container based Applications across Heterogeneous Container Clouds.Four the purpose of improving migration effciency,thispaper developed the Image Pre-Synchronization technology.Experimentalresultsshow thatusing the three-layered modelcan migrate Dockercontainer basedapplicationsacross container cloudssuccessfully，and the technologyof image pre-synchronization can helpthe timeof migrating.For the situation of migrating Docker container based applications between heterogeneous container orchestrating engines in homogeneous clouds,the improvement is $60 . 3 3 \%$ on average.And for the situation of migrating Docker container based applications between Kubernetes clusters in heterogeneous clouds,the improvement is $4 3 . 6 7 \%$ on average.

Key Words: docker containers; migration of applications; three-layered model; Heterogeneous container clouds

# 0 引言

企业总是运行多种异构技术。目前云计算服务市场处于百花齐放、百家争鸣的状态，国外的云服务提供商包括亚马逊、微软、谷歌等，国内的云服务提供商包括阿里、华为、美团等。为了充分利用就近计算优势，提高业务应用的全域服务能力以及避免被特定的云计算服务提供商锁定，企业需要将自己的业务应用部署到多个地域、多个云计算服务提供商的数据中心内[1]。但是在跨域传输数据时需要付出很大的代价：一方面，跨域数据传输不仅消耗时间长，而且消耗宝贵的网络带宽资源，性价比低；另一方面，安全规则限制下某些数据不允许被跨域传输。因此现在学术界和工业界都提倡在异构容器云之间进行应用的迁移。

然而现阶段异构容器云间的应用迁移仍然存在着许多挑战：a)对于复杂应用来说，如何在迁移过程中保持与编排引擎的交互，从而维持应用在迁移前后的健康检查机制、节点亲和性等编排规则的一致性；b)基于Docker容器的应用如何抛开迁移前后的存储和网络环境能满足容器应用运行所需的条件；c)如何让基于Docker容器的应用总迁移时间更短；d)频繁的迁移操作会导致数据中心的能耗快速增加，以及占用网络带宽，对数据中心的日常使用带来影响。

目前对多数据中心的容器管理主要是以云联邦（cloudfederation)的形式进行[l\~3],如Kubernetes 集群联邦、HashicorpNomad和Mesos集群联邦等。虽然它们都能对多个数据中心的容器进行管理，但都局限于同构容器编排引擎，无法调度异构容器编排引擎之间的资源，不能将基于Docker容器的应用在Kubernetes 集群[l0]与Docker Swarm集群[1l\~l3]之间调度。文献[4]中提出了基于日志重放的容器迁移方法，该方法的迁移时间随着容器运行时间的增加而增加，然而企业级应用往往需要长时间运行，因此该方法存在耗时长的问题，而且该方法仅适用于同构的容器云环境；文献[5.6中利用Checkpoint-Restart技术来进行容器应用迁移，但是该方法需要迁移前后的环境中文件系统一致，并且要求网络一致，无法适用于不同云提供商、跨地域的多数据中心的应用迁移。国外主流的研究Docker容器迁移技术团队CRIU[8]也是利用了与CR技术类似的思想来进行容器迁移；文献[7]中提出的应用迁移三层模型将应用迁移过程分为BaseLayer、ApplicationLayer和InstanceLayer这三层，该方法虽然能在BaseLayer层保证迁移前后文件系统一致性，但是由于未考虑到异构容器云之间的异构性，无法实现迁移前后对应用的接管。因此文献[4\~7]中提出的方法同样都无法解决基于Docker容器的应用在异构容器云之间的迁移。

本文提出基于Docker容器的应用跨异构容器云迁移三层模型TMHCC，该模型能同时适用于同构云异构容器编排引擎和异构云中Kubernetes集群的情况。通过镜像预同步技术的引入，能有效提高应用迁移的效率。

# 1基于Docker容器的应用跨异构容器云迁移三 层模型TMHCC

# 1.1异构容器云定义

异构容器云分为同构云异构容器编排引擎和异构云同构容器编排引擎两种情形。前者是指云平台本身的是同构的，但是容器服务使用了不同的容器编排引擎。而后者则是指虽然云平台本身是异构的，但是使用的都是同一种容器编排引擎。若两个数据中心都使用的是阿里云的容器服务，两者都使用相同类型的存储和网络，但是一个数据中心使用的是Kubernetes容器编排引擎，而另一个数据中心使用的是DockerSwarm容器编排引擎，这种情形就是同构云异构容器编排引擎。若两个数据中心一个使用的是阿里云的容器服务，而另一个数据中心使用的是华为云的容器服务，两家容器服务在网络和存储方面存在着异构性，但是两个数据中心用的都是Kubernetes容器编排引擎，这种情形就是异构云同构容器编排引擎。

# 1.2 三层模型

基于Docker容器的应用跨异构容器云迁移三层模型如图1所示。该模型将应用在进行跨容器云迁移时分成镜像层、编排层和应用层这三个层次。

![](images/36238f8160fb867f61f0755cd9324070072b2e6fcd7dd8130a479432034c7f47.jpg)  
图1基于Docker 容器的应用跨异构容器云迁移三层 Fig.1Three-layered model of migrating Docker container based applications across heterogeneous container clouds

# 1.2.1TMHCC镜像层

在Docker中，容器镜像是容器的基础[9]。因此在将基于Docker容器的应用进行迁移时，确保迁移前后的源数据中心和目的数据中心之中含有该应用所依赖的镜像文件至关重要。基于Docker容器的应用跨云迁移三层模型在镜像层同步源数据中心和目的数据中心的镜像仓库。Docker、Kubernetes以及各云提供商（如华为和阿里）等都遵循OCI规范，因此源数据中心和目的数据中心的容器镜像格式都相同。在进行镜像同步时无须对镜像格式进行转换。

# 1.2.2TMHCC编排转换技术

基于Docker容器的应用跨云迁移三层模型在编排层根据源数据中心和目的数据中心的特性进行编排模板的同步。应用的编排模板包含一组容器服务的定义及其相互关联，可用于多容器应用的部署及管理。DockerSwarm支持Docker

Compose 模板规范，可以用Compose文件来编排和部署应用。Kubernetes集群支持以YAML文件或者JSON文件的格式来编排和部署应用的各种资源对象，也支持通过Helm来简化应用的部署。对于应用在同构云异构容器编排引擎之间迁移的情形，编排层通过SwarmNetes来同步编排模板；对于应用在异构云Kubernetes集群之间迁移的情形，编排层通过HelmConvert来同步编排信息Chart模板。

对于同构容器云中的 Docker Swarm 集群和 Kubernetes集群之间的应用迁移，通过设计和研发SwarmNetes来实现编排信息同步。SwarmNetes 架构如图2所示。SwarmNetes能将 v1、v2 和 v3 版本的 Docker Compose 编排文件与Kubernetes 的 ConfigMap、Service、ReplicationController、DaemonSet、Deployment、Pod 和PersistentVolumeClaim这6中资源对象进行相互转换。

![](images/13230a569eb70606474e3e8f7f7033560126d9f927168305a5bb30a0315e296d.jpg)  
图2SwarmNetes 架构 Fig.2Architecture of swarmnetes

虚线所示方向为应用从Kubernetes集群向DockerSwarm集群迁移时编排文件转换过程，SwarmNetes从输入的Kubernetes编排信息文件中提取应用信息，并保存在中间表示层SwarmNetes对象中，通过转换将SwarmNetes对象转换为DockerSwarm集群可以识别的Swarm 对象，最后根据Swarm对象输出DockerSwarm集群的编排文件；实线所示方向为应用从Docker Swarm集群向Kubernetes集群迁移时编排文件转换过程，SwarmNetes从输入的DockerSwarm编排信息文件中提取应用信息，并保存在中间表示层SwarmNetes 对象中，通过转换将 SwarmNetes 对象转换成Kubernetes可以识别的Kubernetes对象，最后根据Kubernetes对象输出Kubernetes集群的编排文件。SwarmNetes实现编排信息转换算法如算法1所示。

算法1SwarmNetes编排信息转换算法

1.SwarmNetesobject $\mathbf { \sigma } = \mathbf { \sigma }$ LoadFile(InputFiles);   
2．if Provider $\scriptstyle = =$ Kubernetes then   
3.Swarmobject=kubernetes.Transform(SwarmNetesObject)   
4.SwarmFile=Kubernetes.Output(SwarmObject)   
5.else   
6.KubernetesObject $\ c =$ swarm.Transform(SarmNetesObject)   
7.KubernetesFile $\mathrel { \mathop : } =$ Swarm.Output(Kubernetesobject)

# 8．end if

由于异构云存储和网络方面存在的异构性，使得基于Docker容器的应用在异构云的Kubernetes集群之间迁移时存在无形的障碍，即若一个基于Dokcer容器的应用使用了某个云服务提供商特定的存储或者网络，迁移到基于另一个云服务提供商的数据中心时，该应用无法成功启动，目的数据中心无法识别应用中存储和网络的类型。对于异构容器云Kubernetes集群之间的应用迁移，本文通过设计和研发HelmConvert将源数据中心应用的Chart模板转换为适用于目的数据中心的Char模板。

HelmConvert的架构如图3所示。输入层读取一个应用的Chart模板，并对读取后的内容进行相应的处理，如将Chart模板中values.yaml文件中定义的各项配置渲染到templates文件夹中定义的各种资源对象等。识别层对输入层的结果进行识别，该层主要根据用户提供的云服务提供商类别，如“Huawei”或者“Ali”，分别表示华为容器服务提供商以及阿里容器服务提供商，以及各云服务提供商容器服务的特性来识别输入的Chart模板使用了何种类型的存储和网络。在转换层，主要根据本文给出的异构存储和网络转换方法进行相应的转换，使得转换后的Chart 模板能适用于目的数据中心的容器服务提供商。最后在输出层对转换后的Chart模板进行输出。

![](images/7a8480b202731bea3db422bd944feb56f504f65a2e375ccb9eae3e22d2446024.jpg)  
图3HelmConvert架构   
Fig.3Architecture of helmconvert

华为云容器服务支持EVS（Elastic Volume Service，云硬盘）、文件存储和OBS（Object Storage Service，对象存储服务等类型的存储，阿里云容器服务支持阿里云云盘、NAS（NetworkAttachedStorage，阿里云文件存储）、OSS（ObjectStorage Service，阿里云对象存储）这三种类型的存储。虽然各家在各种存储实现方式上存在着区别，但是华为云容器服务和阿里云容器服务都支持以PV（持久化存储卷PersistentVolume）和PVC（持久化存储卷声明PersistentVolumeClaim）的形式来提供存储资源。Kubernetes提供PV和PVC这两个API资源来抽象存储的细节。集群管理员只需关注如何通过PV提供存储功能，而无须关注用户如何使用它。类似的，用户仅需将PVC挂载到容器中，而不需关注存储卷的具体技术实现。存储的异构性对用户是透明的。PVC和PV的关系与Pod和Node的关系类似，前者消耗后者的资源。正是由于PV和PVC对存储细节的抽象，使得异构存储之间相互转换有了可行的解决方法。HelmConvert将华为云EVS和阿里云云盘互相转换、华为云文件存储和阿里云NAS互相转换以及华为云OBS和阿里云对象存储互相转换。

容器服务为满足多种复杂场景下基于Docker容器的应用间的互相访问，提供了不同的访问方式，从而满足不同场景提供不同的访问通道。这些网络访问可以分为集群内访问、VPC内访问、四层负载均衡和七层负载均衡这四种访问方式。集群内房网和VPC内访问属于私网访问，后两者为公网访问。在研究中发现，对于集群内访问方式，华为云和阿里云都遵循原生Kubernetes标准，因此当基于Docker容器的应用使用集群内访问方式时，可以在异构云平台之间进行无缝迁移。对于其他三种访问方式HelmConvert通过特征属性识别相应网络类型并进行转换。

# 1.2.3TMHCC应用层

基于Dokcer容器的应用依赖于镜像文件以及对这个应用的编排信息文件。源数据中心的应用经过在镜像层对镜像文件的同步和在编排层对编排信息的同步，目的数据中心已经具备该应用的基本要素。最后在应用层根据编排信息文件和镜像文件启动该应用即可。对于同构云异构容器编排引擎的情况，当目的数据中心为Kubernetes集群时，通过kubectlcreate-f[file]可以创建相应的应用；当目的数据中心为Docker Swarm集群是，通过docker-composeup或者dockerstack deploy-compose-file=filename 可以创建相应的应用。对于异构云Kubernetes集群的情况，通过Helm来简化了应用的管理，利用helminstall指令即可创建应用。

# 1.3基于镜像预同步的应用迁移技术

对于未采用镜像预同步技术进行应用迁移的方法本文称之为传统方法。传统方法如图4所示，需要进行以下五个步骤：

a)将源数据中心应用的编排信息文件1转换为目的数据中心能识别的编排信息文件2，并将编排信息文件2同步到目的数据中心。在该步中，根据不同情形用SwarmNetes 或者HelmConvert进行相应的转换;

b)在目的数据中心根据编排信息文件2创建应用时会从镜像仓库2拉取应用所依赖的镜像文件，若镜像仓库2中没有该应用所依赖的镜像文件，则进行step3；若镜像仓库2中有该应用所依赖的镜像文件，则进行 step4;

c)从源数据中心的镜像仓库1同步应用所需的镜像文件到镜像仓库2中；

d）从镜像仓库2中拉取应用所需的镜像文件；  
e)根据编排信息2和镜像文件创建运行并运行。

传统方法实现应用迁移所需的总时间 $\mathrm { T } _ { 1 }$ 如式(1)所示。

$$
T _ { 1 } = T _ { O r c S y n c } + T _ { \mathrm { { I m } } a g e S y n c } + T _ { A P P R u n }
$$

$$
T _ { O r c S y n c } = T _ { O r c C o n v e r t } + T _ { O r c \mathrm { R e } p }
$$

其中：TorcSync 为编排信息同步的时间，是 TorcConvert 和 TorcRep之和。TorcConvert 为 SwarmNetes 在源数据中心将编排信息1转换为编排信息2的时间。对于同构云异构容器编排引擎的情形，TorcConvert即为通过SwarmNetes 进行编排信息转换的时间；对于异构云Kubernetes 集群的情形，TorcConvert 即为HelmConvert 进行编排信息转换的时间。TorcRep 为将编排信息2从源数据中心同步到目的数据中心所用的时间。TImageSync为镜像仓库1和镜像仓库2进行镜像同步的时间，TAppRun在目的数据中心通过编排信息2和镜像文件创建应用所用的时间。

![](images/7a89ad49340be4cda00985ab6c66d6bc0e18971349cb36fefec75ad45e27ec28.jpg)  
图4应用迁移传统方法

![](images/9a0e94fd49bf4dc1dea39364d35e5b6c7a63775701808ee205ec3c7b3bb1cef4.jpg)  
Fig.4Traditional method of migrating applications   
图5基于镜像预同步的应用迁移技术

基于镜像预同步的应用迁移技术在源数据中心引入镜像预同步（Image Pre-Synchronization,IPS）模块，IPS实时监测源数据中心新建镜像的操作，若监测到有新建的镜像文件，立即监测目的数据中心的镜像仓库2中是否有该镜像文件，若没有则将该镜像文件同步到镜像仓库2中，如图5所示。

基于镜像预同步的应用迁移技术需要进行以下步骤：

a)在源数据中新实时检测新镜像文件的生成，若发现新建立的镜像文件，立即同步到目的数据中心，主要由镜像预同步IPS 模块负责；

b）将源数据中心应用的编排信息文件1转换为目的数据中心能识别的编排信息文件2，并将编排信息文件2同步到目的数据中心。在该步中，根据不同情形用SwarmNetes或者HelmConvert进行相应的转换；

)在目的数据中心根据编排信息文件2创建应用时会从镜像仓库2拉取应用所依赖的镜像文件，若镜像仓库2中没有该应用所依赖的镜像文件，则进行step4；若镜像仓库2中有该应用所依赖的镜像文件，则进行step5;

d)从源数据中心的镜像仓库1同步应用所需的镜像文件到镜像仓库2中；

e)从镜像仓库2中拉取应用所需的镜像文件；

f)根据编排信息2和镜像文件创建并运行应用。

基于镜像预同步的应用迁移技术实现应用迁移需要的总时间 $\mathrm { T } _ { 2 }$ 如式（3）所示。

$$
T _ { 2 } = T _ { o r c S y n c } + T _ { A P P R u n }
$$

应用迁移时镜像同步阶段占用了主要之间，从Ti、T2的表达式可以看出基于镜像预同步的应用迁移技术大大缩短了基于Docker容器的应用进行跨容器云迁移时的总时间。

# 2 实验与分析

基于镜像预同步的应用迁移三层模型是在基于Docker容器的应用跨异构容器云迁移三层模型的基础之上引入了基于镜像预同步的应用迁移技术。本文选取不同的基于Docker容器的应用来进行实验，并对引入镜像预同步技术前后的实验结果进行了对比分析。

# 2.1同构云异构容器编排引擎

为验证基于镜像预同步的应用迁移三层模型在DockerSwarm集群和Kubernetes集群之间（即同构云异构容器编排引擎之间）的可行性及有效性。本文选取Docker容器中的四个典型应用来验证基于镜像预同步的应用迁移三层模型在同构云异构容器编排引擎情形下的可行性和有效性。这个四个应用分别为：

a)Counter。Counter应用统计访问数据库的次数，并在Web页面上显示。该应用依赖redis:3.0和tuna/docker-counter23:latest 这两个镜像，镜像文件大小分别为91.5MB和696.0MB。

b)Wordpress。Wordpress 是一款个人博客系统，使用PHP和MySQL数据库开发。该应用依赖wordpress:4.8-apache和mysql:5.6这两个镜像，镜像文件大小分别为408.0MB和256.0MB。

c)Gitlab。Gitlab应用用于仓库管理，使用Git作为代码管理工具，并在此基础上搭建web服务。该应用依赖redis:latest、postgresql:9.5和 gitlab:8.13这三个镜像，镜像文件大小分别为133.0MB、232.0MB和770MB。

d)Vote。Vote负责统计对Dog和Cat这两个对象的投票 结果，并在web页面上显示。该应用依赖redis:alpha、 postgres:9.4、 docker/example-voting-app-worker docker/example-voting-app-vote 和 tmadams333/example-voting-app-result这5个镜像，镜像文件 大小分别为27.8MB、263.0MB、574.0MB、83.5MB和226.0 MB。

# 2.1.1实验环境

在该实验中，实验平台选取开源的Openstack，其版本为pike。并在Openstack中分别建立基于Kubernetes 集群的Docker容器环境和基于Docker Swarm的Docker容器环境。如图6所示，Kubernetes集群包括Master节点（IP地址为10.33.122.77）、节点1（IP地址为10.33.122.86）和节点2（IP地址为10.33.122.81）这三个节点，各节点配置参数如表1所示；同样DockerSwarm集群也包括管理节点（IP地址为10.33.35.35)，节点1（IP地址为10.33.35.34）和节点2（IP地址为10.33.35.19）这三个节点，各节点参数配置如表2所示。各个节点之间的网络带宽均为 $1 0 0 0 \mathrm { M }$ 。

![](images/b41957d02d69abbcc2ea2ca1a7f10ce2bdc77baa98c61794e56c8023aa04d82e.jpg)  
Fig.5Technology of migrating applications based on Image Pre-Synchronization   
图6Kubernetes 集群和Docker Swarm 集群 Fig.6Kubernetes clusters and Docker Swarm clusters

Table1 Configuration of nodes in Kubernetes clusters   

<html><body><table><tr><td>项目</td><td>规格说明</td></tr><tr><td>操作系统</td><td>CentOS7.4内核版本3.10</td></tr><tr><td>虚拟内核数</td><td>2</td></tr><tr><td>内存</td><td>4GB</td></tr><tr><td>跟磁盘</td><td>100GB</td></tr><tr><td>Docker 版本</td><td>17.03.2-ce</td></tr><tr><td>Kubernetes 版本</td><td>V1.9.0</td></tr></table></body></html>

表2Docker Swarm 集群节点配置

表1Kubernetes集群节点配置  
Table 2Configuration of nodes in Docker Swarm clusters   

<html><body><table><tr><td>项目</td><td>规格说明</td></tr><tr><td>操作系统</td><td>CentOS7.3 内核版本3.10</td></tr><tr><td>虚拟内核数</td><td>4</td></tr><tr><td>内存</td><td>4GB</td></tr><tr><td>跟磁盘</td><td>100GB</td></tr><tr><td>Docker 版本</td><td>17.03.2-ce</td></tr></table></body></html>

# 2.1.2实验结果

实验中分别用传统方法和基于镜像预同步的三层模型将Counter、Wordpress、Gitlab 和Vote 这四个应用从Kubernetes集群迁移到DockerSwarm集群，迁移所用时间如图7所示。传统方法迁移所用时间分别为121.71s、117.46s、193.25s和185.10s，而利用基于镜像预同步的三层模型进行迁移分别只需要 $4 6 . 9 7 \mathrm { ~ s ~ }$ 、 $5 4 . 2 8 \mathrm { ~ s ~ }$ 、62.06s和 $8 2 . 0 8 \mathrm { ~ s ~ }$ 。

随后，本文再分别用传统方法和基于镜像预同步的三层模型将 Counter、Wordpress、Gitlab 和Vote 这四个应用从DockerSwarm进群迁移到Kubernetes集群之中，迁移所用时间如图8所示。传统方法所用时间分别为 $1 2 8 . 3 4 \mathrm { ~ s ~ } . 1 2 0 . 2 5 \mathrm { ~ s ~ } .$ ：184.02s和191.22s，而利用基于镜像预同步的三层模型进行迁移分别只需要45.72s、53.32s、62.73s和 $7 9 . 5 2 \mathrm { ~ s ~ }$ 。

![](images/8f9c3a7923fbfca3a5308ea1ab52ae3899b82ae6e62c2d8cb18de5e65f1851eb.jpg)  
图7应用从Kubernetes 集群迁移到Docker Swarm集群所用时间 Fig.7Time of migrating applications from Kubernetes clusters to Docker Swarm clusters

![](images/bbf84414462dd204cd898bab162045926f2b89d3193e4e73dbc8123384d7a888.jpg)  
图8应用从Docker Swarm集群迁移到Kubernetes 集群所用时间 Fig.8Time of migrating applications from Docker Swarm clusters to Kubernetes clusters

从图7和8的实验结果之中可以看出基于Docker容器的应用在在DockerSwarm集群和Kubernetes集群之间迁移时镜像同步占用了大部分时间，基于镜像预同步的三层模型通过镜像预同步技术在很大程度上减少了应用在DockerSwarm集群和Kubernetes集群之间迁移的时间，使得应用迁移时间性能平均提升了 $6 0 . 3 3 \%$ 。

# 2.2 异构云Kubernetes集群

为验证基于镜像预同步的应用迁移三层模型在华为云容器服务的Kubernetes集群和阿里云容器服务的Kubernetes集群之间(即异构云Kubernetes集群之间)的可行性和有效性。本文选取Nginx 这个应用来进行验证。Nginx 由俄罗斯的程序设计师Igor Sysoev 开发，是一个高性能的HTTP 服务器、反向代理服务器以及电子邮件代理服务器（IMAP/POP3）。为了尽可能涵盖华为云容器服务和阿里云容器服务之间异构存储和异构网络的所有情况，本文将Nginx这个应用分别设计为使用不同类型的存储和网络。应用Nginx1在华为云容器服务中使用的存储类型为华为云EVS，网络类型为VPC内访问，在阿里云容器服务中使用的存储类型为阿里云云盘，网络类型为VPC内访问；应用Nginx2在华为容器服务中使用的存储类型为华为云文件存储，网络类型为四层负载均衡，在阿里云容器服务中使用的存储类型为阿里云NAS，网络类型为四层负载均衡；应用Nginx3在华为云容器服务中使用的存储类型为华为云OBS，网络类型为七层负载均衡，在阿里云容器服务中使用的存储类型为阿里云OSS，网络类型为七层负载均衡。Nginx1、Nginx2和 Nginx3这三个应用都依赖nginx:latest这个镜像，该镜像大小为109MB。

# 2.2.1实验环境

本文在华为云容器服务和阿里云容器服务中分别搭建了Kubernetes集群，如图9所示。

![](images/15cc5cf01405d47927192d5357375440a4365357bd17dc3538e2a4aba699c9a2.jpg)  
图9华为容器服务Kubernetes集群和阿里容器服务Kubernetes集群  
Fig.9Kubernetes clusters based on Huawei container service and Kubernetes clusters based on Ali container service

数据中心1位于北京，是在华为容器服务中搭建的Kubernetes集群，其包括一个Master节点（IP地址为192.168.0.193）和两个Worker节点（IP地址分别为192.168.0.200和192.168.0.202)，并为数据中心1搭建了私有镜像仓库1，其IP地址为192.168.0.204。数据中心2位于深圳，是在阿里容器服务中搭建的Kubernetes集群，该Kubernetes集群拥有过3个Master节点（IP地址分别为192.168.0.195、192.168.0.196和192.168.0.197)和3个Worker节点（IP地址分别为192.168.0.198、192.168.0.199和192.168.0.200)，并为数据中心2搭建了私有镜像仓库2，其IP 地址为192.168.0.200。数据中心1和数据中心2中各节点配置参数如表3和4所示。

表3数据中心1各节点参数配置  
Table 3Configuration of nodes in data center 1   

<html><body><table><tr><td>项目</td><td>规格说明</td></tr><tr><td>操作系统</td><td>EulerOS2.0 (SP2) 内核版本3.10</td></tr><tr><td>虚拟内核数</td><td>4</td></tr><tr><td>内存</td><td>8GB</td></tr><tr><td>磁盘</td><td>40GB（系统盘）+100GB（数据盘）</td></tr><tr><td>Docker 版本</td><td>17.06.0.10</td></tr><tr><td>Kubernetes版本</td><td>v1.9.7</td></tr><tr><td>所在区域</td><td>华北-北京</td></tr><tr><td></td><td>表4数据中心2各节点参数配置</td></tr><tr><td></td><td>Table 4 Configuration of nodes in data center 2</td></tr><tr><td>项目</td><td>规格说明</td></tr><tr><td>操作系统</td><td>CentOS7.4 内核版本 3.10</td></tr><tr><td>虚拟内核数</td><td>4</td></tr><tr><td>内存</td><td>8GB</td></tr><tr><td>磁盘</td><td>40GB（系统盘）</td></tr><tr><td>Docker 版本</td><td>17.06.2-ce-3</td></tr><tr><td>Kubernetes 版本</td><td>v1.10.4</td></tr><tr><td>所在区域</td><td>华南-深圳</td></tr></table></body></html>

# 2.2.2实验结果

在验证基于镜像预同步的三层模型在异构云Kubernetes集群之间的适用性时，本文分别用传统方法和基于镜像预同步的三层模型将Nginx1、Nginx2、Nginx3这三个应用从华为容器服务的Kubernetes集群中迁移到阿里容器服务的Kubernetes集群之中，迁移所用时间如图10所示。在用传统方法进行迁移时，Nginx1、Nginx2和Nginx3这三个应用迁移所用时间分别为28.16s、24.13s和 $2 5 . 9 6 \mathrm { s }$ 。而当用基于镜像预同步的应用三层模型进行迁移时，Nginx1、Nginx2和Nginx3这三个应用迁移所用的时间分别只需要13.72s、12.76s 和 12.95s。

![](images/d465b0f565a4839d58c9319c3a117af5f1419e425c534e481f5027efe12ac9b9.jpg)  
图10应用从华为Kubernetes 集群迁移到阿里Kubernetes集群所用时间

![](images/55ca78d9046fca3beca93ba290db8d8ed2184395a3748c069d49b5659cdc7559.jpg)  
Fig.10Time of migrating applications from Kubernetes clusters based onHuawei to Kubernetes clusters based on Ali   
图11应用从阿里Kubernetes 集群迁移到华为Kubernetes集群所用时间  
Fig.11Time of migrating applications from Kubernetes clusters based on Ali to Kubernetes clusters based on Huawei

随后，本文再分别用传统方法和基于镜像预同步的三层模型将Nginx1、Nginx2和Nginx3这三个应用从阿里容器服务的Kubernetes集群中迁移到华为容器服务的Kubernetes集群之中，迁移所用时间如图11所示。在用传统方法进行迁移时，Nginx1、Nginx2和Nginx3这三个应用迁移所用时间分别为 $4 1 . 3 3 \mathrm { ~ s ~ . ~ } 3 3 . 8 1$ s和37.91s。而当用基于镜像预同步的应用迁移三层模型进行迁移时，Nginx1、Nginx2 和Nginx3这三个应用迁移所用的时间分别只需要25.68s、22.71s和$2 1 . 6 8 \mathrm { ~ s ~ }$ 。

从图10和11中的实验结果之中可以看出，基于Docker容器的应用在华为容器服务的Kubernetes集群和阿里容器服务的Kubernetes集群之间迁移时，与基于Docker容器的应用在DockerSwarm集群和Kubernetes集群之间迁移时一样，镜像同步阶段占用了应用迁移的大部分时间。基于镜像预同步的三层模型通过镜像预同步技术在很大程度上减少了应用在华为容器服务的Kubernetes集群和阿里容器服务的Kubernetes集群之间迁移的时间，使得应用迁移时间性能平均提升了 $4 3 . 6 7 \%$ 。

# 3 结束语

为满足将基于Docker容器的应用在异构容器云之间迁移的需求，本文提出了基于Docker容器的应用跨异构容器云迁移三层模型。并在编排层设计和研发了SwarmNetes 来屏蔽异构容器编排引擎之间的异构性，使得基于Docker容器的应用在同构云异构容器编排引擎之间的迁移成为可能；同时也在编排层设计和研发了HelmConvert来屏蔽不同提供商的容器服务之间的异构性，使得基于Docker容器的应用在异构云Kubernetes集群之间的迁移成为可能。并在三层模型的基础上，本文提出了基于镜像预同步的应用迁移技术来优化基于Docker容器的应用跨异构容器云迁移的时间效率。下一步的工作应该将研究如何减少三层模型带来的网络带宽消耗，确保数据中心之间网络传输频繁时不会给用户正常工作带来影响。Docker容器技术也在处在不断发展和更新的进程中，各种容器编排引擎和各云提供商的容器服务也在不断完善，力求充分发挥容器的优势，现阶段的研究无法囊括未来未知的各种情况，今后还需要继续关注Docker容器技术的发展，针对Docker容器技术的新特性进行完善。

# 参考文献：

[1]AbdelBaky M,Diaz-Montes J,Parashar M,et al.docker containers across multiple clouds and data centers [C]//Proc of the 8th IEEE/ACM International Conference on Utility and Cloud Computing.New York: ACM Press,2015:368-371.   
[2]Kumar KM,KumarD S,MurudiV.Multi Data Center Cloud Cluster Federation-Major Challenges & Emerging Solutions [C]//Proc of IEEE International Conference on Cloud Computing in Emerging Markets.Piscataway,NJ:IEEE Press,2016:107-122.   
[3]Gupta V, Chaunhan S,Sharma D.Platform virtualization: understanding virtual machines，LXC，Docker,Kubernetes and Ubernetes[J]. International Journal of Innovations in Engineering and Technology. 2016,7(6):442-447.   
[4]Yu C Y, Huan F.Live migration of docker containers through logging andreplay [C]//Procof the 3rd International Conferenceon Mechatronics and Industrial Informatics.Paris,France:Atlantis Press, 2015:623-626.   
[5]Mirkin A,Kuznetsov A,Kolyshkin K.Containers checkpointing and live migration [C]// Proc of Linux Symposium.20o8: 85-90.   
[6]Laadan O，HallynSE. Linux-CRtransparentapplication checkpoint-restart in Linux [C]// Proc of the Linux Symposium.2010: 159-172.   
[7]Machen A,Wang SQ,Leung KK,et al.Live service migration in mobile edge clouds [J].IEEE Wireless Communications.2018,25 (2): 140-147.   
[8]CRIU[EB/OL].[2018-08-28].https://criu.org/Usage_scenarios# Container_live_migration.   
[9]浙江大学SEL实验室.Docker容器与容器云[M].2版．北京：人民 邮电出版社,2016.   
[10]Kubernetes [EB/OL].[2018-09-21].https://kubernetes.io/.   
[11]Docker Swarm [EB/OL].[2018-09-21].https://docs.docker.com/.   
[12]毛祺，卢胜林．基于Docker Swarm 集群的容器迁移策略的实现[J]. 信息技术,2016(9):156-160.(Mao Qi,Lu Shenglin.Implementation of container migration strategy based on the docker swarm cluster [J]. Information Technology,2016 (9):156-160.)   
[13]卢胜林，倪明，张翰博．基于Docker Swarm 集群的调度策略优化 [J]．信息技术，2016（7):147-151.(Lu Shenglin，Ni Ming,Zhang Hanbo.The optimization of scheduling strategy based on the Docker swarm cluster[J].Information Technology,2016(7):147-151.)