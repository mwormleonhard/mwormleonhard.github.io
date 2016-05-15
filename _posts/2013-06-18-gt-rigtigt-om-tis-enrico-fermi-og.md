---
comments: true
layout: post
title: Gæt rigtigt! - om tis, Enrico Fermi og bagsiden af en kuvert
date: '2013-06-18T19:48:00.001+02:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Fermi
- Skæg med tal
modified_time: '2013-06-18T19:48:53.058+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5797720121335946360
blogger_orig_url: http://labnoter.blogspot.com/2013/06/gt-rigtigt-om-tis-enrico-fermi-og.html
---

Hvis du nogensinde har prøvet at besvare "mærkelige" spørgsmål, så som
"Hvor mange træer bruges mon til at udgive Jyllandsposten på årsbasis",
"Gad vide hvor meget altervin der drikkes årligt i den danske
folkekirke", eller "Hvor mange popkorn kan der mon være i en
swimmingpool?" (ud over ved hjælp af google) så håber jeg ikke du har
givet op ved udsigten til at skulle finde (på) en masse tal som
tilsyneladende er næsten umulige at kontrollere eller vurdere. Det er
faktisk ikke så svært endda, men først et lille sidespor:

Estimater af den art kaldes Fermiberegninger eller Fermiopgaver, og er
opkaldt efter Enrico Fermi, der efter sigende var særligt ferm(i) til
netop at estimere størrelsesordener for alt muligt og umuligt.

Historien siger at han ved den første A-bombesprængning stod og ventede
på at trykbølgen rejste de par kilometer der nu var ud til
observationsposten hvorefter han helt roligt rev et stykke papir af sin
notesblok og lod det blive taget af vinden/trykfronten og så hvor det
landede, hvorefter han skriblede lidt på sin blok og sagde "cirka 10
kilotons". Den er muligvis apokryf, men det er stadig en god historie,
og den er på ingen måde usandsynlig.

Man kan nemlig komme meget langt i den slags beregninger ved bare at
ramme den rigtige størrelsesorden for hvert enkelt gæt --- og med
"størrelsesorden" mener jeg egentlig bare "antallet af nuller".
Hvis man er rigtig ambitiøs, kan man også prøve at få det første ciffer
rigtigt, men der er faktisk ikke engang nødvendigt, hvis man bare vil
have en idé om hvor stort resultatet er. 

Det føles indledningsvis meget
forkert at lave så grove overslag, men det er faktisk muligt at vise at
fejlen i gennemsnit bliver relativt meget mindre end forventet. Jeg skal
spare dig for at fægte med logaritmer, men blot konstatere at hvis det
er lige sandsynligt at man gætter for højt eller lavt, så vil de fejl
man indfører ved at estimere så groft mere eller mindre ophæve hinanden,
og næsten enhver rimelig serie af estimater vil ende indenfor en
størrelsesorden (faktor 10) af det korrekte resultat.

Inden det bliver alt for abstrakt så er det nok lettest at demonstrere
metoden ved at gennemgå et eksempel eller 2...


## Eksempel 1: Træer og Jyllandsposten

_Spørgsmål: "Hvor mange træer går der på årsbasis til at udgive
Jyllandsposten?"_

Vi lader nu som om vi kun har bagsiden af en kuvert og en sløv blyant,
og er nødt til at gøre nogle antagelser, for at kunne nå svaret.

Oplag: Jyllandsposten er en ret stor avis, så oplaget er jo nok 100.000
om dagen. 10.000 virker for lavt, og 1.000.000 virker for stort. Bemærk
igen at vi alene er interesseret i antallet af nuller --- vi regner med at
resten jævner sig ud efterhånden.

Vægt: I snit vejer et eksemplar vel 1kg. 100g er for lidt og ikke engang
Tante Berlinger vejer 10kg på en søndag med ekstra boligtillæg fra
Frederiksberg.

Der er 400 dage på et år. Her kan ikke engang jeg få mig til at tilnærme
med hverken 100 eller 1000 --- det føles ALT for forkert, men ok, hvis det
er det eneste betydende ciffer der ikke er 1 så går det jo også nok.

