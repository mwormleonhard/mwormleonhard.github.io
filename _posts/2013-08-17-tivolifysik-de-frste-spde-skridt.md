---
layout: post
title: Tivolifysik - de første spæde skridt
date: '2013-08-17T18:21:00.002+02:00'
author: Martin Worm-Leonhard
tags:
- Tivolifysik
- Mobiltelefon
- Anna-og-lotte
modified_time: '2013-08-17T18:21:46.749+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-7061854392995244637
blogger_orig_url: http://labnoter.blogspot.com/2013/08/tivolifysik-de-frste-spde-skridt.html
---

Indledning
----------

For nylig skrev jeg lidt om
[karruseller]({%post_url 2013-07-11-verdens-strste-karussel %}) og
førstehåndsoplevelse af fysik når man er i tivoli, og nu har jeg
heldigvis haft muligheden for at sætte mine fødder der hvor min mund er.
I den forløbne uge var jeg nemlig i Legoland sammen med en flok glade
nørder, og hvad var så mere nærliggende end at tænde for accelerometeret
i min smartphone og forsøge at indsamle nogle data, bare for at se om
konceptet har nogen gang på jord. Det viste det sig heldigvis at have,
og selvom kvaliteten af data ikke er overvældende (Mere om det senere),
så er det godt nok til at der afgjort er baggrund for en opfølgende
studietur. :-)

Materialer og metoder
---------------------

