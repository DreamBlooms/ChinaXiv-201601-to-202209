# Simultaneous fusion, imaging and encryption of multiple objects using a single-pixel detector

;HI DONGFENG1A), HUANG JIAN1\*,WANG YINGJIAN $^ { 1 , 2 }$ , YUAN KEE1, XIE CHENBO1, LIU DONG1 AND ZHU WENYUE1

1KeyLaboratoryofAtmospheric CompositionandOptical Radiation，Anhui InstituteofOpticsandFine Mechanics，Chinese   
Academy of Sciences,Hefei 230031,China   
2University of Science and Technology of China, Hefei 230026, China

AEmail: dfshi@aiofm.ac.cn;\*Email: jhuang@aiofm.ac.cn

# Abstract

A novel technique for the simultaneous fusion,imaging and ecryption ofmultiple objects using asingle-pixel detector is proposed. Here,encoded multiplexing speckles are employed to illminate multiple objects simultaneously.The mixed lightreflected fromtheobjects isdetectedbyasingle-pixel detector.An iterativereconstruction method isusedtorestore thefused imagebysumming the multiplexed specklesand detected intensities.Next,clear imagesoftheobjectsare recovered by decoding the fused image. We experimentally obtain fused and multiple clear images by utilizing a singlepixel detectortocollect the direct and indirect reflected light.Technicalybyutilizing the speckles with per-pixel exposurecontrol，multipleobjects’information is multiplexed intothedetected intensitiesand then demultiplexed computationally under the single-pixel imaging and compressd sensing schemes.An encryption experiment is performed by seting the multiplexed speckles’encoding as keys. We find that the encryption performance in a scattering medium is better than that in a clear medium.

# INTRODUCTION

