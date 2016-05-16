---
comments: true
layout: post
title: Langhåret laserfysik
date: '2014-01-14T19:31:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Optik
- Laser
- Køkkenfysik
- Lys
modified_time: '2014-01-14T19:31:45.272+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5482766647721265774
blogger_orig_url: http://labnoter.blogspot.com/2014/01/langharet-laserfysik.html
---

En gang for længe siden så jeg et godt forsøg
på [fysikbasen.dk](http://fysikbasen.dk/) --- en i øvrigt udmærket samling
forsøg til inspiration og hyggenørden, både til skole- og hjemmebrug
(afhængig af éns køkken/laboratoriefaciliteter, naturligvis). 

Det gik ud
på at man tilsyneladende kunne [måle diameteren på et hår ved hjælp af
en laserpointer](http://fysikbasen.dk/index.php?page=Vis&id=87), og da
teorien så sund ud, og en hurtig test viste at det sandsynligvis var
holdbart og udførligt under standardbetingelser måtte jeg jo prøve.

Selv lider jeg ikke i udpræget grad af hårpragt, men heldigvis var
venner, kolleger og UNF'ere så venlige at donere et par løse hår, der
straks blev emballeret og gemt til jeg kunne tage mig sammen til at få
lavet forsøget.[^1]

Det var så nu, så træd nærmere, træd nærmere, ryk frem i vognen,
chaufføren gi'r bolcher!

Teorien siger at hvis man sender monokromatisk, kollimeret lys --- så som
en laserstråle --- gennem en smal spalte, så vil man se et
interferensmønster, altså et mønster af skiftevis mørke og lyse bånd,
hvis bredde og afstand vil afhænge af lysets bølgelængde, spaltens
bredde og afstanden mellem spalten og skærmen. Det kan I læse meget mere
om hos [Tante Wiki](http://en.wikipedia.org/wiki/Diffraction#Single-slit_diffraction),
så det vil jeg ikke gå i detajler med hér.

I stedet vil jeg bemærke at af forskellige årsager så gælder de samme
regler og formler hvis man putter et meget tyndt objekt (som fx, ja, et
hår) i vejen for en laserstråle. Så erstatter man bare spaltebredden med
hårets tykkelse, og så er dén ged barberet.

Jeg foldede altså lynhurtigt en forsøgsopstilling af en A5-blok, lidt
tape, to limklemmer, et par glas og en grøn laserpointer. Limklemmen
holder håret udstrakt, og man kan se hvor laseren rammer håret, ved at
der er en lysere plet pga. spredt lys. Det så cirka sådan her ud (den
anden limklemme holder aftrækkeren inde på laseren):

[![]({{site.url}}/images/384001cca322660a1adb0daa64dff5ab.jpg)]({{site.url}}/images/25e2777b978ccdc9140428d40fe1f677.jpg)

Minsandten om der ikke straks dukkede et smukt diffraktionsmønster op på
den modstående væg, i en sådan grad at jeg måtte klappe i mine fede
skumgummifingre og spontant udbryde "No, Mr. Bond, I expect you to die!"
--- inden jeg tog solbriller på (lyset er ret svært/ubehageligt at kigge
på, selv i reflekteret form) og fandt min trofaste lineal frem, og målte
afstanden mellem  hhv. første- og andenordens minima, dvs. hvor langt
der var mellem det første hhv. andet par af mørke bånd på hver side af
strålens center.

Dette gentog jeg for hver hårdonor, og tog middelværdien af de to
målinger for hver person.

[![]({{site.url}}/images/73b693ce4858c17dc1170ca74c6db6fb.jpg)]({{site.url}}/images/3b471b03de16b96adcd0425fce68c484.jpg)

Udstyret med disse data, samt afstanden mellem opstilling og væg (255cm)
og laserens bølgelængde (532nm) kan man begynde at regne, idet det vides
at: \\[d=\\frac{n \cdot \lambda}{\sin \theta_n}\\] 
Hvor d er
diameteren af håret, n er ordenen --- altså hvilket sæt af mørke områder
der bruges, og \\(\\theta_n\\) er vinklen som der er mellem
centerstrålen og det relevante mørke område. 

Denne vinkel er heldigvis
let at finde, hvis man kan sin trigonometri, den er nemlig
\\[\theta_n=\tan^{-1}\left(\frac{x}{l}\right)\\] Hvor
\\(\\theta_n\\) er som ovenfor, x er afstanden fra centerstrålen til
det relevante mørke område, og l er afstanden fra håret til væggen.

Et regneeksempel: Afstanden mellem de to førsteordens minima (mørke
områder) er 4,4 cm, altså er vinklen: 
\\[\theta_1=\tan^{-1}\left(\frac{2,2cm}{255cm}\right)=8,63\cdot 10^{-3} \text{ radianer}\\]
og diameteren bliver således:
\\[d=\frac{1 \cdot 532\cdot10^{-9}m}{\sin(8,63\cdot10^{-3})}=61,7\mu m\\]

Dette gentages for alle hår og giver derved følgende resultater:

| Nummer | Køn | Farve |  d-1 [m] |  d-2 [m] | d-middel [m] |
|:------:|:---:|:-----:|:--------:|:--------:|:------------:|
|    1   |  K  |  Rødt | 7,33E-05 | 6,78E-05 |   7,06E-05   |
|    2   |  K  | Blond | 6,17E-05 | 6,03E-05 |   6,10E-05   |
|    3   |  K  | Blond | 7,33E-05 | 7,05E-05 |   7,19E-05   |
|    4   |  M  |  Sort | 7,33E-05 | 7,24E-05 |   7,28E-05   |
|    5   |  K  | Blond | 9,69E-05 | 9,87E-05 |   9,78E-05   |
|    6   |  M  |  Sort | 9,04E-05 | 9,04E-05 |   9,04E-05   |
|    7   |  M  | Blond | 6,46E-05 | 6,31E-05 |   6,39E-05   |
|    8   |  K  | Blond | 6,03E-05 | 5,71E-05 |   5,87E-05   |


Altså i alle tilfælde et sted mellem 59 og 90 \\(\mu m\\) i diameter,
hvilket passer meget godt med at fysikbasen siger at hår generelt er
mellem 80 og 120  \\(\mu m\\), og Wiki siger 17 til 180  \\(\mu m\\).
Jeg synes ikke jeg har data nok til at jeg vil begynde at udtale mig om,
hvorvidt der er en funktion af hårfarve eller køn, men nu var det jo
også mest for at se om det kunne lade sig gøre, og det kunne det.
Mission accomplished.

Naturligvis kan man også måle andre småting end hår --- sytråd, ståltråd,
enkeltledere fra kobberledning og så videre --- måske man endda har en
wire med en kendt bredde? Så kan man jo "kalibrere" metoden --- eller i
hvert fald se hvor præcist man måler... Det havde jeg ikke lige, men
hvis du har gjort forsøget, så råb endelig højt i kommentarerne.

\\Worm

------------------------------------------------------------------------

[^1]: Og som jeg nu efterhånden har rendt rundt med i kuverter i min
    rygsæk i næsten et halvt år --- det havde været interessant at forsøge at
    forklare udenforstående --- men på den anden side er det nok ikke det
    mærkeligste jeg har i bemeldte beholder.
