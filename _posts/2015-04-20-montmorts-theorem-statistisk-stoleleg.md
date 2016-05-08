---
layout: post
title: 'Montmort’s Theorem: Statistisk stoleleg'
date: '2015-04-20T21:40:00.001+02:00'
author: Martin Worm-Leonhard
tags:
- Modellering
- Monte Carlo
- Hovedbrud
- Tilfældighed
- R
modified_time: '2015-04-20T21:40:07.268+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-4290683674752097849
blogger_orig_url: http://labnoter.blogspot.com/2015/04/montmorts-theorem-statistisk-stoleleg.html
---

For nogen tid siden faldt jeg over [denne
side](http://www.futilitycloset.com/2014/10/28/montmorts-theorem/), der
stiller følgende drilleopgave:
(Lad være med at trykke på linket, hvis du selv vil pusle med den)

Hvis nu n studerende, der sidder på n forskellige pladser i et lokale
alle sammen rejser sig op (fx for at holde pause, hente kaffe eller hvad
de nu gør, sådanne væsener) og når de så kommer tilbage i lokalet sætter
sig på en helt tilfældig plads.

Hvad er så sandsynligheden for at mindst én person sidder på sin
oprindelige plads? Hvad sker der med sandsynligheden efterhånden som n
stiger?

Intuitivt virker det som om det skal blive meget mindre sandsynligt,
efterhånden som n stiger.

Det er jo ret hurtigt at se at hvis n=1, så er sandsynligheden 100% -
der er kun den samme person, og den samme plads.
Hvis n=2, så sidder de enten begge på deres pladser eller ingen af dem
gør. nu er sandsynligheden altså kun 50%.
For n=3 sker der dog allerede noget sjovt... sandsynligheden stiger
pludselig til 66.7% (2/3), da kun 2 ud af 6 mulige kombinationer af
bagdele og stolesæder medfører at alle får nye pladser.

Hmmm... Der må være noget [los](http://da.wikipedia.org/wiki/Los)... Men
hvad? 

Lad os alle regne!

Finten er i kravet "mindst én skal have sin oprindelige plads" --- havde
det været "kun én" eller "ingen", så havde det været væsentlig lettere
at regne på, men som det står nu, så skal der gribes dybt i kassen med
matematik. Altså den rigtige slags, med bogstaver. Ikke bare almindelig
regning. Det er jeg jo ikke meget for[^1], så jeg valgte snydeløsningen
og simulerede det i stedet.

Det bliver jo hurtigt dyrt i kaffe, hvis man skal have n studerende til
at vade rundt på gangene en million gange, så jeg greb fat i noget
R-kode. Ikke verdens hurtigste løsning, men i det mindste kunne den køre
mens jeg sov.

Jeg tog altså og lod antallet af studerende, n, variere fra 1 til 50, og
for hvert antal lod jeg dem holde pause 10.000.000 gange. Dette er
(også) et eksempel på *Monte Carlo simulering* som jeg har [skrevet om
før]({%post_url 2015-02-12-monte-carlo-simulationer-med-pi-pa %}) 

Herefter undersøgte jeg hvor stor en andel af de forskellige kørsler der
resulterede i at mindst én studerende ramte sin egen plads.

Det kom til at se således ud:

[![]({{site.url}}/images/-TB6ljbb8Paw/VTVSFPss04I/AAAAAAAAC0I/RbDMXCICoI0/s1600/montmort.mc.1e7.png)]({{site.url}}/images/-TB6ljbb8Paw/VTVSFPss04I/AAAAAAAAC0I/RbDMXCICoI0/s1600/montmort.mc.1e7.png)

Jeg har zoomet ret kraftigt på y-aksen, så de første 4 punkter ligger
udenfor grafen, men da jeg har opskrevet de første tre ovenfor, så går
det nok.

Det vi ser her er et typisk resultat fra en Monte Carlo simulering der
konvergerer mod en bestemt værdi, men alligevel hopper lidt rundt om
den, fordi usikkerheden på de sølle 10 millioner kørsler er større end
forskellen fra målværdien.[^3].

Det viser sig ud fra ovenstående at lige så snart \\(n \approx 6\\), så
udvikler den sig ikke længere, men stort set er lig med den spøjse
konstant \\(\frac{1}{e}\\).

For at se hvordan det kan være er det desværre ikke nok at løse den
numerisk/simuleret --- her er man nødt til at være analytisk, men da det
involverer fæle begreber som
[derangements](http://en.wikipedia.org/wiki/Derangement), og kræver at
man kan folde en rekursiv formel om til en
~~sommerhat~~ rækkeudvilking/sumform, så vil jeg lade den ligge indtil
jeg finder et større stykke papir  --- og/eller en venlig l\[æø\]ser
sender den til mig.[^4]

Jeg synes bare at resultatet var så sjovt at jeg måtte a) teste og b)
dele det.

Så der har vi det altså --- i både en lille forsamling, en
gennemsnitsklasse og et helt førsteårshold er der ca. 63.2% chance for
at mindst én studerende sidder på sin egen plads igen, hvis de alle
rejser sig og fordeler sig tilfældigt.

\\Worm --- der føler sig lidt permuteret.

------------------------------------------------------------------------

[^1]: I hvert fald ikke når den skal være stringent. Kombinatorik er
    åbenbart svært! [^2]

[^2]: Anekdotisk i hvert fald svært inden kaffe og tocifrede
    tidspunkter.

[^3]: Ja, man skal bruge RIGTIG MANGE kørsler, hvis man skal være meget
    præcis.

[^4]: Jeg tilbyder intet andet honoar end at blive udøddeliggjort i
    disse annaler.
