---
layout: post
title: Hvor stor er en bøvs?
date: '2014-10-24T19:06:00.001+02:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Gas
- Køkkenkemi
- Weekendvidenskab
- Øl
modified_time: '2014-10-24T19:06:39.557+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-347644885311857819
blogger_orig_url: http://labnoter.blogspot.com/2014/10/hvor-stor-er-en-bvs.html
---

Ahhhh... så blev det fredag, og dermed tid til at slå fødderne op,
håret ud og irritationen ned! [^1]

Uanset om man, som jeres ikke specielt ydmyge skribent, finder nydelse i
at fejre det med forgærede produkter baseret på bygmalt og humle, eller
bare snupper en kold hindbærbrus, så oplever man sandsynligvis at
massebalancen, idealgasloven og Henrys lov ikke tager nogen fanger! Den
gas der indtages opløst i vand skal på en eller anden måde ud igen, hvis
ikke man skal komme til at lide af det der med et ret malende medicinsk
udtryk hedder meteorisme.

Af og til kan det virke som om det er litervis af gas man er nødt til at
slippe ud --- enten den ene eller anden vej, man kan det nu også passe? Og
hvorfor vil det så gerne ud igen, så snart efter indtagelsen, når det
tilsyneladende har det fint med at være opløst i drikkevarerne i
timevis?

Lad os alle regne!

Hvis nu man bare havde været så venlig at tryksætte læskedrikke med
kvælstof ville det hele være meget lettere --- så kunne man regne det som
et simpelt spørgsmål om opløselighed af gas i væske, og den er alene
afhængig af (partial)trykket af gassen over væsken samt væskens art og
temperatur.

Men nej - det smager ikke rigtig af noget og \\(\require{mhchem}
\ce{CO2}\\) er så usportsligt indrettet at den både går i opløsning som
en gas og reagerer med vand ved at danne kulsyre, der straks derefter
danner et buffersystem af forskellige karbonatspecier[^2] i ligevægt
med hinanden --- eller på kemisk:
\\[ \begin{aligned}
\ce{CO2 (g)  &<-> CO2 (aq)} \\\
\ce{CO2 (aq) + H2O (l) &<->  H2CO3 (aq)}\\\
\ce{H2CO3 (aq) + H2O (l) &<-> H3O+ (aq) + HCO3- (aq)}\\\
\ce{HCO3- (aq) + H2O (l) &<-> H3O+ (aq) + CO3^{2-} (aq)}
\end{aligned}\\]

Og bare for at gøre det endnu værre, så er kulsyreholdige drikkevarer jo
under forhøjet tryk i dåsen/flasken, hvilket medfører at man også skal
betragte det som en overmættet opløsning, lige så snart man
trykudligner/åbner for godterne. 

Slår man op i sin databog/gummibibel
eller udøver passende google-fu finder man ud af at for kuldioxid er
opløseligheden, givet ved Henrys konstant \\(K_H = 3.4\cdot10^{-2}\frac{mol}{L\cdot atm}\\), samt at de to relevante
syrestyrkekonstanter er: 
\\(pK_{a1}=3.6 \text{ eller } 6.3 \text{ og } pK_{a2}=10.3\\).

Men hvad er nu det for noget med to værdier for den første
syrestyrkekonstant? Jo, det er såmænd på grund af at alle ligevægtene er
koblede, og efterhånden som der dannes kulsyre, så dissocierer denne
straks til kuldioxid og vand, hvorved den tilsyneladende eller effektive
værdi af \\(pK_{a1}\\) bliver højere end den reelle eller teoretiske.

Dette lyder som en hovedpine --- og det er det såmænd også --- jeg husker at
have tilbragt adskillige (u)hyggelige stunder i min gymnasietid med at
regne på det koblede ligevægssystem, men nu er jeg heldigvis blevet
ingeniør med ret til at måle i træskolænger, og derfor dyppede jeg
straks noget pH-papir i hhv. min øl og noget cola og fik følgende:

[![]({{site.url}}/images/-pCfzrTvpIdk/VEp86lmzSPI/AAAAAAAACfs/jORE_ILZ3wA/s1600/2014-10-24%2B17.50.02.jpg)]({{site.url}}/images/-pCfzrTvpIdk/VEp86lmzSPI/AAAAAAAACfs/jORE_ILZ3wA/s1600/2014-10-24%2B17.50.02.jpg)

Nemlig at pH i øl er ca. 4 og i cola ca. 2. I begge tilfælde er vi mere
end 2 enheder under den effektive pKa for kulsyre, og ligevægten er
derved forskudt så langt over mod kulsyre at vi kan derfor tillade os at
ignorere syre-base-kemien og stadig betragte det som en simpel
opløselighedsopgave med hydrering af kuldioxiden. 

Pyha, det var rart ---
så kan man også magte at regne, selvom man HAR drukket sin øl.

Subsidiært kan man bare være doven[^3] og tro blindt på at [Tante
Wiki](http://en.wikipedia.org/wiki/Carbonic_acid) har løst de relevante 6
ligninger med 6 ubekendte korrekt, og se at for tryk og pH relevante for
læskedrikke så vil det være rimeligt at antage at koncentrationen af
opløst \\(\ce{CO2}\\) er ca. 100 millimolær, svarende til ca. 4.4 gram
per liter. 

Dette er i øvrigt i udmærket overensstemmelse med tidligere
forsøg udført på en danskvand, hvor en halv liter Rrrrrrrammmmmløsa[^4]
taber i størrelsesordenen 2-2.5g i vægt når den afgasses aggressivt.

Jamen så er vi jo næsten i mål - nu skal vi bare antage at vi ønsker at
maksimere mængden af uhøvisk gasudslip[^5] og derfor bunder en blå
patron hurtigst muligt, hvorved vi altså indtager 33 millimol
\\(\ce{CO2}\\)  som et hurtigt kig på idealgasloven ( \\(pV=nRT\\) )
fortæller os fylder 739.2 mL  ved STP, hvilket passer meget godt med at
man får en lidt ubehagelig trykken for maven, idet mavesækken godt nok
er vældigt elastisk, men ikke gerne antager et volumen væsentligt over
en liters penge uden at klage lidt...

Ud fra ovenstående er det dermed en rimelig antagelse at en god stor
bøvs nok andrager i området 100-500 mL gas afhængig af de lokale forhold
i mave-tarm og mængden af indtaget kulsyreholdig væske --- hvilket også
passer meget fint med at jeg lige har målt volumen af min mundhule til
sølle 150mL (i hamsterkonfiguration) og det ikke altid er muligt at
holde hele gasudslippet inde bag sammenknebne læber.

Hvis nogen af jer skulle få lyst til at ræbe under vand[^6] eller på
anden måde rent faktisk måle et volumen, hvad enten I er beruset af
videnskaben eller ethanol, så hører jeg naturligvis gerne om det.

Uanset hvad må I alle have en rigtig god weekend!  
\\Worm

------------------------------------------------------------------------

[^1]: Det er også meget populært i nattelivet at slå hinanden ned, har
    jeg ladet mig fortælle. Det kan jeg ikke anbefale. Så skal nogen på
    arbejde.

[^2]: Ja, jeg ved godt at en specie er en julekage, og at det er en fæl
    fordanskning --- men jeg har ikke fundet et bedre ord som ikke smager
    endnu dårligere.

[^3]: Hellere mig end øllet.

[^4]: Ja, undskyld, men i anledning af fredag er der vrede metaltyskere
    i min computer.

[^5]: Indsæt selv dårlige vittigheder om at spise højr\[eæ\]b. Dennis
    Jügensen kom alligevel først med dem.

[^6]: Nej, ikke sangen de en overgang spillede meget på P3.