Withthedevelopmentofsemiconductortechologytraditionalimagingmatrixdetectors (suchascharge-coupleddevices[CCDsand complementarymetal-oxide-semiconductors[CMOs]tendtoavelargearrysofsmallpixels.Telatestmatrixdetectorscanapture high-resoltioniagesithlosofpixel.lterativelyanmagingsstem-bsedanedgle-peldectoru as aphotodetector[PDorphotomultipliertube[PMT)asreceivedincreasingatentionfromresearchersinecentyears.Thissinglepixelmaging(S)systememplosrandompecklestollumnatetebect,andthnteintensitsofteflectedortrasiht fromtheobjectareacquiredbyanun-scanedsingle-pixeldetector.Subsequently,theimageoftheobjectcanbercoveredbasedonthe correlationbetweentheiluminationspecklesandthedetectedintensties.Thisnewimagingsystem，whichincludesanintegrated computationalalgorit,canreducetecostorsizeofmatrixdetectors,specialliteifraredadteraertzregionoftesectru, wherematrix detectorsdonothavesuchgoodspecificationscompared totheirperformanceinthevisualspectrum.Traditional SPI systems forimageencrption-11]avebnstudied,whereterandomspecklesor/andtheetectedintensitesareutilizdaskeys. Here,anSPIthqueomsingultjectfusionagingandectionispopose,andanxperetalstudytoateth SPItechniqueisonducted.Encodedmutplexingspeckleseablethsimultaneous illminationofmultipleobjectsandcanbeapliedt fuse,imageandencrypttheseobjects.Theexperimentalresultsdemonstratetheefectivenessoftheproposedtechnique,evenina scattering environment.

This technique originated from compressed sensing(CS) theory[12] that allows the recording an image consisting of $N ^ { 2 }$ pixels using much fewer than $N ^ { 2 }$ measurements if it can be transformed to a basis where most pixels have negligibly small values.For example, theoretically-eg-pielouldpotetiallyeedtocostctamega-pieliageSpciicallaoplef e4 mega-pixelimageistakenandtenrecoveredtroughsparsesignalreconstructionmethods.Thisisposiblebecausenaturalimagestend tobesparse (i.e.，onlyasmallfractionof theseprojections haverelevantinformation）insomebasesoffunctions.Thehardware limitationsof raditionalimagingsystemsinesoftheirspatialesolutionandtemporalresolutioncaneefectivelyadreedsing thischaracteristic.Todate，severalmatriximagingsystems[13-15]havebenbuilt，andthefectivenessofthetheoryhasben confirmedexperimentallForexample,ametodofeficientspace-timesmplingwithpixel-wisecodedexposure toreconstructavideo fromasingleodediagewhilemaintaiingighspatialresolutionasbeeproposed3].Additionall,iangetal.aveclisd single-shotcompressedultrafastphotographyatonehundredbillonframespersecondwithrandomsampling4].Colletingthespectral information of an imaging scene via random sampling has also been proposed [15].

SimultaneouslytheCSalgorithmhasalsoreceivedsubstantialattentionforSPIThefirst workoncompressve SPI[3]was performedatRiceUniversity；theresultsshowedthatcompresiveSPIcanobtainahigh-qualityimagewithfarfewerNyquist measurements.Subsequently,teCSalgorithasbecomewidelyusedinSPsystems.Nvertheles,intheaboveSPrelatedreferences [1-7],theimagingeneisompletelyampledbyteilminationseckles.Howeeraccordingtoteaboveaalysisuateige informationcanberecoveredwhenthesceneisincompletelysampledbyillminatiospeckles.Then,speckleswithbservedspatial multiplexingmodecan beusedtosimultaneouslysample multipleobjects inanorderly manner.Iother words,an SPIsystem with spatial multiplexed speckles can be employed to achieve the fusion, imaging and encryption of multiple objects.

The whole procedureoftheproposedtechnique isdemonstratedinFig.1,in which fourobjectsserveasanexample.First,the computerprogramproducesfourcomplementarybinaryencodedmatrices—B1,B2,B3,andB4andmultiplexedspeckles(SS)S.The illuminationspecklesCareproducedbyresizingthematricesobtaedbymultiplyingthemultiplexedspecklesandencoded matrices. The assembling procedure of illumination speckle $\mathrm { C } _ { j }$ is shown in the gray frame of Fig. 1. The illumination speckles are loaded into the projectionsystemandthenprojectedontothescene.ThereflectedlightintensityGofthefourobjectsisdetectedbyasingle-pixel detector.Thefusedimageof tefourobjectscanberestoredusinganiterativereconstructionmethod.Next,fourrandomsamplingiages named fip, $\mathrm { f } _ { 2 \mathrm { p } }$ $\mathrm { f } _ { 3 \mathrm { p } }$ and $\mathrm { f } _ { 4 \mathrm { p } }$ ， indicating different random partial object information,can be recovered by multiplying the fused image and encodedmatrics.Finally,theigialimagesoftheorespondingjectcanbebtaiedusingthCSalgorit.Hre,ultiplegs arefusedandencryptedbyintegrating theminthe ixed measurement.According totheaboveanalysis,theencoded matricesarevery importantwhenrecoveringaccurateimageinformationduringsecondaryprocesing.Whentheencodedmatricesareunkowurate object informationcanotbeobtained.Acordingly，usingtheencoded matricesof theproposedmethodaskeyscanresultinthe encryption of the objects’ information.

![](images/e3a4303c5331323d91a255ab5d326bc33a28bdd5a4c12dfb66be31ef4d35ecea.jpg)  
Fig.1.Procedure of the proposed method: SS: multiplexed speckles， Sj: the $\mathrm { j }$ -th multiplexed speckle；B1-B4: four_complementarybinary encoded matrices； Cj: the j-th illumination speckle; HP: the Hadamard product of $\mathrm { S _ { j } }$ and the encoded matrices; PI: projection ilumination; MO: multiple objects; G: intensities detected bythe single-pixel detector; IT: the fused information $\hat { \boldsymbol { f } }$ calculated via an iterative reconstruction method; HP': Hadamard product of the fused information $\hat { \boldsymbol { f } }$ and the encoded matrices; $\mathbf { f } _ { \mathrm { l p } } .$ f2p, $\mathrm { f } _ { 3 \mathrm { p } }$ and $\mathrm { f } _ { 4 \mathrm { p } }$ : four random sampling images; $\mathrm { C S ^ { \prime } }$ : computed images offourobjects basedonthe CS algorithm; f1,f2,f3 andf4: fourrecovered images.

Compared withthe priorliteratureconcerning SPImethods,inaditiontotheadvantagesof SPI,the proposed technique has the followingaditioaladvantages.First,teuitedprocesswhichincorporatestheencryptionofthefusedimagewiththeopesd acquisitionofultipleojectsesuresthesecurityfprivatecotentand,tusimprovestheecrptioperformanceoftheSsystem relativetoconventioalsingle-pielencryptionmetods(inhchspcklesoandetectedintensitisaremploedaskeys)byproiding athirdkeybasedoteecodedmatricesusedinthismethod.Second,multipleojectscnbefused,imagedandecryptedusingsubNyquistmeasurements，whichsignificantlyreduces thedataacquisitionandallowsfasterdatacommunicationtousers.Therefore,the system efficiency can be greatly increased using the proposed method.

# RESULT

Experimental setup: The experimental system used to study the proposed approach is described as follows. A ${ 5 3 2 \mathrm { - n m } }$ continuous wave (cw)laserservsasthelghtsourceAdigitalmicromirrordevice(DMD:TDsystem)isusetogenerateiumnatispekles. Thre single-pixeldetectors (ThorlabsPM-PMM02)anddataacqusitionsystem (NIUSB-6211)areemployedforlightdetectioand dataacquisition,respectively.Thelaserbeamentersabeamexpander(BE)andthenpasss throughtheDMD,which provides timevarying illuminationspeckles.Tediectandidiectrfletedlightfromtemultiplebjects(MO)isollcedbycollctinglesad measuredbythesingle-pixeldetectors,andthentheintensitydataaresenttoacomputerthroughthedataacquisitionsystem.TheDMD has a tilted micro-planar mirror array; each of the flat mirrors can be tilted $\pm 1 2 ^ { \circ }$ independently to the“ON’ or“OFF” state.When a micromirror is tilted $+ 1 2 ^ { \circ }$ ,the corresponding pixel of the speckle is sampled and is equal to 1; when it is tilted $- 1 2 ^ { \circ }$ ,the corresponding pixel of the specklisequaltoO.TheDMDsystem withper-pixelexposurecontrolcanachievetheanticipantillminationspeckles,whichisthe foundation of the successful implementation of the proposed technique.

Various paternsofthemultiplexedspecklescanbeemployedinthe SPIsystem.Randompaterns,in whicheachmask hasarandom distributionofbinaryvalues,havebeenwidelyused.Inthiscase,complexoperationsarerequiredtoobtaintheobjectinformation. Hadamardpatesprovideaotherstrategytateablestheconstructioofteiagewithaiearlyiterativealgorith,iheire very lowcomputational complexity. Here, Hadamard paterns of the multiplexed speckles are chosen for our experiments.

A Hadamard pattern is based on orthogonal discrete square waves, with values of either $+ 1$ or $^ { - 1 }$ . Because the illumination speckles producedbytheDMDsystemarebinarypositiveandnegativereflectionvaluescannotbereadilyutilized.Toaddressthisisue,two approachescanbeemployed.Thfirstapproachinvolves theuseof transformativeHadamardmatricesandensures thatallentriescosist ofvaluesofeitherlorO.Thesecondapproach involvesapairofmatrices thatarerelatedtotheHadamardmatrixbyasubtraction operation.Thesecondaproachcanimprovethesignal-to-noiseratio(SNR)of themeasurementsandisutilizedinoursystem7].The process is described as follows.The entries of a Hadamard matrix $\mathrm { ~ H ~ }$ are either $+ 1$ or $^ { - 1 }$ . We create the complementary pair $\mathrm { H } _ { \pm } { = } ( \mathrm { E } { \pm } \mathrm { H } ) / 2$ ， where E represents a matrix for which all entries are equal to 1.As a result, we have one matrix $\mathrm { H } _ { + }$ where the original $+ 1$ entries retain their value,and the $^ { - 1 }$ entries become zero. In the other matrix $\mathrm { H _ { - } }$ , unity-valued entries become zero,and the $^ { - 1 }$ entries become 1.As the detected intensity is linear with the speckles, the speckles with $\mathrm { H } _ { + }$ and $\mathrm { H _ { - } }$ patterns are employed in the projection; thus, the coefficient under the Hadamard basis can be calculated by subtracting the two detected intensities.

