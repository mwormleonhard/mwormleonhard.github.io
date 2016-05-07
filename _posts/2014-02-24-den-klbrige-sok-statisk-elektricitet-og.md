---
layout: post
title: 'Den klæbrige sok: Statisk elektricitet og dens egenskaber'
date: '2014-02-24T21:35:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Energi
- Kræfter
- Bagsiden af kuverten
- Statisk elektricitet
- Elektrostatik
modified_time: '2014-02-24T21:38:42.175+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5346334997085393683
blogger_orig_url: http://labnoter.blogspot.com/2014/02/den-klbrige-sok-statisk-elektricitet-og.html
---

Jeg har lige været nede at vaske tøj[^1] og bemærkede ved den lejlighed
at efter en tørretumbling har mange tøjstykker --- især sokker i mit
tilfælde --- en tendens til spontan pardannelse eller det der er værre,
pga den statisk elektriske ladning de påføres ved at udsættes for varm
og tør luft og en lejlighed til at gnide op ad hinanden[^2]. 

Ja,faktisk udmærkede den ene af mine sokker sig ved at kunne hænge fast på
væggen som et lettere sørgeligt strikket ballondyr, og det fik mig
naturligvis til at tænke på hvor store kræfter statisk elektricitet
egentlig kan antages at have indenfor rimelighedens grænser.

Lad os alle regne...

At en statisk ladning kan opnå et forbløffende elektrisk potentiale er
næppe nogen overraskelse for nogen der har fået stød af deres dørhåndtag
efter at have løbet en tur i noget nylontøj og et par gummisko, eller
lignende potentialbyggende aktivitet, så som at køre bil i frostvejr.

Gnister kan springe adskillige millimeter --- en ret imponerende bedrift,
når man overvejer hvor godt luft isolerer.
Lad os bare for at tage et pænt rundt tal sige at det er muligt at lade
et emne op til 25.000 volt uden at svede for meget --- det er nok til at
få en gnist til at springe et par millimeter eller tre.

