---
comments: true
layout: post
title: Om at blive gennemskuet - ioniserende stråling og kameraer
date: '2014-11-10T20:18:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Rejsevidenskab
- Mobiltelefon
- Lys
- Billedanalyse
modified_time: '2014-11-10T20:18:42.399+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-6257749582036482385
blogger_orig_url: http://labnoter.blogspot.com/2014/11/om-at-blive-gennemskuet-ioniserende.html
---

Der var engang, selv før indførelsen af det omsiggribende
sikkerhedsteater, hvor det ikke desto mindre kunne være en nervepirrende
oplevelse at skulle igennem sikkerhedskontrollen i en lufthavn. Navnlig
hvis man var ivrigt fotograferende, hvad enten det var professionelt
eller bare for sjov. Det var nemlig således at de første
røntgenapparater til gennemlysning af (hånd)bagage meget vel kunne gå
hen og sværte den film[^1] man havde med, uanset om den sad i et kamera
eller lå i sin æske.

Røntgenstråling er jo immervæk bare fotoner der ikke sådan bare lige
lader sig stoppe af simple lavdensitetsmaterialer, men de kan stadig på
en god (eller dårlig) dag fremkalde[^2] samme respons på en film som
almindelige, synlige fotoner.

Det er faktisk denne effekt man den dag i dag anvender til akkumulerende
persondosimetre, altså passive målere der viser hvor meget
(røntgen)stråling en person er blevet udsat for over et stykke tid --- i
har sikkert bemærket de der små plasticæsker mange læger render rundt
med uden på kitlen --- det er såmænd bare et stykke fotografisk film med
en sjov hat på. Men hvad har dét nu at gøre med prisen på flæskesteg?
Jo, nu skal du høre...