![](images/1197e1de3e4bb2b061ed043e75808e607bb7778e2aebcb5d27579d5e154df67f.jpg)  
Fig2 PLp labeledwithditolodseeoddatrcdtouratonarals(seckngdig)stiely

Four binarycartoon animals(horse,chicken,dogandpig)printedonA4 paper areemployedas themultipleobjects in the experiment and are placed side by side at the object position, as shown in Fig. 2. The $3 { \times } 3$ mirrors of the DMD are combined into a speckle cell that corresponds to an image pixel, and the intermediate $7 6 8 \times 7 6 8$ mirrors are utilized in the experiment. Thus, the resolution of the entire lighted area is $2 5 6 \times 2 5 6$ pixels. The imaging area is divided into four areas; thus, the imaging resolution is $1 2 8 \times 1 2 8$ pixels. Four $^ { 1 2 8 \times 1 2 8 }$ pixel encoded matrices labeled with borders of different colors are shown in Fig.2 and arrnged in a $2 { \times } 2$ manner. These matrices were produced by a random processand have complementary orthogonal properties with a compresion ratio of $2 5 \%$ . During the acquisitionproce,teecodedmatricesminuchngdTepreprocsisesedasfllo.Frst384paisofopltary Hadamardspecklesaregeneratedas multiplexedspeckleswithvaluesofOor1accordingtotheabove method.Next,four-combined illumination speckles with $7 6 8 \times 7 6 8$ mirrors are reproduced by arranging and resizing intermediate matrices via multiplying the Hadamard speckleswiththeencoded matricesandarethenloadedintotheDMDsystem.Finall,thefour-combined iluminationspecklesare employedtoillminatethefourobjects,andthdirectandindirectreflectedlightsfromfourobjectsiscollctedbythesingle-pixel detectors.Hereeachsubpartoftheilluminationspecklescalluminatetecorrespondingobjectitoutcrossing.Tediecteflected lightfromthefourobjectsiscollectedbythecollctinglensanddetectedbydetetor1.Tereflecedlightfromthefourobectspasses throughgroundglassandtn,teidirectrefctedlightisetectedydetector2.Tereflectedligtfrothefourojectsislted byashetofwhiteA4paper,andthen,thindirectreflectedlightisdetectedbydetector3,whichisareverse-orientedpotodiode withoutadirectviewoftebjets.efusion,imagigandencryptionofthemultplebectsareachevedusingtheintensitisdetected by the three detectors,respectively.

