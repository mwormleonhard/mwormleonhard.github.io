---
comments: true
layout: post
title: Magnetfeltstyrkemåling med mobiltelefon
date: '2013-05-23T16:50:00.001+02:00'
author: Martin Worm-Leonhard
tags:
- Magnetisme
- Mobiltelefon
- Køkkenfysik
- Anna-og-lotte
modified_time: '2013-05-29T20:15:25.275+02:00'
thumbnail: http://3.bp.blogspot.com/-0vKL-1CX8-s/UZ4REPY8D1I/AAAAAAAABkU/3ywKasCYB1Y/s72-c/magnetopstilling2.JPG
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-840709741508133863
blogger_orig_url: http://labnoter.blogspot.com/2013/05/magnetfeltstyrkemaling-med-mobiltelefon.html
---

Indledning
----------

Mange af os render rundt med en håndfuld ret sofistikerede
måleinstrumenter i lommen - magnetometer, accelerometer,
spektrofotometer, lysstyrkemåler, gyrokompas, gravitationssensor,
barometer og måske endnu mere. Det meste af tiden nøjes vi dog med at
tale til/i dem --- for jeg snakker naturligvis om vores smartphones. 

Jeg har fået en (fiks?) ide om at man kan bruge dette universalinstrument til
mangt om meget, og jeg har allerede demonstreret at kameraet kan
anvendes som [spektrofotometer](http://www.lmfk.dk/artikler/data/artikler/1302/1302_53.pdf) og
for nylig er jeg begyndt at interessere mig for de øvrige sensorer, så
efterhånden som jeg får udforsket dette felt - hvad der findes af apps,
hvad der kan lade sig gøre, og hvor meget man skal gøre sig umage - vil
der nok dukke adskillige flere indlæg op.

Jeg valgte, vanen tro, at starte med at forsøge at gøre noget svært
nemt. Magnetfelter er jo meget fascinerende, men noget okkulte at måle
og kvantificere for de fleste af os. Heldigvis har min telefon indbygget
et treakset magnetometer, så jeg besluttede mig for at se om jeg kunne
måle hvordan et magnetfelt varierer med afstanden.

Opstilling
----------

![Opstilling-2]({{site.url}}/images/magnetopstilling2.jpg) ![Opstilling-1]({{site.url}}/images/magnetopstilling1.jpg)

Mobiltelefonen (en LG Nexus 4) anbringes i en passende holder - hér et
whiskyglas, da det havde nogle passende dimensioner. 

En (kraftig) køleskabsmagnet (Blå plast med en lille
Neodym-Jern-Bor-magnet indstøbt) anbringes omtrent ud for
magnetfluxsensoren ved at den klodses op på en andet glas. 

Jeg fandt ud af hvor sensoren sad ved at "scanne" bagsiden af telefonen
med magneten, mens jeg så på værdien fra sensoren, og forsøgte at ramme
deromkring hvor den aflæste værdi var størst.

Feltstyrkemålinger foretages ved forskellige afstande med
["Sensors"](https://play.google.com/store/apps/details?id=aizen.sensors)-appen
og registreres manuelt. 

Afstande er målt med den viste lineal fra bagkant af telefon til forkant
af magnet.

Da sensorprogrammet både rapporterer den samlede fluxtæthed som absolut
værdi, og opløser den i x,y,z-vektorer noterede jeg både den samlede
værdi og x-komponenten, som er ca. den retning som jeg bevæger magneten
ad. Alle værdier opgives at være i mikrotesla (µT), så det tror jeg på.

Målinger
--------

 | Afstand \[cm\] |  Samlet fluxtæthed \[µT\] |  Fluxtæthed i x-retning \[µT\]| 
 |:--------------:|:------------------------:|:------------------------------:|
 | 2,5            |  140                      |  65                           |
 | 3,8            |  77                       |  21                           |
 | 4,5            |  69                       |  14                           |
 | 5,2            |  64                       |  8                            |
 | 6,0            |  61                       |  5                            |
 | 7,0            |  59                       |  2                            |
 | 7,8            |  58                       |  1                            |
 | 9,8            |  55                       |  -1                           |


Bemærk at når feltstyrken måles med/i en retning så har den også et
fortegn. De "-1" i nederste højre hjørne er altså helt ok.
Jeg beklager i øvrigt den tudegrimme tabel - jeg skal have fundet en
smartere måde at bygge dem på.

Analyse
-------

Lad os starte med at forholde os til den samlede feltstyrke / fluxtæthed
som funktion af afstand. Hvis man plotter de rå data kommer det til at
se således ud:

![]({{site.url}}/images/magnetrådata.png)

Der er i hvert fald helt tydeligt noget signal hér. Spørgsmålet er
hvilken funktion det følger. Hvis fluxtætheden aftager med en potens af
afstanden, så vil vi forvente at et dobbeltlogaritmisk plot vil give en
ret linie, så lad os prøve at lave sådan ét. Bemærk at jeg har trukket
baggrundsfluxen (målt til ca. 54µT) fra alle målinger, for kun at have
den del af signalet der hidrører fra magneten.

![]({{site.url}}/images/magnetloglog.png)

Det må jo siges at være en forbavsende pæn ret linie, der passer fint
med datapunkterne - og min software siger da også at \\(R^2 = 0,97\\).
Hvorvidt det sidste punkt er en outlier kan diskuteres - det faktum at
den målte værdi er meget tæt på baggrundsniveauet må nok antages at
medføre noget større usikkerhed på værdien.
Tendensliniens hældning er -2,994, hvilket jo ret kraftigt antyder at vi
har at gøre med et fænomen der aftager med afstanden i tredje potens,
altså \\( Feltstyrke \propto \dfrac{1}{Afstand^3}\\).

Lad os derfor forsøge at tilpasse en funktion af formen \\( B =
\dfrac{a}{d^3} + c \\) til data.

Her er B feltstyrken, a en karakteristisk konstant for magneten og c
altså baggrundsniveauet - feltstyrken der måles når magneten er
uendeligt langt væk.

Dette har jeg gjort i R og fået at \\( B = \dfrac{1332}{d^3} + 54 \\)
og \\(R^2 =0,999\\).

Lægger vi denne linie ind oven i det originale dataplot fås følgende:

![]({{site.url}}/images/magnetslutfit.png)

Der må jubles - det er godkendt! Især når man tager forsøgsopstilingens
(mangel på) kompleksitet i betragtning.

Diskussion og konklusion
------------------------

Teorien siger at fluxtætheden af et magnetfelt skal aftage med afstanden
fra kilden i tredje potens. Dette må siges at være eftervist ud over
enhver rimelig tvivl.

Jeg vil undlade at forholde mig til størrelserne af den fundne
koefficient (a), og hvad den siger om min køleskabsmagnet da øvelsen
alene var at undersøge sammenhængen mellem feltstyrke/fluxtæthed og
afstand, men det kunne utvivlsomt lade sig gøre at kvantificere graden
af magnetisering af materialet, hvis det var det man ville.

Man opnår i øvrigt samme generelle konklusion hvis man gentager øvelsen
med x-vektor datapunkterne, men dem kan du jo selv lege med.

Jeg må altså konkludere at det sagtens er muligt at finde / eftervise
sammenhængen mellem magnetisk fluxtæthed og afstand til kilden, hjemme
på køkkenbordet med en mobiltelefon og en lineal som de eneste
måleinstrumenter.

Jeg har lavet databehandling i [R](http://www.r-project.org/), da jeg er
godt hjemme i det, og det giver mig noget mere fleksibilitet, men man
kan uden problemer opnå det samme resultat med MS Excel eller et andet
regneark. Her skal man bare være lidt mere opmærksom på at udvalget af
fitbare funktioner kan være begrænset, så man skal muligvis massere sine
data lidt mere med håndkraft.

Fremtidige forsøg / Andre muligheder
------------------------------------

Hvad sker der mon hvis feltlinierne bevæger sig parallelt med sensoren,
i stedet for vinkelret på? Altså hvis man drejer magneten 90 grader - så
måler man et svagere felt - men er sammenhængen med afstand den samme?

Hvis man nu bruger en elektromagnet og varierer strømstyrken i stedet
for afstanden? Hvad får man så?

Er der andet man kunne finde på at undersøge - garanteret! Har du nogle
gode forslag?

\\Worm
