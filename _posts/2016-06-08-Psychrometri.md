---
layout: post
title:  "Psychrometri: Er du varm og/eller våd?" 
date:   2016-06-08
author: "Martin Worm-Leonhard"
tags:
- Metrologi
- Meteorologi
comments: true
---

Med den nyligt overståede varme- og/eller hedebølge i mente, så er det jo værd at bemærke at mennesker fra naturens side er udstyret med fordampningskøling: Det kan godt være det ikke er særligt lækkert at svede, og det føles måske heller ikke specielt behageligt, men det _er_ nu en gang ret praktisk, når vi nu er afhængige af at holde vores kernetemperatur stabil. 
Når vi sveder, så afkøles vi gennem fordampningen af vand fra hudens overflade. At vi så føler os lidt nussede bagefter skyldes ofte at der jo også er olier, salte og proteiner til stede i sved, og at de ikke fordamper, men efterlader et mere-eller-mindre klæbrigt lag på overfladen af huden.

Men... Der er tidspunkter hvor det ikke hjælper ret meget at svede --- fx hvis man er i en regnskov, eller måske i dampbad. For at fordampningskølingen skal virke ordentligt, så skal vi jo kunne komme af med vandet. Vi har kun ét sted at aflevere det, og det er til luften. Hvis den melder "alt udsolgt", så der ikke er plads til mere vand, så kan sveden jo ikke fordampe, og ender i stedet med at havne i sandalerne, uden at kunne køle.

Hvorfor nævner jeg lige regnskove og dampbade? Jo, det er klassiske eksempler på steder der har meget høj relativ luftfugtighed. Den relative luftfugtighed er et mål for hvor mættet luften er med vanddamp. 100%RH[^1] svarer til at luften er fuldstændig mættet med vanddamp, og dermed ikke kan optage mere. Så hjælper det overhovedet ikke at svede. 0%RH er den tøreste luft vi kan have --- den indeholder ingen vanddamp overhovedet. 

Begge ovenstående scenarier er stærkt usædvanlige i den virkelige verden, men det er jo heller ikke fordi det skal være enten-eller for at være potentielt ubehageligt[^2]. 

Hvis du nogensinde har været i et badeland eller lignende institution med både dampbad og sauna, så har du måske undret dig over at et dampbad ved 40--45&deg;C kan være meget sværere at tåle end en sauna ved 70--80&deg;C. Det er fordi det ikke hjælper noget at svede når man er i dampbad --- luften indeholder allerede al det vand den kan, så du kommer ikke af med varmen på den måde, og derfor føler du også i højere grad at det "hagler af dig". Saunaen har derimod relativt tør luft, så der hjælper det faktisk at svede, og derfor kan man tåle en højere temperatur.[^3]

Nå, men vi skal jo også til sagen --- men faktisk er hele ovenstående svada både en udmærket begrundelse for hvorfor det er relevant/interessant at måle den relative luftfugtighed, men det forklarer også ret godt hvordan man gør det på en snedig måde...

Man tager i al enkelhed to termometre. De skal helst være ens, eller i hvert fald kalibreret sammen. Det ene pakker man ind i våd køkkenrulle, vat eller lignende. Når jeg siger "våd", så mener jeg "vædet med rent vand". Det er jo ikke luftens indhold af vodka vi skal måle.[^4]

Man lader nu begge termometre nå til ligevægt, i skyggen og med rigelig luftstrøming forbi dem begge. Det lyder måske lidt fancy, men i virkeligheden kan det (eksempelvis) gøres såden her (Øllen er til mens man venter på ligevægt):

[![Opstillingen]({{site.url}}/images/psychrometer-opstilling.jpg)]({{site.url}}/images/psychrometer-opstilling.jpg)

Som man kan se på mit screenshot herunder, så målte det tørre termometer 25&deg;C, og det våde målte 18&deg;C. 7 graders forskel/afkøling bare med lidt våd køkkenrulle i skyggen --- det synes jeg alligevel var et ret sjovt og utvetydigt resultat.

[![Opsamlingen]({{site.url}}/images/psychrometer-screenshot.png)]({{site.url}}/images/psychrometer-screenshot.png)

Nu kommer den snedige argumentation: Jo mere vand der er i luften, jo mindre vil fordampningen afkøle det våde termometer, og ved 100% luftfugtighed vil de vise det samme. Desværre er det sådan at hvor meget vand der i alt, absolut kan være i en given mængde luft også afhænger af temperaturen, så vi er ikke helt færdige endnu --- der er en konverteringsfunktion, men den er hverken intuitiv eller simpel, så jeg valgte i stedet at slå op i en [tabel som jeg googlede mig frem til](https://www.eduplace.com/science/hmxs/es/pdf/5rs_3_2-3.pdf), og her kunne jeg aflæse at når det tørre termometer (tørmometer?) er 25&deg;C og der er 7&deg;C forskel, så er den relative luftfugtighed 51%RH.

Ifølge min google-fu, så var middelluftfugtigheden over postnummer 5000 den dag et sted omkring 58%RH, så det er meget muligt min altan har været lidt tørere, eller på anden måde finden en helt acceptabel forklaring på den smule fejlvisning.

Endelig skylder jeg lige at sige at jeg syntes det var sjovt at blive lidt stædig og tvinge/lokke Python til at aflæse mine USB-termometre under Linux, og det derfor blev et næsten-heldags projekt, men at man med almindelig gammeldags analog hardware kan lave en måling på 5--10 minutter. Det er herligt at være nørd ;-)

Vil du gerne læse mere? --- så er der fx nogle kinesere der har skrevet en [artikel om at gøre det med automagisk i en mikrocontroller](http://maxwellsci.com/print/rjaset/v6-2984-2987.pdf), og der er også nogle helt fine artikler på [Tante Wiki](https://en.wikipedia.org/wiki/Psychrometrics), både [generelt om måling af luftfugtighed](https://en.wikipedia.org/wiki/Hygrometer) og om den specifikke ["Våd-temperatur"](https://en.wikipedia.org/wiki/Wet-bulb_temperature).

Og nej. "Psychrometri" er ikke en stavefejl. Til gengæld er det et herligt ord, der smager godt --- både varmt og koldt! ;-)

Med Hygrometriske Hygge-hilsner  
\\Worm

------------------------------

[^1]: Relativ humiditet --- blot en latinisering af "fugtighed".

[^2]: Bare spørg Kierkegaard.

[^3]: Ja, det er som altid en smule mere kompliceret end som så --- fugtig luft er også bedre til at flytte varme end tør, så derfor varmer den dig også mere effektivt op, så generelt har man bare tabt hvis man forsøger at være cool i et dampbad.

[^4]: Selvom det selvfølgelig snart er festivaltid...
