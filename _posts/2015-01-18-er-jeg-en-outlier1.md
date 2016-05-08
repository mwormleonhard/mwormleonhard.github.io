---
layout: post
title: Er jeg en outlier?
date: '2015-01-18T19:27:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Statistik
modified_time: '2015-01-18T19:27:00.804+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-644926752356173026
blogger_orig_url: http://labnoter.blogspot.com/2015/01/er-jeg-en-outlier1.html
---

Før jul engang var jeg med til at designe og opsamle et lille datasæt
til brug for en statistikforelæsning. Forsøgspersonerne var de
tilstedeværende medlemmer af UNF Odense, og der blev lavet nogle fine
eksempler ud fra det kun ganske let masserede datasæt.

Imidlertid var der én søjle i datasættet der sprang i øjnene, nemlig den
der var mærket "Alder" og så sådan her ud: 27, 34, 19, 29, 24, 20, 25,
31, 20, 19, 20, 23.

Ja, det mig der er nummer 2 fra venstre, og i betragtning af at
foreningen hedder Ungdommens Naturvidenskabelige Forening, så er det jo
ikke så sært at jeg af og til griber lidt godmodig flak med ansigtet for
at være den residente (og resistente) Gamle Prut(TM).[^2]
Men er det egentlig rimeligt?[^1] Det er jo en god lejlighed til at nusse
med lidt anvendt statistik på bagsiden af en kuvert.

Lad os alle regne...

Lad mig først slå fast at jeg her kun agter at beskæftige mig med
hvordan man kan bestemme om et datapunkt ER en outlier --- altså om det
adskiller sig så meget fra resten af data, at det risikerer at skævvride
resultaterne eller på anden måde medføre et dårligere udkomme af
undersøgelsen. 

Hvad man gør med outliere, når man har fundet dem ---
trækker dem om bag ved laden og skyder dem, giver dem en rask lille
justeringsflad, capper dem til næststørste/-mindste værdi eller noget
helt syvende - afhænger naturligvis af den enkelte applikation. Der er
også mange forskellige kriterier for detektion af outliere, og jeg vil
kun berøre nogle af de enkleste. Og når vi nu har fået
CMY[^3]-afsnittet af vejen så lad os komme til ~~Skagen~~ sagen.

En klassisk parametrisk måde at afgøre om noget er en outlier er at se
om punktet ligger mere end et vist antal standardafvigelser (ofte 3-5)
fra middelværdien, men her antager man normalfordelte data, og i små
inhomogene datasæt er der ikke altid ret meget information i
middelværdier og varians. Og så er det en djævelsk besværlig størrelse
at skulle regne ud i hånden, hvis man "bare lige skal...".

I stedet er der andre, og lidt mere robuste, størrelser man kan bruge
til at estimere variansen i sit datasæt, og dermed komme med et
kvalificeret bud på om jeg er en outlier.

Den første er IQR:  InterQuartile Range. Altså hvor langt der er mellem
de to kvartiler. Hvis man opskriver datasættet i stigende rækkefølge, så
er første eller nederste (25%) kvartil den værdi man finder en fjerdedel
af vejen gennem rækken, og øverste kvartil (75%) er den man finder tre
fjerdedele gennem rækken.

Sorterer vi datasættet ovenfor får vi: 19, 19, 20, 20, 20, 23, 24, 25,
27, 29, 31, 34.

Da der er 12 observationer er første kvartil nummer 12/4=3 og har
værdien 20. Tredje kvartil er nummer 9 (3*12/4) og har værdien 27. 

Den
interkvartile afstand bliver altså 27-20 = 7. Traditionelt angiver man
grænseværdierne for outliere som første kvartil minus halvanden IQR og
tredje kvartil plus halvanden IQR. De halvanden virker lidt tilfældigt
valgt og er vist primært "Fordi
[Tukey](http://en.wikipedia.org/wiki/John_Tukey) Siger Det" (og fordi
det har en tendens til at virke udmærket).

I vores tilfælde får vi altså grænserne \\(20-1.5\\cdot 7=9.5\\) og
\\(27+1.5\\cdot 7=37.5\\), og da vi ingen datapunkter har udenfor dette
interval, så lader det til at jeg godt må være med i hulen lidt endnu ---
i hvert fald ifølge denne metode.

En anden metode, som  jeg selv sværger til, nok primært fordi den har
det fedeste akronym, er baseret på Median Absolute Deviation[^4] og
denne størrelse er måske lidt sværere at sætte på formel uden det bliver
lidt lysesort[^6], men algoritmen er ret simpel.

På samme måde som kvartilerne er medianen af data defineret som det
midterste tal i rækken, og denne bruges ofte i såkaldt robust statistik
i stedet for middelværdien, da den er mindre påvirket af eventuelle
outliere.

Medianen er den midterste observation, eller hvis der, som her, er et
lige antal, gennemsnittet af de to midterste, og har således værdien
23.5.

Man finder nu den absolutte forskel (altså uden fortegn) fra alle
observationerne og til denne. Starter vi med bare at trække medianen fra
det oprindelige datasæt får vi: 3.5, 10.5, -4.5, 5.5, 0.5, -3.5, 1.5,
7.5, -3.5, -4.5, -3.5, -0.5.

Nu sløjfer vi fortegnene, og ordner dem i stigende rækkefølge: 0.5, 0.5,
1.5, 3.5, 3.5, 3.5, 3.5, 4.5, 4.5, 5.5, 7.5, 10.5.

Så tager vi medianen af dette nye talsæt --- middelværdien af værdi nummer
6 og 7 er "3.5" og vi har således MAD=3.5.

I dette scenarie er den traditionelle grænse for outliere medianen
plus/minus 5 gange MAD[^7], og herved får vi intervallet \\(23.5 \pm
5 \cdot 3.5 = [6;41] \\), og heller ikke her er jeg altså udenfor
intervallet.

Konklusion: På trods af alle tegn på det modsatte er jeg ikke en outlier
i UNF Odense. I hvert fald ikke aldersmæssigt.

\\Worm

------------------------------------------------------------------------

[^1]: Ja, det er der jo vist nok mange subjektive meninger om, men lad
    os nu forsøge at holde os til videnskaben...

[^2]: Adskillige mener at på mystisk timey-wimey-wibbely-wobbely vis så
    har jeg ALTID været en gammel prut. Men da mine øvrige
    funktionsbeskrivelser i foreningen inkluderer "Orakel" og
    "Universalnørd" og "Hyggeonkel", så kan vi alle leve med tingenes
    tilstand.

[^3]: Akronymet kan oversættes til "Tildæk mit æsel" på engelsk.

[^4]: MAD, I tell you! MAAAAAAD![^5]

[^5]: Worm kigger op... Ja, hvem ville mig noget?

[^6]: Sædvanligvis er det kun skipister der kan blive mørkesorte. Det
    er klassen lige under "spild af god højde"

[^7]: På grund af årsager. Udledningen/rationalet overlades til den
    vågne l\[æø\]ser.
