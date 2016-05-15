---
comments:true
layout: post
title: '06 DEC: Sorte legemer og stearinlys'
date: '2014-12-06T10:00:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Julenørd
- Lys
modified_time: '2014-12-06T10:00:04.269+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-3805513231208968517
blogger_orig_url: http://labnoter.blogspot.com/2014/12/06-dec-sorte-legemer-og-stearinlys.html
---

"Der er netop nu ekstra lang ventetid på Pladderballe skadestue, idet
der er sket det uheldige at adskillige børn her i adventstiden har fået
julelys i øjnene..." --- som Monrad og Rislund på karakteristisk vis
oplyste om i en af deres mange radioaviser.

Selvom det naturligvis er dybt politisk ukorrekt og energimæssigt
ineffektivt at oplyse sit domicil med fossile brændsler i form af
stearinlys (der for det meste i virkeligheden er paraffin, men det er et
stykke kemisk *coitus dipterae*), så varmer og hygger det jo alt sammen,
men hvorfor har stearinlys sådan en dejlig varm glød? Jo det har noget
at gøre med glødende kul...

Ser man på en typisk stearinlysflamme, så er den lyssvag i midten og
kraftigt lysende i kanten, og det skyldes primært flammedynamiske og
fluidmekaniske effekter --- at der ikke kan nå at komme helt så meget ilt
fra luften ind i midten, hvorfor denne zone bliver let reducerende og
brændstoffet (fordampet stearin/paraffin) ikke reagerer fuldstændigt med
ilt. Dette skaber en masse fine sodpartikler, der derefter reagerer
kraftigt, når de kommer ud i den friske luft lidt længere fra vægen, og
så ser vi den karakteristiske gule flammefarve.
Men hvorfor brænder både tændstikker, stearinlys og de fleste andre
organiske stoffer med den samme gule farve?

Dette skyldes at det vi ser som en homogen flamme i virkeligheden er en
sky af glødende kulpartikler, og hvis man gerne vil vide hvor varmt der
i virkeligheden er inde i sådan en stearinlysflamme, men ikke lige har
et termometer i industristørrelse, så er der heldigvis nogle kloge
mennesker der har regnet på det for os.

Det viser sig nemlig at man kan beregne hvilken intensitet og frekvens
af elektromagnetisk stråling der udsendes fra et sort legeme[^1] som
funktion af dets temperatur --- eller på almindeligt dansk: Hvor varmt
noget skal være for at være rødglødende.[^2]

Dengang jeg stadig havde fysik gik det under navnet "[Wiens
forskydningslov](http://en.wikipedia.org/wiki/Wien_approximation)" og
Tante Wiki har lige genopfrisket min hukommelse og fortalt mig at den
siger at \\[\lambda_{max}=\frac{2.9\cdot 10^{-3}m \cdot K}{T}\\]
Altså at den mest intense bølgelængde der udsendes af et varmt sort
legeme er omvendt proportional med temperaturen i kelvin. Dette giver jo
god mening --- jo varmere noget bliver, desto mere bevæger det sig op af
spektret fra infrarød over rød og gul, indtil det bliver hvidligt.

Man kan måske undre sig over at det ikke bliver grønt, blåt og violet i
stedet for bare hvidt, men det skyldes at samtidig med at bølgelængden
med maksimal intensitet flytter sig nedaf i bølgelængde mod den blå ende
kommer der gradvist også mere af alle de andre bølgelængder, idet den
totale intensitet stiger med temperaturen i fjerde potens[^3], hvilket
kaldes "[Stefan-Boltzmanns
lov](http://en.wikipedia.org/wiki/Stefan%E2%80%93Boltzmann_law)" indtil
vi ser så blandet et spektrum at det fremstår som hvidt lys.

Ovenstående er i øvrigt også årsagen til at man taler om at en lampe kan
have en "farvetemperatur" --- altså hvilken temperatur et sort legeme skal
have for at udsende lys svarende til lampen man taler om.

Nå, men det var udenomssnak --- hvad var det nu med stearinlys? Vi ville
gerne vide hvor varme de var, og kan se på dem at de udsender gult lys,
hvilket vel vil sige at det har en bølgelængde på cirka 580nm. Lidt
fingergymnastik på formlen ovenfor giver os så at  
\\[T=\frac{2.9\cdot 10^{-3}m \cdot K}{\lambda_{max}}=\frac{2.9\cdot 10^{-3}m \cdot K}{580\cdot 10^{-9}m}=5000K\\]

Øhhh.... hvad?

Jeg skal gerne indrømme ikke at være nogen stor kapacitet på området
stearinlys, men at de skulle være næsten lige så varme som solen, det
tror jeg alligevel ikke på... Hvad sker der her?

Jo, det skyldes såmænd førnævnte effekt --- at et varmt sort legeme ikke
kun udsender stråling med én bestemt bølgelængde, men at det er en
såkaldt kontinuumskilde --- den udsender en masse forskellige bølgelængder
samtidig, og Wiens forskydningslov fortæller os kun hvor toppen af
spektret ligger.

Hvis jeg skal slippe godt fra dette uden at skulle ud i en hel masse
grim (men spændende) fysik, matematik og simulering, så kan jeg
heldigvis hugge denne her fra [Tante Wiki](https://commons.wikimedia.org/wiki/File:Black_body.svg#/media/File:Black_body.svg):
[![]({{site.url}}/images/-2djCYcl9Si8/VHzeY27bwrI/AAAAAAAACig/lq3QpgjxsQM/s1600/600px-Black_body.svg.png)]({{site.url}}/images/-2djCYcl9Si8/VHzeY27bwrI/AAAAAAAACig/lq3QpgjxsQM/s1600/600px-Black_body.svg.png)

Her kan man se at selv når temperaturen er ret lav, så har fordelingen
af udsendt stråling stadig en "hale" ind i det rød/gule område, selvom
langt størstedelen af strålingen udsendes i det infrarøde område.

Faktisk er selv de ret ydmyge ca. 1000K som en stearinlysflamme er i
virkeligheden nok til at lyse gult med et rødligt skær, simpelthen fordi
det er den eneste del af den udsendte energi som vi kan se med øjnene.
Resten kan vi mærke som infrarød stråling (varme).

Her har vi jo så også forklaringen på at stearinlys er ret ineffektive
som lyskilde i forhold til den afbrændte mængde energi --- til gengæld
varmer de godt, og det er jo rart her i den kolde tid.

\\Worm --- lysnisse

------------------------------------------------------------------------

[^1]: En af disse fysiske abstraktioner, på linie med kugleformede,
    friktionsfrie elefanter i vakuum, men når det kommer til små
    sodpartikler så er "sort legeme" jo nok i virkeligheden en okay
    beskrivelse...

[^2]: Ca 650 grader celcius plus/minus en træsko, hvis jeg husker
    rigtigt, men det er jo ikke det vi diskuterer.

[^3]: Hvilket bl.a kan bruges til at vise at himlen er varmere end
    helvede, men det er et andet indlæg, som jeg forhåbentlig får tid til at
    skrive meget snart...
