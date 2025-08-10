Laddningstid och andvändbarhet
=======================

Uppgiften handlar om att skriva om hur laddningstideen påverkar användarvänligheten för dom 3 utvalda webbplatser.

Urval
-----------------------

Dom hemmsidor som jag valde var att kolla på för undersökningen är: 

"Netflix" = netflix.com - browsing sidan,
"With Love" = withlove.tv - discovery sidan och
"Disney +" = disneyplus.com - home sidan.
Dessa sidorna valde jag eftersom dom är liknande och används för att titta på serier och fillmer allihopa och då är det väldigt roligt att se ladnings tider och användbarhet för dessa sidor.

Metod
-----------------------

Jag valde att använda mig "Pagespeed insights" för att få fram webbplatsernas olika värden samt se förbättrings förslag som går att implementera. Värdena las in i Google kalkylark för att jänföra olika värdena för de olika hemsidorna.

Resultat
-----------------------

Resultat från Pagespeed av mätningarna på webbplatserna
<iframe class="excel" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vTBuOaYSXdjc4QwApPGVHYDZE9Ag20E3H812t_MegLh_e8cKO9Nr9BswTDy4jg1KEJ4Mfn70o-ZWysp/pubhtml?gid=0&single=true&widget=true&headers=false"></iframe>

Netflix
-----------
<img src="%base_url%/assets/img/netflix.png" alt="andra" style="height: 200px;">
Förbättrings förslag från Pagespeed:
<ul>
    <li>Begäranden om renderingsblockering Möjlig tidsbesparing: 190 ms</li>
    <li>Använd effektiva cachelivslängder Möjlig databesparing 339 Kibit</li>
</ul>

With Love
-----------
<img src="%base_url%/assets/img/withlove.png" alt="andra" style="height: 200px;">
Förbättrings förslag från Pagespeed:
<ul>
    <li>Förbättra bildleveransen Möjlig databesparing 281 Kibit</li>
    <li>Reducera CSS som inte används Möjlig databesparing 34 Kibit</li>
</ul>

Disney +
-----------
<img src="%base_url%/assets/img/disneyplus.png" alt="andra" style="height: 200px;">
Förbättrings förslag från Pagespeed:
<ul>
    <li>Fördröjning av dokumentbegäran Möjlig tidsbesparing: 200 ms</li>
    <li>nvänd effektiva cachelivslängder Möjlig databesparing 261 Kibit</li>
</ul>


Analys
-----------------------

<h4>Prestandaöversikt</h4>
With Love har en mycket bättre resultat än både Netflix och Disney+ både på mobil och desktop 75 och 76 poäng i PageSpeed.


Netflix och Disney+ presterar lågt på mobil 37 och 27 samt lågt även på desktop 36 och 30. Detta tyder på långa laddtider eller ineffektiv rendering.


Man kan även se skilnaden i Speed index väldiugt tydligt


- With Love: 1,1 s → mycket snabb visuell laddning<br>
- Netflix: 3,8 s → långsam visuell uppbyggnad<br>
- Disney+: 3,4 s → också relativt långsam<br>


Time to First Byte (TTFB) är relativt bra för alla tre, vilket tyder på att serverresponsen inte är huvudproblemet. Problemet ligger mer i hur innehållet laddas och renderas.

<h4>Flaskhalsar & orsaker</h4>
Netflix: Renderingsblockerande skript är en stor faktor. Detta betyder att CSS- och JS-resurser laddas på ett sätt som stoppar sidans visuella rendering. Bristande caching gör att användare laddar om resurser vid varje besök.


With Love: Bra optimerad när det gäller laddningstider, men kan spara ännu mer datamängd genom att optimera bilder och ta bort oanvänd CSS (vilket också förbättrar stilhantering och rendering).


Disney+: Har liknande problem som Netflix med fördröjningar i dokumentbegäran och brist på caching. Dessa orsakar längre visuell uppbyggnadstid och onödiga datanedladdningar.

<h4>Rekommendationer</h4>
För Netflix och Disney+: 
    Implementera asynkron/lazy loading för JavaScript och CSS för att minimera renderingsblockering.
    Optimera caching-regler så att statiska resurser lagras längre på användarens enhet.
    Komprimera och optimera bilder.


För With Love: 
    Vidare optimera bilder (använd moderna format som WebP eller AVIF).
    Rensa oanvänd CSS (t.ex. med verktyg som PurgeCSS).

<h4>Slutsats</h4>
With Love ligger i topp när det gäller PageSpeed-prestanda, men har fortfarande förbättringspotential, främst på bildoptimering och CSS-rensning.


Netflix och Disney+ behöver fokusera på att reducera renderingsblockering och förbättra cachehantering, eftersom det är här den största prestandavinsten kan göras.


Trots liknande TTFB-resultat presterar sidorna väldigt olika, vilket visar att klientoptimering (hur webbläsaren hanterar resurser) är avgörande för helhetsupplevelsen.



Referenser
-----------------------

Pagespeed insights: För att göra mättningar av hemsidan

Google kalkylark: För att sammanfata resultaten på ett ställe

Övrigt
-----------------------
Ett arbete av mig Filippa Lissäng Öst.
