# 3D打印模型及BIM模型Web嵌入应用

# 张军朱贺 魏树臣李凯

（中建八局第一建设有限公司，济南250000）

【摘要】3D打印模型源文件一般为特定格式的STL文件,现开发人员引入开源WebGL语言实现了HTML5页面无需安装插件即可实现3D打印模型的在线浏览，无需任何浏览器插件支持，同时引入二维码编译脚本能实现手机端扫描二维码进行模型预览和源文件下载。BIM模型Web嵌入应用借助3dsmax 开放式插件,将 revit模型导入到3dsmax，3dsmax 安装开放式模型上传插件实现一键生成 HTML5可直接打开的三维模型并附带渲染的纹理模型，浏览器终端支持旋转、放大、漫游及简易交互功能，可深入应用前景广阔。

关键词】3D打印;HTML5;Three.js;BIM;Revit;3dsmax;WebGL

【中图分类号】TU17 【文献标识码】A 【文章编号】1674-7461(2017)03-0058-05   
【DOI】10.16670/j.cnki.cn11-5823/tu.2017.03.10

# 引言

随着信息化技术在建筑业的深入应用，很多建筑工程公司在提智慧工地的概念，其中有一项是3D打印技术应用，3D打印在建筑工程中可实现整体建筑模型、复杂细部构造节点的打印，3D打印房屋技术也已经逐渐从实验室走向实际应用，可以说3D打印技术在建筑工程领域应用场景较为广泛,应用前景非常广阔。目前我司很多工程项目部都配备了小型3D打印机，3D打印首先需要技术人员建立3D 模型,模型建立最初所用的软件多是3dsmax、Autodeskrevit、Sketchup等，但市面上3D打印机多支持的源模型为STL、OBJ格式，部分项目部做的模型可以共用，故公司软件开发人员建立了一个公用平台，项目部人员可将建立好的STL 源文件上传网端，实现HTML5页面直接浏览三维模型，并能支持手持终端二维码扫描预览、下载和分享模型。

