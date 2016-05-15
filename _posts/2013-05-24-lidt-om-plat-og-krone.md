---
comments: true
layout: post
title: Lidt om plat og krone
date: '2013-05-24T08:22:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Statistik
- Weekendvidenskab
modified_time: '2013-05-29T20:13:58.687+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-2639868357949694848
blogger_orig_url: http://labnoter.blogspot.com/2013/05/lidt-om-plat-og-krone.html
---

Jeg sad lige og legede lidt med binomialfordelingen, og kom til at tænke
på følgende:

Hvis man slår plat eller krone 9 gange i alt, så har man i alt 512
mulige udfald. \\((2^9)\\)
Sandsynligheden for KUN at slå plat er altså 1 ud af 512 eller 2
promille \\(\pm\\) en træsko.

Sandsynligheden for at slå plat 4 gange i alt er 126 ud af 512 eller ca.
25%, MEN sandsynligheden for at slå plat 5 gange i alt er OGSÅ 126 ud af 512

Spørgsmålet er nu: Hvordan kan det være lige sandsynligt at slå plat 4
og 5 gange? Det må da immervæk være mindre sandsynligt at ramme 5 ud af
9 end 4 ud af 9?

Ja, DU kan jo garanteret sagtens regne det ud --- men hvis nu du befinder
dig i et tilstrækkeligt øllet og lige tilpas nørdet selskab, så kan det
jo være du kan vinde en omgang.

For god ordens skyld: Djævelen ligger som altid i detaljen --- det kommer
til at lyde svært/sort på grund af den måde spørgsmålet formuleres på.

Den simpleste måde at indse rigtigheden på er jo at spejle problemet ---
plat 5 gange svarer til krone 4 gange, og derfor er regnestykket
symmetrisk, men skulle du have lyst til at fylde en serviet, så er
formlen hér. 

Sandsynligheden for at have præcis k successer ud af n
forsøg, hvor sandsynligheden for at lykkes er p, er givet ved:


$$ P(X=k) = \frac{n!}{k! \cdot (n-k)!} \cdot p^k \cdot
(1-p)^{(n-k)}$$

Moralen? Hvis man kun ser på et problem fra én vinkel kan det let komme
til at se væsentlig mere kompliceret / underligt ud end det er...

God Weekend!  
\Worm
