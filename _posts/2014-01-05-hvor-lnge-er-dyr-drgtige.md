---
comments:true
layout: post
title: Hvor længe er dyr drægtige?
date: '2014-01-05T21:45:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Modellering
- Zoologi
- R
modified_time: '2014-01-05T21:45:05.787+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-3395805351713296185
blogger_orig_url: http://labnoter.blogspot.com/2014/01/hvor-lnge-er-dyr-drgtige.html
---

Godt nytår allesammen! Jeg håber I er kommet godt ind i det og stadig
kan tælle til 1023 på fingrene.

Her i weekenden blev jeg i et quizspil udsat for spørgsmålet "Hvor længe
er en flodhest drægtig?", og selvom det lykkedes mig at vælge den
rigtige mulighed ved en kombination af ekstrapolation og svineheld så
fik det mig alligevel til at tænke over at der jo må være en sammenhæng
mellem størrelsen af dyret og hvor længe det er om at bage afkommet
færdig. Vi ved instinktivt at store dyr er drægtige længere end små dyr,
men hvordan hænger det helt præcist sammen?

Efter at have forsøgt at distrahere mig selv med både det nyeste afsnit
af Sherlock, samt Varm luft i Canal Grande gik det op for mig at jeg
blev nødt til at undersøge det nærmere for at tilfredsstille min nørdede
nysgerrighed, og selvom min google-fu er stærk, så valgte jeg alligevel
at forsøge at udlede en form for svar fra tilgængelige data, så jeg
satte vand over til en kold pilsner og satte i værk.

Tante wiki hjalp mig med at finde den nødvendige information - på
 <http://en.wikipedia.org/wiki/Gestation_period> er der en fin liste
over hvor længe forskellige (patte)dyr er drægtige, og endda links til
de forskellige dyrs hovedartikel, ud af hvilke man hurtigt kan læse hvor
store de forskellige dyr er.
Jeg valgte at bruge kropsvægten som
indikator for "størrelse", da den er lettest at forholde sig til, og da
der er mange dyr og arter der kan variere meget i størrelse,
valgte/estimerede[^1] jeg nogle, efter min mening rimelige, værdier for
middelværdier --- usikkerheder måles alligevel bedst i træskolængder, og
hvis bare man har punkter nok så burde fejlen udjævnes.[^2]

Så efter en halv times tid med et excelark og et par besværgelser i
RStudio havde jeg følgende plotsæt (klik for at forstørre):

[![]({{site.url}}/images/-ej4unP21bAY/Usm2bKhrNgI/AAAAAAAAB_o/uCgP_uFwCqg/s400/Rplot1.png)]({{site.url}}/images/-ej4unP21bAY/Usm2bKhrNgI/AAAAAAAAB_o/uCgP_uFwCqg/s1600/Rplot1.png)

Alle graferne viser de samme data --- drægtighedsperiode i døgn, som
funktion af kropsvægt i kg. Det er kun akserne der er forskel på.

Øverst til venstre er data på lineære akser (x-aksen er skåret af ved
1000 kg for at kunne se punkterne bedre --- der er et par elefanter,
næsehorn og en hval ude til højre for plottet) og der fremgår ikke nogen
tydelig funktionssammenhæng.

Øverst til højre er x-aksen gjort logaritmisk, og nu ser det lidt ud som
om der er to rette linier/funktioner --- én op til ca 30 kg, og en lidt
mere rodet derover, men stadig ikke én model der kan beskrive det hele.

Nederst til venstre er y-aksen logaritmisk (x-aksen er igen skåret af
ved 1000 kg for at kunne se punkterne bedre --- der er stadig et par
elefanter, næsehorn og en hval ude til højre for plottet --- det kan være
de er gået i vandet sammen), og nu ser det ud som om drægtighedsperioden
nærmer sig et loft asymptotisk, men det er mest et artefakt af den
logaritmiske skala, og det er stadig svært at finde en simpel model der
beskriver alle data.

Nederst til højre, hvor begge skalaer er logaritmiske begynder det at
ligne noget. Det kunne godt være en ret linie! Jojo, der er stadig en
masse støj og nogle outliers, men nu er det jo også data fra
virkeligheden der er filtreret gennem wikipedia og mine estimater og
samlet sammen i bersærkergang, så i anledning af at det er den bedste
model vi har lige nu, lad os så se hvad det betyder at vi har en lineær
sammenhæng på et dobbeltlogaritmisk plot.

