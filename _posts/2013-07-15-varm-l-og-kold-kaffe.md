---
comments: true
layout: post
title: Varm øl og kold kaffe
date: '2013-07-15T20:16:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Varmelære
- Modellering
- Kaffe
- Køkkenfysik
modified_time: '2013-07-15T20:16:06.863+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5336626189325687774
blogger_orig_url: http://labnoter.blogspot.com/2013/07/varm-l-og-kold-kaffe.html
---

For nogen tid siden var jeg så uheldig at skulle meget tidligt op, for
at komme med et tog. Dette medførte at jeg, i et forsøg på at være
venlig overfor mine medrejsende, følte mig nødsaget til at købe 4
deciliter brændstof til sjælen, også kendt som det varme, vandige
ekstrakt af tørrede, ristede bær fra planter af *Coffea*-familien, "det
lune brune" --- eller slet og ret "kaffe". Omstændighederne var således,
at bemeldte drik måtte an\[s\]kaffes fra en syvelleve, hvilket, i
overensstemmelse med forventning, bestemt ikke gav anledning til nogen
oral orgasme over kvaliteten, men koffeinindholdet fik dog min
almentilstand til at nærme sig normen (for mig) i en sådan grad, at jeg
observerede noget mystisk ved papkruset --- på trods af at man ikke fik
udleveret de sædvanlige bølgepapfingerskånere, så brændte man sig ikke
på ydersiden og det føltes som om der var en dobbelt væg...? Det må
undersøges!

Jeg drak altså min kaffe ud, og tog kruset med på tur og hjem igen,
hvor jeg dissekerede det og fandt følgende:

[![]({{site.url}}/images/-FzKBlML8Mws/UeQpFGFrC_I/AAAAAAAABt4/1it-IobSBV4/s320/2013-07-15+18.30.44.jpg)]({{site.url}}/images/-FzKBlML8Mws/UeQpFGFrC_I/AAAAAAAABt4/1it-IobSBV4/s1600/2013-07-15+18.30.44.jpg)

Den var altså god nok! Der _var_ to lag pap, adskilt af ca. 1mm luft
hele vejen rundt. Meget snedig konstruktion, faktisk, hvor inderkruset
hviler på en krave i bunden og holdes på plads af drikkekanten foroven,
hvor begge lag er foldet rundt, sammen. Et thermopapkrus, med andre
ord.

Men --- hvis yderkoppen ikke bliver nær så varm, så holder den vel også
kaffen varm længere? Et forsøg måtte være på sin plads, så jeg ilede ned
til min nærliggende Baresso og købte en stor kop kaffe, så jeg havde en
enkeltlags kontrolkop. Mens jeg destruerede indholdet under
kontrollerede forhold (på altanen, med en bog) slog det mig at muligvis
var låget også væsentligt for at holde indholdet varmt --- der er trods
alt få ting der er så gode til at fjerne varme som fordampning.

Da jeg er så heldig at have fået fingrene i et Vernier Go! Temp
USB-termometer kunne jeg forholdsvis hurtigt sætte et forsøg i gang, og
jeg endte med at optage 5 datasæt: 

- enkeltlagskop ("baresso") med og uden låg, 
- dobbeltlagskop ("7-11") med og uden låg, 
- som kontrol mit trofaste gamle porcelænskrus. 

Hver beholder blev fyldt med 400 mL næsten
kogende vand (undtaget porcelænskruset, der kun kunne rumme 300 mL -
ups!) og hensat til frivillig afkøling i køkkenet, mens der blev taget
en temperaturmåling hvert sekund i ca. en time:

[![]({{site.url}}/images/-LB2vAMQVErc/UeQuNfhVgFI/AAAAAAAABuI/FOSnfqpq5oE/s320/2013-07-14+17.06.30.jpg)]({{site.url}}/images/-LB2vAMQVErc/UeQuNfhVgFI/AAAAAAAABuI/FOSnfqpq5oE/s1600/2013-07-14+17.06.30.jpg)

Herefter blev data eksporteret fra Vernier Logger Lite som tekstfiler,
der derefter blev behandlet i R.
De rå data ser således ud:


[![]({{site.url}}/images/-NTsYX1EgYY0/UeQuxI5r1vI/AAAAAAAABuQ/0Q8C7shnadQ/s320/Rplot001.png)]({{site.url}}/images/-NTsYX1EgYY0/UeQuxI5r1vI/AAAAAAAABuQ/0Q8C7shnadQ/s1600/Rplot001.png)

Det første der springer i øjnene er at jeg har været lidt fumlefingret
med at få kogt vand, målt det af, monteret termometeret og startet
forsøget  — kurverne starter ikke i den samme temperatur. I tilfældet
"krus" skyldes det dog at kruset i sig selv starter med at suge en god
mængde varme for at komme i ligevægt med indholdet, hvorimod
varmekapaciteten af et papkrus kan negligeres.  
Der ses dog en tydelig tendens til at låget er mere afgørende end
hvorvidt det er enkelt- eller dobbeltlagskrus der anvendes.  
Nå,  men hvis man ikke kan sammenligne direkte, så må man jo modellere ---
og umiddelbart virkede det lidt uoverskueligt at skulle kombinere
bidragene fra alle de måder varme kan transporteres på (varmestråling,
varmeledning og konvektion), men dovenskaben vinder jo ofte i
ingeniørvidenskab, så jeg kom i tanke om at vores gamle ven Newton havde
formeleret en elegant regel om varmeudveksling:

