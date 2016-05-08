---
layout: post
title: Dimensionsanalyse og stegning af kalkuner
date: '2015-02-03T00:23:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Varmelære
- Skalering
- Dimensionsanalyse
- Køkkenfysik
modified_time: '2015-02-03T00:23:18.902+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8697119742235500246
blogger_orig_url: http://labnoter.blogspot.com/2015/02/dimensionsanalyse-og-stegning-af.html
---

Jeg har haft lyst til at skrive det her indlæg ret længe --- mest fordi
det handler om noget jeg ikke rigtig forstod, og så tænkte jeg at det
ville være en fin måde at tvinge mig selv til at lære det på, for at
kunne forklare det ordentligt.

Emnet er som sagt "dimensionsanalyse" --- og det er en måde at analysere
sammehænge mellem forskellige størrelser i et system, for at kunne
udlede hvordan de afhænger af hinanden -- og her kommer det vigtige ---
UDEN at man behøver kende størrelserne på forhånd eller tage på
formelsafari --- man kan simpelthen udlede ligninger eller størrelser der
er karateristiske for systemet uden at have brug for en formelsamling,
og på den måde lære noget om hvordan de forskellige størrelser påvirker
hinanden.

Ja, det lyder ret abstrakt --- og det er det måske også, det er netop
derfor jeg har gået og ledt efter et godt eksempel, der er bare
tilnærmelsesvis relevant, uden at være ALT for langhåret --- det er trods
alt de færreste der har brug for at regne på centrifuger[^1] og
diffusion[^2] i deres hverdag.

