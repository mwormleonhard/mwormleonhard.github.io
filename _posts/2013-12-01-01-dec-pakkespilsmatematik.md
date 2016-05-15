---
comments:true
layout: post
title: '01 DEC: Pakkespilsmatematik'
date: '2013-12-01T10:00:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Julenørd
- Statistik
- Tilfældighed
modified_time: '2013-12-01T10:00:01.143+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-4046534892707417628
blogger_orig_url: http://labnoter.blogspot.com/2013/12/01-dec-pakkespilsmatematik.html
---

Vi kender det alle sammen --- man sidder og hygger sig til en julefrokost,
og pludselig er der nogen der finder et par raflebægre og nogle
terninger frem og annoncerer at der er pakkespil. Efter et øjebliks
panik lykkes det én at snige sig ud og omvikle en arbitrær dåseøl og 2
ruller á 200 biletter til endestadionen med sidste uges eksemplar af
Ingeniøren, og man er klar til at deltage i fezlighederne, som om intet
var hændt.

Nu melder spørgsmålet om optimering sig jo straks, idet næsten alle
nørder har et talskubbergen, der tvinger dem til at prøve at gennemskue
systemet og skubbe til kuverten, ikke så meget for monetær vinding[^1],
men fordi man kan!

Givet "de sædvanlige regler"[^2], der indebærer at legen går i to
tempi, begge af ukendt varighed; Først må man tage en gave fra puljen,
hvis man slår en 6'er, og når puljen så er tom, eller klokken slår
første gang, må man tage fra hinanden, hvis man slår noget andet. Når
klokken slår (igen) stopper legen, og man er blevet den lykkelige
indehaver af hvad der står foran én.

Er der så en vindende taktik?

Jeg skal gerne indrømme at jeg er ude i noget spilteori, hvor jeg ikke
er sikker på at jeg kan bunde, men det gør det jo bare sjovere. Selv
hvis mennesker opførte sig bare tilnærmelsesvist ens og
forudsigeligt[^3], så ville jeg påstår det er umuligt at lave en
generel vindende taktik i et spil der er 100% baseret på tilfældige
udfald. Man er simpelthen nødt til at forholde sig til den enkelte
situation i det enkelte spil man befinder sig i. Eller måske lave en
stor simulering/numerisk model/???.

Lad os derfor i stedet forestille os et spil hvor der er 10 deltagere -
det er vist en meget normal fordeling[^4] --- og regne lidt på de
interessante størrelser der er i spil.

Først er jeg nødt til at sige:  
Nej, det bliver ikke hverken mere eller mindre sandsynligt at lige netop
DU slår en 6'er uanset hvor få eller mange du eller din sidemand har
slået tidligere. Hvis terningen er lige, så er sandsynligheden 1/6 -
hver gang.

Men det rejser jo så spørgsmålet: Hvornår har du så ret til at råbe
"korrupt" --- og forlange terningen udskiftet?

Antallet af 6'ere følger en binomialfordeling, og hvis vi ser på alle
terningslag rundt om bordet, så giver den første omgang altså 10
stikprøver, og dermed er sandsynligheden for antal seksere som følger:


| Antal         | 0        | 1        | 2        | 3        | 4        | 5        | 6        | 7+           |
|---------------|----------|----------|----------|----------|----------|----------|----------|--------------|
| Sandsynlighed | 16%      | 32%      | 29%      | 16%      | 5%       | 1.3%     | 0.2%     | &lt;&lt;0.1% |

Hvis vi anlægger julens mildhed og godtroenhed og siger at et givent
udfald skal være mindre end én procent sandsynligt for at kunne bære at
beskylde værten for at snyde skal vi altså se mere end 5 6'ere i en
given omgang før det er kriminelt. 

Heldigvis løber sådan et spil gerne
over mange omgange, så med tiden får vi en større og dermed sikrere
stikprøve. Når spillet er løbet 2 omgange (20 slag) skal vi have set
over 8 seksere før det er slemt, men der er stadig ca 12% sandsynlighed
for at vi kun har set nul eller en enkelt.
Efter tredje omgang er 0-1 sekser suspekt, og flere end 10, og
udviklingen ender som følger:

| Antal slag i alt         | Nedre suspekt            | Øvre suspekt             |
|:------------------------:|:------------------------:|:------------------------:|
| 10                       | NA                       | 5                        |
|--------------------------|--------------------------|--------------------------|
| 20                       | NA                       | 8                        |
|--------------------------|--------------------------|--------------------------|
| 30                       | 1                        | 10                       |
|--------------------------|--------------------------|--------------------------|
| 40                       | 2                        | 13                       |
|--------------------------|--------------------------|--------------------------|
| 50                       | 3                        | 15                       |
|--------------------------|--------------------------|--------------------------|
| 60                       | 4                        | 17                       |
|--------------------------|--------------------------|--------------------------|
| 70                       | 5                        | 29                       |
|--------------------------|--------------------------|--------------------------|
| 80                       | 6                        | 22                       |
|--------------------------|--------------------------|--------------------------|
| 90                       | 7                        | 24                       |
|--------------------------|--------------------------|--------------------------|
| 100                      | 9                        | 26                       |

Hvis man bare vil have en hurtig tommelfingerregel og ikke regner med at
have indtaget urimelige mængder juleøl[^5], så er binomialfordelingens
middelværdi \\(np\\) og dens varians \\(np(1-p)\\), i dette tilfælde
altså \\(\frac{n\cdot5}{36}\\) og et 99% konfidensinterval svarer til
plus/minus cirka 2.5 standardafvigelser, og standardafvigelsen er
kvadratroden af variansen.

Hvis vi udsætter det for lidt fingergymnastik og grov overforsimpling,
så får vi:

Det forventede antal 6'ere: \\(\frac{Antal~slag}{6} \pm 0.931 \sqrt{Antal~slag} \approx \frac{Antal~slag}{6}\pm \sqrt{Antal~slag}\\)

Hermed bliver intervallet for 60 slag altså \\(60\cdot\frac{1}{6} = 10
\pm \sqrt{60} = 10 \pm 7-8\\) stykker --- det er vist godt nok til rock for nu slet ikke at tale om julefrokoster.

Hov, nu er min taletid udløbet --- det skulle jo gerne blive jul inden
påske!

Men hvad er så dagens lektion?

1.  Det er svært at vide noget med sikkerhed, når man kun har en meget
    lille stikprøve.
2.  På et tidspunkt bliver det urimeligt svært at blive mere sikker uden
    en enorm stikprøve. (Jfr \\(\sqrt{n}\\))
3.  Tænk ikke så meget over retfærdighed og statistik under
    pakkespillet --- hævn dig bagefter i stedet!



\\Worm - Talskubber (af reserven).

------------------------------------------------------------------------

[^1]: Jfr. overstående kommentar om gavernes natur.

[^2]: Jeg har kun sjældent oplevet dem afvige, men er klar over at det
    kan være et semireligiøst spørgsmål i visse kredse. Ingen krænkelse er
    tiltænkt.

[^3]: Breaking News: Det gør de ikke!

[^4]: Ikke at forveksle med en normalfordeling - endnu!

[^5]: Eller er i et selskab hvor det er normalt at regne på
    servietterne/dugen.
