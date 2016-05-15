---
comments:true
layout: post
title: Om gynger og penduler
date: '2014-11-18T14:08:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Tivolifysik
- Mobiltelefon
- Weekendvidenskab
modified_time: '2014-11-18T14:08:11.237+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-8097221570221601556
blogger_orig_url: http://labnoter.blogspot.com/2014/11/om-gynger-og-penduler.html
---

For et par uger siden var jeg ude at besøge nogle venner der har bygget
en nørdling, og det er jo meget hyggeligt. (Se, mor! Det er en Nørd! Ja,
det er Onkel Worm - det er rigtigt...)

Men sådan nogle skal jo (ligesom større nørder) også luftes lidt en gang
imellem. I dette tilfælde gik turen til en nærliggende legeplads med
tilhørende gyngestativ, og eftersom bemeldte legeaggregat virkede solidt
nok til at bære både nørdlingen og de ca. 90kg legebarn der udgøres af
jeres ikke specielt ydmyge skribent[^1] var der jo en oplagt mulighed
for at lave et lille forsøg. Frem med mobiltelefonen. Op på gyngen. Hvem
siger at fysik ikke er sjovt?

En gyngetur er jo faktisk bare en oplevelse af at være et simpelt
pendul, forudsat at man kan sidde helt stille og stå for fristelsen til
at forsøge at accelerere.[^2] Der findes en udmærket youtube-video der beskriver meget
af fysikken, og den kan du se lige her nedenfor.[^3]

{%include youtubeframe.html id="UXo6WvHRs_I" %}

Kort sagt ville jeg gerne se hvor pæn og regulær en svingning jeg kunne
lave, og om det var muligt at sammenligne min svingningstid med den
teoretiske. Den mest velegnede sensor i mit lommelaboratorium var
"Lineær acceleration", så den blev sat til at logge så meget og hurtigt
som den kunne --- næsten 200Hz, til min store glæde og imponade.

Opsamling og analyse af accelerationsdata er forholdsvist enkel[^4] og
diskuteret flere andre steder i mine skriblerier, så lad os bare kaste
de rå data på bordet:

[![]({{site.url}}/images/-674i5HeGF0o/VGs728X1DjI/AAAAAAAAChU/GsQ0u40FT5Q/s1600/Gynge-alle.png)]({{site.url}}/images/-674i5HeGF0o/VGs728X1DjI/AAAAAAAAChU/GsQ0u40FT5Q/s1600/Gynge-alle.png)

Her ser vi jo straks at der er lidt fnidder i starten mens jeg kommer i
stilling, og at efter at have svinget frit et lille minuts tid kunne jeg
ikke helt afholde mig fra at få lidt mere fart på, men det må være en
diskussion/simulation til en anden dag. Hvis vi skærer alt det ikke helt
regulære bort får vi:

[![]({{site.url}}/images/-E96RjZKaIac/VGs8iaNaCRI/AAAAAAAAChc/6X4tlgViI8I/s1600/gynge-fri.png)]({{site.url}}/images/-E96RjZKaIac/VGs8iaNaCRI/AAAAAAAAChc/6X4tlgViI8I/s1600/gynge-fri.png)

Og det er jo så smukt og periodisk at man må knibe en tåre (og undre sig
over hvordan jeg sad stille så længe) og man kan jo allerede tælle at
det er cirka 10 hele svingninger på 30 sekunder, så det må jo være en
svingningstid på cirka 3 sekunder. Og det er jo sådan set godt nok til
mange formål, men nu har jeg jo ferie og derved god tid til at
hyggenørde, så mon ikke en lille FFT / spektralanalyse var på sin plads,
bare for at se om det er muligt og hvor "rene" data er. Ergo:

[![]({{site.url}}/images/-_cuR2W7fFdQ/VGs-e2z7bnI/AAAAAAAACho/lpntDNQSYmU/s1600/gynge-spektrum.png)]({{site.url}}/images/-_cuR2W7fFdQ/VGs-e2z7bnI/AAAAAAAACho/lpntDNQSYmU/s1600/gynge-spektrum.png)

Og minsandten om ikke det viser præcis det jeg troede og håbede --- én
klar peak et sted nede mellem 0 og 0.5 Hz. Kaster man den rigtige
besværgelse over fouriertransformationen kan man få den præcise værdi
for den mest intense frekvenskomponent ud: \\(f_{gynge} = 0.332Hz\\)
svarende til en svingningstid på  \\(T_{gynge} = \frac{1}{0.332Hz}=3.01s\\).

Snupper vi lige en lynhurtig formelsafari, så kan vi se at
svingningstiden for et frit svingede pendul er givet ved: \\[T=2 \pi
\\sqrt{\frac{l}{g}}\\]
Hvor l er længden af pendulet, fra omdrejningspunkt til massemidtpunkt,
og g er tyngdeaccelerationen. Hvis jeg stod oprejst på gyngen kunne jeg
lige akkurat nå lejet den var ophængt i, så længden er nok ca. 2m[^5],
og tyngedeaccelerationen er jo sædvanligvis \\( \approx 9.8 \frac{m}{s^2}\\), hvorved vi får 
\\[T_{teori}=2 \pi \sqrt{\frac{2m}{9.8 \frac{m}{s^2}}}=2.84s\\]

Umiddelbart er der altså en forskel på ca. 6% fra den teoretiske værdi,
og det er jo et ganske acceptabelt resultat. Den største fejlkilde er jo
nok sjusningen af pendulets længde, og det er jo muligt med lidt
fingergymnastik at udregne den reelle længde, hvis vi antager at det er
vores måleresultat der er korrekt --- så får vi 2.25m, hvilket jo heller
ikke er helt ude i skoven, mine orangutanarme taget i betragtning.

Det var gyngerne --- så mangler vi jo karusellerne... Eller måske den
dæmpede svingning på en af de der fjederfandener... Smut så ud og leg ---
og lav jer nogle data!

\\Worm

------------------------------------------------------------------------

[^1]: På forskellige gynger naturligvis - man skal jo ikke traumatisere
    afkommet - eller kompromittere datakvaliteten.

[^2]: Svært, ja, men for videnskaben...

[^3]: Så slipper jeg (næsten) for at skulle være fysiker i denne
    omgang.

[^4]: Jeg brugte Sensor Kinetics Pro til opsamling og R til
    dataanalyse. Brug hvad du har. Your mileage may vary.

[^5]: Dårlige vittigheder om beliggenheden af mit massemidtpunkt
    frabedes. Gode er okay.
