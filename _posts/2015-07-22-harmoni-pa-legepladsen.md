---
layout: post
title: Harmoni på legepladsen
date: '2015-07-22T22:13:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Energi
- Kræfter
- Modellering
- Tivolifysik
- Mobiltelefon
- Billedanalyse
modified_time: '2015-07-22T23:42:17.262+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8998957199583073019
blogger_orig_url: http://labnoter.blogspot.com/2015/07/harmoni-pa-legepladsen.html
---

For nogen tid siden var jeg ude at besøge Simultantolken --- vi skulle
lige have lagt nogle skumle planer om noget der måske bliver til et
bogværk en dag --- men det hører I i givet fald nærmere om. Imidlertid
sker der jo det at hun på et tidspunkt må forlade huset kortvarigt, for
at hente sin nørdling --- jeg bliver udstyret med en kop kaffe, en nøgle,
og en åben tilladelse til at lege[^1].

Efter at have drukket kaffen og filosoferet lidt over hvorfor man kan
stikke et sugerør gennem en kartoffel hvis man holder for den ene ende
når jeg frem til at jeg jo lige så godt kan give efter for mine
dybtliggende impulser --- og gå hen på legepladsen.

Dér finder jeg mange sjove ting og muligheder... men jeg bliver
alligevel fascineret af en af de der fjeder-gyngeheste --- i ved --- sådan
en hér:

[![]({{site.url}}/images/-akUIQKJB82c/Va_klGsx4VI/AAAAAAAADBQ/FHC7EiME8j0/s400/vlcsnap-2015-07-21-20h33m20s300.png)]({{site.url}}/images/-akUIQKJB82c/Va_klGsx4VI/AAAAAAAADBQ/FHC7EiME8j0/s1600/vlcsnap-2015-07-21-20h33m20s300.png)

