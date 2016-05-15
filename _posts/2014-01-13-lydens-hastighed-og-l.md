---
comments:true
layout: post
title: Lydens hastighed - og øl!
date: '2014-01-13T20:34:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Lyd
- Køkkenfysik
- Øl
modified_time: '2014-01-13T20:35:20.516+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-6174535788042035947
blogger_orig_url: http://labnoter.blogspot.com/2014/01/lydens-hastighed-og-l.html
---

Det skal ikke være nogen hemmelighed at jeres til tider knap så ydmyge
skribent er meget glad for øl --- altså måske ikke så meget den slags
masseproducerede pseudopilsnere som knapt fortjener prædikatet og vel
bedst kan sammenligne med at elske i en kano, men som dog har sin
berettigelse på festivaler og detslige, men det er jo en religionskrig
(for nogen) så det vil jeg ikke komme yderligere ind på hér.

I stedet vil jeg observere at jeg havde haft en lang dag på kontoret (og
i lab) og havde fortjent en fyraftensbajer, og i den forbindelse af
vanvare og distraktion kom til at puste hen over mundingen på en nyligt
tømt halvliters glasflaske og observerede en ret klar og tydelig tone,
som man jo gør[^1].

Det slog mig derefter under indtaget af det udmærkede, men på ingen måde
exceptionelle bryg at tonen velsagtens måtte afhænge af
flaskestørrelsen, og dermed måtte kunne benyttes til at bestemme lydens
hastighed --- om ikke i øl, så dog i luft. Så det prøvede jeg, og det
viste sig ikke helt let, ja faktisk krævede det en sidevogn af rom til
at inducere lidt inspiration, men det lykkedes dog til sidst. Forklaring
følger...

Min grundide var følgende: Enhver bølgeudbredelse, herunder lydbølger
følger den ret simple sammenhæng: \\[ v=f \cdot \lambda\\] Hvor v er
bølgens hastighed i det relevante medie (her lyd i luft), f er
frekvensen i Hz og \\(\lambda\\) er bølgelængden.

Den første opgave er altså at fastslå hvilken frekvens min flaske tuder
med, og det gøres let ved at optage lyden med et program som
[Audacity](http://audacity.sourceforge.net/), som koster gratis, og har
masser af fine features, som fx muligheden for at foretage
frekvensanalyse på det optagede - og det ser så sådan ud i dette
tilfælde:

[![]({{site.url}}/images/-GJLVo--F58A/UtQ1CMWJHzI/AAAAAAAACBg/nPrp-Ncr98I/s400/oelflaske.png)]({{site.url}}/images/-GJLVo--F58A/UtQ1CMWJHzI/AAAAAAAACBg/nPrp-Ncr98I/s1600/oelflaske.png)

Herudfra kunne jeg udlede at grundtonen (den store top) var 169Hz, og
hvad det svarer til i toner, om noget, skal jeg ikke kunne sige.
Men hvad er så bølgelængden? Ja, det ville være oplagt at tro at det var
flaskens længde[^2] --- der må vel være noget fysik der binder en stående
bølge fast i toppen og bunden af sådan et svingningskammer...

Frem med linealen --- flasken er 24 cm = 0,24m ergo må lydens hastighed
være: \\[ v=169Hz\cdot0,24m=40,6\frac{m}{s}\\]
Men hov! Nu går det galt! Jeg kan jo huske fra min fysikundervisning af
lydhastigheden er et sted i nærheden af 340 \\(\frac{m}{s}\\)[^3].

Adskillige flasker (altså til forsøg, ikke konsum), fløjter, et par
elektrikerrør og reagensglas senere var jeg glad for nyligt at have
anlagt frisure som Walter White, idet jeg ellers nok ville have hevet
håret ud i ret store totter --- det kunne simpelthen ikke bringes til at
passe med det jeg havde lært, og godt nok ved jeg godt at man lærer
forsimplede modeller af virkeligheden under sin uddannelse, meeen...

Heldigvis er min google-fu stærk, og efter lidt spændende roden rundt på
nettet fandt jeg ud af at mine mærkelige resultater skyldes at flasker
slet ikke er resonatorer for simple, stående bølger, men såkaldte
[Helmholz-resonatorer](http://en.wikipedia.org/wiki/Helmholtz_resonance),
der kort beskrevet går ud på at den frekvens man hører er et resultat af
at luftsøjlen i flaskehalsen står og svinger (hopper op og ned), mens
flaskens hovedvolumen fungerer som en slags fjeder[^NJ] den står og hopper
på. 

Heldigvis kan tante wiki en formel for hvordan det så kommer til at
se ud med resonans under de forhold: \\[f_{H} =\frac{v}{2\pi}\sqrt{\frac{A}{V_0L}}\\] Her er \\(f_H\\)
Helmholz-resonansfrekvensen, \\(v\\) er lydhastigheden, \\(A\\) er
flaskehalsens tværsnitsareal, \\(V_0\\) er flaskekroppens volumen og
\\(L\\) er længden af flaskehalsen.

Frem med linealen igen, og husk at regne i SI-enheder, ellers bliver du
kølhalet:  
Mundingen af flasken er ca. 2cm i diameter altså er \\(A=\pi \cdot r^2 = \pi \cdot (0,01m)^2 = 3,14\cdot10^{-4}m^2\\);  
Flasken har indeholdt en halv liter, så det er nok rimeligt at antage at
\\(V_0=5\cdot10^{-4}m^3\\);  
Længden kan måles umiddelbart fra munding til krave: \\(L=0,075m\\);  
Frekvensen er stadig den samme: \\(f_H=169Hz\\) og lidt fingergymnastik
senere har vi altså: 
\\[v=\frac{f_H \cdot 2 \cdot \pi}{\sqrt{\frac{A}{V_0L}}} =
\frac{169Hz \cdot 2 \cdot \pi}{\sqrt{\frac{3,14\cdot10^{-4}m^2}{5\cdot10^{-4}m^3 \cdot 0,075m}}} =
367 \frac{m}{s}\\]

Tabelværdien for lydhastighed i tør luft ved 20 grader er \\(343,2 \frac{m}{s}\\), så jeg rammer altså ca 7% for højt, men det synes
jeg faktisk er helt acceptabelt, metoden og redskaberne taget i
betragtning, så jeg vill ikke engang forsøge at (bort)forklare det med
at lydens hastighed er anderledes i fugtig og/eller \\(CO_2\\)-holdig
luft, hvilket ellers er ret rimelige tilstande at forvente i en nyligt
tømt ølflaske.

Et supplerende forsøg med en vinflaske gav i øvrigt en lydhastighed på
\\(342\frac{m}{s}\\), så det er nok rimeligt at antage at det ikke KUN
var det rene svineheld.

Har du pustet hen over noget sjovt og fundet en værdi? Eller har du
regnet på et orgel? Eller noget endnu mere mystisk? Så drop en
kommentar...

\\ØlWorm

------------------------------------------------------------------------

[^1]: Normalt vil jeg ellers kunne skaffe adskillige vidner på at jeg
    kun har én tone i livet, og den lugter ikke godt, men det tæller vel
    heller ikke helt som et instrument...

[^2]: Eller et helt multiplum deraf.

[^3]: Ja, jeg ved det godt - hvis jeg allerede ved det, hvorfor så
    forsøge at regne det ud? Fordi jeg kan! Det er sjovt og god nørd!

[^NJ]: Nej, det er ikke en Nik-og-Jay-reference. Gå ud og vask din mund med kongevand.