Derfor glædede det mig meget da Henrik den første for nylig ikke bare
forklarede mig hele teorien så den var til at forstå på 15 minutter, men
også pegede mig i retning af bogen "Scale-up in Chemical Engineering"
(2nd ed., Wiley), hvor der [på side
12](http://books.google.dk/books?id=iz-v6-veOSgC&lpg=PP1&pg=PA12#v=onepage&q&f=false)
er et glimrende eksempel på hvordan man kan bruge dimensionsanalyse til
at vurdere stegetiden for en kalkun.

Jeg vil ikke lyve for jer --- der kommer til at være en en smule
formelfræs og mere fysik og matematik end man skulle tro var nødvendigt
for at stege en kalkun, men jeg synes det er god nørd, så nu får I den
alligevel.

Lad os alle regne...

Vi skal jo først lige have sandsynliggjort historien, så lad os ---
bare for eksemplets skyld --- sige at vi i min familie er vant til at
spise and til jul, og derfor er ret gode til at tilberede sådan en
fætter, men pludselig skal til at stege en kalkun fordi der kommer mange
til middag. 

Sådan et dyr har vi aldrig stegt før, men hvor svært kan det
være --- det er jo teknisk set bare en meget stor and, der ikke kan
svømme. Kan den egentlig flyve? Nå, men det kan den i hvert fald ikke
længere, når den ligger på køkkenbordet!

Med ingeniører i familien der både ynder at lave mad og nørde, så
kombinerer vi naturligvis disse emner, og laver en rask lille øvelse i
termodynamik[^3].

Hvis vi kikker på sådan et stykke plumpt fjerkræ der ligger inde i
ovnen, så kan vi udlede at stegetiden (t) må afhænge af overfladearealet
(A) --- jo større overflade den modtager varme gennem, jo hurtigere bliver
den færdig --- en flad minutsteak steger jo også hurtigere end en rund
kødbolle (med samme masse bliver det en ret stor kødbolle!).

Varmen afsættes fra ovnrummet i overfladen af fuglen, og derfor må
overfladetemperaturen (To) jo være med til af beskrive hvor hurtigt
fjerkræet optager energi.

Dernæst skal vi jo have varmen ind i dyret, og hvor hurtigt dét går
afhænger af kødets varmeledningsevne, altså hvor godt det er til at
flytte varme igennem sig og dets varmekapacitet, der beskriver hvor
meget energi det kræver at varme en given mængde op.

For at forsimple opgaven springer jeg lige nogle mellemregninger over og
konstaterer at de to størrelser er med god tilnærmelse konstante og
derfor kan vi slå dem sammen i den termiske diffusivitet (a), der
alligevel er ret tæt på det som en almindelig køkkenskriver ville forstå
ved ordet "varmeledningsevne".

Fætteren er færdig når den er gennemvarm / gennemstegt, altså må
kernetemperaturen (Tk) også være relevant at have med.

Godt så. Nu har vi følgende størrelser med følgende enheder[^4]:


-   Stegetid, t, sekunder (s)
-   Overfladeareal, A, kvadratmeter \\((m^2)\\)
-   Overfladetemperaturen, To, Kelvin (K)
-   Kernetemperaturen, Tk, Kelvin (K)
-   Termisk diffusivitet, a, \\(\frac{m^2}{s}\\) - ja, det er en
    sær enhed. Stol på mig.


Nu kommer vi til den egentlige analyse --- det hele er som sagt en kende
langhåret[^5], men bare hold godt fast. 

Det baserer sig på noget der hedder [Buckinghams
pi-teorem](http://en.wikipedia.org/wiki/Buckingham_%CF%80_theorem), der
fortæller os at hvis vi har n forskellige fysiske størrelser (her har vi
n=5: {t, A, To, Tk, a}) og der i dem indgår i alt k forskellige enheder
(her har vi k=3: {s, m (afledt af \\(m^2\\)), og K}), så kan vi lave \\(p =
n-k=5-3=2\\) dimensionsløse størrelser der fortæller noget om systemet. 

At det er dimensionsløse størrelser vi er ude efter betyder altså at vi
skal have elimineret enhederne ved at gange og dividere de forskellige
fysiske størrelser med hinanden, således at enhederne går ud med
hinanden[^6].

Det første der springer i øjnene er at hvis vi skal have temperaturerne
til at gå væk, så er vi nødt til at dividere dem med hinanden, og vi får
\\[\Pi_1=\frac{Tk}{To}\\] Så går Kelvin ud med Kelvin[^7] og vi er
enhedsløse. 

Denne størrelse giver også meget god fysisk mening --- forholdet mellem
kernetemperaturen og overfladetemperaturen må på en eller anden[^8]
måde være karakteristisk for det færdigstegte stykke fjerkræ. At man
bruger \\(\Pi\\) til at angive/navngive størrelserne er bare en
konvention. Jeg holder mig af og til til dem.

Så skal vi af med resten af størrelserne i endnu et udtryk. Det er
heldigvis ikke så svært, da det hele er i de samme potenser... så vi får
altså \\[\Pi_2=\\frac{a\\cdot t}{A}\\] og her kan 10 sekunder med
papir og blyant også forvisse os om at vi er sluppet af med både
(kvadrat)meter og sekunder.

Nå, men hvad fortæller det os så?

Jo, for hvis vi vil stege kalkunen helt ligesom anden, så skal vi have
den samme temperaturfordeling, altså skal \\(\Pi_1\\) være uændret, og
så skal vi blot holde \\(\Pi_2\\) konstant for at få et udtryk for
stegetiden. 

Vi kan betragte a som en konstant, idet fjerkræ vel er fjerkræ[^9] --- i
hvert fald termodynamisk! Så kan vi se at for at holde
\\(\Pi_2\\) konstant skal vi øge stegetiden, t proportionalt med
overfladearealet, A --- eller på matematisk\\[t \\propto A\\] 
Man kunne
mene at det ikke hjælper os så meget, idet enhver der har prøvet at
bestemme overfladearealet af en and hhv. en kalkun ved at det ender med
tårer[^10], meget fedtede målebånd og notatark man kan se igennem.

Heldigvis kan vi an\[d\]tage at anden og kalkunen har cirka samme facon
og massefylde, og derfor må både overfladeareal, A og masse, m være
relateret til længden, l af dyret på samme måde, og vi kan nu udlede:
\\[m \propto l^3 \wedge A \propto l^2 \Leftrightarrow \\\ 
A \propto m^{\frac{2}{3}}\\]
hvilket vi kan indsætte i hvores
proportionalitet ovenfor og få \\[t \propto m^{\frac{2}{3}}\\] 
Godt nok kender vi ikke proportionalitetsfaktoren, men det utroligt
smukke er at man også få kan den til at gå væk, hvis man bare skal bruge
den relative tid, så kan man nemlig dividere den ene fugl med den anden
og så får man: \\[ \frac{t_{kalkun}}{t_{and}}= \left(\frac{m_{kalkun}}{m_{and}}\right)^\frac{2}{3}\\]

Vejer
kalkunen altså 5kg og standardanden, vi baserer beregningerne på, 3kg,
så skal den stege \\[ \frac{t_{kalkun}}{t_{and}}= \left(\frac{5}{3}\right)^\frac{2}{3}=1.41\\] 
gange så længe som
anden.

Således. Det var noget af en omgang, men nu tror jeg nok jeg i hvert
fald selv forstår det. Jeg håber jeg om ikke andet så har kunnet
illustrere ideen i at man kan udlede sammenhænge og proportionaliteter
uden at kende sit systems eksakte parametre. 

Hmmmm... Jeg bliver jo helt sultan... Gad vide om der er noget kold and
tilbage...

\\Worm 


------------------------------------------------------------------------

[^1]: Med mindre man vil vide om det virkelig kan betale sig at købe
    den dyre vaskemaskine der centrifugerer ekstra hurtigt, så tøjet er
    tørere, men også mere krøllet, når man tager det ud...

[^2]: Med mindre man undrer sig over at plastbøtten til paprikagryden
    er blevet gennemfarvet rød mens den lå i fryseren, og gerne vil vide
    hvor længe den har ligget...

[^3]: At husets mere handlekraftige medlemmer nok laver maden mens vi
    andre diskuterer integraler og varmekapaciteter for fjerkræ er en
    detalje... En lækker detalje, men alligevel mindre vigtig i det store
    billede... :-)

[^4]: Ja, jeg steger kalkuner i SI-enheder. Det bør du også.

[^5]: Altså ikke kalkunen - den skal helst være plukket inden den
    steges - ellers lugter den værre end brændt Worm.

[^6]: Selvom jeg er romantiker, så håber jeg ikke de forelsker sig og
    ender med at producere afkom - det er sådan noget rod - bare se på
    kemien og deres små nuttede undersyrlinger som ikke må lege med de store
    drenge...

[^7]: Al termodynamisk slash/fanfic henvises til /dev/null

[^8]: Ja, vi skal jo ikke helt glemme anden, selvom vi regner på
    kalkuner.

[^9]: Jaja, det er måske en overforsimpling, men vi antager en meget
    fed kalkun!

[^10]: Og vi vil jo netop gerne undgå saltvands"marinaden"...