Og jeg kom uvilkårligt til at tænke på at det jo med god tilnærmelse er
(eller i hvert fald kunne være) en [dæmpet harmonisk
oscillator](https://en.wikipedia.org/wiki/Harmonic_oscillator#Damped_harmonic_oscillator)...
Men hvordan måler eller karakteriserer man dét? Hmmm......

Man KUNNE jo gaffae eller stripse[^2] sin debilxylofon fast til sædet
(eller hovedet (altså af hesten)) og sætte den i gang og så bruge
accelerometeret --- men det ER jo prøvet, og jeg havde ikke lige gaffa i
lommen og kun de korte strips i tasken.

Hmmm... Hvis man nu bare optog den på video? Så kunne det jo være at
man kunne bruge en af de hvide knopper, der sikrer at nørdlingerne ikke
kommer til skade på bolte eller møtrikker, til at følge bevægelsen?

Jo, det må være en passende udfordring --- jeg har også ønsket mig at lave
noget mere billedanalyse.

Så --- muligvis fik simultantolken efterfølgende nogle undrende
henvendelser fra grundejerforeningen efterfølgende, men jeg
trak/tvang/svingede altså hesten ud i yderposition, slap den så rent som
muligt og kastede mig hed i græsset og startede en videooptagelse på min
mobiltelefon. Den ser cirka sådan her ud:

{%include youtubeframe.html id="MwRCj3zz-aA" %}

Ja, det er jo lidt kedeligt og pletvist en anelse rystet... Altså
videoen[^3]. Den er også lidt pixelleret, men altså --- originalen er
304MB --- denne her er har jeg stampet voldsomt på...

Nå, men jeg har jo selv redt min billedanalyseseng, så jeg må jo hellere
lægge mig i den...

Heldigvis har jeg tidligere bygget et lille program i Python til at lege
interaktivt med nogle væsentlige parametre i billedanalyse, nærmere
bestemt funktionen cv2.HoughCircles fra [opencv](http://opencv.org/)
billedanalysepakken, der kan --- tadaaa... Finde cirkler i et
billede.[^4]

Jeg troede det letteste var at finde en af de hvide boltbeskyttere --- og
det var det også --- det svære var at nøjes med at finde én af dem --- og
den samme hver gang. Så jeg endte med at finde hestens øje i stedet.
Undevejs så et af mine adskillige aktive skriveborde således ud:

[![]({{site.url}}/images/-PSgs_abg7G4/Va_ojIaq4wI/AAAAAAAADBc/AiDD5ihIYTs/s400/Screenshot%2Bfrom%2B2015-07-21%2B21%253A19%253A30.png)]({{site.url}}/images/-PSgs_abg7G4/Va_ojIaq4wI/AAAAAAAADBc/AiDD5ihIYTs/s1600/Screenshot%2Bfrom%2B2015-07-21%2B21%253A19%253A30.png)

Bemærk at jeg er gået i sort-hvid og har beskåret billedet ret kraftigt.
Det er fordi det giver et meget mindre datasæt at analysere, og kan
således faktisk foregå i pseudo-realtid[^5] og uden at kræve
menneskelig indgriben.

Og ja --- de 20 linier pythonkode I ser i baggrunden var faktisk alt hvad
det krævede at konvertere over 300MB video af en gyngehest til en flad
tekstfil på ca 80kB der beskriver øjets position i hver eneste frame.

Udstyret med denne fil kunne jeg jo fyre op under R og forsøge at se om
det gav noget brugbart --- først tilføjede jeg lige en søjle med tiden i
millisekunder --- det er jo ret let at beregne, når man har 29.83 billeder
i sekundet, så har man 33.52 ms per billede. R laver nogle udmærkede
scatterplotmatricer til eksplorativ dataanalyse:

[![]({{site.url}}/images/-5j9q723y3zo/Va_quC5gTbI/AAAAAAAADBo/t_31IJcKpSY/s400/gyngehest-scatterplot.png)]({{site.url}}/images/-5j9q723y3zo/Va_quC5gTbI/AAAAAAAADBo/t_31IJcKpSY/s1600/gyngehest-scatterplot.png)

Ud af dette lidt rodede billede kunne man se at det faktisk var
placeringen af øjet på X-aksen som funktion af tid, der var mindst
påvirket af vind og vejr og rystende hænder - det er i hvert fald en pæn
trompet-/jointform uden alt for mange knæk[^6]

Så lad os isolere denne, centrere den om nul (trække middelværdien fra)
og se på de første par sekunder:

[![]({{site.url}}/images/-sdGbnIJMG-E/Va_sXaoTPuI/AAAAAAAADB0/yNkeePXQY0c/s400/gyngehest-xtid.png)]({{site.url}}/images/-sdGbnIJMG-E/Va_sXaoTPuI/AAAAAAAADB0/yNkeePXQY0c/s1600/gyngehest-xtid.png)

Og det er jo så smukt at man nærmest må knibe en tåre. Det er så ren en
sinus/cosinus at man skulle tro jeg havde snydt.

Ser man på hele forløbet, så ser det sådan ud:

[![]({{site.url}}/images/-1S6EhYa99bQ/Va_tSLJdm5I/AAAAAAAADB8/Fd0grjT4KbA/s400/gyngehest-eyex-total.png)]({{site.url}}/images/-1S6EhYa99bQ/Va_tSLJdm5I/AAAAAAAADB8/Fd0grjT4KbA/s1600/gyngehest-eyex-total.png)

Og her kan man jo se følgende:


1.  Jo, der er nogle enkelte outliere, hvor algoritmen har fanget
    noget andet. De får lov at leve --- de er så få at de ikke får stor
    indflydelse på fittingen af den beskrivende funktion
2.  Den lander ikke helt på nul og krummer en anelse --- muligvis
    fummelfingret kameramand. Lad os se om vi slipper godt fra det.
3.  Det er svært at se her (men meget tydeligt hvis man zoomer) --- men
    data fortætter med at have stort set samme frekvens, uafhængigt at
    amplituden --- den er altså lige lang tid om at rokke en tur frem og
    tilbage, uanset om den næsten er nede at kysse jorden, eller om den
    bare står og rokker blidt. Det er jo netop i god overensstemmelse
    med teorien!

Okay, så --- vi har nu noget der aftager asymptotisk mod nul: Amplituden,
vi har noget der er konstant: Frekvensen, og så har vi et par
skaleringsfaktorer (fase, og amplitudens maksimum) --- så vi skal altså
fitte et udtryk der ser cirkus sådan her ud: \\[ EyeX=A \cdot e^{-kt}\cdot \cos(\tau\cdot t + \phi) \\] 
Hvor EyeX altså er
positionen af gyngehestens øje (i pixels), t er tiden (her i ms), A er
det maksimale udsving, k er hastighedskonstanten --- hvor hurtigt
svingningen dæmpes, \\(\tau\\) er tidskonstanten for svingningen --- hvor
hurtigt går det for en hel svingning og \\(\phi\\) er fasen - der
beskriver hvor på kurven svingningen starter.

Det var en længere svada, og jeg er da også glad for at jeg bare kunne
fodre R med at jeg gerne villa have modellen til at se sådan ud og så
kunne den finde konstanterne ved Nonlinear Least Squares optimering...

Troede jeg...

Det viste sig at når man har en dæmpet harmonisk svingning beskrevet ved
4248 punkter, så er der mange lokale minima, som sådan en algoritme kan
falde ned i[^7], men lidt kælen for modellen[^8] og nogle rimelige
startbetingelser gav et ret godt fit... Faktisk endte det med at se
sådan her ud for de første 10 sekunder:

[![]({{site.url}}/images/-qO50gTft2wk/Va_yd7TKHqI/AAAAAAAADCM/NycXgJ1mkXE/s400/gyngehest-modelfit.png)]({{site.url}}/images/-qO50gTft2wk/Va_yd7TKHqI/AAAAAAAADCM/NycXgJ1mkXE/s1600/gyngehest-modelfit.png)

Her er de røde +'er data og den sorte kurve er model --- den synes jeg
godt jeg kan være bekendt.

Det bliver lidt værre når man zoomer ud og ser på det i sin helhed:

[![]({{site.url}}/images/-tS6sbZyZ-c0/Va_zqFjUUnI/AAAAAAAADCU/pPAH5Tqn7gA/s400/gyngehest-helmodel.png)]({{site.url}}/images/-tS6sbZyZ-c0/Va_zqFjUUnI/AAAAAAAADCU/pPAH5Tqn7gA/s1600/gyngehest-helmodel.png)

Her ses tydeligt at der er nogen afvigelse fra  virkeligeheden når vi
kommer ud over de første 20 sekunder, men ikke desto mindre er fase og
frekvens stadig nogenlunde passende --- og den er heller ikke HELT ved
siden af i vurderingen af hvor længe der går før den klinger ud og står
stille igen.

Jeg vil ikke trætte jer med parametrene, for de er ikke så vigtige i
denne sammenhæng som det faktum at selv med disse ret primitive data:
Håndholdt mobilkamera, tilfældig gyngehest, sat i gang med håndkraft,
vind, vejr og vinkrelrethed er noget der bare må gå som det går, og
jeres ikke spor ydmyge skribent har skullet ligge helt stille i
adskillige minutter... og alligevel så kan man med 20 linier python og
10 linier R hive data ud og lave en helt anstændig model i løbet af en
aftens tid.

Det har aldrig været lettere eller sjovere at være en nørd!

Som altid kan I få data, kildemateriale og kode, hvis I ikke synes det
er sjovere at lave det selv...

\\Worm 

------------------------------------------------------------------------

[^1]: Letsindigt, ville nogen nok mene --- altså tilladelsen til at lege
    --- men når jeg har fået lov på forhånd, så er jeg jo på den anden side
    fri for at bede om tilgivelse bagefter.

[^2]: Jo, det er et ord.

[^3]: Og naboerne, muligvis.

[^4]: Jo, med nogle af de navngivningskonventioner jeg har set, så er
    det nødvendigt at specificere.

[^5]: Også kendt som "Hurtigt nok til at jeg ikke gider optimere
    yderligere"

[^6]: Så var det vel snarere et waldhorn eller en vandpibe.

[^7]: Lidt ligesom når man kører i grøften på vej hjem fra arbejde og
    ender med at være bankevissen, bare fordi øllerne er der --- også selvom
    man skal i byen senere.

[^8]: Den numeriske model, altså. Den langhårede model er ikke hjemme.
