---
comments:true
layout: post
title: Lys, lygter og afstande
date: '2013-09-24T22:17:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Optik
- Mobiltelefon
- Køkkenfysik
- Lys
- Anna-og-lotte
modified_time: '2013-09-24T22:20:50.020+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-1002775886365174032
blogger_orig_url: http://labnoter.blogspot.com/2013/09/lys-lygter-og-afstande.html
---

Indledning
----------

Ganske som [med magnetisk
feltstyrke](http://labnoter.blogspot.dk/2013/05/magnetfeltstyrkemaling-med-mobiltelefon.html) så
må der jo være en lovmæssighed for hvordan intensiteten af almindeligt
synligt lys varierer med afstanden fra kilden --- det kan godt være at man
kan se et lejrbål på lang afstand, men man skal ikke mange skridt væk
fra det før det ikke lyser omgivelserne væsentligt op længere. Er det
muligt at udlede og/eller bekræfte denne, alene ved hjælp af sin
mobiltelefon?

Som jeg tidligere har været inde på, er en moderne smartphone et
sandt overflødighedshorn af sensorer, herunder en lysstyrkesensor, som
den bruger til at justere baggrundsbelysningen af skærmen efter
omgivelserne, så man ikke bliver blændet, hvis man bruger den i et mørkt
lokale, men stadig kan se (sådan nogenlunde) hvad der er på skærmen selv
i skarpt sollys.

Jeg lokaliserede lyssensoren på min Nexus 4 ved at scanne hen over
overfladen med en lille lommelygte, mens jeg så på udslaget i appen
"[Sensors](https://play.google.com/store/apps/details?id=aizen.sensors)"
og kunne derved konstatere at den sad i øverste venstre hjørne. Jeg
brugte samme app til dataopsamling.

Teori
-----

Hvis vi betragter en (tilnærmet) punktlyskilde, så som en nøgen pære
eller en lysende flamme, så spreder lyset sig i en jævn kugle ud fra
kilden, og derfor må lysintensiteten altså være omvendt proportional med
overfladearealet på denne kugle, idet der hele tiden er "den samme
mængde lys" til rådighed, men et stadigt større areal at sprede det
over.

Arealet af en kugleoverflade tyder på at noget skal i anden potens, men
lad os nu bare lave nogle data, og se hvad vi får.

Opstilling
----------

[![]({{site.url}}/images/-coo3VYhTP9E/UkHqF9MVGxI/AAAAAAAAB00/VVQq9Fs-qz0/s400/IMG_0005.JPG)]({{site.url}}/images/-coo3VYhTP9E/UkHqF9MVGxI/AAAAAAAAB00/VVQq9Fs-qz0/s1600/IMG_0005.JPG)

Ja, det behøver ikke være så svært --- et tilnærmelsesvist mørklagt køkken
(jaja, billedet er taget med blitz), en lettere kannibaliseret
lommelygte, et whiskyglas (t\[øo\]mt, naturligvis) som mobilholder, en
lineal og et stykke notepapir var såmænd alt hvad det krævede. 

Man kunne
sikkert også have brugt et stearinlys, men jeg valgte
glødepæreløsningen, da den er en smule mere stabil, om end knap så
hyggelig. Jeg noterede nu den modtagne lysstyrke på mobilens sensor for
7 mere eller mindre arbitrære afstande mellem 5 cm og 30 cm, og fik
følgende datasæt.

Data
----

  ---------------|-------------------
  Afstand \[cm\] | Lysstyrke \[lux\]
  :-------------:|:-----------------:
  8              | 118
  11             | 59
  14             | 37
  17             | 28
  20             | 20
  25             | 11
  30             | 8
  ---------------|-------------------

Databehandling
--------------

Her har jeg blot anvendt MS Excel til at lave plottet og indlægge en
tendenslinie baseret på en potensfunktion, da jeg allerede havde en god
idé om at det ville være en sådan der bedst beskrev data, men
naturligvis bør og kan man gennemgå hele det sædvanlige eksplorative
cirkus med at plotte data mod hinanden på inverse, logaritmiske og andre
sjove akser, hvis man vil forvisse sig om at jeg har ret.


Men ikke desto mindre får man et Ret Pænt Resultat, selv med en sådan
mængde videnskabelig uredelighed:

[![]({{site.url}}/images/-IoP9SblnQuk/UkHuijurLnI/AAAAAAAAB1A/eRGYKfLppDU/s400/glodelampe.png)]({{site.url}}/images/-IoP9SblnQuk/UkHuijurLnI/AAAAAAAAB1A/eRGYKfLppDU/s1600/glodelampe.png)

Så min forudsigelse om "noget med anden potens" ser jo ud til at holde ---
lysstyrken aftager nydeligt med afstanden i (cirka) anden potens, og det
giver jo også mening, ud fra ovenstående argument om at lyset fordeles
jævnt på en kugleskal.

Arealet af en kugleskal er jo som bekendt
\\(4\pi r^2\\), og stiger altså med radius i anden potens. Når vi så
skal fordele lyset jævnt på dette areal, og ihukommer at enheden for
lysstyrke (lux) netop er et mål for mængden af lysenergi pr arealenhed,
så går det hele op i en højere enhed.

Konklusion
----------

Det er muligt, med en forholdsvist simpel opstilling under ret primitive
forhold og lyssensoren fra en mobiltelefon at eftervise at  intensiteten
af lys fra en punktkilde aftager med kvadratet på afstanden.

Outro
-----

Måleenheder for lys er lidt af en jungle, selv når man bruger
SI-enheder. Vær opmærksom på hvad du egentlig måler. Lux som funktion af
meter bør være sikker.

Husk at det ovenstående kun gælder for homogene punktlyskilder.
Eksperimentér eventuelt selv med lysdioder, stearinlys, lommelygter,
lasere (pas på øjne og sensorer!) og andre mere eller mindre
retningsbestemte lyskilder. Betyder farven af lyset noget?

Jeg forsøgte selv med en diodelygte med reflektor og fik et acceptabelt
fit med en potens på ca. -1,3. Kan man mon udlede noget fornuftigt af
dette tal omkring form og/eller effektivitet af reflektoren?

Som altid modtager jeg gerne spørgsmål, kommentarer og data --- og
udleverer også gerne mine.

\\Worm