Hvis vi har en lineær sammenhæng på et dobbeltlogaritmisk plot, har vi
altså at \\[\log(drægtighedsperiode~[døgn] = a \cdot log(vægt~[kg]) + b\\]
hvilket vi med lidt velvalgt fingergymnastik kan omskrive til
\\[\text{drægtighedsperiode [døgn]} = \text{(vægt [kg])}^a \cdot 10^b\\]
altså en potensfunktion ganget med en konstant. Meget vel, men
hvad er potensen så?[^3] Og hvor god ER modellen egentlig?

Spørger vi vores trofaste ven R siger hun at potensen, a, er ca. 0.274 og
at \\(R^2=0,76\\) hvilket med nogen forsimpling betyder at 76% af
variationen i drægtighedsperiode er forklaret af variationen i vægt.

Dette er ganske acceptabelt for en model af denne art, og af de
tilhørende diagnostiske plots kan vi se at residualerne er ret
jævnt/tilfældigt fordelt, så der er ikke nogen grund til at tro at vi
begår en systematisk fejl ved at bruge denne model --- der er bare nogen
uforklaret variation/usikkerhed forbundet dermed. 

Plottene er medtaget
herunder for fuldstændighedens skyld, men spring dem bare over, med
mindre du er datanørd.

[![]({{site.url}}/images/-XrzvmLaAfYE/Usm8ZWJKA6I/AAAAAAAAB_4/oOgzlofi0s0/s400/Rplot2.png)]({{site.url}}/images/-XrzvmLaAfYE/Usm8ZWJKA6I/AAAAAAAAB_4/oOgzlofi0s0/s1600/Rplot2.png)

Her er det dobbeltlogaritmiske plot med den fittede linie indsat:

[![]({{site.url}}/images/-ZhpBiYB7kAI/Usm8Zc_XWGI/AAAAAAAAB_8/-5Lrj4_USrw/s400/Rplot3.png)]({{site.url}}/images/-ZhpBiYB7kAI/Usm8Zc_XWGI/AAAAAAAAB_8/-5Lrj4_USrw/s1600/Rplot3.png)

At drægtighedsperiode er proportional med kropsvægt opløftet til 0.274
er et lidt mystisk resultat ved første øjekast --- en potens et sted
imellem en tredjedel og en fjerdedel er ikke umiddelbart intuitiv, men
hvis vi nu lige tænker os om, så er vægt jo bare et andet mål for
rumfang[^4], og rumfang er jo længde i tredje potens, så en potens på
en tredjedel, svarende til at uddrage den tredje rod giver jo egentlig
bare "længde".

Havde potensen været præcis en tredjedel kunne vi altså have brugt den
som argumentation for at der burde være en lineær sammenhæng mellem et
dyrs fysiske dimensioner og dets drægtighedsperiode, men det passer jo
ikke heeeeeelt --- men på den anden side så kommer dyr i mange mystiske
former, så det bliver jo nok alligevel svært at blive enige om hvilken
fysisk dimension man bør bruge (giraffer bliver fx hurtigt en outlier
hvis man bruger "højde").

Dette kan muligvis også forklare at vi ikke får et "pænt" tal --- det er i
øvrigt utroligt svært at føre en tilsvarende simpel argumentation for
hvad potensen "en fjerdedel" kan fortolkes som...

Skal man lave det til en hurtig og grov tommelfingerregel så betyder det
at drægtighedsperioden for et pattedyr næsten fordobles for hvert ekstra
nul man sætter på kropsvægten --- det burde være præcist nok til rockmusik
og pubquiz.

Det føles og varsler i øvrigt ret godt at starte året med noget så
overflødig, men stadig tilfredsstillende fordi-jeg-kan-nørden. Jeg håber
jeres 2014 også bliver fyldt med den slags!

\\Worm

------------------------------------------------------------------------

[^1]: Videnskabeligt for "gæt".

[^2]: Fraregnet personligt bias, som jeg jo ikke kan sige mig fri for,
    da jeg havde en svag ide om hvordan det hang sammen, men jeg tror ikke
    jeg er helt vågen nok til at interpolere mig frem til et snyderesultat
    her søndag aften

[^3]: Jaja, haha...

[^4]: Antaget konstant massefylde, godt nok, men det er nok ikke helt
    urimeligt. Det er jo kun fysikere der har friktionsfri homogene sfæriske
    elefanter i vakuum...
