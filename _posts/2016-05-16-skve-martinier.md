---
layout: post
title:  "Den skæve martini" 
date:   2016-05-16
author: "Martin Worm-Leonhard"
tags:
- Hovedbrud
- Skæg med tal
- Modellering
comments: true
---

Her i starten af pinsen sad Nørdinden og undertegende og nød den postprandiale somnolens[^1], da jeg pludselig faldt over en sjov opgave, som vi følgelig måtte skynde os at pusle lidt med. Opgaven handlede, meget relevant for weekenden, om væskestanden i et martiniglas.

Hvis man nu tager et martiniglas, der jo som bekendt er konisk, og antager at det er fyldt til en eller anden brøkdel, p,  af sin højde, hvorefter man tipper glasset, så det næsten løber over, altså så væsken står præcist op til kanten på den ene side. Hvor højt står væsken så på den anden side?
Den originale opgavetekst kan ses ved [Fivethirtyeight](http://fivethirtyeight.com/features/can-you-solve-the-puzzle-of-the-overflowing-martini-glass/).

Vi startede med at forsøge at være matematikere og videskabelige og løse det generelle tilfælde analytisk:
[![]({{site.url}}/images/martiniregne.jpg)]({{site.url}}/images/martiniregne.jpg)

Det blev bare meget hurtigt til noget rod med dobbeltkrumme flader og en geometri der bare generelt ikke var specielt samarbejdsvillig.

Så var det at Nørdinden styrtede ud i køkkenet og begyndte at rode skabe og skuffer igennem --- noget jeg primært havde undladt, idet jeg vidste at vi ikke ejede et martiniglas (Ja, jeg skammer mig passende). I stedet viser hun sand ingeniørtankegang og kommer tilbage med en tragt, som hun har stoppet hullet i ved hjælp af stemplet fra en 10mL engangssprøjte.

I denne tragt fylder vi nu forskellige mængder vand, slår streger på ydersiden i hhv. normal og tippet konfiguration, og efter at have lavet tre punkter på denne måde måler vi det hele op med et almindeligt målebånd og det forkromede øjemål.

Ud over de tre fyldningsgrader ved vi jo allerede at hvis man har drukket hele martinien, så er der ikke noget tilbage at vippe med, så nul bliver til nul. Hvis man slet ikke har rørt den og den er randfuld, så kan den ikke tippes, så 1 bliver til 1. De øvrige brøkdele plottes sammen med disse punkter i R, og så får man følgende meget smukke plot:
[![]({{site.url}}/images/martiniplot.png)]({{site.url}}/images/martiniplot.png)

Tendenslinien der er lagt ovenpå gættede vi meget hurtigt ved at bemærke at "cirka en halv" bliver til "cirka en kvart" og at den generelle tendens var at jo mere tomt glasset var, jo mere faldt væskestanden. Det måtte altså være en potensfunktion, og potensen 2 passede visuelt meget godt.

Altså: er glasset i lodret konformation fyldt til brøkdelen p, så er det i tippet konfiguration fyldt til brøkdelen \\(p^2\\). Starter det med at være halvt fyldt når væsken altså \\(0.5^2 = 0.25 \\) en fjerdedel op af siden, når det er tippet og så fremdeles.

Så vi lod det egentlig være ved det og konstaterede at det føltes / lugtede meget rigtigt, og desuden var der en sofa der kaldte.

Det er for sent at sende svar ind til den originale konkurrence, men jeg modtager altid gerne løsning, forslag og irettesættelser...
Og nu har jeg oven i købet fået både social-medie-integration og diskussionsforum op at køre, så der er jo ikke rigtig nogen grund til at lade være med at fortælle os hvor vi tog fejl :-)

Hvis nogen kan folde den analytiske løsning, så vil vi meget gerne høre om det --- og også gerne publicere det, hvis vi må og det ønskes.

\\Worm --- Spiritus al-kuhul

[^1]: Ja altså det at man bliver træt når man har spist, det er ikke noget sjofelt... Selvom det jo naturligvis kan udvikle sig...