Alle forsøg er foretaget i Legoland, data er opsamlet af undertegnede
med en LG Nexus 4 smartphone med programmet [Sensor Kinetics
PRO](https://play.google.com/store/apps/details?id=com.innoventions.sensorkineticspro&hl=en),
der kan eksportere til csv-filer. 

Der er opsamlet data fra den afledte
sensor der hedder "Linear acceleration", som en virtuel sensor, som
telefonen selv danner ud fra rå accelerometerdata, ved at trække
tyngdekraftens bidrag fra. Dette medfører dog også at den ikke leverer
data lige så hurtigt som sensoren kan levere dem, da de først skal
behandles, men jeg fik en datarate på ca. 5Hz ud af det, og det viste
sig tilstrækkeligt til det meste. 

Jeg havde foretrukket at bruge
programmet [Sensor
Logger](https://play.google.com/store/apps/details?id=com.kzs6502.sensorlogger&hl=en),
der kan levere data direkte ned i en csv-fil uden at spilde kræfter på
at tegne pæne grafer, men da Android netop er blevet opdateret så
brækkede det program desværre, og jeg måtte improvisere.

Data er optaget ved at starte programmets logning og putte telefonen i
brystlommen, så den følger min krops bevægelser tættest muligt. Herved
bliver det, der i data kaldes positivt på X-aksen til min højre,
positivt på Y-aksen er min "opad" og positivt på Z-aksen er "mig der
stopper/accelereres baglæns".

Dette giver naturligvis nogle usikkerheder --- da telefonen ikke ligger
helt fast kan den bevæge sig lidt mere end mig, og have sin egen inerti,
og derved får man en kombination af et fysisk lavpasfilter og nogle
formodentligt lidt over-/underdrevne data.

En anden mulighed var at spænde den fast på armen eller, endnu bedre,
låret med sådan en løbe-musik-telefon-holde-dims, men for nuværende
virkede det meget godt.

Jeg markerede start og slut på turen ved at banke 3 gange på lommen
(tydeligt udslag i Z-retning) og har efterfølgende klippet data til,
efter dette, så vi kun har de interessante stumper tilbage.

For alle ture er der endvidere beregnet en "samlet acceleration" som er
defineret ved \\[Samlet=\sqrt{X^2+Y^2+Z^2}\\]
Den har ikke noget direkte fysisk modstykke, så vidt jeg kan se --- ret
mig endelig hvis jeg tager fejl --- men den er en meget god generelt
indikator for hvor "vild" forlystelsen er som funktion af tid.

Al dataanalyse er foretaget i [R](http://www.r-project.org/) vha
[R-studio](http://www.rstudio.com/) og rådata og kode kan rekvireres ved
at skrive til mig.

Resultater og diskussion
------------------------

### Tekopperne

Dagens første stop var tekopperne - for dem der ikke måtte være bekendt
med fænomenet så er det en kop man sætter sig i, hvorefter hele koppen
kan rotere om sin egen midterakse ved deltagernes muskelkraft, samtidig
med at koppen i sin helhed roteres om to andre akser - både en lokal for
3 kopper og en global for alle kopper. 

Hmmm... Jeg kan godt se jeg burde
have taget et billede. Jeg beklager. Nå, men det bliver i hvert fald en
meget epicyklisk, roterende oplevelse. Data fra turen ser således ud,
efter at være blevet udglattet en smule (5-punkts rullende middelværdi),
da de ellers ligner det rene støj:

[![]({{site.url}}/images/-Z0Ch1oLDs_s/Ug-DSSFf4PI/AAAAAAAABx4/B5G2Gsfb_uU/s400/Rplot004.png)]({{site.url}}/images/-Z0Ch1oLDs_s/Ug-DSSFf4PI/AAAAAAAABx4/B5G2Gsfb_uU/s1600/Rplot004.png)

Umiddelbart ser det jo meget tilforladeligt ud --- en roterende bevægelse
om flere akser må jo forventes at være cyklisk i sin påvirkning (noget
min mave kan bekræfte var tilfældet), men billedet mudres her noget af
at man ikke sidder stille med rank ryk og strakte knæ, men kastes noget
rundt i koppen både af kræfterne, af sammenstød med dem man sidder
sammen med og af at sidde og knokle med at trække sig selv rundt. 

Der
burde jo slet ikke være påvirkning i Y-retning, da vi ikke bevæger os op
og ned, men da jeg læner mig forover det meste af tiden, så bliver der
alligevel et bidrag i denne retning. Her kunne man nok med fordel have
gaffertapet telefonen til sædet i stedet. 

Nå, men der er stadig muligt
at gøre et par observationer, hvoraf den første er at der er en meget
tydelig spike i data ved ca 45 sekunder. Det var da vi besluttede os for
at ændre koppens rotationsretning om midteraksen, hvilket jo svarer til
at man skifter fortegn på påvirkningen og derfor midlertidigt har en
stor kraftpåvirkning fra denne indsats, indtil man er kommet op i fart
den anden vej.

Da vektorerne er en smule skæve er det svært at lave en ordentlig
frekvensanalyse, men Hvis vi prøver at zoome lidt in på de to
væsentligste vektorer, nemlig X(sort) og Z(rød) ser vi

[![]({{site.url}}/images/-K5UrwsrIK6Q/Ug-GEVWNiTI/AAAAAAAAByE/Hh0DM52YkQQ/s400/Rplot005.png)]({{site.url}}/images/-K5UrwsrIK6Q/Ug-GEVWNiTI/AAAAAAAAByE/Hh0DM52YkQQ/s1600/Rplot005.png)

en tydelig periodicitet i x-retningen med en periode på ca 4-5 sekunder,
hvilket svarer meget godt til en rotation om den største akse. Vi ser
også X og Z er faseforskudt, altså ikke følges ad, men helt tydeligt er
det ikke, og det er svært at afgøre hvor meget der er artefakter og hvor
meget der er reelle data. Laver man en egentlig spektrumanalyse får man
noget der ser således ud:

[![]({{site.url}}/images/-blu7gbuwpug/Ug-ICvP3wjI/AAAAAAAAByQ/NnCSPHmvXi4/s400/Rplot002.png)]({{site.url}}/images/-blu7gbuwpug/Ug-ICvP3wjI/AAAAAAAAByQ/NnCSPHmvXi4/s1600/Rplot002.png)

Det ses heraf at de mest intense signaler er ca 0,25 Hz, svarende meget
godt til ovennævnte observerede peride om storaksen og ca 0,6 Hz
svarende meget godt til den mellemste eller mindste akse samt 1Hz, der
kunne være rotationen om den lokale midterakse, selvom det virker lidt
hurtigt, og intensiteten af signalet allerede her er så lav at jeg ville
være tilbøjelig til at kalde det støj.

#### Delkonklusion

Skal man måle noget rigtig godt på tekopperne, så skal man have en
"designated data collector" (DDC) der forsøger at sidde helt stille og
rankt --- eller måske en rulle gaffa. Det er dog stadig muligt , selv på
disse noget kompromitterede data at få nogle nogenlunde fornuftige
resultater.


### X-treme Racers

Næste stop var X-treme racers --- en rutschebane om hvilket det eneste
negative der er at sige, er at den ikke er bygget til mennesker på 190cm
med en femur på næsten 50cm (Jeg kunne kun lige akkurat snige mig under
højdegrænsepinden). 

Den udmærker sig ved at starte med noget der til
forveksling minder om den nedafgående halvdel af en kasteparabel,
hvorved man føler at man stort set letter fra sædet og kun holdes fast
af bøjlen. Men kan det nu også passe? Det var faktisk et af de spørgsmål
der foranledigede dette studie i første omgang... Så lad os se på det!

[![]({{site.url}}/images/-hMLHRijKHnQ/Ug-MP1nQY0I/AAAAAAAAByc/Trn2KAIpKAU/s400/Rplot010.png)]({{site.url}}/images/-hMLHRijKHnQ/Ug-MP1nQY0I/AAAAAAAAByc/Trn2KAIpKAU/s1600/Rplot010.png)

Det allerførste der springer i øjnene er at, jo, den er god nok - spiken
i Y-retning ved ca. 15 sekunder falder fint sammen med det første store
fald, og den når næsten \\(10 \frac{m}{s^2}\\), hvilket jo meget godt modsvarer en
kortvarig ophævelse af jordens tyngdekraft. 

Spiken ses også på Z-aksen,
da jeg jo også accelereres fremad. Herefter er Y-aksen ret rolig, men X
og Z pulserer kraftigt, hvilket svarer fint til at banen herefter består
af en stribe hårnålesving hvor man hurtigt skifter retning og hastighed,
men ikke højde. Afslutningsvis kommer en serie småkurver der krummer i
adskillige planer og retninger, afsluttet med en pludselig opbremsning.

Alt i alt fantastisk korrelation mellem data og subjektiv oplevelse, og
det ses at man udsættes for ret store kræfter på denne tur --- helt op til
og med ca 1 tyngdekraft, bare i skiftende retninger.

Det er fristende at tro at man kan integrere kurverne en enkelt gang og
få en hastighedsprofil, eller måske endda 2 og få en stedprofil --- så
kunne man 3D-tegne rutschebanen ud fra data - men så let går det
desværre ikke. 

Dataraten er for lav og driften er for stor og man ender
med at tro man kører 250 km/t et sted ude over Billund lufthavn. Jeg har
prøvet :-) (Det er et kendt problem med selv [højkvalitetsudstyr lavet
til
formålet](http://en.wikipedia.org/wiki/Inertial_navigation_system#Error)...
Men, hvis du kan gøre det bedre, så skriv, så får du mine data!)

#### Delkonklusion

I en almindelig rutschebane er det fuldt ud muligt at opsamle data der
udviser fin overensstemmelse med den subjektive oplevelse af turen, samt
at kvantificere de kræfter der virker på én undervejs. Det kunne være
sjovt at prøve at korrelere den samlede påvirkning med fx hjerterytme,
blodtryk, pupiludvidelser, hudens galvaniske respons eller anden
stress-indikator.

### Polar Explorer

På samme måde som X-treme racers er Polar explorer også en klassisk
rutschebane, der dog er ny nok til at have rigeligt med plads til voksne
mennesker og et noget mere solidt fastspændingssystem inklusive
formstøbte sæder, der har den fordel at kræfterne overføres mere
effektivt mellem vogn og passager, så det både giver en bedre
rutschebanetur og bedre målinger :-)

Nu kender I jo efterhånden turen, så lad os uden videre kaste nogle
grafer på bordet:

[![]({{site.url}}/images/-mgeu0WVW0vg/Ug-QjTN7AyI/AAAAAAAAByo/2QPOn1FlyDQ/s400/Rplot001.png)]({{site.url}}/images/-mgeu0WVW0vg/Ug-QjTN7AyI/AAAAAAAAByo/2QPOn1FlyDQ/s1600/Rplot001.png)

Igen ser vi at der er fin overensstemmelse mellem data og subjektiv
virkeligehed --- man starter med at køre stille og roligt op, hvorefter
man kastes kraftigt nedad og ud i et voldsomt venstresving, der går
direkte over i en kurver opad og et kraftigt højresving. Gentag et par
gange. 

Under disse manøvrer komme man op og trække lige godt det
dobbelte af tyngeaccelerationen (2g). Herefter kommer et relativt stille
og roligt område hvor man rangeres ind i en "klippehule", hvorefter den
store overraskelse droppes på én --- helt bogstavligt! 

Efter at have holdt
stille i et par sekunder eller 10 dropper hele vognsættet et par meter
lodret ned, og som det kan ses på Y-akse-spiken omkring de 55 sekunder
er der tale om et stort set frit fald. derefter er der et par søde små
kurver og bakker igennem et "sightseeinglandskab", hvoefter turen er
slut.

#### Delkonklusion

Se ovenfor under X-treme racers. Det samme gør sig gældende her.

### Kålormen

På vej ud kom vi forbi kålormen, og måtte nødvendigvis lige have en tur
--- for videnskaben, forstås :-) 

Her havde vi et meget mere veldefineret system i regulær cirkelbevægelse
end tilfældet var med tekopperne. I al sin enkelhed består kålornen af
en serie vogne der kører på et cirkulært spor, der samtidig bugter sig
op og ned i noget som enten er en sinuskurve eller en serie halvflade
parabler med skiftende fortegn. 

Desværre er det en klassisk
børneforlystelse, så jeg kunne (heller) ikke sidde helt ret og vinkelret
på kørselretningen. Jaja, det er selvfølgelig muligt at lave en
koordinattransformation, men det må være en øvelse for den vågne
l\[æø\]ser. Ikke desto mindre ser vi væsentlig pænere data end fra
tekopperne:

[![]({{site.url}}/images/-MsmmO8hyGIw/Ug-U7EN_aRI/AAAAAAAABy0/WLVCwalcfW0/s400/Rplot008.png)]({{site.url}}/images/-MsmmO8hyGIw/Ug-U7EN_aRI/AAAAAAAABy0/WLVCwalcfW0/s1600/Rplot008.png)

Her er også anvendt udglatning --- 3-punkts løbende middelværdi --- og det
ses som forventet at den største bevægelse er i Y og Z, (op/ned og
acceleration/deceleration) og at X-retningen er en stort set konstant
påvirkning ("centrifugalkraft"). 

Oscillationen om X skyldet som
tidligere nævnt at jeg sad skævt i vognen, hvorved noget af bevægelsen
projiceres ned på denne akse. Det eneste der egentlig er decideret
mystisk på dette datasæt er at bevægelsen i Y-retning burde være
symmetrisk, da sporet er det, men dette  kan skyldes at telefonen kunne
bevæge sig lidt opad i lommen, hvilket ville dæmpe udslaget i denne
retning, for det er næppe sandsynligt at det skyldes eksempelvis
manglende motorkraft i forlystelsen, da alle vogne er forbundet, og
derved som samlet arrangement er konstant belastet, og da det er på den
nedadgående del af bevægelsen. 

Det ses også at her kommer man ikke helt
op og svæve, men reduceres i bedste fald til ca. 10-20% af normalvægt. 

Zoomer vi ind og sammenligner vi bevægelsen i Y(sort) og Z-retning(rød)
ses følgende:

[![]({{site.url}}/images/-9q5fVFS_-FI/Ug-XPR_5miI/AAAAAAAABzA/cE1wMTxbd-Q/s400/Rplot009.png)]({{site.url}}/images/-9q5fVFS_-FI/Ug-XPR_5miI/AAAAAAAABzA/cE1wMTxbd-Q/s1600/Rplot009.png)

Her ses faseforskydningen meget smukt og tydeligt. Når man er på toppen
af en bue, svarende til en sort peak, så  ophører påvirkningen "opad"
samtidig med at man påvirkes mere "fremad", svarende meget godt til at
man "skubbes frem" af sporet, indtil man når en dal, hvorefter man
accelereres opad og "bremses" i det vandrette plan, idet
rotationshastigheden er konstant.

Bare fordi jeg kan, så skal vi da lige have et spektrogram på banen:

[![]({{site.url}}/images/-sufgJrBn3Kw/Ug-YgUeUWwI/AAAAAAAABzI/rRRiO_6qWVg/s400/Rplot006.png)]({{site.url}}/images/-sufgJrBn3Kw/Ug-YgUeUWwI/AAAAAAAABzI/rRRiO_6qWVg/s1600/Rplot006.png)

Ganske som forventet ser vi hér kun ét kraftigt signal, ved ca 0,75Hz,
svarende ganske fint til at der går lige over et sekund mellem man
rammer én top og den næste.

Outro
-----

Således var ordene --- man kan tage sin mobiltelefon med i en
forlystelsespark, og så fortsætter forlystelserne med at give udbytte i
timevis derhjemme :-)

Der er naturligvis masser af optimerings- og forbedringsmuligheder,
hvoraf den mest oplagte er at prøve at finde en måde at overføre kræfter
mere direkte mellem forlystelse/menneske og måleudstyr (mobiltelefon).

Som ingeniør vil jeg jo som udgangspunkt anbefale gaffertape, men som et
temmelig låddent hankønsvæsen vil jeg så hurtigt glemme den idé igen, da
jeg ikke tror der bliver set med helt milde øjne på at man gaffer sin
telefon fast til forlystelsen (men prøv at spørge uden for sæsonen - det
kan være du kan finde et lokalt legebarn :-)) hvilket jo kun efterlader
muligheden at klistre den fast til personen, hvilket vel trods alt også
vil give et mere troværdigt billede af hvad mennesket oplever? Måske er
det her førnævnte armbindstelefonholdedims kommer ind i billedet.

Af et første, primitivt forsøg er jeg meget tilfreds.

Spørgsmål? Kommentarer? Forslag? Bare kom med dem - herunder, ude til
højre eller på anden måde - eller vi ses måske i en forlystelsepark en
dag. Det er mig der sidder og slår mig på lommen inden rutschebanen
starter... :-)

\\Worm