Experimentalresultsofmulti-objectfusionand imaging:Anevolutionarylineariterativemethod[7]aiming toreconstructheimage insignificantlylesstimethanconventionalCSisproposed.TheevolutionarylineariterationschemechoosesasubsetoftheHadamard specklestorecover thefusedimageofthemultipleobjectsbyselectingthepaters withthemostignificantintensities measuredbythe single-pixeldetector.TherecoveredfusionimagesbasedontheintensitiesofthedirectreflectedlightareshowninFig.3,andthe columnspresenttheresultsotainedusingdiferent numbersofHadamardspeckles.Basedontheresults,the SNRsof therecovered results increaseasthenumberofultiplexedspecklesincrease.However,wecannotidentifythemulti-objectinformationfromthersults inFig.3.Fortunatelyasedonthepropertisofcodedmatrices,fourcompresedimagescanbeobainedbyultiplyngtefused imagewiththeencodedmatrices,asshowninthefistrowofFig4.Finalytheresultsofthefinalrecoveredimagesobtainedusing compressionsensingareshown inthesecondrowofFig.4.Theexperiment was determinedtobesuessfulbasedonthefacthat completelyacurate image informationcanberecovered exactlyfromcompressedsamplesviatheCSalgorithm.Theresultsshowthat thequalityofrecoveredimages isafectedbytheSNRofthefusedimageandthatapositiecorelationexistsbetwenthem.The differences among the images reconstructed from the fused images with coverage spanning compresion ratios from $2 5 \%$ to $100 \%$ are nearlyngligible.Accordingtotheresults,diferentencodedmatricescanefectivelyachevethefusionofmutipleobectimages.The compression ratio of the encoded matrices is $2 5 \%$ ,so the fusion of the information of the four images is achieved.If the compression ratio isfurthereduced,theimagesofmoreobjectscanbfusedandimagedusing theresultsofonemeasurement.Howeverinthetraditioal SPIsystem,eachobject mustbeindividuallmeasuredonce tomaintainthesame imageresolution.Thus,theproposed methodcan effectivelyreducethedataacquisitionandimprovetheimagingeficiency.Notetattheimagesarenotsubjectedtoanyaditional processing, such as filtering.

Scatering medialimitopticalobservationsbecausetheirandomrefractiveindexvariationsdistort thespherical wavefrontgenerated byeverypointsource,resultinginasmearedimageatamatrixdetectr6].Inourimagigsystem,asingle-pixeldetectoriseployed to measurethewolereflectedintesityandtheintesitydistributionisotofonce;thus,theproposedtchnquecanbepledto fuseandmage multipleobjectsthroughscatering media.Weusedtwodiferentdetectionunitsforimagereconstructioninacatering environment:1)detector2covered withapieceof ground glassand2)reverselyplaceddetector3withapieceofwhiteA4paperasa reflectigdifuser.Intefirstcasethereflectedlightfromteobjectspassstroughtegroundglassbeforebeingcollctedbythe colectinglsanddirectedintodetector2.Fusedimagerecostructionsithcompressionobtaindintissitatioaresowinig.5. Theseimagesappearnoisybecausethelightcolectedbydetector2wasrelativelyweakasaresultofthelowtransmitanceofte ground glass,resultinginadetecionsignalwithalowerS.Basedothecorelationcoefficient withthereconstructionutilingcomplete Hadamardbasisfordirectreflectedlight,thefusedesultimproesasteumberofutiplexedspeklesincreassandthebstultis similar to that obtained with a compression ratio of $2 5 \%$ in the above situation.We use the proposed method to restore the images of the fourobjectssowinFig6.TeresultsindicatethatwecanclearlydentifythejectiformationInthsecondcase,tereflectedlight fromthebjectsiseflectedbyasheetofwhiteA4papeandthncollectedbytecollectinglensanddirectedintodetector3.Tefused imagrconstructionswithcompresionobtainedinthissituationareshowinFig.7.TheSNRsofthercoveredimagesarelowerthan thoseinthefirstcasebecause thelightcollectedbythedetectorwas weakerbecauseofthelowreflectivityofwhiteA4paper.Although scateringreucs teS,tefourbjectssoinig.8anstillepereive.Tabilttimagemultipleectsthroughatin media makesour system valuable innumerous aplications,ranging fromoptical communication through turbulent atmosphere to microscopic imaging in turbid tissues.

