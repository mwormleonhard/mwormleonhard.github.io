---
comments:true
layout: post
title: "(Hvornår) Er posten hurtigere end internettet?"
date: '2014-09-08T23:41:00.000+02:00'
author: Martin Worm-Leonhard
tags:
- Bagsiden af kuverten
- Dataoverførsel
- Skæg med tal
- Sanity check
modified_time: '2014-09-08T23:43:37.728+02:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-5309875168571459867
blogger_orig_url: http://labnoter.blogspot.com/2014/09/hvornar-er-posten-hurtigere-end.html
---

Her til aften, mens jeg stod og bonede issen, kom jeg gennem en længere
associationsrække[^1] til at overveje hvor mange data man skulle flytte
hvor langt før det var hurtigere at putte et lagermedie[^2] i en kuvert
end at overføre dem via FTP, TCP/IP, HTTP, rsync eller i daglig tale
"over internettet".

Det er naturligvis et gammelt spørgsmål, som Tanenbaum tog op allerede
dengang jeg var ved at få tænder og som formodentligt/forhåbentligt er
blevet skamredet i datalogi og signalbehandling 101 lige siden. Ikke
desto mindre er det et sjovt og nørdet spørgsmål, så... Lad os alle
regne.

Der er naturligvis mange faktorer der kan spille ind, men
beregningerne er jo ikke så svære, så I kan selv lege videre
bagefter...

Lad os antage at jeg skal sende nogle grimt store datafiler til en
gammel ven på AU. Hvis jeg lægger dem ud på en ekstern harddisk eller
USB-pind, så kan jeg jo nok i (optimistisk) gennemsnit regne med at de
er fremme efter 24 timer --- og her er det væsentlige --- uanset hvor mange
data jeg sender!

Hvis vi begge to er på arbejde --- og det er vi jo ofte --- så sidder vi ret
nær forskningsnettets backbone og kan nok godt pine 40--50 Mbit/s ud af
et direkte link, hvis vi gør os umage eller giver netværkschefen kage
til kaffen. 

Så kan man på 24 timer flytte \\[ 50\frac{Mbit}{s} \cdot
24timer \cdot 3600\frac{s}{time} = 4,32 Tbit = 540Gbyte \\]
Det er rimeligt mange data --- medmindre man lave partikelfysik eller
meget præcis analysekemi, men stadig indenfor en realistisk mængde som
man kan have behov for at få flyttet i en professionel kontekst.

Så hvis jeg skal have et par Terabytes til århus, så er posten hurtigere
end forskningsnettet!

Hvis jeg derimod sidder herhjemme og gerne vil dele mine feriebilleder
med de gamle i ydre udgård, så lider jeg som så mange andre af
asymmetrisk internet og har kun et sølle upload på 2Mbit/s, hvilket
efter samme udregning giver 21,6Gbyte.

Hvis jeg nu var fotonørd kunne
jeg formodentlig godt producere sådan en mængde data på et par uger på
Madeira, og det vil det jo nok under alle omstændigheder være lettere at
forklare mine forældre at der kommer en pind med posten end at de skal
logge ind på min server... Men det er stadig lidt et konstrueret
tilfælde...

Er vi indenfor bygrænsen (½ times transport stort set uanset modus) er
det straks en anden sag. Her kan mine sølle 2 Mbit/s kun nå at overføre
ca. 450Mbyte --- det er jo ikke engang en film i en bare nogenlunde
kvalitet, og man begynder at skulle overveje om det i virkeligheden ER
et overhead at skulle kopiere data ud på en ekstern harddisk...

Konklusion: Så længe man er i lokalområdet  flytter man ofte data
hurtigere ved at tage dem i lommen og sætte sig op på sin cykel! Og så
får man også mødt sine venner i den virkelige virkelighed!

Se også:

- <https://what-if.xkcd.com/31/>
- <http://en.wikipedia.org/wiki/Sneakernet>

FIN/ACK  
\\Worm

------------------------------------------------------------------------

[^1]: Der vil være for svær/pinlig af forklare hér.

[^2]: Elektronisk, altså. Ikke en flaske øl
