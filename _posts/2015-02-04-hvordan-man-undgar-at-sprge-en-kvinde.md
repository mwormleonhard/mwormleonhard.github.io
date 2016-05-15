---
comments:true
layout: post
title: Hvordan man undgår at spørge en kvinde hvad hun vejer...
date: '2015-02-04T19:50:00.000+01:00'
author: Martin Worm-Leonhard
tags:
- Kræfter
- Bagsiden af kuverten
- Trigonometri
- Anna-og-lotte
modified_time: '2015-02-04T22:15:16.819+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-4152235515507869721
blogger_orig_url: http://labnoter.blogspot.com/2015/02/hvordan-man-undgar-at-sprge-en-kvinde.html
---

Bag den lidt kryptiske og i nogen grad traditionsbundne overskrift
gemmer sig et relativt hverdagsagtigt men også temmelig ingeniørrelevant
problem. Det hele startede for nogle uger sider, da Nørdinden forsøgte
at overbevise mig om at jeg skulle med til klatring[^1] --- et koncept
som jeg stadig ikke helt ved hvad jeg skal synes om... 

Så indledningsvis
forsøgte jeg at afværge med et modspørgsmål om hvem hun havde
forestillet sig skulle sikre mit kurfyrstelige kæmpekorpus mod
pludseligt og smertefuldt at adlyde tyngdekraftens kalden mens jeg
desperat forsøgte at hænge fast i en klump plastic spændt fast på noget
krydsfinér...

Hun mente ikke det var noget problem, idet man tilsyneladende må sikre
op til halvanden gange sin egen kropsvægt (der må være noget
taljeværk[^1a] involveret), hvorefter jeg iførte mig mit måske ikke
helt blankpolerede men dog forkromede øjemål og mine bedste fermibriller
og kunne oplyse hende om at det var nok stadig lige på kanten.

Nu er der ingen af os der er specielt følsomme over vores hvilemasse,
men det medfører så også at ingen af os er i besiddelse af en
personvægt, og i stedet for at gøre noget så trivielt som at finde én vi
kunne bruge, måtte vi jo udtænke en løsning --- og --- for sportens skyld ---
helst én der alene kunne afgøre spørgsmålet om jeg vejede mere eller
mindre end halvanden gang så meget, uden vi behøvede bestemme vores
respektive masser.

Hvordan gør man så det? Jo, nu skal I høre... Lad os alle regne...

Det mest oplagte var at forsøge at lave en slags vippearrangement
med en vægtstang hvor vi kunne sidde i hver sin ende og man kunne flytte
omdrejnings/understøttelsespunktet indtil vi var i balance. Så var
forholdet mellem vores masser jo helt simpelt forholdet mellem de to
længder vægtstang vi skulle bruge for at balancere.

Her opstod dog det praktiske problem at finde noget der var langt og
stift nok[^2] til ikke at gå i stykker eller deformere væsentligt under
belastningen, for ikke at tale om etableringen af det stabile
omdrejningspunkt --- vi overvejede at låne et par meter stålrør eller
armeringsjern på en nærliggende byggeplads, men det sneede udenfor og så
ville vi jo nok bare være endt med at bygge en snemand i stedet, hvis vi
endelig fik skrabet sofaen af ryggen.

Svaret meldte sig dog spontant under en balanceakt inspireret af en
diskussion om vektorer og projektioner --- hvis vi nu stillede os på
hinandens fødder[^3], holdt fast i hiandens hænder, og så lænede os
bagud med rank ryg og strakte knæ indtil vi var i balance, så måtte man
da kunne udlede noget af det?

Som sagt, så gjort! Det kom til at se sådan hér ud:

[![]({{site.url}}/images/-Y2DbyZTHiSs/VNIKocvLlRI/AAAAAAAACm4/gzU0uH-A0Ao/s1600/vlcsnap-2015-02-04-12h44m21s292.png)]({{site.url}}/images/-Y2DbyZTHiSs/VNIKocvLlRI/AAAAAAAACm4/gzU0uH-A0Ao/s1600/vlcsnap-2015-02-04-12h44m21s292.png)

Som I kan se skal den mindre masse læne sig væsentlig længere bagud for
at kunne udbalancere den større... Jeg har tegnet et par hjælpelinier på
billedet, og selvom de blev lidt skæve burde det være relativt let at
henføre de relevante størrelse til følgende skitse:

[![]({{site.url}}/images/-XWOZ3WGIvDU/VNILenyy-mI/AAAAAAAACnA/HAJ8rvXF2tQ/s1600/2015-02-04%2B12.18.05.jpg)]({{site.url}}/images/-XWOZ3WGIvDU/VNILenyy-mI/AAAAAAAACnA/HAJ8rvXF2tQ/s1600/2015-02-04%2B12.18.05.jpg)

Heraf ser vi altså at hvis vi skal være i balance, så skal vores
vandrette kraftkomposanter være lige store, altså har vi at
\\(F_L=F_W\\). 

