---
comments: true
layout: post
title: Præcision, nøjagtighed, afrunding og tilnærmelser
date: '2014-01-07T21:19:00.001+01:00'
author: Martin Worm-Leonhard
tags:
- Usikkerhed
- Skæg med tal
modified_time: '2014-01-07T21:22:40.781+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-4992074823826065854
blogger_orig_url: http://labnoter.blogspot.com/2014/01/prcision-njagtighed-afrunding-og.html
---

Ifølge [Den Danske Ordbog](http://ordnet.dk/ddo) er "præcision" og
"nøjagtighed" synonymer. Jeg, og de fleste andre udøvere af
eksperimentelle fag, har en tendens til at være uenige. For os er
"præcision" (eller repeterbarhed) et mål for hvor ens resultatet af
gentagne målinger er, hvoimod "nøjagtighed" (eller sandhed/trueness) er
et mål for hvor tæt man ligger på "den sande værdi"[^1]. 

Det er således
muligt at have en metode der er meget nøjagtig, uden at være specielt
præcis --- så er man bare nød til at tage gennemsnittet af en masse
målinger, for at være sikker på at man ikke rammer ved siden af ved et
tilfælde, og hvis man er præcis uden at være nøjagtig, så kan man få det
samme (forkerte) resultat hver gang.

Der er mange flere aspekter af dette og hvis man begynder at blande
forskellige standarder ind i det, så kan man nærmest drukne, bare i
terminologien.

Men det var et sidespor --- i virkeligheden ville jeg jo skrive lidt om
hvorfor jeg synes det i langt de fleste tilfælde er helt acceptabelt at
måle usikkerheder i træskolængder.

Lad os starte med en velkendt størrelse og tilnærmelse: \\( \pi \\)  
Pi har uendeligt mange decimaler, og der går endda i forskellige nørdede
kredse sport i at kunne recitere så mange som muligt af disse. De fleste
vil kunne huske at pi er tre-komma-noget, måske endda 3.14. 

Hvis man
spørger google siger de at \\(\pi=3.14159265359 \\) --- jeg kan en
remse[^2] der tillader mig at udvide det til  3.14159265358979. 

Dengang jeg gik i skole[^3] lærte vi at en god tilnærmelse til \\(\pi\\) var
\\(\frac{22}{7} = 3.14285714286\\), om end jeg har dem mistænkt for at
det blot var for at smugle brøkregning ind af bagdøren. 

Vores (nørd)instinkt siger os at to decimaler på sådan et lille tal ikke er
specielt nøjagtigt, og at en tilnærmelse som 22/7 der afviger allerede
på tredje decimal ikke er meget værd, men hvor meget betyder det
egentlig?

Starter vi med afrundingen 3.14 ved vi at den tredje decimal ligger i
intervallet (-)5--4 (ellers havde afrundingen jo været 3.13 eller 3.15),
så den maksimale fejl vi kan begå ved at bruge denne tilnærmelse (hvis
vi leger at vi ikke kender den sande værdi af pi) er
\\(\frac{0.005}{3.14}=0.00159=0.16\%\\) eller 1.6 meter pr. kilometer,
for nu at bruge afstande som eksempel. Det er faktisk helt acceptabelt i
langt de fleste tilfælde.

Sammenligner man med den sande værdi af pi bliver det faktisk bedre:
\\(\frac{3.14}{\pi}=0.99949\\), altså en fejl på 0.051%, eller 51 cm
pr kilometer.

Anvender man 22/7 som eksakt brøk bliver det lidt bedre:
\\(\frac{\frac{22}{7}}{\pi}=1.00040\\) --- 40 cm per kilometer, men i
begge tilfælde skal man huske 3 cifre, og med 3.14 slipper man for
brøkregning, så det må jo næsten være en smagssag.

Bevares --- i nogle tilfælde har man brug for større nøjagtigheder - hvis
man skal ramme en dværgloppesøns butterfly, for nu at citere en musical,
eller mere realistisk set måle afstanden til en håndfuld satellitter ved
hjælp af radiosignaler og kendskab til lysets hastighed, hvorefter man
vil forsøge triangulere sig frem til længde- og breddegrad, samt højden
over havet. 

Det lyder kompliceret, og det er det såmænd også[^4], men
ikke mere end at vi (næsten) alle har en dims der kan det, enten i
lommen eller i vores bil --- nemlig en GPS-modtager. Disse kan endda også
lave ruteplanlægning, men det er en ridetur på en helt anden kamel. Hvis
man skal triangulere ud fra nogle signaler fra geostationært kredsløb,
cirka 36000 km ude i rummet, så bliver en usikkerhed på "en meter per
kilometer" meget hurtigt noget rod, der kan ende med at man kører i
vandet, eller får uventede gæster.

Men hvornår er det så overkill at vælte sig i decimaler? Ja, for det
meste, vil jeg påstår, men bemærk at jeg i det følgende taler om antal
betydende cifre, snarere end decimaler --- det hænder jo at man har brug
for både meget store og meget små tal --- og antal betydende cifre er så
hvor mange af disse cifre der ikke er et foranstillet nul, eller et nul
der alene angiver størrelsesorden. 3.14 har således 3 betydende cifre,
hvorimod 0.00001 kun har ét, og opgives lyshastigheden i vakuum
som 299792458 m/s er det altså med 9 betydende cifre.

Der er nogle faldgruber --- man kunne fristes til at tro at med kun ét
betydende ciffer er den maksimale fejl man man begå på 100% - i det
tilfælde hvor man afrunder en sand værdi på 0.5 til 1 --- men 0.5 har jo
også kun ét betydende ciffer, så lad os se på 5 i stedet --- det ligger
lunt i midten af encifrede tal og kan være en afrunding af intervallet
\[4.5;5.5\[[^5] --- altså en maksimal fejl på 10%.

Med to betydende cifre får vi med samme fremgangsmåde en typisk maksfejl
på 1%, og med 3 betydende cifre en promille --- i det generelle tilfælde
ses altså en (omtrentlig) relativ fejl på \\(1:10^x\\) hvor x er
antallet af betydende cifre.

Nu kan man hurtigt estimere hvor mange betydende cifre det giver mening
at have i sine beregninger --- hvis man er GPS-system-designer og gerne
vil have en usikkerhed på ca 10 meter i forhold til de 36000 km der er
til geostationært kredsløb, så ser man på brøken
\\(\frac{10m}{36\cdot10^6m}=2,8\cdot10^{-7}\\) --- altså vil det være
en god ide at udføre sine beregninger med flere end 7 betydende cifre.

I langt de fleste dagligdags tilfælde vil et slutresultat med 3
betydende cifre være langt rigeligt, og ofte endda overkill --- det er de
færreste mennesker der kan (be)mærke en usikkerhed på en millimeter per
meter, eller en meter per kilometer, så kunsten er --- som altid --- at vide
hvornår det kan betale sig med den ekstra indsats.

Ja, jeg ved det godt --- det er --- og blev --- lidt noget rod at forsøge at
forklare om usikkerhed og unøjagtighed i generelle tilfælde og
vendigner, men jeg håber at de ovenstående refleksioner og eksempler kan
være med til at spare dig for unødigt arbejde, overdreven nidkærhed og
usikkerhed om størrelsen af din usikkerhed[^6].

\\Worm --- pernittengryn

------------------------------------------------------------------------

[^1]: Desværre ofte en mytisk størrelse i den virkelige virkelighed,
    men man kan jo snyde og lave sine prøver selv, når man vil undersøge
    hvor præcis hhv. nøjagtig en given metode er.

[^2]: En af de ting jeg så én gang og som derefter nægter at flytte ud
    af mit hoved, måske fordi den er så let at identificere sig med: "How I
    need a drink, alcoholic of course, after the heavy chapters involving
    quantum mechanics"

[^3]: Før smartphones, ja faktisk før GSM-mobiltelefoner og dengang
    hvor lommeregnere kunne afhentes i klassesæt på viceinspektørens kontor
    når de større klasser skulle lave særligt udfordrende regning. Ak ja,
    nostalgi er ikke hvad det har været.

[^4]: Faktisk er man nødt til at kompensere for relativistiske effekter
    for ikke at blive væk --- et faktum den USAnske hær ikke troede på til at
    starte med, så de har/havde en kontakt der kan slå det fra i deres
    modtagere.

[^5]: Jeg antager at man bruger "almindelig afrunding" som lært i
    skolen og ikke [IEEE afrunding](http://en.wikipedia.org/wiki/IEEE754#Rounding_rules).

[^6]: Meta-usikkerhed?