For nylig var jeg i embeds medfør på en lille tur til Finland, og
undervejs slog det mig at Dr. P på et tidspunkt for nylig havde sendt
mig et [link](http://www.news.wisc.edu/23166), der påstod at man kunne
måle kosmisk stråling med kameraet i sin mobil / staveplade. På samme
måde som røntgen og anden ioniserende stråling kan sværte en film, så
kan det også anslå én eller flere pixels i en CCD eller anden
detektorchip i et digitalkamera.

Så jeg besluttede mig for et lynhurtigt og meget diskret regelbrud i
videnskabens navn. Man må jo (tilsyneladende) ikke tage billeder eller
filme i sikkerhedskontrollen, men alligevel tog jeg chancen og satte min
mobiltelefon til at optage video inden jeg lagde den ned i min lukkede
jakkelomme. Herefter lod jeg jakke og mobil tage den sædvanlige tur
gennem sikkerhedskontrollen, inklusive gennemlysning.

Herefter stod jeg så med ca. 8 minutters video[^3] der primært bestod
af sort skærm og et temmeligt skramlende lydspor. Nå, men inden jeg
begyndte at kaste flere kræfter og systematisk analyse efter det, så
kunne jeg da godt lige gennemse det visuelt og se om der var noget at
komme efter.

Og Hereuka! Blink and you'll miss it, men nogle enkelte frames har
tydelige spor af at være blevet ramt af noget der får detektoren til at
slå ud --- det ligner mest et dårligt billede af en nattehimmel,
indersiden af en lomme eller en fejl i detektoren (hvilket det jo også
simulerer), men der er signal!

[![]({{site.url}}/images/-4rdh3Z8az3w/VGEFzd99i2I/AAAAAAAACgI/nwPPhUNeav4/s1600/vlcsnap-2014-11-10-19h32m46s855.jpg)]({{site.url}}/images/-4rdh3Z8az3w/VGEFzd99i2I/AAAAAAAACgI/nwPPhUNeav4/s1600/vlcsnap-2014-11-10-19h32m46s855.jpg)

Ja, det er hvad vi har at arbejde med --- og der kun nogle enkelte frames
á 33ms hvor det overhovedet er synligt... men måske er der flere, hvor
man bare ikke kan se det med øjet?

Så er det vist på tide at finde pythonen frem! [^4]

Så 10 liniers klytkode og lidt slangetæmning på mellemniveau senere er
jeg kommet overens med cv2-biblioteket til billedanalyse og har fået
genereret en enorm tekstfil med en primitiv værdi for mængden af lys i
hver enkelt af de 14854 frames der er i filmen...

Og sådan noget er jo ret let at visualisere med R[^5] --- Først det rå
plot:

[![]({{site.url}}/images/-7MevuPMYTk4/VGEK2TP801I/AAAAAAAACgY/ZEBH-FiaT9U/s1600/gennemlysning_raw.png)]({{site.url}}/images/-7MevuPMYTk4/VGEK2TP801I/AAAAAAAACgY/ZEBH-FiaT9U/s1600/gennemlysning_raw.png)

Nåja --- der er jo nok nogle ikke-helt-mørke frames i start og slut mens
jeg får fumlet den op og ned af lommen, så det er der ikke meget spas i.
Lad os zoome lidt ind på det område omkring 6'03'' hvor jeg så glimt på
detektoren:

[![]({{site.url}}/images/-iJDtLMk7iYQ/VGELPzo6yTI/AAAAAAAACgg/QVHSwg9o4pU/s1600/gennemlysning.png)]({{site.url}}/images/-iJDtLMk7iYQ/VGELPzo6yTI/AAAAAAAACgg/QVHSwg9o4pU/s1600/gennemlysning.png)

Jojo, nu er der da helt sikker noget --- jeg har mere eller mindre
arbitrært lagt et cutoff ind, hvor der er 4 sikre datapunkter over, og
et under som man kunne tage med hvis man var desperat nok.

Bemærk også den sjove periodiske tendens de øvrige datapunkter har --- jeg
er ikke sikker, men jeg tror det er et artefakt af at det er et
komprimeret videoformat min telefon optager i. Her gemmer man ikke alle
billederne fuldt ud, men kun fx ét hvert sekund, hvorefter man bare
gemmer forskellen fra denne "keyframe" og så rekonstruerer billederne ud
fra denne forskel. Derved kunne man sagtens forestille sig at fejl og
støj også akkumuleres, navnlig når der ikke er noget lys på detektoren,
og at denne fejlfunktion så nulstilles hver gang der tages en ny
keyframe.

Så vi kan altså konkludere at selv den temmeligt svage røntgen i en
moderne lufthavn uden videre kan detekteres med en lillebitte CCD-chip i
en mobiltelefon.

Dr. P har netop foreslået at man legede lidt med den store CMOS sensor i
et rigtigt kamerahus... Det kunne være sjovt at se om man kunne
detektere mindre hverdagskilder på den måde --- radondøtre i en kælder,
måske? K-40 i såkaldt "sundhedssalt"?

Gå ud og leg med verden og videnskaben!

Som altid uddeler jeg gerne kode, rådata og andet til interesserede ---
eller bytter med kolde pilsnere.

\\Worm

---------------------------

[^1]: Ja, det er jo som sagt en perspektivering helt tilbage til
    dengang mor var en lille dreng og gik i korte bukser og optog
    ferieminder på fysiske filmstrimler... I dag er de fleste, hvis ikke
    alle, gennemlysningsstationer vist nok ikke skadelige for fotografisk
    film. De kan dog, som I kan se, stadig lave bitflip i halvledere, så det
    er jo nok en god ide at slukke sit elektroniske udstyr helt inden man
    sender det gennem sikkerhedskontrollen...

[^2]: Jaja, tøhø...

[^3]: Der var lidt kø, og jeg skulle jo være lidt diskret...

[^4]: Nej, nej, I behøver ikke holde de små børn og unge piger for
    øjnene, jeg taler naturligvis om prorammeringssproget - hvad ellers?

[^5]: Eller matplotlib, eller gnuplot eller... (gys) Excel, for den
    sags skyld... Jeg bruger bare det jeg har lettest ved at tale med...
