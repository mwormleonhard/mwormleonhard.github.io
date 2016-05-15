---
comments:true
layout: post
title: Hoverboards - nu med mere fysik
date: '2014-03-24T20:44:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Energi
- Kræfter
- Bagsiden af kuverten
- Magnetisme
- Sanity check
modified_time: '2014-03-24T20:44:55.453+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5123400766339620033
blogger_orig_url: http://labnoter.blogspot.com/2014/03/hoverboards-nu-med-mere-fysik.html
---

"Scientists: You have N years" (0&lt;N&lt;20) er et meget almindeligt
meme for folk der ønsker sig et stykke teknologi der har været skildret
i klassisk sci-fi, så som "Tilbage til fremtiden Mk Y" (1&lt;=Y&lt;=3),
der jo (på nuværende tidspunkt) er sat i vores ret nære fremtid.

En af de mest ønskede dimser er hoverboardet --- et skateboard der kan
svæve frit ca. 10--50 cm over (næsten) enhver overflade. Personligt ville
jeg hellere have "Mr. Fusion", der tilsyneladende kan omdanne
almindeligt (organisk?) affald til næsten ubegrænset, ikke-forurenende
energi, men jeg kan godt se hvorfor det er sejt at have et hoverboard.

Eftersom man tilsyneladende allerede kan leveitere
[superledere](https://www.youtube.com/watch?v=de1ZqrQAI1I),
[tog](http://en.wikipedia.org/wiki/Shinkansen#Maglev_.28Chuo_Shinkansen.29) og
[frøer](https://www.youtube.com/watch?v=A1vyB-O5i6E) uden de helt store
armbevægelser er det vel mere et ingeniørmæssigt problem end et
videnskabeligt?

Lad os alle regne!

Det største problem er tilsynelandende at med mindre nogen sidder
med et par ton [cavorit](http://en.wiktionary.org/wiki/cavorite) og bare
venter på at verden er klar til det, eller der bliver gjort et stort
gennembrud inden for spin/kvante-låse, flux pinning eller bare Ganske
Almindelig Antityngde[^1], så har vi ikke rigtig noget at skubbe fra
på, ud over jordens magnetfelt[^2], og det er ikke ret stort. Faktisk
andrager det kun \\(25--65\mu T\\). 

Til sammenligning er feltet fra en
almindelig køleskabsmagnet let 10mT --- altså omkring 500 gange stærkere,
men selv de [stærkeste permanente NIB
magneter](http://www.supermagnete.de/eng/data_table.php) kommer sjældent
over en feltstyrke på 1--1,5T uden at være specialvarer, og vi har jo
aldrig set sådan en fætter svæve spontant over jorden, selvom nogle af
dem er stærke nok til at de automatisk retter ind efter nord-syd
feltlinerne, hvis man stiller dem på højkant eller hænger dem op i en
snor... De er også djævelsk svære at regulere, så vi må nok have fat i
en elektromagnet.

Nu leger vi lige fysikere og regner på friktionsløse elefanter i vakuum,
eller i hvert fald tillader vi os at se bort fra problemer så som vinkel
til feltet, lokale variationer i styrke, skærmning etc. og antager et
homogent felt på \\(45\mu T\\) som vi kan støde fra imod --- hvor meget
energi skal vi så bruge på at løfte 100 kg 10 cm og holde dem der?

Magnetfelter er notoriske for at være noget skrald at skulle regne
analystisk på i den virkelige virkelighed, så lad os huske at vi er
fysikere, med en option på ingeniører, og bruge Gilberts model for
magnetiserede flader nær hinanden, bare for at få et svar med en
usikkerhed i træskolængder. Så burde man kunne beregne kraften mellem to
magnetiserede flader som:
\\[F=\frac{B_1 \cdot B_2 \cdot A}{2 \mu_0}\\]
Hvor \\(\mu_0\\) er vakuumpermeabilieteten;  \\(\approx 1,3\cdot
10^{-6}\frac{N}{A^2}\\),  \\(B_1\\) og \\(B_2\\) er styrken af de
interagerende felter i T og A er arealet de virker på hinanden over i
\\(m^2\\).

Hvis vi vil kunne løfte 100kg mod tyngdekraften skal vi bruge ca 1000N i
runde tal, og vi har vel på en god dag 0,1 \\(m^2\\) overflade at gøre
godt med, så vi får:
\\[ 1000N = \frac{45\mu T \cdot B_2 \cdot 0,1m^2}{2 \cdot 1,3\cdot 10^{-6}\frac{N}{A^2}}\\]
og efter lidt fingergymnasitk finder vi så at \\(B_2 = 578T \\) Det er
edderbrølemig en stor magnet, taget i betragtning at de største
superledende af slagsen jeg har hørt om er omkring de 25T, men da
verdens allerstørste magnetfelt tilsyneladende er på 2,8 kT, så burde
det ikke være helt umuligt... 

Superledere har det dog med at dø en
spektakulær død ved sådanne strøm- og feltstyrker, da de har et
maksimalt felt de tåler inden de holder op med at være superledere og
spreder sig selv ud over fædrelandet med overlydshastighed.

Men... Hov! Nu tilstøder der en uforudset komplikation --- tilsyneladende
kan selv de største og ondeste almindelige elektromagneter (meget
 passende kaldet [Bitter
Electromagnets](http://en.wikipedia.org/wiki/Bitter_electromagnet)) ikke
danne permanente felter meget over 30--40T på grund af førnævnte tendens
til at skille sig selv ad ved store strøm- og feltstyrker, også i
ikke-superledende anvendelser... Hmmmm.... Så ER det altså et
videnskabeligt gennembrud der skal til...

Men hov! (Igen) Hvor kom så de 2,8 kT så fra? Jo, for hvis man er
ligeglad med at magnetfeltet holder meget kortvarigt, så kan man designe
en elektromagnet der ved hjælp af [korte pulser og
sprængstof](http://en.wikipedia.org/wiki/Electromagnet#Exploding_electromagnets)
leverer helt absurde feltsyrker i meget kort tid --- hvilket jo er
fascinerende i sig selv!

Nå, men uanset hvad der skal holde jeres hoverboards oppe (forhåbentlig
om få år), så vil jeg godt sætte en kasse kælderkolde blå chimpanser på
at det ikke bliver magneter...

Almindelig opdrift med nedadstrømmende luft --- "Løvblæserbræt" har stadig
fysisk gyldighed, men givet at selv de bedste batterier har en
energitæthed på ca 2 MJ/kg mod benzins ca 40 MJ/kg, så vil jeg anbefale
jer at bruge en benzindrevet, hvis I vil længere end ud af indkørslen...
Opvisninger bliver også mere spektakulære når der kan gå ild i
isenkrammet...

Med begge fødder plantet på jorden,  
\\Worm

------------------------------------------------------------------------

[^1]: Kendt fra bla. Iain M Banks, hvor det er allestedsnærværende -
    læs hans bøger alligevel --- det er rigtig god sci-fi, selvom den er
    "blød".

[^2]: ER der andet? Jeg kan ikke lige komme på noget, der ikke er endnu
    værre at skulle interagere med, med nuværende teknologi?[^3]

[^3]: Fraregnet et løvblæserdrevet minihovercraft (med eller uden ål),
    men de har deres egne problemer med energiforsyning i størrelsesordenen
    1-2 kW