![](images/93ec6d2cb8195d167b2f3b84ad1fc92295fd7ca958a43dd4dd600b964ff41803.jpg)  
Figd coefcient between the recovered images and the reconstructionutilizing a complete Hadamard basis ( $100 \%$ compression ratio).

# Compression Ratio :12.5%

# Compression Ratio : $2 5 \%$

![](images/236b44119cc3a612bdd7803b56e8e7f8aa8371b556f4f5626480d034cb791c26.jpg)  
iguil oy multiplying the fusionresult withthe encoded matrices,and the secondrow presents the finalrecovered results.

![](images/da6e71a40431e22bfb9a58fd96960aa47862a57529eca8950b91bc5fd33643ba.jpg)  
Figse indicatingtheetddoldsisftlht $100 \%$ compression ratio).

![](images/35753649d6822e982de9f6230c98198cddd545d412b714f4371e8c7e6c0ba0fa.jpg)  
CompressionRatio:12.5%   
CompressionRatio: $2 5 \%$

![](images/e7fb698fb14a3283d1b28c0b687c3b6348dce759283c8f59f6605d993c882633.jpg)  
Fig6ui obtaiedud coeficientsbetweentherecoveredimagesandthereconstructionutlizingthecompleteHadamardbasisfordirectreflectedlight( $100 \%$ compression ratio).   
Fig7se indicatinttodosilddssdlht $100 \%$ compression ratio).

![](images/d6853439af3709fd48dd17bdd3764920311c20eae8e671d75b2e3e77b6a567ea.jpg)  
CompressionRatio: $1 2 . 5 \%$   
CompressionRatio: $2 5 \%$   
Figuli obtinedbio coefficients betweenrecovered imagesandthereconstructionutilizing thecomplete Hadamardbasis fordirectreflected light( $100 \%$ compression ratio).

Experimentalencryptionresults:Weusetheexperimentalresultstoverifythesystem’sencryptioncapability.Intheinformation encryptiontasmissnprocess,tetectedtesitidultipleedpecklesaretramitdaspubliciformatiodoefour encodedmatricesareransmited inanencrypted manner.Inotherwords,theencoded matricesaretheonlykeys.Itisassuedthat duringtheinformatintransmsionthavesdropperobtainsultipleedspecklesndintesitiesdetectedythesingl-pieetecto determines theencodedmatriceswithacertainlevelofaccuracyandthenuses thepartialacurateiformationtoestoreteiagesof thefourncryptedobjects.Fig.9showstherestorationofmultipleobjectsunderdiferentbiterrorratiosanddierentnumbersof Hadamardasisusingthdectrefleeditesities.Acodingtoteresults,asthebitrratosdecease,theualityofteoerd imagesgraduallyimproves.Thequalityoftherecoveredimagesalsoimprovesasthecompressionratioincreases.Thecorelation coeficientsinthfgureconfimtheseconclusions.Notethaterestoredimageissimultaneouslyaectedytebiterorratioadthe numberof multiplexed speckles.Toobtain high-qualityobject information,aneavesdroppernotonlyrequires high-precisionecoded matrices butmust alsouse more specklestorestore theimage.The system’sencryption performancecanbefurtherimproved bythe encrypted transmission of speckles or/and intensities.

Imageencryptioninascatering environment wasalsoperformed.Fig.10shows therestorationofmultipleobjectsatdifferentbit erorratiosanddiferentnumbersofHadamardbasisusingtheindirectreflectedintensitiesfromdetector2.Theresultsshowthatthe relationshipbtwnterestoredimagqualitydtheeroratiostesameastatdeteriedforthaboesituatio.Howeeforte secondscateringenvironment,becauseof thelower SNRof the fused image,thequalityofrecovered imagesshowninFig.11 deterioratesrapidlyrelatietotheprevioussituation.Thesefindingsareconfirmedbythecorelationcoeficientssowninthefigure. Notethatwhenthecompressionratioexceedsacertainvalue,teqaliesoftherecoveredimagesarenotnecessrilynhancdate compresionratioincreases.According totheresults,theacurateencryption informationsoughtbytheeavesdroperbecomes more dificultobtaininascateringenvironmentthaninaclearmedium.Tus,ascatering mediumimproves theencrytionperformance.

