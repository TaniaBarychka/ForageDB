---
title: "ForageDB"
author: "Tania Barychka"
date: "19/11/2019"
output: html_document
---

This is dedicated to explorative analysis of the FoRAGE dataset by Uiterwaal et al 2018 https://www.researchgate.net/publication/329938560_Data_paper_FoRAGE_Functional_Responses_from_Around_the_Globe_in_all_Ecosystems_database_a_compilation_of_functional_responses_for_consumers_and_parasitoids.



Import data and summarise the explanatory variables.


```
##     Data.set                                              Source    
##  Min.   :   1.0                                              : 599  
##  1st Qu.: 521.5   Sandheinrich and Atchison 1989 CJFAS       :  32  
##  Median :1042.0   Galarowicz & Wahl 2005 CAN J FISH AQUAT SCI:  29  
##  Mean   :1042.0   Donnelly and Phillips 2001 ENVIRON ENTOMOL :  28  
##  3rd Qu.:1562.5   Thompson 1975 J ANIM ECOL                  :  25  
##  Max.   :2083.0   Morales-Ventura et al 2004 J APPL ICHTHYOL :  22  
##  NA's   :599      (Other)                                    :1947  
##  Predation.or.Parasitism      Dim                 Field.            Habitat    
##      : 599               Min.   :2.000               :2630              : 599  
##  Par :  23               1st Qu.:2.000   Field       :   8   Aquatic    :1149  
##  Pred:2060               Median :3.000   In the field:  44   Mixed      :   8  
##                          Mean   :2.588                       Terrestrial: 926  
##                          3rd Qu.:3.000                                         
##                          Max.   :3.000                                         
##                          NA's   :599                                           
##  Fresh.or.marine..fish.only. Predator.cellularity       Vert.invert  
##        :2283                         : 599                    : 599  
##  Fresh : 278                 Metazoan:1992        Angiosperm  :   2  
##  Fresh :   4                 Unicell :  91        Invertebrate:1520  
##  Marine: 117                                      Protozoan   :  91  
##                                                   Vertebrate  : 470  
##                                                                      
##                                                                      
##    Major.grouping.1    Major.grouping.2            Predator.scientific.name
##  Insect    :712                :857                            : 599       
##            :601     Hemiptera  :243     Lepomis macrochirus    :  49       
##  Fish      :399     Coleoptera :226     Xylocoris flavipes     :  48       
##  Crustacean:383     Copepod    :191     Neoseiulus californicus:  42       
##  Arachnid  :308     Mite       :182     Phytoseiulus persimilis:  37       
##  Ciliate   : 42     Perciformes:181     Ischnura elegans       :  31       
##  (Other)   :237     (Other)    :802     (Other)                :1876       
##       Predator.type         Prey.cellularity         Vert.invert.1 
##              : 855                  : 599    Invertebrate   :1670  
##  Adult female: 360   Metazoan       :1832                   : 599  
##  Wild caught :  95   Non living food:  18    Vertebrate     : 162  
##  Adult       :  92   Non living prey:   6    Protozoan      : 113  
##  Adult male  :  77   Unicell        : 227    Algae          : 107  
##  3rd instar  :  65                           Non living food:  18  
##  (Other)     :1138                           (Other)        :  13  
##   Major.grouping.1.1  Major.grouping.2.1              Prey     
##  Insect    :750                :1031                    :1042  
##            :620      Hemiptera : 283     Red spider mite: 106  
##  Crustacean:530      Cladoceran: 267     Water flea     :  72  
##  Arachnid  :211      Mite      : 206     Daphnia        :  62  
##  Fish      :117      Copepod   : 115     Rotifer        :  46  
##  Rotifer   : 83      Diptera   : 112     copepod        :  41  
##  (Other)   :371      (Other)   : 668     (Other)        :1313  
##               Prey.scientific.name       Prey.type       Data.type   
##                         : 658                 :1194           : 599  
##  Tetranychus urticae    : 115      Egg        : 129   Mean    :1530  
##  Daphnia magna          : 108      Adult      : 127   Raw data: 553  
##  Drosophila melanogaster:  30      Adult?     : 105                  
##  Myzus persicae         :  30      Wild caught:  82                  
##  Aphis gossypii         :  27      3rd instar :  59                  
##  (Other)                :1714      (Other)    : 986                  
##  Prey.replaced. Hours.starved    Temp..C..     Interference Pred.per.arena
##   : 599                :1341   Min.   :-2.00    :2623       1      :1427  
##  N:1832         24     : 553   1st Qu.:16.00    :   1              : 808  
##  Y: 251         0      : 197   Median :21.50   Y:  58       2      : 129  
##                 48     : 131   Mean   :20.82                5      :  60  
##                 12     :  86   3rd Qu.:25.00                3      :  46  
##                 18     :  57   Max.   :40.20                10     :  37  
##                 (Other): 317   NA's   :844                  (Other): 175  
##  X2D.Arena.size..cm2.for.arena.bottom. X3D.arena.size..cm3.of.arena.volume.
##         :1752                                  :1429                       
##  63.62  :  67                          500.00  :  70                       
##  7.07   :  59                          20000.00:  47                       
##  78.54  :  44                          250.00  :  46                       
##  28.27  :  36                          60000.00:  45                       
##  44.18  :  35                          10000.00:  44                       
##  (Other): 689                          (Other) :1001                       
##  Predator.mass..mg.             Predator.mass.source.code
##  Min.   :        0                           :776        
##  1st Qu.:        0   Original species length :397        
##  Median :       10   Alternate species length:349        
##  Mean   :  1204819   Original length         :240        
##  3rd Qu.:      250   Alternate species mass  :160        
##  Max.   :278000000   Original species mass   :136        
##  NA's   :774         (Other)                 :624        
##  Predator.mass.regression.code Prey.mass..mg.    
##             :1516              Min.   :0.00e+00  
##  Order      : 565              1st Qu.:0.00e+00  
##  Species    : 286              Median :0.00e+00  
##  Family     : 178              Mean   :5.59e+05  
##  Zooplankton:  43              3rd Qu.:2.00e+00  
##  Class      :  37              Max.   :3.86e+08  
##  (Other)    :  57              NA's   :897       
##               Prey.mass.source.code Prey.mass.regression.code
##                          :894              :1553             
##  Alternate species length:488       Order  : 511             
##  Original length         :273       Family : 186             
##  Original species length :258       Class  : 151             
##  Alternate species mass  :125       Species:  99             
##  % adult mass            :110       Density:  75             
##  (Other)                 :534       (Other): 107             
##                    Units.of.a     Data.set.1     Mean.R2.of.fits 
##                         : 599   Min.   :   1.0   Min.   :0.0000  
##  Arenas per pred per day:  12   1st Qu.: 521.5   1st Qu.:0.3900  
##  m^2 per pred per day   : 723   Median :1042.0   Median :0.6400  
##  m^2.5 per pred per day : 257   Mean   :1042.0   Mean   :0.5962  
##  m^3 per pred per day   :1091   3rd Qu.:1562.5   3rd Qu.:0.8200  
##                                 Max.   :2083.0   Max.   :1.0000  
##                                 NA's   :599      NA's   :599     
##  Fitted.a..median.of.BS.samples.    CI.a.low           CI.a.hi         
##  Min.   :0.000e+00               Min.   :       0   Min.   :0.000e+00  
##  1st Qu.:0.000e+00               1st Qu.:       0   1st Qu.:0.000e+00  
##  Median :0.000e+00               Median :       0   Median :0.000e+00  
##  Mean   :2.401e+06               Mean   :   57970   Mean   :5.374e+07  
##  3rd Qu.:0.000e+00               3rd Qu.:       0   3rd Qu.:0.000e+00  
##  Max.   :4.830e+09               Max.   :46300000   Max.   :9.270e+10  
##  NA's   :599                     NA's   :599        NA's   :599        
##  Fittted.h..day.       CI.h.low           CI.h.hi         Number.of.bootstraps
##  Min.   :  0.0000   Min.   :  0.0000   Min.   :  0.0000   Min.   :200         
##  1st Qu.:  0.0004   1st Qu.:  0.0000   1st Qu.:  0.0012   1st Qu.:200         
##  Median :  0.0109   Median :  0.0024   Median :  0.0209   Median :200         
##  Mean   :  0.9244   Mean   :  0.4516   Mean   :  1.9891   Mean   :200         
##  3rd Qu.:  0.0636   3rd Qu.:  0.0308   3rd Qu.:  0.0996   3rd Qu.:200         
##  Max.   :313.0000   Max.   :288.0000   Max.   :518.0000   Max.   :200         
##  NA's   :599        NA's   :599        NA's   :599        NA's   :599         
##                                                                                                  Notes.1    
##                                                                                                      :2024  
##  Arena contains 0.1g flour                                                                           :  16  
##  Higher prey densities were carried out in a smaller container size, 1150 cm3, and fewer predators, 5:  13  
##  Predator mass is wet weight                                                                         :  13  
##  Arena contains 475g wheat                                                                           :  12  
##  Prey replaced at low densities only                                                                 :  12  
##  (Other)                                                                                             : 592  
##  Notes.2       
##  Mode:logical  
##  NA's:2682     
##                
##                
##                
##                
## 
```
