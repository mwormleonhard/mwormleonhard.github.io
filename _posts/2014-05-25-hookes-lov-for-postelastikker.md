---
comments: true
layout: post
title: Hookes lov for postelastikker
date: '2014-05-25T00:15:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Kræfter
- Køkkenfysik
- Anna-og-lotte
modified_time: '2014-05-25T00:19:02.920+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8951394732893218794
blogger_orig_url: http://labnoter.blogspot.com/2014/05/hookes-lov-for-postelastikker.html
---

"Rygterne om min død er stærkt overdrevne" som Mark Twain vist nok
morsede det en gang, og på samme måde vil jeg lige sige at jeg stadig
lever og nørder i bedste velgående, men jeg er lige i gang med at bygge
en [sommerskole](http://show.unf.dk/) (se også
[her](https://www.facebook.com/unfscienceshow2014)), så jeg har haft
meget lidt tid til at fare i bithuset her på siden.

Når det så er sagt, så gik jeg her forleden og skulle folde et
engangsmanometer af en 1mL sprøjte, en postelastik og lidt tape, og det
gik sådan set også meget godt, indtil tryklinien sprang læk, men det kan
I høre om en anden dag.

[![]({{site.url}}/images/e477e570687d6cb35632bc7dd9d26bef.jpg)]({{site.url}}/images/e477e570687d6cb35632bc7dd9d26bef.jpg)

Nej, det, der slog mig var at jeg havde antaget at [Hookes
lov](http://en.wikipedia.org/wiki/Hooke's_law) også gælder for
elastikker og ikke kun for fjedre, men jeg havde faktisk kun en
fornemmelse at have det i, så et forsøg måtte jo laves! (Det er en af
mange skønne ting ved at være en nørd --- videnskab og eksperimenter kan
være en overspringshandling :-))

Hookes lov siger meget kort fortalt at kraften man skal bruge for at
strække eller komprimere en fjeder er ligefremt proportional med den
længde man vil forlænge eller komprimere den med. På formel ser det
således ud: \\[ F=kx\\] hvor F er kraften man påfører, k er en
karakteristisk konstant for fjederen (et mål for stivheden) og x er
forlængelsen.

Intuitivt føles det som om det også gælder for elastikker --- i hvert fald
til en vis grænse. Jo flere kræfter man bruger, jo længere bliver
elastikken, indtil den ikke kan strækkes længere og/eller den går i
stykker og man får ondt i fingrene.

Jeg husker svagt en opstilling fra min fysikundervisning i gymnasiet ---
noget med en masse lodder og en fin, næsten ideel fjeder og noget
indbygget måleværk. Det kan vi gøre bedre. Jeg brugte en pose hvedemel,
5 papirclips, min køkkenvægt og en lineal:

[![]({{site.url}}/images/0a8b1d9a5bf540eb5807a6102a3ee4a4.jpg)]({{site.url}}/images/0a8b1d9a5bf540eb5807a6102a3ee4a4.jpg)

Herefter noterede jeg hvad vægten viste for forskellige længder af
elastikken, fra slap til min lineal ikke var længere, og på den måde kan
jeg jo så beregne forlængelsen og den vægt som elastikken bærer. Jah,
det burde måske omregnes til en kraft, men vægt og kraft er jo
proportionale (vægten er jo blot en funktion af massen og
tyngdekraften), når trækket er lodret, så det står ikke i vejen for
konceptet.

Jeg fik følgende data:

| Længde [mm] | Vægt [g] | Forlængelse [mm] | Last [g] |
|:-----------:|:--------:|:----------------:|:--------:|
|     160     |   1450   |         0        |     0    |
|     170     |   1320   |        10        |    130   |
|     180     |   1220   |        20        |    230   |
|     190     |   1190   |        30        |    260   |
|     200     |   1120   |        40        |    330   |
|     210     |   1040   |        50        |    410   |
|     220     |   1010   |        60        |    440   |
|     230     |    970   |        70        |    480   |
|     240     |    930   |        80        |    520   |
|     250     |    890   |        90        |    560   |
|     260     |    850   |        100       |    600   |
|     270     |    810   |        110       |    640   |
|     280     |    777   |        120       |    673   |
|     290     |    740   |        130       |    710   |
|     300     |    710   |        140       |    740   |


Hvis man nu plotter forlængelsen som funktion af lasten, så får man
følgende (efter omstændighederne) meget smukke graf:

[![]({{site.url}}/images/583e197dd3de034a395fbcbc8683d4cc.png)]({{site.url}}/images/583e197dd3de034a395fbcbc8683d4cc.png)

Den vågne l\[æø\]ser vil straks bemærke at jeg har fusket lidt og
klippet de to nederste punkter væk. Dette skyldes at elastikken på det
tidspunkt endnu ikke var helt udstrakt, og derfor stadig ændrede
geometri, og følgelig ikke var inde i sit lineære område. 

Faktisk kan
man diskutere om det er tilfældet før vi kommer op omkring 400 gram, men
jeg synes det hører i kategorien "godt nok til rock" som det står.
Fittet burde naturligvis også gå igennem (0,0) --- når den ikke er
belastet bør den jo hverken være forlænget eller forkortet, men her må
jeg atter henvise til forskellem mellem virkelige og ideelle systemer.
Jeg kunne sikkert godt finde på en røverhistorie om hvorfor og hvordan,
men det må blive i et andet afsnit.

Vi kan altså udlede at denne postelastik bliver ca 0,2mm længere, pr
gram den belastes med, eller ca 20 cm pr. kilogram. Dette gælder som
sagt kun i det det linære deformationsområde, altså efter den er begyndt
at strække sig, men inden den begynder at knirke og klage. Det kunne
være lidt sjovt at få hele billedet med en dag, men det kan I jo selv
lege med...

Lang historie kort (nok for sent nu): Min antagelse var gyldig, og hvis
jeg bare forspænder elastikken nok, så burde mit manometer performe helt
fint.

\\Worm