![](images/3581f01f6a7b3dd3677b0f4520a38cabeaaa0bde248012bfbae8fe7a04f9563e.jpg)  
Fig.9.Image encryption experiment usingthedirect reflected intensities fromdetector1.Theresultsobtaiedundererrorratiosof $50 \%$ $40 \%$ $30 \%$ and $20 \%$ for the encoded mtie reflected light ( $100 \%$ compression ratio).

![](images/f905dba288043254062ea1d8bbbcfc723f77b27d88b658b29c787f0866d49950.jpg)  
Fig.10.Image encryptionexperiment using thescateredreflected intensitiesfrom detector2.Theresultsundererorratios of $50 \%$ $40 \%$ $30 \%$ and $20 \%$ for the encoded ma reflectedlight( $100 \%$ compression ratio).

![](images/548adf61d5bb4980edc312664422b770b6b4d8cdde74a1fef1a75c87f6bf7bfc.jpg)  
Fig.11.Image encryption experimentusingthescateredreflected intensities fromdetector3.Theresultsunderrorratiosof $50 \%$ $40 \%$ $30 \%$ and $20 \%$ for the encodec ma reflected light ( $100 \%$ compression ratio).

# DISCUSSION

Based on CS theory,the vastmajorityofobjects nsometransformations havesparsefeatures; asaresult,randomsamples ofimages canbeemployedtoobtaincompleteandaccurate image information.Thischaracteristichasbeenappliedinmanysystems.Byapplying this principletoanSPIsystem,ametodforcompressngmultiplebjectsbyusing multiplexed specklesisproposed.Basednthe multiplexedspeckles,anSPtechniqueformult-bjectfusion,imagingandencryptionisdevelopedandtestedexperimentalyhe results revealedthattheproposedmethodenablesthesimultaneous imagingofmutpleobects,eveninascateringenvironment,andis highlyefficientforinformationencryption.Notethatinthispaper,thefusedimagecontainsfourobjects’information；thus，the compressionratioisaqarteroftheabovevaluerelativetothe wholeinformation.Inother words,theproposed methodrealies the fusion, imaging and encryption of multiple objects via sub-Nyquist measurements.

Additionally,thefusion,magingandencryptionofmorebjectscanbeachievedbyfurthercompresingtheencodedmatrices.In general,teallddsdistuattieltlcoealit withthenumberandpateoftheencodedmatrices.Thechoiceoftheencodedmatrixplaysakeyroleinimagereconstruction.Because various matricescanbechosen,theproblemofoptimizingtheencoded matrixshouldbecarefullystudiedinthefuture.However,when weusethismethodtoencrptultipleobjects,theoptialencodedmatrixwithighncrytionperformanceandtransmisioefciency canbepre-selectedbyinvestigatingthesparsecharacteristicsofthetransmitedinformation.Inadition，duetoenvironmental interference,lghtsourceistabiltndtherfactos,tealityofteiformatioacquiedythssteisotgh;tusiet systemconfigurationandrestorationalgorithmsmustbeexplored.Webelievethathisnewtechiquewillpavethewayfortheuseofthis SPIsysteminseveralfields,icludingopticalcommunicatio,imagingaroudcoers,andespeciallmagingmultiplebjectsa scattering medium, such as water or fog.

# METOD

he reconstruction of the proposed technique involves two main steps: spatial multiplexing and multi-image demultiplexing

# Spatial Multiplexing

When we have multiple objects $f _ { I } , f _ { 2 } . . . .$ and $f _ { i }$ to fuse, image and encrypt via SPI, different encoded matrices $B _ { I } , B _ { 2 } . . . . .$ and $B _ { i }$ with resolutions of $N { \times } N$ are employed to sample the multiple objects. It is assumed that the $j t h$ illumination speckle $C _ { j }$ is generated by arranging the matrices achieved by multiplying multiplexed speckle $S _ { j }$ and $B _ { I } , B _ { 2 } . . . . . B _ { i }$ and can be expressed as:

$$
\begin{array} { r l } & { C _ { j } ( 1 { : } N , 1 { : } N ) = B _ { 1 } \circ S _ { j } , } \\ & { C _ { j } ( 1 { : } N , N + 1 { : } 2 N ) = B _ { 2 } \circ S _ { j } , } \\ & { . . . } \\ & { C _ { j } ( 1 { : } N , ( i - 1 ) N + 1 { : } i N ) = B _ { i } \circ S _ { j } , } \end{array}
$$

