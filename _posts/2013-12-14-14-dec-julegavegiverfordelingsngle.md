---
layout: post
title: '14 DEC: Julegavegiverfordelingsnøgle'
date: '2013-12-14T10:00:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Julenørd
- Skæg med tal
- Statistik
modified_time: '2013-12-14T10:00:03.839+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-4059740390404117478
blogger_orig_url: http://labnoter.blogspot.com/2013/12/14-dec-julegavegiverfordelingsngle.html
---

Uden at skulle gå ind i hele debatten om hårde kontra bløde pakker, så
er der jo én ting vi alle ønsker os af vores julegaver --- at de ikke skal
byttes! Selvfølgelig til dels fordi det betyder at man har fået lige det
man ønskede sig, og kun i det kvantum man ønskede sig, men lad os nu se
det i øjnene --- det er vel i lige så høj grad for at undgå
januarudsalgsjulegavebyttehelvedet! 
Men hvor sandsynligt er det egentlig
at man er så heldig? Det må jo både afhænge af omfanget ef éns
ønskeseddel og mængden af personer der giver én gaver, og mængden af
gaver per person. Det begynder at ligne noget vi har regnet på før...

Faktisk minder det ret meget om
[fødselsdagsparadokset]({%post_url 2013-12-02-02-dec-fdselsdagsparadokset %}),
bare i en lidt mere generel form, så gad vide om ikke noget af den samme
matematik eller udledningsstrategi kan gøres gældende?
Hvis vi antager at man har \\(W\\) ønsker på sin ønskeseddel, og \\(F\\)
familiemedlemmer/venner/katte der giver gaver, og vi indledningsvis
regner med at folk ikke snakker sammen[^1] og giver én gave hver, så
følger det trivielt at for at undgå dublering skal \\(W \geq F \\) ---
man skal have mindst lige så mange ønsker som man har gavegivere. 
Det kan jo være svært nok, hvis éns familie er stor og/eller éns
behov/kreativitet er lille, men lad os regne det igennem i et simuleret
tilfælde --- det er nok lettere tilgængeligt for både skribent og læser
end den generelle udledning.

Lad mig se --- en relativt normal[^2] familie består vel at et par
forældre og 1,7 barn --- lad os bare sige 2, det griser ikke så meget ---
3--4 bedsteforældre og 2 onkler/tanter man er på gave med, lad os bare
være gavmilde og sige at man får gaver af 10 personer, altså skal man
under forudsætningen have mindst 10 ønsker for at have en mulighed for
ikke at få dubletter. Lad os først antage et amok-i-silvan[^3]
scenarie, hvor man bare sætter krydser i relevante
[reklametryksager]({%post_url 2013-12-09-09-dec-julekataloger %}),
og derved får talt sig op på 25 (realistiske) ønsker.

Den første gavegiver kan vælge frit (tilfældigt) fra listen uden risiko
for kollision --- sandsynligheden for at alle gaver er unikke på dette
tidspunkt er altså \\(\frac{25}{25}=1\\).
Den næste der vælger tilfældigt har \\(\frac{24}{25}=96\%\\) chance
for at ramme forbi den valgte gave, og den næste så
\\(\frac{23}{25}=92\%\\) og så fremdeles, 10 gange. 

Alle disse
sandsynligheder skal derefter ganges sammen for at få den samlede
sandsynlighed for at alle gaver er unikke, eller på matematisk: 
\\[P(\text{alle gaver unikke }) = \frac{25 \cdot 24 \cdot 23 \cdots 16}{25^{10}} = 12,4\%\\]
Altså kan man kun forvente at slippe for at skulle bytte gaver ca. hvert
8. år, selv med mere end dobbelt så mange ønsker som gavegivere. 

Tager
vi samme situation, men kun med 10 ønsker, så bliver sandsynligheden
\\[P(\\text{alle gaver unikke }) = \frac{10\cdot9\cdot8\cdots1}{10^{10}} = 0,04\%\\]
Altså en hændelse der i snit vil forekomme 1 ud af 2756 gange --- bevares,
det er stadig bedre end at sikre julegaverne ved at spille lotto, men
man undgår nok ikke en tur ud i vrimlen.

Det analytiske udtryk, eller bedste tilnærmelse vil jeg overlade til
l\[æø\]serne --- der er jo nok nogle timer der skal fordrives inden det
bliver jul, og det er jo så hyggeligt med lidt rekreativ matematik til
bromkagerne.

Dagens morale må være at jo større en familie man har, jo vigtigere er
det med en meget lang ønskeseddel!

\\Worm --- pakkenisse.

------------------------------------------------------------------------

[^1]: Eller bare er godt forvirrede i juletravlheden og/eller har svært
    ved at oveholde en aftale, fordi det jo skal være ekstra godt og det er
    jo kun jul en gang om året.

[^2]: I den grad det ord kan anvendes i nærheden af jeres ydmyge
    skribent og/eller læsere af nærværende medie.

[^3]: Eller Fætter BR, eller hvad der nu passer i det konkrete
    tilfælde. Betegnelsen har historiske rødder i rollespilsmiljøet på
    Aalborgkanten, og er derved kanonisk.