Da disse kræfter er en projektion af tyngekraften,
\\(F_g=m\cdot g\\) ind på vores hældning kan vi altså udlede ud fra
almindelig trigonometri at \\[\tan(\beta)=\frac{F_L}{g\cdot m_L}
\wedge \tan(\alpha)=\frac{F_w}{g\cdot m_W}\\] 
og da vi allerede ved at \\(F_L=F_W\\) kan vi lave lidt omskrivning og få at
\\[
F_L=tan(\beta)\cdot g \cdot m_L \wedge F_W=tan(\alpha)\cdot g \cdot m_W \Leftrightarrow \\\ 
tan(\beta)\cdot g \cdot m_L = tan(\alpha)\cdot g \cdot m_W \Leftrightarrow \\\ 
\frac{m_W}{m_L}=\\frac{\tan(\beta)}{\tan(\alpha)}
\\]
Så skal vi bare måle vinklerne, og det kan vi jo gøre i hvilket program
vi nu måtte ønske --- jeg har bare brugt GIMP, da jeg alligvel havde
vækket den og der har jeg ved at følge hjælpelinierne fået
\\(\beta=27.42^{\circ} \wedge \alpha=13.66^{\circ}\\). Det sætter
vi bare ind i formlen og får...

Hmmm...

Så skulle jeg veje 2.13 gange så meget som hende. Det virker ikke videre
sandsynligt... Godt nok er jeg et stort brød i sammenligning, meeen...
Hov! Den vågne l\[æø\]ser vil allerede have bemærket at grundet forskel
i højde og tilbagelæningsgrad, så er hendes arme cirka vandrette, men
mine går nedaf --- det vil altså sige at jeg også løfter hende en smule,
og derved bliver min (tyngde)vektor større[^4], og hendes mindre. Den
simplest mulige kompensation for dette må være af indføre en
kompenserende kraft i regnestykket --- markeret \\(F_{komp}\\) i den
reviderede skitse:

[![]({{site.url}}/images/-C7gjrj1Aepo/VNIXkX36kLI/AAAAAAAACnQ/jWTMvCkOSXQ/s1600/2015-02-04%2B13.56.45.jpg)]({{site.url}}/images/-C7gjrj1Aepo/VNIXkX36kLI/AAAAAAAACnQ/jWTMvCkOSXQ/s1600/2015-02-04%2B13.56.45.jpg)

Efter lidt yderligere fingergymnastik kan jeg få flyttet om på
størrelserne sådan at det giver
\\[\frac{m_W\cdot(1+\tan(\gamma))}{m_L\cdot(1-\tan(\gamma))}=\frac{\tan(\beta)}{\tan(\alpha)}\\]
Og vi måler straks på billedet: \\(\gamma=18^{\circ}\\), og så er det
jo bare at indføre de faktorer og gentage beregningen... og nu vejer jeg
så kun 8% mere. Det er jo nok lidt vel lidt...

Nå, måske var det ikke så god en idé, som det virkede til --- jeg kan
umiddelbart ikke lige se at der er noget graverende galt, men nu jeg
kigger på billedet og skitsen igen, så springer det jo i øjnene at vi
ikke støtter på et fælles omdrejningspunkt, men hver især roterer om
hælen, og der er immervæk cirka en fod imellem[^5], hvorved vi også
projicerer noget vandret kraft ind i gulvtæppet, og denne har jeg ikke
kompenseret for. Der er måske andre ting jeg ikke har tænkt over, men
det er alligevel ikke HELT skidt at disse meget hurtige og improviserede
beregninger spænder et sandsynligt felt ud.

Nå, men vi må altså konstatere at sandheden nok ligger et sted mellem de
to opnåede resultater, og så lade det ligge ved det indtil videre --- der
skal vist koges lidt mere suppe på dén idé, inden den kan bruges, men nu
er det meget tæt på at blive et princip at vi SKAL have et eller andet
til at virke...

Jeg har dog valgt at skrive om det alligevel, selvom resultatet er
"grimt" --- fordi der publiceres for få negative resultater --- fordi det
var et stykke sjov mekanik og trigonometri, og fordi det måske kan
inspirere nogen af jer derude til at finde fejl i mine antagelser,
beregninger eller andet --- eller endnu bedre: Prøv selv! Forbedr
teknikken! Leg med virkeligheden og hinanden --- og skriv om det for
pokker! :-D

Kan I hygge jer og nørde godt, derude!  
\\Worm

------------------------------------------------------------------------

[^1]: Hvad ER det med nørder og de mærkelige sportgrene de dyrker? Nå,
    men det er vel egentlig ikke så mærkeligt...

[^1a]: Altså - sådan en man hejser ting op med - ikke et stykke
    anatomi.

[^2]: Jaja, tøhø...

[^3]: Ja, det blev en lidt rodet superposition til at starte med, men
    tilsyneladende kan lugt også kollapse en bølgefunktion.

[^4]: Ja, det kan jo være svært at undgå at blive en gammel gris, når
    man skal skrive sådan noget i ramme alvor...

[^5]: Et af de eneste steder hvor det er okay at måle i britiske
    (imperial) enheder er vel når det faktisk ER fødder...