Each sub-region with $N { \times } N$ pixels of illumination speckles corresponds to an object; thus, each illmination speckle can illminate several objects simultaneously. The resolution of the restored image is equal to $1 2 8 \times 1 2 8$ . The sub-regions of the above formula are arranged in columnsforsimplicity.Intheactualsystem,thesub-regionscanbearangedasrequired.Inthesystemdesribedhere,foursub-regions are arranged in a $2 { \times } 2$ manner.The matrices of the illmination speckles are loaded into the DMD system via a computer.Multiple objects areplaced inechdivisionoftheilluminationspeckle,andthn,aseriesofiluminationspecklesareemployedtoiluminate multiple objects simultaneously.

The reflected intensities from the multiple objects can be expressed as

$$
\begin{array} { r l } & { g _ { j , 1 } = \sum _ { N \times N } B _ { 1 } \circ S _ { j } \circ f _ { 1 } , } \\ & { g _ { j , 2 } = \sum _ { N \times N } B _ { 2 } \circ S _ { j } \circ f _ { 2 } , } \\ & { \cdots } \\ & { g _ { j , i } = \sum _ { N \times N } B _ { i } \circ S _ { j } \circ f _ { i } , } \end{array}
$$

Thewholeeflectionitesityfrosevealbectssetectedysingle-pieldtector.Tus,tetectedinteitisoftesiglepie detector can be written as

$$
\sum _ { i } g _ { j , i } = \sum _ { N \times N } B _ { 1 } \circ S _ { j } \circ f _ { 1 } + \sum _ { N \times N } B _ { 2 } \circ S _ { j } \circ f _ { 2 } + \ldots + \sum _ { N \times N } B _ { i } \circ S _ { j } \circ f _ { i } ,
$$

Suppose binary encoded matrices have the following properties:

$$
\begin{array} { r l } & { \boldsymbol { B } _ { i 1 } \circ \boldsymbol { B } _ { i 2 } = \left\{ \begin{array} { l l } { 0 \qquad } & { i 1 \neq i 2 } \\ { \boldsymbol { B } _ { i 1 } \qquad } & { i 1 = i 2 } \end{array} \right. , } \\ & { \Pi \boldsymbol { B } _ { i } = \boldsymbol { E } , } \end{array}
$$

where $E$ represents a matrix with all entries are equal to 1,and $\Pi$ indicates the accumulation of all matrices.In other words,multiple encodedmatricesachievecompletesamplingofthefusedobjectinformation.Inadition,theyareorthogonaltoeachother.Further simplifying Eq. (3), we have

$$
\begin{array} { r } { g _ { j } = \displaystyle \sum _ { N \times N } S _ { j } \circ \hat { f } , } \end{array}
$$

where fused image $\hat { f } = B _ { 1 } \circ f _ { 1 } + B _ { 2 } \circ f _ { 2 } + . . . + B _ { i } \circ f _ { i }$ represents the accumulation of the random samples from multiple objects, and （2 $g _ { j } = \sum _ { i } g _ { j , i }$ .From Eq.(6), wecan determinethatthe acquisition process can be described bythe interaction between the multiplexed specklesandthefusedimage.MultiplexedspeckleswithHadamard paternsareused inthis paper.As thelluminationspecklesproduced by the DMD system are binary,we create complementary pairs of ilumination speckles $\mathrm { H } _ { + }$ and $\mathrm { H } .$ . The intensities detected when illumination speckles $\mathrm { H _ { j ^ { + } } }$ and $\mathrm { H _ { j } }$ are used to illuminate the objects can be expressed as ${ \bf g } _ { \mathrm { j ^ { + } } }$ and $\mathbf { g } _ { \mathrm { j } } .$ ，respectively，and then, the two intensities are subtracted. This process can be written as

$$
g _ { j } = g _ { j + } - g _ { j - } = \sum _ { N \times N } ( H _ { j + } \circ \hat { f } - H _ { j - } \circ \hat { f } ) = \sum _ { N \times N } ( S _ { j } \circ \hat { f } ) ,
$$

The iterativereconstruction method is employed to recover the fused object information, which canbe expressed as

$$
\hat { f } = \sum _ { j } S _ { j } \circ g _ { j } ,
$$

where $\hat { \boldsymbol f }$ is the recovered fusion image. Here, the number of the multiplexed speckles is equal to $j$ .The above formula indicates that the fused magecanbeexpressedasaweightedsumofmultiplexedspecklesbasedonthecorrespondingcoefcientsobtainedfromthe detected intensities.The compresion ratio is defined as the ratio of the numberofmultiplexed speckles to image pixels:

$$
c r = j / N ^ { 2 } \times 1 0 0 \% .
$$

During this analysis, a speckle cell is utilized as an image pixel.

# Multi-object Demultiplexing

Theaboeequationdemonstratesthathenthereflectedintensitisfrommultipleojectsaredetected,theyaremixedtogetr.us,the imageofmultipleobjectsisrecoveredbyterativereconstructionmethod.However,wemustobtaintheimageofeachindividualject. Fortunately,based on the properties ofencoded matrices,random samples ofeach object can be obtained as follws:

$$
\hat { f } _ { i } = B _ { i } \circ \hat { f } = B _ { i } \circ ( B _ { 1 } \circ f _ { 1 } + B _ { 2 } \circ f _ { 2 } + . . . + B _ { i } \circ f _ { i } ) = B _ { i } \circ f _ { i } ,
$$

Fromtheaboveformula,theHadamardproductofthefusedimageandencodedmatricescaneusedtoobtainthecorespondingrndom objectinformation.Next,thecompleteinformationofeachobjectcanbedeterminedwithhighprecisionbysubstitutingtheencoded matrices and the random sampled image in the CS algorithm. Optimizations can be achieved as follows:

$$
f _ { i } = y a _ { i } \quad \mathrm { s u b j e c t t o } \operatorname* { m i n } \bigg \{ \Big \| \hat { f } _ { i } - B _ { i } y a _ { i } \Big \| _ { 2 } ^ { 2 } + \lambda T ( a _ { i } ) \bigg \} ,
$$

Here, $y$ represents the transform to the chosen domain resulting in a sparse representation $a _ { i } , \lambda$ and $T$ represent the regularization coefcientandfunction,respectively.TecodeemployedforCSinthispaper17]isthefunctionInpaintingGSRoftheoftware package.Accordingtoteaboeaalysis,henteaccurateecodedmatrixcaotbeotained,curateimagesofteojectscaotbe recovered; that is, the encoded matrix can be utilized as a key to encrypt the object.

