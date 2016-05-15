---
comments: true
layout: post
title: Færre trykgradienter på cykelstierne?
date: '2013-06-24T21:41:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Fluidmekanik
- Meteorologi
- Trafikfysik
- Drag
modified_time: '2013-06-24T21:41:55.451+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-7754630530672821341
blogger_orig_url: http://labnoter.blogspot.com/2013/06/frre-trykgradienter-pa-cykelstierne.html
---

På vej til campus på min cykel, en alt for tidlig lørdag morgen (for at
forberede UNF Odenses [Sciencecamp
2013](http://odense.unf.dk/sommercamp-intro.php)) slog det mig at
geografi og vejr tilsyneladende havde rottet sig sammen for gøre turen
så svær for mig som muligt - i hvert fald føltes det som om det var op
ad bakke hele vejen, men det var nok bare paranoia, induceret af
koffeinmangel og det faktum at klokken endnu ikke var blevet tocifret.
Men det fik mig til at tænke over om det var muligt at sammenligne mod-
og medvind med at køre op og ned af bakker - og ja, selvfølgelig kan man
det, i hvert fald rent kvalitativt - det har jeg lige gjort, og den
eneste forskel er at vinden sjældent har så jævn og konstant en hældning
som landskabet. Men det må være muligt at regne på, så det vil jeg
naturligvis forsøge.

Det gjorde det i øvrigt ikke på bemeldte dag --- regnede altså.

Hvis vi indledningsvis skal prøve at forsimple opgaven mest muligt, så
lad os betragte blæsevejr som en statisk funktion af at man bevæger sig
fra et område med ét tryk til et område med et andet - modvind kommer af
at man bevæger sig fra lavt tryk til højere tryk, og vinden er naturens
måde at forsøge at udligne trykforskellen på. Vi ser altså bort fra
coriolis og lokale geometriske og geografiske faktorer der kan påvirke
vindens styrke og retning.

Ser man på DMIs vind- og frontkort kan man sjusse sig frem til at en let
brise på 5-8 m/s cirka passer med at trykgradienten er 5 millibar (som i
SI-enheder bør kaldes hektopascal - hPa) på tværs af Jylland, nær Grenaa
(ca. 170 km), svarende til \\(\frac{500Pa}{170km} \approx 3 \frac{mPa}{m}\\).

Hvor svært det er at bevæge et/sit legeme imod en gas eller væske
afhænger af emnets geometri, størrelse og hastighed, men hvis vi starter
med at se på det som en tilstandsfunktion kan vi se bort fra hastigheden --- 
så kan vi altid bagefter se om det er en rimelig antagelse.

Hvis vi nu antager at mit tværsnitsareal forfra er \\(2m^2\\) og min
dybde er 0,3m ser vi at kraften på mig som følge af forskellen i tryk
mellem min for- og bagside bliver: $$3 \frac{mPa}{m} \cdot 2m^2 \cdot 0,3m \approx 2mN$$ 

To millinewton er så lille en kraft at det
ikke er værd at bemærke --- det er mindre end tyngdekraften på et riskorn,
og der er jo ikke meget arbejde i at løfte sådan ét. Det er altså
tydeligvis ikke den statiske trykgradient der gør det hårdt at cykle i
modvind... Men hvad er det så?

Jo, det forholder sig sådan at det ikke er helt så ligetil at beskrive
hvor svært det er at bevæge sig gennem et medie der gør modstand --- det
afhænger af en serie af faktorer, herunder hvordan éns tværsnit ser ud,
hvad massefylden af mediet er og hvor hurtigt man bevæger sig. 

Alt sammen ting som vi instinktivt egentlig godt ved --- det er svære at løbe
gennem vand end gennem luft, for eksempel. Sjovt nok er ligningerne de
samme for luft/gasser og væske --- der er bare nogle størrelser der
opfører sig lidt anderledes. Derfor omtaler man også hele området under
ét som _fluid dynamik_. Her er "fluid" altså en fordanskning og skal
fortolkes som "noget der flyder", snarere end "noget der er flydende".

Nå, nok om etymologien, lad os få en ligning på bordet.
Luftmodstand kan beregnes ved hjælp af den såkaldte "drag equation", der
altså ikke har noget at gøre med at iklæde sig tøj der normalt forbindes
med det modsatte køn...

$$F_D=\frac{1}{2} \cdot \rho \cdot v^2 \cdot C_D \cdot A$$
hvor \\(F_D\\) er den resulterende kraft, \\(\rho\\) er massefylden af
mediet man bevæger sig igennem, \\(v\\) er hastigheden man bevæger sig
med, \\(C_D\\) er drag-koefficienten --- en enhedsløs størrelse jeg
straks vender tilbage til, og \\(A\\) er tværsnitsarealet  af det, der
bevæger sig.

Inden vi begynder at regne på det, kan vi lige så godt afskaffe
kraftbegrebet og erstatte det med effekten som kræves --- altså hvor mange
Watt (Joule per sekund) det kræver at kæmpe sig gennem mediet --- i dette
tilfælde luft. 

Det gør vi ved at gange kraften med hastigheden. Ved
samme lejlighed kan vi ligeså godt få sat de konstante størrelser ind.

Massefylden af luft er naturligvis afhængig af tryk og temperatur, men
indenfor en træskolængde kan vi godt tillade os at antage at
\\(\rho_{luft}=1,2 \frac{kg}{m^3}\\). Mit tværsnitsareal er stadig
 \\(2m^2\\), og ifølge [Tante
Wiki](http://en.wikipedia.org/wiki/Drag_coefficient) er
drag-koefficienten for meget lidt aerodynamiske legemer, under hvilke
jeg regner mig og min havelåge, \\(C_D \approx 1 \\). 

Efter lidt fingergymnastik får vi således: $$P_{luftmodstand} \approx
\frac{1}{2} \cdot 1,2 \frac{kg}{m^3} \cdot v^3 \cdot 1 \cdot
2m^2 = 1,2 \frac{kg}{m} \cdot v^3$$ hvor \\(P_{luftmodstand}\\)
 er den effekt jeg skal yde for at overvinde luftmodstanden og \\(v\\)
er min hastighed i \\(\frac{m}{s}\\). 

Bare rolig --- enhederne går op: \\(\frac{kg \cdot m^2}{s^3}\\) er faktisk det samme som Watt. 
Find eventuelt en nyudsprunget student der endnu ikke har glemt sin
grundlæggende fysik, hvis du ikke selv gider regne efter.

Nå, men alt dette bogstavskubberi leder os altså frem til at selv ved en
ganske rimelig hastighed på omkring 5 m/s, så skal jeg yde 150W for at
overvinde luftmodstanden en vindstille dag, men selv ved en ret let
modvind, ligeledes på 5 m/s bliver den nødvendige effekt ca. 1200W, da
en fordobling af hastigheden (i forhold til luften) jo ottedobler
effektbehovet. 

Til gengæld bliver jeg således kun sparet for 150W, hvis
jeg havde den samme vind i ryggen! En urimelig asymmetri, synes jeg...

For at sætte effekttallene i relief: En glad amatør kan efter sigende
yde ca. 3W per kg kropsvægt "i flere timer" --- for mit vedkommende bliver
det altså omkring 270W --- og elitesportsfolk har et peak-output på
onkring 2000W i sprint. Der er altså ikke noget at sige til at det er
hårdt at cykle i modvind!

Men... men.... hvordan opnår professionelle cykelryttere så deres
vanvittigt høje hastigheder? Ja, de piller i sagens natur ved de eneste
faktorer de har kontrol over, nemlig drag-koefficienten og
tværsnitsarealet --- hvis de eksempelvis kan få kombinationen af de
faktorer (der ovenfor giver \\(1,2 \frac{kg}{m}\\))  ned på cirka
\\(0,2 \frac{kg}{m}\\), svarende til et tværsnitsareal på \\(0,5m^2\\)
og en drag-koefficient på 0,7, så skal de jo kun bruge en sjettedel af
den effekt jeg skal bruge for at køre med samme hastighed, og dermed kan
de køre \\(\sqrt[3]{6}=1,8\\) gange så hurtigt ved det samme
energioutput. 

Nu begynder jeg at forstå hvorfor de er så fanatiske med
at være aerodynamiske og optimere både deres og cyklens
tværsnitsareal...  
Som et lynhurtigt sanitycheck kan man jo lige se på
hvad det giver af sprinthastighed ved P=2kW: $$\begin{aligned} 2000W
&= 0,2 \frac{kg}{m} \cdot v^3 \Leftrightarrow \\ v &=
\sqrt[3]{\frac{2000W}{ 0,2 \frac{kg}{m}}} \Leftrightarrow \\ v
&= 21 \frac{m}{s} \end{aligned}$$ 

Altså cirka 78 km/t --- det lyder
måske lidt højt, men husk at vi ikke har trukket rullemodstand,
tranmissiontab, friktion og så videre fra, så alt i alt er det vist godt
nok til rock.

Hov! Nu glemte jeg helt min op-og-ned-af-bakker-analogi, men som den
vågne elev vil have opdaget, så er det ikke længere helt ligetil at
sammenligne en given med- eller modvind med en bakke med en given
hældning, idet man i stedet for et konstant træk eller skub fra
tyngdekraften vil opleve en varierende grad af modstand som funktion af
hastighed.  
Hvis I selv har lyst til at lege med cykelfysik kan I jo forsøge at
beregne hvor stor hastighed man når, inden kræfterne er i ligevægt hvis
man tager den på frihjul ned af L'Alpe d'Huez på en gammel havelåge i
ordonnansfrakke og/eller på en racer og i aerodynamisk stilling og
påklædning...

\\Worm
