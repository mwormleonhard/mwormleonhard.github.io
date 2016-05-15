---
comments:true
layout: post
title: Gæt et tal &mdash; for let øvede
date: '2015-02-01T14:44:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Skæg med tal
- Statistik
- Spilteori
modified_time: '2015-02-02T10:54:19.857+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5054016512681776784
blogger_orig_url: http://labnoter.blogspot.com/2015/02/gt-et-tal-for-let-vede.html
---

I torsdags havde vi et foredrag i [UNF Odense](https://odense.unf.dk/),
der handlede om Spilteori. Det kunne godt lyde som om det handler om
hvordan man vinder i Ludo[^1] eller andre tidsfordriv, og på en god dag
med solen i ryggen og på vej ned af bakke, så kan man da godt bruge
nogle af værktøjerne på den måde...

Men i virkeligheden handler det mere om hvordan man optimerer udbytter
eller mindsker tab, helt generelt, i situationer der involverer flere
"spillere"  og en serie udfald, der afhænger af alle spillernes ageren.

Både økonomi, krig, politik og mange andre "virkelige" fænomener
analyseres spilteoretisk, men udgangspunktet for en spilteoretisk
analyse er at alle spillere er fuldt oplyst og fuldstændig rationelle,
og som vi alle ved er det sjældent tilfældet når man begynder at blande
mennesker og (gys) virkeligheden ind i det.

Som et lille sjovt eksempel bad foredragsholderen alle de
tilstedeværende skrive et tal mellem 0 og 100 (med højst én decimal) på
en seddel. Den der så kom tættest på 2/3 af gennemsnittet af alle
tallene vandt.

Der var endda en præmie, idet studier viser at det hjælper folk til at
tage det seriøst og/eller ændrer deres adfærd, også selvom det bare er
en SDU-kaffekop.

Det lyder som en ret ligefrem opgave, men hvad er egentlig det
rationelle at gøre --- og hvad gør folk?

Foredragsholderen var så venlig at lade mig beholde datasættet efter
at vi havde regnet sammen og gjort op, men inden vi ser på dét, så lad
os lige analysere problemet.

Det er et af de problemer der meget let giver hovedpine - for hvis vi
starter med at antage at alle tallene er jævnt fordelt fra 0-100 og der
er "uendelig mange"[^2], så er middelværdien jo 50, og dermed er 2/3 jo
33.3.

Men det kan folk jo relativt let regne ud, og dermed må man jo antage at
de netop gætter på denne værdi, og så bliver 2/3 jo 22.2...

Men det kan folk jo relativt let regne ud, og dermed må man jo antage at
de netop gætter på denne værdi, og så bliver 2/3 jo 14.8...

Men det kan folk jo relativt let regne ud...

Eller burde man egentlig ikke starte med at sige at maksimum bliver
66.6? Jo, det burde man vel, men det er igen en detalje som det sikkert
ikke er alle der fanger, og det ender jo samme sted efter uendelig mange
iterationer.

Derfor ender ligevægten (det spilteoretiske begreb der betyder "den
stabile løsning") med at være at alle ender med at gætte på 0 (evt 0.1,
afhængig af decimaler og afrundingsregler). Så langt, så godt.

Men som nævnt ovenfor kræver det at alle spillere er fuldt
rationelle[^3], og det er de ikke --- men de fleste kommer et godt stykke
igennem tankerækken, som data viser:

Vi fik følgende gæt (ordnet i stigende rækkefølge):

>{0.1, 3.0,
>6.0, 6.2, 6.9, 7.0, 7.2, 7.4, 11.3, 14.0, 16.0, 16.0, 16.6, 16.7, 16.7,
>18.6, 22.0, 22.3, 22.4, 22.5, 24.0, 27.0, 31.2, 31.4, 32.0, 32.7, 33.3,
>33.3, 34.0, 37.0, 37.5, 39.5, 43.2, 44.0, 44.4, 47.5, 63.4, 66.6, 67.4,
>69.7, 82.0}

Hvis mønsteret ikke er klart, så har jeg tegnet et lille histogram:

[![]({{site.url}}/images/-sonv2SsKOFo/VM4qsofvvNI/AAAAAAAAClU/fuKrhWRz0T4/s1600/g%C3%A6t.png)]({{site.url}}/images/-sonv2SsKOFo/VM4qsofvvNI/AAAAAAAAClU/fuKrhWRz0T4/s1600/g%C3%A6t.png)

Heraf ses det lidt tydeligere at der er en klar og tydelig
klyngedannelse i den nederste tredjedel, ganske som forventet, men også
at folk har gjort sig nogle antagelser om hvor mange iterationer de
øvrige spillere har kunnet overskue --- der er en tydelig top omkring 33,
en større ved 22, den største er ved 16--17, og så er der igen en
håndfuld gæt ved 6-7...

Gennemsnittet blev 28.8 og 2/3 altså 19.2, og dermed ret langt fra nogle
af de oplagte værdier.

Hvad kan man udlede af det? Tjah --- vel egentlig ikke ret meget andet end
at det er sjovt at lege med komplekse systemer involverende mennesker,
og at de ikke altid opfører sig rationelt. Måske ikke noget at rydde
forsiden for, men stadig hyggeligt at gå og tænke lidt over og nørde
med...

I øvrigt lavede Politiken forsøget for nogle år siden --- det kan du læse
mere om
[hér](http://politiken.dk/oekonomi/ECE123939/gaet-et-tal-konkurrence-afsloerer-at-vi-er-irrationelle/) [^4]

\\Worm

------------------------------------------------------------------------

[^1]: Ligesom i "Global Atomkrig" - den eneste måde at vinde på er ikke
    at spille. (Eller være så beruset at man er ligeglad, men den taktik kan
    kun anbefales i meget få tilfælde)

[^2]: I praktisk er 30-50 formodentlig nok, hvis antagelsen om
    fordeling holder. Uendelig kan være meget mindre end man tror...

[^3]: Et begreb der er mere firkantet end man skulle tro, når man taler
    matematik og spilteori.

[^4]: Gad vide om man kunne få fingrene i deres data....