*"Hastigheden, hvormed temperaturen af et legeme ændrer sig, er
proportional med forskellen mellem legemets temperatur og omgivelsernes
temperatur"*

Den vågne l\[æ|ø\]ser vil straks gennemskue at dette er en
differentialligning: \\[ \frac{dT}{dt}=-k \cdot (T-T_a)\\] Selvom
differentialligninger er en af de reneste former som universet taler til
os i, vil jeg ikke trætte jer med den analytiske løsning, men blot
konstatere at den leder til følgende udtryk: \\[ T(t)=T_a+(T_0-T_a)
\cdot e^{-kt}\\] hvor \\(T(t)\\) er temperaturen til tiden t,
\\(T_0\\) er starttemperaturen, \\(T_a\\) er omgivelsernes temperatur
og k er en konstant, der er karakteristisk for systemets evne til at
udveksle varme. 

Det ses at der er nogen lighed med udtrykket for
eksempelvis radioaktivt henfald og andre førsteordensprocesser, og k er
derfor i nær familie med "halveringstiden" --- i dette tilfælde vil
\\(\frac{ln(2)}{k}\\) nemlig være den tid det tager for temperaturen at
bevæge sig halvdelen af vejen fra den nuværende temperatur til
omgivelsernes temperatur, eller med andre ord: Jo mindre værdi af k, jo
langsommere bliver kaffen kold.

Jeg brugte nu Rs *nls* (nonlinear least squares) funktion til at løse
denne ligning numerisk for hvert datasæt. Indledningsvis havde jeg låst
Ta til 26C, da det var temperaturen i køkkenet, men det gik op for mig
at solen var på vej ned, og derfor havde ramt forsøgopstillingen i
forskellig grad, og jeg derfor ikke kunne regne med en konstant Ta.
Derfor lod jeg algoritmen optimere på denne også, i et forsøg på at få
et bedre fit, også selvom det til tider gav en tilsyneladende
omgivelsestemperatur omkring 40C --- vi er jo i dette tilælde alene
interesserede i hastigheden af temperaturændringen, altså k. Det gav
følgende plot:

[![]({{site.url}}/images/-vU3VbyFfxlI/UeQ0-ektG1I/AAAAAAAABug/i-FJjifa62I/s320/Rplot003.png)]({{site.url}}/images/-vU3VbyFfxlI/UeQ0-ektG1I/AAAAAAAABug/i-FJjifa62I/s1600/Rplot003.png)

De sorte linier er modellen, og de røde punkter (der ligger så tæt at de
ligner linier) er målingerne. Det må siges at være godt nok til rock.

k-værdierne underbygger altså vores hypotese fra oversigtplottet — "med
låg" afkøles cirka halvt så hurtigt som "uden låg", og i begge tilfælde
er den dobbeltvæggede kop lidt bedre end den enkeltvæggede.

Porcelænskruset har en k-værdi på 5.34e-04, og ligger altså nogenlunde
på par med andre beholdere uden låg.

Konklusionen må altså være at hvis du gerne vil holde kaffen varm længe,
så skal du have låg på din kop.

Dobbeltvæggede kopper hjælper lidt, men mest på at man ikke brænder
fingrene.

Gad vide om man kan måle forskel på om der er monteret en bølgepapring
på en enkeltlagskop? Det må blive en opgave for den flittige elev (eller
hans|hendes lærer).

Hov! Jeg blev så opslugt af kaffeforsøg at jeg helt glemte øllet! Nå --- 
det må blive et andet indlæg, men tillad mig at opstille nogle hypoteser
og tanker:

- Det holder ikke øl koldt at lægge låg på --- her spiller fordampning ingen
rolle.

- Et ølkrus af spejlglas ville være ideelt, dernæst et blankt og hvidt,
dernæst et klart glas (med mindre man drikker mørkt øl) og endelig et
mat og farvet.

- Gad vide om kondens på ydersiden af glasset faktisk virker afkølende ved
fordampning? Det varmer jo indledningsvis øllet op, når det afgiver
fordampningsvarmen, for at kondensere, så det må gå lige op, eller måske
endda varme øllet, da det jo sjældent fordamper igen...

- Det er egentlig lidt synd at lave forsøg på godt øl...

- Men hvis jeg nu finder et godt modelsystem, så kan jeg drikke øllet
MENS jeg laver forsøg...

- Jeg burde egentlig undersøge/optimere "våd-avis-kølesystemet" ved
lejlighed.

- Det kunne jo være udmærket på årets Smukfest...

Nå --- nu degenererer det vist --- Jeg må hellere lave mig en kop kaffe.

\\Worm
