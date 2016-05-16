---
comments: true
layout: post
title: Vandraketvidenskab
date: '2013-05-28T20:31:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Mobiltelefon
- Baghaveballistik
- Raketvidenskab
- Billedanalyse
modified_time: '2013-05-29T20:12:25.016+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5098052324447312618
blogger_orig_url: http://labnoter.blogspot.com/2013/05/vandraketvidenskab.html
---

Raketter er fed nørdlir! Derfor!  
Nå, jeg skal være saglig? Jamen, det er da ikke svært. "Raketvidenskab" er jo nærmet per definition synonymt med noget der er langhåret og involverer en masse matematik, fysik, ingeniørkunst og faremomenter. 
Det er jo også tilnærmelsesvis sandt. Men det behøver ikke være _så_ svært igen. 
Se bare på [Copenhagen Suborbitals](http://www.copenhagensuborbitals.com/), som utvivlsomt er
utroligt skarpe og dygtige og ved hvilken ende af en
[regnestok](http://da.wikipedia.org/wiki/Regnestok) der er den farlige,
men alligevel - eller måske netop derfor - agter at sende en bemandet
raket op inden for en overskuelig tidshorisont... og ser ud til at være
godt på vej.  
Dette indlæg er måske knap så ambitiøst, men jeg håber da alligevel at
kunne udnytte lidt af jeres raketfacination til at slippe godt fra at
snige nogle simple fysiske beregninger og betragtninger med ind i
teksten.

## Baggrund
Tilbage i 2012 var jeg med til at lave sommerskole i [UNF
odense](http://odense.unf.dk/), og en af de aktiviteter vi havde var
netop "Raketvidenskab" - det gik i al sin enkelthed ud på at undervise i
den videnskabelige metode ved at undersøge vandraketters egenskaber.

En vandraket består af en sodavandsflaske, på hvilken der er monteret et
sæt finner og en adapter / ventil. Flasken fyldes så med et kvantum
postevand og sættes under tryk med en cykelpumpe, indtil trykket skyder
proppen, og hurtigt derefter vandet, ud og raketten flyver. Simpelt og
så ufarligt som ballistiske øvelser i fuldskala med rimelighed kan
blive.

Mens vi gik og ~~legede med dimserne~~ forberedte os på undervisningen
fik vi taget en stribe ret gode billeder og videoklip, som efterfølgende
er forsøgt malket for hver eneste bit information de ville rykke ud med
uden at gribe til tortur. Gennemgående var det dog lidt problematisk at
det faktisk er svært at fotodokumentere processer der dækker afstande på
30+ meter på tidskalaen "sekunder" - især når man kun har sin
mobiltelefon at gøre det med. Ikke desto mindre er hér dokumenteret et
af de bedre resultater.


##Forsøget

En ½L Faxe Kondi i blød plastflaske tømmes (gerne ned i en frivillig) og
et [Rokit](http://eu.rokit.com/)-kit monteres på flasken.   
Flasken fyldes med 1½-2dL postevand og lægges ned, så den forventede affyringsvinkel er
omtrent 30 grader over vandret. Vi benyttede her et praktisk anbragt hul
i plænen. Der pumpes luft i med en cykelpumpe indtil raketten går af. Så
vidt jeg husker sker det gerne ved omkring 5-7 atmosfæres tryk i
flasken. Affyringen videodokumenteres på god afstand med en mobiltelefon
(Nexus S).


##Resultater (Rådata)
[![]({{site.url}}/images/7ba1a8b84a2e098f71c99fd97e19ccc6.gif)]({{site.url}}/images/4b49b7d90e19199a056dde20564d0d82.gif)  
Ja, det er en animeret gif. Ja, jeg har opdaget det er 2013. If it ain't broken...

Som det lige akkurat ses på ovenstående animation var det muligt at følge raketten i 15 frames - cirka et halvt sekund i realtid, og opløsningen er ikke noget at råbe hurra for. Men nu er vi jo heldigvis videnskabsfolk, og derfor ikke bange for at måle på noget der ser grimt ud.

##Databehandling
Den oprindelige video i mp4-format blev gennemset med [VLC media
player](http://www.videolan.org/index.html) og de 15 frames der
indeholdt rakettens synlige flugt blev eksporteret som png-filer. Disse
blev efterfølgende samlet i GIMP, til ét billede der indeholdt alle 15
positioner af raketten. Dette kompositbillede blev derefter opmålt i
[ImageJ](http://rsbweb.nih.gov/ij/) og pixel-koordinaterne for rakettens
bagkant eksporteret til en tekstfil, der dannede grundlaget for et
regneark - min egen kopi er i MS Excel, men en Google Docs klon er
linket til nedenfor.  
Det samlede billede med markører ser således ud:  

[![]({{site.url}}/images/8445ecfb0aa98fcb3a04e5d7a552d87e.png)]({{site.url}}/images/0dbd270a3aa79733e8ac5f7b21a9647b.png)


Hvis du har lyst til at lege med tallene selv, så er som de som lovet i
[regnearket hér](https://docs.google.com/spreadsheet/ccc?key=0AlW7mckOGZhSdG1DbFptU1drVjhCOXUtWXdOTjJwNGc&usp=sharing).  
Beklager at du må finde dig i at det allerede er fyldt med mine
beregninger og noter, men bemærk at kun søjlerne A-D kan betragtes som
"data" - resten er afledte størrelser. X og Y koordinaterne er absolutte
i forhold til billeder og målt i pixels (px).  
Hvis vi skal have nogle meningsfyldte enheder ud af det, så må vi
konvertere det til relative positioner og konvertere til meter.
Heldigvis har vi en praktisk målestok yderst til venstre i billedet -
Dr. P står cirka på linie med rakettens flugt og er cirka på højde med
mig, så lad os sige at han er 1,90 meter høj. Han måles til 44 pixels,
så altså har vi at opløsningen på billedet er \\(0,043 \frac{m}{px}\\).

VLC siger at frameraten i den oprindelige video er 29,77 billeder per
sekund, så nu har vi også en tidsskala.

Nu er det en relativt simpel øvelse at fremstille forskellige afledte
størrelser og visualiseringer af forløbet.

##Resultater
Kasteparablen kan demonstreres ved at plotte relativ Y-position mod relativ X-position:

[![](https://docs.google.com/spreadsheet/oimg?key=0AlW7mckOGZhSdG1DbFptU1drVjhCOXUtWXdOTjJwNGc&oid=6&zx=vehjcja7dep)](https://docs.google.com/spreadsheet/oimg?key=0AlW7mckOGZhSdG1DbFptU1drVjhCOXUtWXdOTjJwNGc&oid=6&zx=vehjcja7dep)

Desværre er min google-docs-fu ikke stærk nok til at jeg kan vise en
tendenslinie, og dermed at et andengradspolynomium som forventet fitter
data bedre end en ret linie, trods den lave affyringsvinkel.

Derimod er det muligt at se en masse andre sjove ting. Hvis vi for
eksempel ser på den totale acceleration som funktion af tid får vi
følgende:


[![](https://docs.google.com/spreadsheet/oimg?key=0AlW7mckOGZhSdG1DbFptU1drVjhCOXUtWXdOTjJwNGc&oid=8&zx=frhyhy6fke2w)](https://docs.google.com/spreadsheet/oimg?key=0AlW7mckOGZhSdG1DbFptU1drVjhCOXUtWXdOTjJwNGc&oid=8&zx=frhyhy6fke2w)

Heraf fremgår det tydeligt at raketten starter med at accelerere
voldsomt - ca. \\(400 \frac{m}{s^2}\\) svarende til omtrent 40 gange
tyngdeaccelerationen, men at accelerationen ophører i løbet af 3 frames - og allerede efter 150 milisekunder er der ikke længere nogen
nettoacceleration i flyveretningen - variationerne omkring 0 må
tilskrives vind og fotografens rysten på hånden. 

Dette er i god overensstemmelse med at al reaktionsmassen (vandet) udstødes i løbet af
meget kort tid, hvorefter resten er fri flugt.

Som et lille check af dataintegritet kan vi se på Y-komponenten af
accelerationen i fri flugt (ikke afbilledet) - denne burde være lig med
tyngdeaccelerationen \\((9,8\frac{m}{s^2})\\).

I dette tilfælde får vi en middelværdi på cirka \\(12,7\frac{m}{s^2}\\),
hvilket jo er lidt vel højt, men må skønnes indenfor rimelig
måleusikkerhed, når man tager betingelserne for forsøget og
databehandlingen i betragtning.

Endvidere viser vores data at raketten når en maksimal fart på \\(32,5\frac{m}{s^2}\\) svarende til \\(117\frac{km}{t}\\), hvilket også er imponerende, men
på ingen måde virker urimeligt.

Vi kan også ud fra den fittede parabel  (\\(y = -0,0002x^2 +0,5088\\cdot x + 0,9354\\), når x og y måles i pixels) estimere
at flyvelængden er af størrelsesordenen 100 meter, og toppunktet på
banen lå i cirka 14 meters højde hvilket også stemmer godt overens med
det faktisk observerede.

### Konklusion

Det er muligt at foretage en forholdsvist præcis opmåling af en
vandrakets flugt ud fra en videofilm af blot en del af banen, kun ved
brug af frit tilgængelig software og de opnåede resultater er i god
overensstemmelse med det forventede og observerede.[^4]

## Perspektivering og forbedringsmuligheder
Idet vi fraregner muligheden for at montere dataloggere på selve
raketten på grund af dens forholdsvist lille egenmasse må vi konstatere
følgende:

Højere billedopløsning og eventuelt højere framerate ville give mulighed
for mere præcis opmåling i både tid og rum. En mere veldefineret
målestok i helt samme plan som raketten ville give en bedre omregning
fra pixels til meter, uanset hvor meget dr. P så selv mener at han burde
være en SI-enhed.

Et bedre stativ end "Jeg læner mig lige op af denne lygtepæl" kunne nok
også højne datakvaliteten. Det må også være muligt at finde et kompromis
mellem raketbane og optageafstand der optimerer mængden af frames der
faktisk indeholder raketten.

Ikke desto mindre viser resultaterne med sikkerhed at man ikke bør lade
sig afskrække fra at analysere data, selvom de kunne være bedre.

Herudover er der jo rig mulighed for at analysere de opnåede data i
lyset af Newtons tredje, bruge raketligningen, optimere på vandindholdet
og trykniveauet, ja, når først infrastrukturen til telemetri er på
plads, så bliver det bare  endnu sjovere at lege med raketter!  
Affyr varsomt, men ofte og gerne!

## Interessekonflikter?
Dette indlæg er på ingen måde sponsoreret af
[Rokit](http://eu.rokit.com/), men jeg anbefaler dem varmt alligevel.
Jeg er heller ikke på nogen måde tilknyttet Copenhagen Suborbitals, men
ønsker dem alt godt med deres projekt. Jeg er i høj grad syltet ind i
UNF Odense.

\\Worm

[^4]:Okok, jeg ved godt jeg brugte Excel, men eksempelvis Open Office burde kunne gøre nøjagtigt det samme uden at nogen behøver svede. 
