---
comments:true
layout: post
title: Hvad er lightergas for en gas?
date: '2014-08-23T21:28:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Gas
- Køkkenkemi
modified_time: '2014-08-23T21:28:39.776+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-3655408437145996104
blogger_orig_url: http://labnoter.blogspot.com/2014/08/hvad-er-lightergas-for-en-gas.html
---

For nylig havde jeg et hyggeligt møde med et af mine eksterne cerebrale
assets[^1] hvor vi over pizza og øl forsøgte at finde ud af om man kan
sætte elever på et kemi C-hold til at lave nogle øvelser som er lidt
mere spændende end standarden og ikke allerede gik på krykker i Slagelse
dengang vi selv gik i gymnasiet. 

Det havde vi blandet held med, men om
ikke andet så var det meget sjovt at grave sine gamle øvelsesrapporter
igennem for inspiration og opdage at de er ældre end mange 1.G'ere er i
dag.

Vi fik også leget lidt med statisk elektricitet og anden køkkenkemi, så
det var jo helt fint... Der var dog et enkelt forsøg som slog mig som
relativt simpelt og elegant, og jeg kunne jo ikke nære mig for at se om
det virkede lige så godt som det var enkelt. Opgaven var at bestemme
molekylvægten af lightergas og derigennem gætte om "lightergas" var
primært methan, ethan, propan eller butan.

Jovist, man kan bare læse på dåsen, men hvis du er DEN slags, så syne du
sikkert også det er sjovt at afgøre/afbryde gode nørdede diskussioner
vha Google.

Det oprindelige forlæg gik ud på at veje en engangslighter på en
analysevægt før og efter man har tappet ca. 200mL gas ud af den (målt
med inverteret måleglas i vandbad) og så bruge idelagasloven til at
udregne molvægten. 

Simpelt og elegant. Nu har jeg ikke lige en
analysevægt herhjemme, kun en diamantvægt der går op til 10g, og dels er
en lighter tungere end det, og jeg har også en mistanke om at det er
svært at tørre den tilstrækkeligt meget efter at have været neddykket i
vandbadet til at det bliver præcist. Så frem med ingeniørløsningen:


[![]({{site.url}}/images/-93iwTDTxNjY/U_jj1NFjrnI/AAAAAAAACcE/HPpnKMKzUuA/s1600/2014-08-22%2B23.22.34.jpg)]({{site.url}}/images/-93iwTDTxNjY/U_jj1NFjrnI/AAAAAAAACcE/HPpnKMKzUuA/s1600/2014-08-22%2B23.22.34.jpg)

1.  Vej en engangssprøjte fyldt med 10mL luft
2.  Fyld den med 10mL lightergas (fyld og tøm 2--3 gange for at sikre at
    al luft er fortrængt)
3.  Vej den igen
4.  Noter temperatur i lokalet (vægtermometer) og
    lufttryk (mobiltelefonbarometer)
5.  Beregn stofmængden ud fra idelagasloven
6.  Beregn molekylvægten af lightergas ud fra vægtforskel og stofmængde

Meget vel. 

Jeg gentog vejningen nogle gange og fik tal i intervallet 9--13mg i
vægtforskel. Lufttrykket var 1002hPa og temperaturen var 21C = 294K

Idealgasloven[^2]\: \\[pV=nRT \Leftrightarrow \\\\ n=\\frac{pV}{RT}
\Leftrightarrow \\\\ n=\frac{100200Pa \cdot 10 \cdot10^{-6}m^3}{8,314\frac{J}{mol\cdot K}\cdot 294K} =
4,099\cdot 10^{-4}mol\\]

Nu kan vi så uden videre udregne molmassen: \\[ M=\frac{m}{n} =
\frac{9mg}{4,099\\cdot 10^{-4}mol} = 21,95 \frac{g}{mol}\\]

Men hov --- så let går det ikke --- dette her er jo FORSKELLEN mellem en
sprøjte fyldt med  atmosfærisk luft og lightergas, så vi skal huske at
lægge molmassen af atmosfærisk luft til. Den er jo et vægtet gennemsnit
af molmasserne af alle de deltagende gasser --- og det bliver med ret god
præcision 29g/mol.

Altså får vi i ovenstående tilfælde \\( 21,95 \frac{g}{mol} + 29
\frac{g}{mol} \approx 51 \frac{g}{mol}\\), og kan på samme måde
udregne vægten på 13mg til at svare til ca. \\( 61 \frac{g}{mol}\\).

Nu ved vi altså at molekylvægten af lightergas nok ligger i intervallet
51--61 g/mol, og minsandten om ikke det passer rigtig fint med at butan
vejer 58 g/mol og i øvrigt også er det der står på bøtten. 

Det er faktisk ret sjovt at man sådan kan identificere en gasart --- eller
i det mindste finde ud af hvad den vejer og komme med et kvalificeret
gæt uden at have adgang til "rigtigt laboratorieudstyr"[^3]

Bevares, det er med nogen usikkerhed, som altid, når man er ude på
sidste decimal af måleudstyret, men Godt Nok Til Rock? Helt afgjort!

Bare giv den gas, derude!  
\\Worm

------------------------------------------------------------------------

[^1]: Undertype: Human, selvstændigt tænkende.

[^2]: Huskeregler: PosteVand og Ni Røde Tuborg --- eller, som jeg lærte
    ved samme lejlighed "Powernørd".

[^3]: Jojo, det er måske ikke alle der har en finvægt der kan veje
    milligram, men den kan købes for et par hundrede kroner og er guld værd
    hvis man er bare halvseriøs køkkenkemiker
