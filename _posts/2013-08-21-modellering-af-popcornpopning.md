---
comments:true
layout: post
title: Modellering af popcornpopning
date: '2013-08-21T23:15:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Køkkenkemi
- Modellering
- Mobiltelefon
- Weekendvidenskab
modified_time: '2013-08-21T23:15:42.385+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-6061635529709972434
blogger_orig_url: http://labnoter.blogspot.com/2013/08/modellering-af-popcornpopning.html
---

Som den vågne l\[æø\]ser vil have bemærket er jeg aktiv i [UNF
Odense](http://odense.unf.dk/) --- en flok glade og dejlige nørder med
formidling af naturvidenskab og verdens skønhed på sinde. Det er et
pragtfuldt selskab at færdes i, ikke mindst fordi ingen kigger mærkeligt
på én hvis man siger ting som "kunne det ikke være sjovt at optage lyden
af popcorn der popper, og så se om man kunne finde en model der
beskriver processen"[^1], men derimod straks begynder at finde på
forskellige måder man kan udføre forsøget, og eventuelt gøre det endnu
mere sjovt/sejt/nørdet/awesome/all of the above[^1a].

Og jo, det kunne det jo. For personligt har jeg altid syntes at
popcornpopning lød ligesom cellevækst[^2] --- der er en lang "lag-fase"
hvor der ikke rigtig sker noget, derefter tager hastigheden langsomt
til, indtil der er en eksponentiel vækstfase, hvorefter "væksten"
langsomt aftager, efterfulgt af "dødsfasen" --- eller i dette tilfælde
"brænde-på-fasen".

Som sagt, så gjort. Processen er egentlig meget simpel:

- Gør en pose popcorn klar i mikroovnen.
    -   Jeg ved ikke om/hvordan det virker med andre former for
        popningsaggregat end en mikroovn - men send mig endelig et datasæt,
        hvis du laver et!

- Start en lydoptager. Jeg brugte min mobiltelefon med [Smart Voice
    Recorder](https://play.google.com/store/apps/details?id=com.andrwq.recorder),
    indstillet på højeste samplerate (44 kHz) og med AGC slået til, og lagde
    den foran lågen på mikoovnen.
- Start mikroovnen. I min skal en pose have ret præcis 3 minutter på fuld
    pedal og så er de færdige uden at være brændte.
- Vent det nødvendige antal minutter (her 3)
- Stop lydoptagelse
- Analyser data mens du spiser popcornene. Har du også lave
    [ølkølingsforsøg](http://labnoter.blogspot.dk/2013/08/lkling-forstudie-til-festival.html)kan
    du evt. drikke en forhåbentlig stadig kold pilsner til.
- Jeg hentede wav-filen ind i
    [Audacity](http://audacity.sourceforge.net/) og valgte
    "Analysér...Beat Finder" og legede med Threshold indtil jeg skønnede
    at selv de usleste små pop var med, uden at jeg fik for mange
    falske positive. I mit tilfælde var det ved værdien 35%.
-   Herefter eksporterede jeg "beat-tracket" til en tekstfil ("Fil...
    Eksporter etiketter") og fik derved en tekstfil med en liste over
    tider hvor der var detekteret et "pop"
-   Denne tog jeg under kærlig behandling i R, men data er så simple at
    de formodentlig kan behandles i/af/med hvad/hvem som helst der kan
    regne.[^3]  

Herved fremkommer følgende graf:

[![]({{site.url}}/images/-Wr6R4HLJphE/UhUjVpqqnUI/AAAAAAAABzc/l2xQzrFK7Zg/s400/pop1.png)]({{site.url}}/images/-Wr6R4HLJphE/UhUjVpqqnUI/AAAAAAAABzc/l2xQzrFK7Zg/s1600/pop1.png)

Det ses her at jeg ikke var helt gal på den, med min ide om en
Sigmoidisk (S-formet) funktion, så lad os se om ikke vi kan finde sådan
én at forsøge at fitte til data. 

Den simpleste der involverer en
eksponentiel vækstfase er følgende:
\\[Antal=\frac{Max~Antal}{1+e^{-Vækstrate \cdot (Tid -
Maxvækst)}}\\]

Hvor "Max Antal" er det endelige antal popcorn, "Vækstrate" er
beskrivende for hvor hurtigt det eksponentielle trin forløber og
"Maxvækst" er det tidspunkt hvor tilvæksten går hurtigst.

Denne model kan fittes med en enkelt (men ikke helt enkel) linie kode i
R, og derved får man følgende værdier:

-   Max Antal ~ 202 (popcorn)
-   Vækstrate ~ 0,1 (pr. sekund)
-   Maxvækst ~ 124 (sekunder)

Altså at der i alt må forventes at komme ca 202 popcorn ud af posen.
Dette er i god overensstemmelse med tidligere studier udført af
\[Jørgensen, N F og Karlsen M L, 2013\].

En vækstrate på 0,1 pr. sekund betyder ikke at der popper 0,1 popkorn i
sekundet, men at fordoblingstiden under vækstfasen er
\\(T_2=\frac{\ln(2)}{0,1 s^{-1}}\approx 7s \\) --- helt analogt til
eksempelvis cellevækst eller radioaktivt henfald. 

Det passer jo faktisk
også fint med at der skal 8-9 fordoblinger til at poppe alle popcornene,
hvilket jo så giver et aktivt tidsrum på 56-63 sekunder - altså at alle
popkornen popper i løbet af et minuts tid, hvilket jo kan ses at være
tilfældet.

At tiden til den maksimale væksthastighed er ca 2 minutter passer også
fint med mine empiriske observationer af mikroovnens ur - og de faktiske
data.

Jaja, men nu kan enhver jo komme og slynge sådan nogle tal ud. Hvordan
ser det så ud? 

Sådan hér (data: røde cirkler, model: sort linie):

[![]({{site.url}}/images/-jFfZK8M50-g/UhUqRM7skSI/AAAAAAAABzs/k3ar5DC1eAc/s400/pop2.png)]({{site.url}}/images/-jFfZK8M50-g/UhUqRM7skSI/AAAAAAAABzs/k3ar5DC1eAc/s1600/pop2.png)

Det må vist siges at være godt nok til rock! [^4] [^5]

Så der har vi den altså --- det er muligt at modellere forløbet af popning
af popcorn alene vha. en mikroovn, en mobiltelefon og gratis software.
Så er der da ingen undskyldning for ikke at undersøge alle de sjove og
spændende fænomener vi er omgivet af hver eneste dag... Vel?

\\Worm

------------------------------------------------------------------------

[^1]: Næsten ordret citat, ytret af Dr. P under Sommercamp 2013



[^1a]: Man kunne fx veje popcornene før og efter, regne ud hvor meget
    damp der er undsluppet og derigennem udregne et estimat af trykket og
    måske endda temperaturen inde i kernen for at den popper.

[^2]: Altså hvis det sagde "pop", hvergang en celle delte sig.

[^3]: Muligvis endda excel :-) - Som sædvanligt kan man få data, lyd og
    kode ved at henvende sig

[^4]: Eller måske pop --- i dagens og emnets anledning.

[^5]: 
        Hvis ikke sådan en kvalitativ betragtning er tilstrækkelig, så
        spytter R denne beskrivelse ud af fittet:
        Nonlinear regression model
        model: Antal ~ maxantal/(1 + exp(-vaekstrate \* (Tid.s - maxvaekst)))
        data: pop
        maxantal vaekstrate  maxvaekst
        201.9734     0.1018   123.9333
        residual sum-of-squares: 800.9
        Number of iterations to convergence: 12
        Achieved convergence tolerance: 3.745e-07
