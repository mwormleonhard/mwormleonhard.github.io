---
comments:true
layout: post
title: At stege pandekager og regne på ting der ikke sker
date: '2013-08-13T00:07:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Statistik
modified_time: '2013-08-13T00:07:55.467+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8389114346178812899
blogger_orig_url: http://labnoter.blogspot.com/2013/08/at-stege-pandekager-og-regne-pa-ting.html
---

Jeg faldt over dette [interessante
indlæg](http://www.johndcook.com/blog/2010/03/30/statistical-rule-of-three/) og
tænkte at jeg lige ville levere en hurtig opsummering, eftersom det er
et problem jeg selv har overvejet, men endnu ikke fundet et lige så
elegant svar på.

Spørgsmålet er i al sin enkelthed: _Hvordan beregner man sandsynligheden
for en hændelse der ikke er sket endnu?_

Hvis du  er i gang med at lave pandekager til et sultent
telegrafregiment og har stegt[^1] 50 pandekager og har brændt 4 af dem
på, så vil du med rimelighed forvente at \\(\frac{4}{50}\cdot100\%=8 \%\\) 
af din samlede mængde pandekager ender med at være brændt på,
uanset hvor mange du laver, under antagelse af at du ikke lærer af dine
fejl.[^2]

Men hvad nu hvis du har stegt 50 pandekager UDEN at brænde en eneste på?
Er det så rimeligt at forvente at det aldrig sker? Nej vel?

Her er så tommelfingerreglen: Hvis du i N forsøg ikke har observeret den
hændelse du undersøger, så er den mest sandsynlige frekvens af den
hændelse lavere end \\(\frac{3}{N}\\).

Med andre ord vil du i ovennævnte eksempel forvente at færre end
\\(\frac{3}{50}\cdot100\%=6\% \\) af din endelige mængde pandekager
brænder på inden du er færdig. Steger du 1000 pandekager i alt kan du
altså ud fra dette estimat forvente at smide op til 60 ud.

Har du stegt de første 200 pandekager uden at brænde nogen på falder
sandsynligeheden tilsvarende til 1,5% og altså kun højst 15 pandekager
ud af 1000 der skal kasseres.

Det er naturligvis en regel der skal anvendes med en vis forsigtighed,
men så længe man er godt tilfreds med usikkerheder målt i
træskolængder[^3] så er det helt fint.

Matematikken er ikke specielt langhåret, men antagelserne er lidt grove,
og kan være svære at gennemskue:

- Vi antager at sandsynligheden for hændelsen vi observerer (at en given
pandekage brænder på) er *p.*
- Sandsynligheden for at de ikke brænder på er så *1-p.*
- I de fleste tilfælde siger man at hvis en given hændelse skal være
usandsynlig ("ikke ske"), så  skal sandsynligheden være under 5%
(0,05).[^4]
- Hvis vi foretager *n* forsøg (steger *n* pandekager) og ingen af dem
skal brænde på, så skal vi altså løse ligningen  \\((1-p)^n = 0,05 \\)
for p.
- Ved at tage (naturlige) logaritmer på begge sider får man \\(n \cdot
\ln(1-p) = \ln(0,05)\\).
- Da \\(\ln(0,05) \approx -3\\), og \\(\ln(1-p) \approx -p\\) for små
værdier af p fås altså efter lidt fingergymnastik at
\\(p\approx\frac{3}{n}\\).

Det følger analogt at hvis man vil være mere end almindeligt sikker[^3]
så skal man bruge 5 i stedet for 3, og så har man et estimat der siger
at antallet med over 99% sandsynligehed er mindre end det fundne tal.

\\Worm

------------------------------------------------------------------------

[^1]: Ja, jeg vil også instinktivt sige "bagt", men det er jo ikke det
    man gør, vel?

[^2]: Det gør mennesker erfaringsmæssigt meget sjældent. Det gør det
    vel til en rimelig antagelse.\

[^3]: Så som de fleste ingeniører. De har godt nok en tendens til at
    opgradere til sømbeslåede støvler og gå to numre op, men det er en
    erhvervsskade.

[^4]: Det er sådan "af historiske årsager". Lidt ligesom cirkulær logik
    er den bedste slags, fordi den er rund.