类似于实现3D打印模型的HTML5页面浏览功能，我司也探索将BIM模型(3dsmax、Autodeskre-vit、Sketchup等）也在网络端实现浏览功能，但是BIM模型的网络端浏览不同于3D打印STL文件的网络端浏览，STL文件本身不支持纹理、色彩的展现，页面后台编译的语言相对简单，BIM模型需保持和桌面软件同样的渲染、纹理效果，页面后台编译的语言相对复杂，目前国内能实现此类功能的专业科技公司较少，为此我司寻找了一个开放式3dsmax插件NaycentUploader,实现了在3dsmax 软件框架下模型一键到云端功能，我司在此功能基础上进行后台调用即嵌入了自己的系统平台。

# 23D打印模型Web嵌入应用

# 2.13D打印模型创建、转换、打印

模型创建应用Autodeskrevit、Autodesk3dsmax等软件，其中Autodeskrevit创建的模型需导出FBX格式文件到Autodesk3dsmax里面进行二次处理。Autodesk3dsmax即可创建模型，也可转换模型，3dsmax可将识别文件另存为STL文件。3D打印机联机软件为CURA,CURA可直接打开 STL文件,用于调整模型大小及打印精细程度。

# 2.2 Web嵌入开发设计

Web嵌入开发编译语言为JavaScript，功能分四点设计：后台STL模型上传、模型在线浏览（支持PC端旋转、平移、缩放，支持触屏类终端单指旋转、双

表13D打印应用关联软件  

<html><body><table><tr><td>软件名称</td><td>支持文件格式</td><td>软件功能</td></tr><tr><td>Autodesk Revit</td><td>Rvt转FBX</td><td>模型创建</td></tr><tr><td rowspan="2">Autodesk3dsmax</td><td>Max、OBJ、FBX等，</td><td>模型转换和</td></tr><tr><td>支持转换为 STL</td><td>模型创建</td></tr><tr><td>CURA</td><td>STL</td><td>3D打印</td></tr></table></body></html>

模型在线浏览核心功能需要引入开源WebGL模型加载程序，利用WebGL模型加载程序将STL文件进行加载，转换为WebGL可以利用的数据。Three.js是一款开源的主流3D绘图JS引擎，可以用来构建3D视图、立体动画、人机交互，引擎内包含容器（container）场景（scene）、摄像机（camera）、指缩放、三指平移）、模型二维码标签（支持扫码三维预览、下载、分享）、模型热度排序（根据下载量及浏览量）。

![](images/304ae0e761ef5317445de4857dc4ac298f266952701e3d76bfb7a34e801ff34f.jpg)  
图1 Autodesk3dsmax导出STL文件

![](images/e467cda5d2cef9fa03d9c2611daf1097053adeebff2a121f4b469ff8a516e9f6.jpg)  
图23D打印模型  
图3开发架构图

# 2.3 Web嵌入功能开发

WebGL完美地解决了现有的Web交互式三维模型显示的两个问题：第一，它通过HTML脚本本身实现Web交互式三维模型的生成、浏览，无需任何浏览器插件支持；第二，它利用底层的图形硬件加速功能进行的图形渲染，是通过统一的、标准的、跨平台的OpenGL接口实现的。

渲染器(renderer）、控制装置（renderer）编译控制变量。STLLoder.js 是一款开源 STL文件（二进制和文本编码的 STL 文件)格式识别加载引擎,和 Three.js两者共同支撑Web端模型的加载、显示、渲染、交互控制。

本次开发以工程项目部为单位设置上传模型文件后台，仅支持 STL文件上传，模型上传完毕Web页面通过调用Three.js和STLLoder.js即可实现3D打印模型的在线浏览。

WebViewerModels3dprint.stl STL模型文件WebGLViewer□threejsloadersSTLLoader.js STL加载脚本文件three.js 3D绘图JS引擎OrbitControls.js Three.js内置脚本STL.html 执行网页LocalServer.pyreadme.txt

# 2.4Web模型二维码扫描预览及下载

为使所有的项目能共享下载模型及移动终端预览模型，本次开发引人二维码生成技术，每个模型在后台上传之后能生成此模型的移动终端预览

![](images/4285f8187ddd0b87087f3893e01ba752f4c5cf61987bb8bab0ce013c8842b1d5.jpg)  
图43D打印模型共享平台

![](images/157b42814e943c77aafe2c0f15d1cc9b322c21a588db561a643c052605b899b2.jpg)  
图53D打印模型Web浏览

二维码，支持移动终端浏览器HTML5页面打开。  
二维码生成采用开源QRCode.js 脚本文件。

# 2.5 应用总结

3D打印模型网络应用资源有限，我司开发人员通过研发将多个项目的3D打印模型实现了在线预览和下载共享，使项目间互通有无，带动了3D打印技术在我司所属项目的普及应用。

Web嵌入应用的核心是引入了Three.js3D绘图引擎，此引擎具备强大的三维图形处理功能，3D打印模型STL文件的在线浏览只是基础的应用，STL 文件表现色彩单一,没有纹理数据,若要加入色彩、纹理显示则需要 Three.js 搭配开源OBJLoder. js脚本文件，此功能也是开发团队下一步研发的方向。

# 3BIM模型Web嵌入应用

# 3.1 BIM模型创建、转换

本次开发人员研究将BIM模型轻量化在Web端（含手机）加载显示，所用的软件为3dsmax，因3dsmax支持多种类型的文件，现在主流应用的Re-vit、Sketchup等BIM软件成果文件均支持导入3dsmax。本文以Revit为例演示将rvt文件实现Web端(含手机)加载显示。

首先用Revit软件将建好的BIM模型导出Fbx格式文件（自带材质），然后在3dsmax中打开本Fbx格式模型，到这步基本就完成操作了，接下来需要借助一款模型上传网端的插件实现一键上传模型。

# 3.23D模型上传插件安装、应用

本次应用的辅助插件为：逆讯3dsmax模型上传插件。此插件由北京逆讯科技公司开发，提供一套直接将模型从3dsmax编辑器一键生成全平台在线浏览的解决方案，允许用户在3dsmax中将自己的模型，实时转化为一个网页链接，可在PC端浏览器，移动终端等Web平台方便分享传播。整个解决方案由3个部分组成：分别是3dsmax插件；后台模型识别处理系统；以及Web前端基于WebGL和Javascript语言编写的3D网页显示系统。

安装完成逆讯3dsmax模型上传插件后，在3dsmax软件插件配置面板上配置本插件，选择“NaycentUploader”替换原插件即可。配置完毕用“Upload”一键上传模型到网端，网端模型存储到逆讯科技的服务器，前提是需要注册逆讯科技服务账号，用户得到的就是一串网页链接。

![](images/db122f1f333eca6b68c963c63604bd6c4dd3fb1eda8ba4acaa0e9eb501f3c084.jpg)  
图6安装逆讯3dsmax模型上传插件程序

Configure Button Sets ? X O □ Utities: Sets: Camera Tradker MAX Default □   
国 Utilities Clean MultiMaterial Collapse Save Delete Color Cipboard More. Sets 5 otStoerer Contol Total Buttons: 白 Follow/Bank Utities: Asset Browser IFLMaceDupicateMaps A   
二 三 AssetBrowser   
一 Perspective Match Levlhrtanc Setd Perspective Match   
一 Collapse MAXFileFinder MAXScript Collapse Measure   
二 Color Clipboard Motion Capture Color Clipboard Naycent Uploader Measure Polygon Counter Measure Ree r 丰 二 Flight Studio (c) ncel

# BIM模型Web端操作

我司将本应用进行扩展、集成，给每个项目开□，让项目上传建好的BIM的模型，项目可多场景上传，如分基础阶段施工、主体阶段施工、装饰阶段施工等场景模型。项目部参照上述的操作只需在后台添加链接即可。BIM模型在线浏览支持PCWeb端鼠标左键旋转、右键平移、滚轮缩放，支持触屏类终端单指旋转、双指缩放、三指平移操作。

![](images/5fbaae4ce21bf02d17b489e7ef82f01b7140666eb7ee5b820109294b75c518a7.jpg)  
图8模型一键上传，反馈链接

# 3.4 BIM模型Web端应用前景

BIM 模型一般需要借助大型专业的软件制作,对电脑的配置要求很高，只能在桌面版软件打开，多数模型存储量较大，而且需要专业的技术人员建模、操作，不能满足非专业人士对BIM模型成果的需求。现BIM模型实现了线上应用的第一步，人人都可以看模型、应用模型，接下来会有更多的拓展功能实现线上应用，如Web端的BIM全生命周期管理、建筑构件属性查询、模型拆分浏览、根据模型设置热交互点接入其他信息等。

![](images/70cf172b271dc8cc6a4ae114baa79948b16aa4d637505e8cfa9d71b43afc51e6.jpg)  
图7配置3dsmax 模型上传插件  
图9PCWeb端显示效果(左键旋转、右键平移、滚轮缩放)

![](images/f2f0cc931b5d515b65dd9caa0ddf34b66d88fe16c209a4eac224f9a641c8568a.jpg)  
手机端显示效果(单指旋转、双指缩放、三指平移)

# 4结语

随着信息技术的快速发展，3D打印应用和BIM应用已经越来越普遍，我司将3D打印模型实现线上共享,将施工图纸中的复杂节点进行3D 打印，各个项目部之间互通有无，推动了3D打印技术在建筑工程领域的普及，也为以后3D打印房屋的应用积累了经验。

BIM模型的Web端应用是一个方向，专业的人干专业的事，但成果可以大家共享，BIM模型现在在Web的功能应用较为局限，但随着科技的进步，BIM在Web端的应用场景、功能会越来越丰富，为整个建筑行业BIM的广泛应用指引了方向。

# 参考文献

[1］李忠富，何雨薇.3D打印技术在建筑业领域的应用[J]．土木工程与管理学报，2015，32(2）：47-53.  
[3］北京逆讯科技有限公司.3dsMax模型上传插件使用说明书.

# 3D-Print Model and Web Embedded Applications in BIM Model

Zhang Jun，Zhu He，Wei Shuchen，Li Kai ( The First Company of China Eighth Engineering Bureau Co., Ltd.， Jinan 2501OO，China)

Abstract: The source files of 3D-printing modelsare always STL files with particular formats，but more recently，by introducing the open-source WebGL Language，programmers have realized the online browsing of 3Dprint models onthe HTML5 Page without instaling any plug-ins.What’s more，no plug-in needed for the browser, either.Meanwhile，through introducing the QR code compiling script，previewing models and downloading source files can be easily achieved just by scanning the QR code on your intellgent mobile phone.The Web embedded applications in BIM models applies theopenplug-in of 3dsmax software to import the Revit models into 3dsmax，and then the open model uploading plug-ins are instaled inthe 3dsmax to generate byone-touchthe 3D model with texturerendering function that available for HTML5.On the browser terminal，you can operate rotating，amplifying, roaming and simple interactive function on the model. This technology is of promising application prospect.

Key Words:3D-Print；HTML5；Three. js；BIM；Revit；3dsmax；WebGL