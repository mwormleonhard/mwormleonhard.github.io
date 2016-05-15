---
comments:true
layout: post
title: '02 DEC: Fødselsdagsparadokset'
date: '2013-12-02T10:00:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Julenørd
- Skæg med tal
- Statistik
modified_time: '2013-12-02T10:00:07.410+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8962075418443235129
blogger_orig_url: http://labnoter.blogspot.com/2013/12/02-dec-fdselsdagsparadokset.html
---

Måske ikke så juleagtigt ved første øjekast, men højtiden er jo noget
med at mødes med familie og venner, og der er noget med Jesu fødselsdag
og vi kender sjovt nok næsten alle sammen én der har fødsesdag
juleaften, eller så tæt på at det er ligegyldigt, og har lidt ondt af
dem, hvis deres familier og/eller såkaldte venner insisterer på at slå
fejringerne og/eller --- endnu værre --- gaverne --- sammen.

Hvis vi kigger på sandsynligheden for at en given person har
fødsesdag juleaften(sdag) - eller en hvilkensomhelst anden arbitrær dag,
så er den med god tilnærmelse 1:365[^1]

Det sjove spørgsmål er nu: Hvor mange mennesker skal man samle, før
sandsynligeheden for at der er to med den samme fødsesdag er 50%?

Her gør mange den hurtige, men fejlagtige antagelse at det må være noget
med halvdelen af antallet af dage på et år, altså ca. 180-190 stykker.
Dette argument ville have nogen gyldighed hvis vi ledte efter nogen med
en specifik fødselsdag - altså havde låst datoen fast på én person, men
her er alle personer, og deres fødsesdage, at betragte som uafhængige.

Derfor skal vi i stedet vende argumentet om og se på det således:  
Den første person vi betragter kan frit "vælge" en dag at have
fødselsdag på --- han konflikter ikke med nogen af de andre, der er kun
ham, så sandsynligheden for at undgå kollision af datoer er 365/365 = 1.
Den næste har 364 dage og den tilhørende sandsynlighed for unik
fødsesdag er 364/365, den tredje har 363 dage etc.

Alle disse sandsynligheder er uafhængige, og således skal de ganges
sammen for at få den samlede sandsynlighed.

Herved fremkommer produktet: \\[\frac{365\cdot364\cdot363\cdots(366-n)}{356^n}\\] hvor \\(n\\) er
antallet af personer i gruppen. Laver man denne øvelse[^2] opnår man
det ret fascinerende resultat at man kun behøver 23 personer for at
sandsynligheden for at alle har unikke fødsesdage passerer de 50% for
nedadgående.

En anden, måske mere intuitiv måde at forstå det på, er at lave følgende
tilnærmelse:

Se på antallet af relationer (kombinationer) *mellem* par af 2 personer
ud af \\(n\\) --- der vil være \\(\frac{n\cdot(n-1)}{2}\\) af disse
kombinationer. Sandsynligheden for at to tilfældige mennesker har
forskellige fødsesdage er stadig 364/365. Sandsynligheden for at \\(n\\)
mennesker alle har forskellige fødsesdage kan så tilnærmes som: \\[
P(n)=\left(\frac{364}{365}\right)^{\frac{n\cdot(n-1)}{2}}\\]
og denne passerer også 50% for nedadgående når n går fra 22 til 23.

Så - nu ved du altså hvorfor over halvdelen af alle skoleklasser (eller
arbejdspladser/afdelinger/...) indeholder et par elever/ansatte/... med
samme fødselsdag - Det kræver ikke nær så meget som man skulle tro. Leg
selv med tallene og se hvor (u)sandsynlig netop fordelingen i din
omgangskreds er.

\\Worm - enebarn.

------------------------------------------------------------------------

[^1]: Uden skudår og under den ikke HELT korrekte antagelse at der fødes
    lige mange børn på alle årets dage, men det er i det område.

[^2]: Som overlades til den vågne l\[æø\]ser


