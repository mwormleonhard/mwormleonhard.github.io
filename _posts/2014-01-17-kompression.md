---
comments:true
layout: post
title: Kompression
date: '2014-01-17T16:26:00.001+01:00'
author: Martin Worm-Leonhard
tags:
- Algoritmer
- Kompression
modified_time: '2014-01-17T16:26:39.550+01:00'
blogger_id: tag:blogger.com,1999:blog-6363822545143881814.post-316946711857516428
blogger_orig_url: http://labnoter.blogspot.com/2014/01/kompression.html
---

Efter at have afsluttet en arbejdsuge der føltes som om den var mindst 10 dage lang, på trods af at det var mandag i går, så er det vel nærliggende at skrive lidt om (data)kompression.
Man kunne (med nogen ret) spørge hvorfor det overhovedet er interessant --- i dag er lagerplads jo nærmest billigere end vådt bølgepap, og internetforbindelser er generelt blevet så hurtige at man ikke skulle tro det var nødvendigt at hoppe på sine data længere, for at få dem stoppet gennem ledningerne.

Til gengæld er de mængder af data der produceres og gemmes (og ikke kun af PET, NSA og andre TLA'er) jo vokset ligeså enormt meget, og brugere har jo vænnet sig til at al ventetid &gt; 200 ms er unaturligt og frustrerende, så det er stadig et område der er relevant at beskæftige sig med. Og så er det god nørd. Det må vi ikke glemme, så lad os starte med en demonstration:

Skriv, eller copy-paste noget tekst i nedenstående input-felt --- jo mere desto bedre --- og observer hvordan det komprimerede output ændrer sig og bliver mere og mere ulæseligt jo mere tekst der er at arbejde med, men at det stadig er muligt at genskabe hele originalteksten ud fra dette tilsyneladende volapyk.
(Hvis du copy-paster kan det godt være du skal afslutte med space eller enter --- jeg er ikke helt sikker på hvordan jeg får den til at opdatere uden --- jeg er jo bare kok).

Kan du allerede nu gennemskue hvordan det virker? Og hvis du er den slags nørd, kan du så gætte algoritmen? Ellers leg lidt mere, eller snyd og læs resten...

<script type="text/javascript"> 
// Fra:http://stackoverflow.com/questions/294297/javascript-implementation-of-gzip  
// LZW-compress a string 
function lzw_encode(s) {
var dict = {};
var data = (s + "").split("");
var out = [];
var currChar;
var phrase = data[0];
var code = 256;
for (var i=1; i<data.length; i++) {
currChar=data[i];
if (dict[phrase + currChar] != null) {
phrase += currChar;
}         
else {
out.push(phrase.length > 1 ? dict[phrase] : phrase.charCodeAt(0));
dict[phrase + currChar] = code;
code++;
phrase=currChar;
}     
}     
out.push(phrase.length > 1 ? dict[phrase] : phrase.charCodeAt(0));
for (var i=0; i<out.length; i++) {
out[i] = String.fromCharCode(out[i]);
}     
return out.join(""); 
}  
// Decompress an LZW-encoded string 
function lzw_decode(s) {
var dict = {};
var data = (s + "").split("");
var currChar = data[0];
var oldPhrase = currChar;
var out = [currChar];
var code = 256;
var phrase;
for (var i=1; i<data.length; i++) {
var currCode = data[i].charCodeAt(0);
if (currCode < 256) {
phrase = data[i];
}         
else {
phrase = dict[currCode] ? dict[currCode] : (oldPhrase + currChar);
}         
out.push(phrase);
currChar = phrase.charAt(0);
dict[code] = oldPhrase + currChar;
code++;
oldPhrase = phrase;
}
return out.join("");
} 

function update_fields() {
outtext.value=lzw_encode(intext.value); 
decoded.value=lzw_decode(outtext.value); 
inputchars.value=intext.value.length+1; 
outputchars.value=outtext.value.length+1; 
compression.value=100*(1-(outtext.value.length+1)/(intext.value.length+1)); 
}  
</script> 
Input:
<textarea cols="40" id="intext" onkeypress="update_fields()" rows="10"></textarea>
Antal tegn: <input disabled="true" id="inputchars" size="5" type="text" value="0" />

Komprimeret output:
<textarea cols="40" id="outtext" rows="10"></textarea>
Antal tegn:<input disabled="true" id="outputchars" size="5" type="text" value="0" />
Kompression:<input disabled="true" id="compression" size="5" type="text" value="0" />%

Genskabt output:
<textarea cols="40" id="decoded" rows="10"></textarea>

First things first --- jeg kan ikke tage æren for at have implementeret
algoritmen selv --- det kunne have været en sjov øvelse, men der er
mange andre ting jeg kan/skal/bør bruge min tid på, så det kan være jeg
vender tilbage til konceptet en dag og ruller min egen, men lige nu er
den tyvstjålet fra
[Stackoverflow](http://stackoverflow.com/questions/294297/javascript-implementation-of-gzip)

På trods af linkets titel er der tale om LZW
([Lempel-Ziv-Welch](http://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Welch))
kompression. 

Denne virker kort/groft sagt ved at lave en ordbog, der løbende
opdateres med strenge fra inputtet, således at alle serier af gentagne
tegn bliver repræsenteret ved én kode eller repræsenteret i tekst som en
glyf. 

Skriver man derfor det samme ord igen senere i teksten vil man se de
erstattet med et "mystisk tegn", som bare er en slags "bogmærke" til
ordbogen der siger "slå op her, når du skal pakke ud igen". 

Det snedige er at måden man bygger ordbogen på er så veldefineret at man
ikke behøver sende den sammen med teksten --- den kan genskabes ud fra det
komprimerede indhold.


Mere vil jeg egentlig ikke gøre ud af det for nuværende --- interesserede
kan læse meget mere hos tante Wiki, og formålet med denne post var
egentlig primært at forsøge mig med at lave lidt sjovt interaktivt
indhold og se om blogger magter opgaven med indlejret javascript.

_**Update 2016-05-07:** Det krævede meget lidt overtalelse og reformattering af koden at få det til at virke i markdown og blive serveret af Jekyll. 
Umiddelbart vil jeg tro at det største problem var at Bloggers exportfunktion havde vredet det temmelig meget ud af facon..._

Disclaimer: Jeg har ikke gået til CS eller algoritmer --- ikke sådan
formelt, i hvert fald --- så jeg kan ikke vurdere om implementationen er
100% tro mod algoritmen. Hvis nogen ligefrem kigger i sovsen hører jeg
gerne om det. Jeg kunne forestille mig at det faktum at den er
implementeret i javascript måske sætter nogle begrænsninger, enten i
størrelsen eller udformningen af ordbogen, men jeg er helt ærligt for
doven til at tegne det.

God Weekend,  
\\Worm