Nu har vi altså et godt gæt på hvor meget papir JP bruger på et år:
$$ 100.000 \frac{aviser}{dag} \cdot 1\frac{kg}{avis} \cdot
400~dage = 40.000.000~kg = 40.000~ton~papir$$

Et almindeligt stort træ som kan bruges til papirfremstilling vejer jo
nok omkring et ton --- igen: 100 kg er for lidt, 10 ton er for meget. 

Der kommer jo nok cirka et ton papir ud af et ton træ. Igen er både
omsætningsforhold på 1:10 og 10:1 "for forkerte", og vi er stadig kun
interesseret i antal nuller...

Ergo går der på årsbasis 40.000 træer til at udgive Jyllandsposten.

Jeg kunne i sagens natur ikke lige umiddelbart finde en kilde der kunne
be- eller afkræfte min udledning,
men [her](http://viden.jp.dk/mediarium/journalistik/default.asp?cid=134373) står
der at "Jyllandsposten bruger på årsbasis mere end 20.000 tons papir",
så vores estimater er med så rigelig sikkerhedsmargin indenfor den
faktor 10 som vi stræbte efter. QED. :-)

Drop endelig en kommentar, hvis du har bedre eller andre tal!

--------------------------------

## Eksempel 2: Tis

I forbindelse med en diskussion om rensningsanlæg og forurening dukkede
spørgsmålet _"Hvor meget tisser Odenses indbyggere på et år?"_ op.  

Her er det naturligvis muligt at finde nogle ret eksakte tal at regne ud fra,
men i stedet for at være kedelige og bare besvare spørgsmålet, så lad os
benytte lejligheden til at se hvor god metoden er. Jeg antager at I nu
selv kan se på tallene og foretage vurderingerne "10 gange så meget er
meget for meget" (ja, den sætning er knudret med overlæg) og  "en
tiendedel er meget for lidt".

- En person tisser en liter i døgnet. 
- Der er 100.000 indbyggere i Odense.
- Der er 400 dage på et år.

Dette giver nu ...regne regne... 40 millioner liter tis på et år. 

Hvis vi bruger de eksakte tal:

- [Urinvolumen](http://en.wikipedia.org/wiki/Fluid_balance): 1½L per døgn
- Indbyggertal, [Odense](http://en.wikipedia.org/wiki/Odense): 170.327. 
- Dage på et år: 365,24

Så får vi: 93.315.350 L urin per år.

Her ramte vi altså lige lidt mere end en faktor 2 ved siden af --- stadig
en glimrende resultat, med hensyn til størrelsesorden, og taget i
betragtning at vores indledende gæt alene er baseret på sund fornuft.


## Outro
Jeg håber I nu er blevet mindre bange for at gætte på og beregne en
"umulig" størrelse. I nørdet lag kan der jo ligefrem gå sport i at finde
det bedste estimat af en given størrelse --- gennem tiden har jeg været
med til at beregne, blandt meget andet:

-   Hvor mange poppede popkorn der kunne være i et stort lokale (ca
    63 mio.)
-   Hvor meget altervin folkekirken udskænker årligt (ca. \\(21m^3\\))
-   Hvor mange af atomerne i mig der engang har siddet i Harald Blåtand
    (ca \\(10^9\\))
-   Hvor meget jern hele verdens befolkning indeholder (ca 30.000 tons ---
    svarende til et lille hangarskib)

Til festligt og/eller øllet lag kan jeg anbefale at bruge papirdug og
udlevere skriveredskaber der ikke laver mærker i bordet --- det er en ofte
brugt fremgangsmåde i flere af de fora jeg hjemsøger :-)

Hvis du selv har fået lyst til at regne på mystiske og sjove ting, så
rigtig god fornøjelse! Kast endelig en kommentar i min retning, hvis du
har et sjovt resultat eller en sær opgave.

Hvis du hellere vil fortsætte med at dyrke Fermiberegninger og sære
størrelser som en tilskuersport så anbefaler
jeg: <http://what-if.xkcd.com/>.