# Image comparison based on correlation coefficients

Tocompare imageacquisitions，weused thecorelationcoeffcientsbetween theunder-sampled images and areference image.This coeficientrangesfromzerotoone,dependingontheresemblanceofbothimages.Ourreferenceimageisalways theimageacquired withoutunder-samplingi.,easuringattheNyqust-Shanoncriterion).Theorelationcoeicientisculatedwiththefolowing function:

$$
r = \frac { \displaystyle \sum _ { m } \sum _ { n } ( A _ { m n } - \overline { { A } } ) \circ ( B _ { m n } - \overline { { B } } ) } { \displaystyle \sqrt { \sum _ { m } \sum _ { n } ( A _ { m n } - \overline { { A } } ) ^ { 2 } \circ \sum _ { m } \sum _ { n } ( B _ { m n } - \overline { { B } } ) ^ { 2 } } } ~ ,
$$

where A and B are the image matrices with indices $m$ and $n$ ,respectively,and $\overline { { A } }$ and $\overline { { B } }$ represent the mean values of the elements in A and B.

# Acknowledgements

This work wassupportedbytheNational Natural ScienceFoundationofChina(Nos.1404344and41505019)andtheCAS Iovatior Fund Project (No. CXJJ-17S029).

# Author Contributions

S.D.F.conceivedsigedupervisedthedynterpretedthedataandotetheauscript.H.perfoedteprits, analyzed thedataandasisted inwritingthemanuscript.W.YJ.conductedtheexperimentsandanalyzedthedata.Y.K.,X.CB.LD. and Z. W.Y. discussed the results and revised the manuscript.

# Additional information

# Competing financial interests: The authors declare no competing financial interests References

Shapio,JH Sun,B.etal.3DComputatioalImagingwithngle-PielDetectors.Sience340,8-847,doi:0.26/science.234454(013). Duarte,M.F.etal.Single-pixel imaging via compressive sampling.IEEE Signal Proces.Mag.25,83-91(2008). ZhagZu (2015). Moris,Pe.inoe 591310.1038/Ncomms6913 (2015). Ryczkowski，P.，Barbier，M.，Friberg，A.T.，Dudley，J.M.&Genty，G.Ghostimaginginthetimedomain.NaturePhotonics0 $1 6 7 \cdot + .$ doi:10.1038/Nphoton.2015.274 (2016). MJn. Nat Commun 7(2016). Kong,L.J.etal.Encryptionof ghost imaging.Physical ReviewA88,doi:Art01385210.1103/Physreva.88.13852(2013). Clente (2010). Chen,W.&fotdd). Taa doi:Artn 10110810.1063/1.4748875 (2012). CandesEJ HitiYGtrer IEEE International Conference on Computer Vision (ICCV),287-294 (2011). 14. Gao,Lid doi:10.1038/nature14005 (2014). 15. LinXe 16. OKatE (2012). 17. J.Zhang,D.BaodWoopBasdSarseRepsetatiofgeestotio,EEgerocss36(4).