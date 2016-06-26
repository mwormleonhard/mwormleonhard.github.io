---
layout: post
title:  "Plat og krone gange mange" 
date:   2016-06-26
author: "Martin Worm-Leonhard"
tags:
- Tilfældighed
- Statistik
- Binomialfordeling
comments: true
---

For nylig henledte Lokoføreren min opmærksomhed på en kommentar fremsat af en af hans gamle venner i anledning af folkeafstemningen om EU-medlemskab, som for nylig blev afholdt i Storbritannien. Kommentaren lød:

> Hvis jeg kastede en mønt 33 mio. gange, kunne jeg nok godt klare at få plat 51,9% af gangene. Kan man overhovedet spørge en befolkning om noget og få et svar det ikke er stort set 50/50?

Som de fleste af jer nok ved, så forsøger jeg at undgå at blande politik og nørd[^1], så jeg vil alene forholde mig til påstanden om møntkast og ikke diskutere om det er en rimelig påstand at man kan ramme 51,9% plat, hvis man kaster en sand/ærlig/lige[^2] mønt \\(33\cdot10^6\\) gange.

Det at kaste en mønt eller foretage lignende "sand/falsk" eksperimenter kaldes [Bernoulli-forsøg](https://en.wikipedia.org/wiki/Bernoulli_trial) og læser man lidt om det, så finder man ud af at laver man en stor mængde af sådan nogle, så kan de forventes at være [Binomialfordelt](https://en.wikipedia.org/wiki/Binomial_distribution).

Vi kan sagtens finde en masse formler at lave fingergymnastik på, men da [R](http://www.r-project.org) sædvanligvis kan regne, så kan vi spørge den om hvad sandsynligheden er for at få 51,9% plat, ved \\(33\cdot10^6\\) kast af en lige mønt:

```r
binom.test(x=0.519*33e6, n=33e6, p=0.5, conf.level = 0.9999)
```

Hvorefter vi får følgende output:

```
  Exact binomial test
  
  data:  0.519 * 3.3e+07 and 3.3e+07
  number of successes = 17127000, number of trials = 3.3e+07, p-value < 2.2e-16
  alternative hypothesis: true probability of success is not equal to 0.5
  99.99 percent confidence interval:
  0.5186616 0.5193384
  sample estimates:
  probability of success 
                 0.519 
```

Hvorved vi altså kan se på p-værdien at sandsynligheden for at få 51,9% plat ved et tilfælde, hvis mønten er ærlig er cirka 1:50.000.000.000.000.000.
Samtidig får vi også et 99.99% konfidensinterval, der siger at hvis man har observeret 51,9% plat, så vil det i 9999 ud af 10.000 tilfælde betyde at den sande andel af plat[^3] ligger mellem 51,866% og 51,934%.

Det er altså IKKE rimeligt at antage på baggrund af 51,9% plat, at mønten er ærlig, når man har kastet 33.000.000 gange. 

Men hvorfor ikke? Hvis vi kaster en mønt 10 gange, så kan vi jo ikke antage at den er skæv eller uærlig, bare fordi vi får 6 eller endda 7 gange plat?

Nej, det er sandt --- og det er en effekt af ["De store tals lov"](https://en.wikipedia.org/wiki/Law_of_large_numbers) der i denne sammenhæng kort sagt siger, at jo flere obervationer man har, jo mere sikker er man på at resultatet er korrekt. Heraf følger også at hvis man vil se en meget lille effekt -- for eksempel afgøre om en mønt viser krone kun 49,9% af gangene i stedet for 50%, så er man nødt til at lave et meget stort antal forsøg, hvorimod det kræver et forholdsvist meget mindre antal eksperimenter at afsløre en mønt der viser krone 90% af gangene. Og det er jo spændende, men det er jo nok til et andet afsnit.

\\Worm

-------------------------

[^1]: Jeg ved også at flere af jer mener at det er en fejl og andre mener at det er sundt. Det er ikke dét vi diskuterer lige her. Det kan vi gøre over øl.

[^2]: Altså en med lige stor sandsynlighed for at vise plat hhv. krone.

[^3]: Ja, jeg beklager, men I ER jo vant til store mængder plat i mine indlæg... ;-)