Det er straks meget være at vurdere hvor god en kapacitor et menneske
(eller for den sags skyld en sok) er, altså hvor meget ladning den kan
opbevare, men heldigvis kommer [Tante Wiki](http://en.wikipedia.org/wiki/Static_electricity) atter til
undsætning med en oplysning om at man i mange modeller antager at et
menneske svarer til en kapacitor på 100 picofarad.

Nu kan vi i første omgang beregne hvor meget elektrisk energi det svarer
til, da vi ved at \\[E_{elektrisk} = \frac{1}{2} \cdot C \cdot V^2\\] 
når C er kapaciteten og V er spændingen. Bemærk analogien til
kinetisk energis masse og hastighed. 

25 kV i 100pF er
altså \\[E_{elektrisk} = \frac{1}{2} \cdot 100\cdot10^{-12}F \cdot (25.000V)^2 = 31,3mJ\\]
31 millijoule er ikke meget energi --- og vi overlever jo sædvanligvis
også at få et statisk elektrisk stød, om end det kan være ubehageligt ---
det modsvarer cirka energien der kræves for at løfte et enkelt riskorn
ca 12cm, men allerede ved denne sammenligning kan vi se at det ikke er
så mærkeligt at man med statisk elektricitet kan løfte små papirsstykker
og få popkorn og riskorn til at danse! 

Det er også rigeligt med energi
til at antænde nogle af de mere temperamentsfulde gas/luft-blandinger og
på en god dag kan de endda antænde fint støv, så som mel - hvilket man i
sagens natur gerne vil undgå hvis man ejer en mølle...

At en energimængde der kan løfte et riskorn 12 cm også kan løfte noget
så let som hår fra hovedet er heller ikke så mystisk igen, men alt dette
er jo dynamiske effekter --- hvad er det der får sokken til at sidde fast
på væggen?

Her skal vi have fat i [Coulombs Lov](http://en.wikipedia.org/wiki/Coulomb's_law), der godt nok i sin
grundform kun beskriver interaktionen mellem punktladninger, men kan
integreres efter behov over flader og rum. Nu er jeg godt nok ingeniør,
men så længe vi arbejder i træskolængder så har jeg det fint med at være
så meget fysiker at jeg vil kalde min sok for en punktladning, frem for
at prøve at definere fladeintegralet der hører til.

Lad os i stedet antage at en sok kan bære ligeså meget ladning som et
menneske. Den er godt nok meget mindre, men til gengæld isolerer den
væsentligt bedre[^3]. Skalarformen af Coulombs lov er: 
\\[ |F|=k_e \frac{|q_1q_2|}{r^2}\\]
hvor \\(q_1\\) og \\(q_2\\) er størrelsen af de respektive ladninger,
r er afstanden mellem dem og \\(k_e\\) er Coulombs konstant som er
\\(k_e=8,99\cdot10^9\frac{N\cdot m^2}{C^2}\\).

Ladningsstørrelsen på sokken kan vi estimere ved at huske at spænding er
det samme som energi per ladning, altså at
\\(Volt=\frac{Joule}{Coulomb}\\) og en sok der indeholder 31mJ ved 25kV
må således bære en ladning på
\\[q=\frac{E}{U}=\frac{31\cdot10^{-3}J}{25\cdot 10^3 V}=1,24\mu C\\]

Ladningen på væggen må jo antages at starte med at være nul --- og så er
der jo ingen tiltrækning --- men der sker noget sjovt når man nærmer et
ladet objekt til en ikke ladet isolator: Der induceres en lokal
ladning, og nej, den opstår ikke ud af ingenting, for det må man ikke
ifølge Reglerne, men hvis man flytter lidt rundt på elektronerne i
overfladen, så kan man opnå en tilsyneladende ladning af ca. samme
størrelsesorden, uden at skulle kølhales for at knække termodynamikken.

Lad os se hvad vi får, sådan i runde tal, hvis vi antager en afstand
mellem ladningerne på 1mm: \\[ |F|=k_e \frac{|q_1q_2|}{r^2}=8,99\cdot10^9\frac{N\cdot m^2}{C^2} \cdot 
\frac{1\mu C \cdot 1\mu C}{(10^{-3}m)^2}=8,99mN\\]
Ooookay, 9 millinewton er nok lidt lidt --- det svarer cirka til
tyngdekraften på et gram --- og jeg vil umiddebart vurdere at vi nok er
tættere på området 10--20 gram, vurderet ud fra hvor let/svært det var at
hive den af væggen igen, og en sok vejer jo ca 20 gram, men i
betragtning af at vi bare skal halvere afstanden mellem ladningerne for
at firedoble kraften, så er det jo nok alt i alt ikke heeelt skeløjet ---
der var jo trods alt ikke noget synligt luftgab mellem sok og væg...

Er der en morale eller pointe, spørger du jo nok nu? Tjah... bum bum
bum... Er det ikke nok at (vores modeller af) virkeligheden giver
mening, og at man kan tillade sig at regne på en tørretumblet sok som en
punktladning og alligevel få noget der lugter af et anvendligt resultat?

Rekreativ naturvidenskab er et undervurderet felt --- min tøjvask blev
eksempelvis utroligt meget mere underholdende af at give anledning til
dette lille regneri...

Kan I nørde godt, derude!  
\\Worm

------------------------------------------------------------------------

[^1]: Urelateret til eventuelle væmmelige associationer overskriften måtte give.

[^2]: Det sker også at mennesker udviser pludselig tiltrækning under
    lignende omstændigheder, men det skyldes kun sjældent statisk
    elektricitet.

[^3]: Altså elektrisk isolator --- menneskers evne som varmeisolatorer er
    også udmærket, men lidt sværere at beregne da vi snyder og udleder
    spildvarme. Det gør sokker kun sjældent.
