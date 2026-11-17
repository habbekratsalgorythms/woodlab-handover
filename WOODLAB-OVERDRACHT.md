# Habbekrats WoodLab — overdracht aan Claude

**Datum:** 17 november 2026  
**Versie:** 1.0  
**Status:** voorbereiding, NIET live, NIET productiegeschikt  
**Doel:** Claude kan zelfstandig het project voortzetten zonder de oorspronkelijke ChatGPT-chat.

## 1. Bedrijfsconcept
Habbekrats WoodLab is een beoogde productlijn onder HabbekratsAlgorythms voor lasersnij- en lasergraveerproducten van hout. **Made to order**: klanten kiezen een vooraf ontworpen template, doen minimale personalisatie en betalen; daarna worden een gecontroleerde productiebon en machinebestanden voorbereid. Fysieke productie, kwaliteitscontrole en verzending blijven menselijk. Overige delen van de bestelketen zoveel mogelijk geautomatiseerd.

Doelgroep: kleine bedrijven (horeca, salons, winkels, kantoor), thuiswerkers en consumenten die eenvoudige houten werkplekaccessoires en bordjes zoeken. Begin in Nederland. WoodLab is een **werknaam**; merkbeschikbaarheid, juridische entiteit en fiscale inrichting zijn niet vastgesteld.

**Geen onbewezen marketingclaims:** niet stellen dat de producten FSC, CO2-neutraal, afvalvrij, duurzaam gecertificeerd, lokaal geproduceerd of door Wihamij geleverd zijn zonder verificatie en toestemming.

## 2. Vast besloten door de eigenaar
1. Maximaal **drie productfamilies** bij de start:
   - QR-bordjes voor reviews, wifi of website/menu.
   - Modulaire bureau-organizer/telefoonhouder als plat bouwpakket.
   - Houten deur- en ruimtebordjes.
2. Geen fysieke voorraad van eindproducten; **op bestelling gemaakt**. Klant mag wel bestellen, maar claim niet dat artikelen uit voorraad leverbaar zijn.
3. Alleen een **bibliotheek met vooraf ontworpen en na fysieke tests goedgekeurde templates**, minimale variatie in tekst/naam/standaardvarianten. **Geen vrije ontwerp-upload en geen klantgerichte AI-beeldgeneratie** in de eerste versie.
4. Snijden en graveren via laser is volgens eigenaar mogelijk bij de werkplaats waarmee hij contact heeft (mogelijk Wihamij, Zevenbergen); prijs, capaciteit, samenwerking en rechten **nog niet bevestigd**.
5. Na geslaagde betaling automatisch werkbon en snij-/graveerbestanden genereren; productieopdrachten aanvankelijk pas na menselijke controle vrijgeven.
6. Geen speelgoed in MVP; kinderproducten en CE-speelgoedcompliance vermijden.
7. Geen uitgaven, proefbestellingen, betaalde API's, zakelijke registraties, contracten, rechtenuitbreiding of commerciële livegang zonder uitdrukkelijk akkoord van eigenaar.
8. Bestaand Habbekrats-experimentenbudget: totaal ongeveer €100 en circa €20 per project als richtlijn, **geen machtiging om aan WoodLab geld uit te geven**.

## 3. Producten en verkoopprijzen — hypotheses, niet gevalideerd

| Product | Concept | Doelgroep | **Testprijs, schatting incl. btw** | Kernrisico |
|---|---|---|---:|---|
| QR-bordje | Tafelstandaard met gegraveerde echte scanbare QR | Horeca, salons, winkels | €24,95 | Scanbaarheid na graveren, correcte URL |
| Desk Companion | Plat bouwpakket organizer + telefoonhouder | Thuiswerkers, bedrijven | €29,95 | Passing, stabiliteit, scherpe randen |
| Deur-/ruimtebordje | Vaste vorm met naam/nummer | Kantoren, B&B, thuis | €14,95 | Montage, afwerking, tekstlengte |

Begin met **vijf drafttemplates per familie (15 totaal)**, plus drie fysieke prototypes (één per familie) zodra eigenaar die kosten expliciet goedkeurt. Pas na succesvolle fysieke tests naar `approved` promoveren. Prijzen zijn geen bestaande aanbiedingen.

## 4. Wat al gedaan is; wat beslist NIET
**Wel:** bedrijfsmodel besproken; 3 productkeuzes; lasergravure vastgesteld als gewenste personalisatie; made-to-order gekozen; templatebibliotheek met minimale aanpassing gekozen. In het chatgesprek zijn een **visuele webshopdemo** en een **interactieve bibliotheekdemo met 15 fictieve conceptontwerpen** getoond (categorieën, filter, voorbeeldgravure). Markt-, juridische en leveranciersoriëntatie is besproken.

**Niet:** geen productiebestanden op fysieke machine bewezen; geen prototype gesneden; geen door Wihamij schriftelijk geaccepteerde opdracht; geen bevestigde kostprijs; geen operationele checkout, payment provider, webshop, verzending, accounts, merkcheck of commerciële verkoop. De chatdemo is **niet** productiegeschikt; getoonde QR-patronen zijn illustratief en **niet scanbaar**.

## 5. Productie: open vragen voor eigenaar en Wihamij
De eigenaar doet schoonmaakwerk bij de vermoedelijke producent en denkt goedkoop plaatwerk te kunnen laten laseren. **Dat is nog geen commercieel aanbod of toestemming.** Vraag eerst:
- Wie is de contractpartij en mogen wij hun bedrijfsnaam noemen?
- Welke hout-/plaatsoorten zijn laserveilig en toegestaan, welke dikten en formaten?
- Welke machine, maximale plaatgrootte, snijbreedte/kerf, minimale gravurelijn en toleranties?
- Welke bestanden, instellingen, kleurconventies en nesting zijn gewenst?
- Hoeveel instel-, snij-, graveer-, materiaal-, afwerkings- en verpakkingskosten per stuk/batch?
- Wat is minimumafname, realistische doorlooptijd, capaciteit en procedure bij afkeur?
- Wie doet splintervrije afwerking, QC, verpakking en fysieke verzending?
- Zijn er beperkingen voor zakelijke rechten, gebruik van ontwerpen en productie van derden?

Publiceer geen samenwerking of leveranciersvermelding zonder toestemming.

## 6. Aanbevolen techniek: ontwerp, niet gerealiseerd
- Catalogus met `products`, `templates`, `template_versions`, prijzen, materiaal/maatvoering en statuses `draft/tested/approved/retired`.
- Alleen veilige invoervelden voor korte gravures en vaste variantkeuze. Escapen tegen HTML/XML/scriptinjectie; inputlimieten en gecontroleerde lettertypen.
- Browserpreview uit dezelfde vastgepinde templateversie als productie. Productfoto, houtkleur en nerf als indicatief tonen.
- Voor QR-items: genereer **echte** QR uit een gevalideerde HTTPS-URL. Test fysiek op meerdere telefoons; geen herleidende tracking standaard aannemen.
- Orderstatus: `draft → payment_pending → paid → production_review → released → producing → quality_check → shipped`; alternatieven `failed/cancelled/refunded`.
- Alleen geverifieerde server-side payment-webhooks; idempotency; nooit produceren op basis van alleen een browsermelding.
- Onveranderlijke productiesnapshot: order-ID, gekozen template en versie, materiaal/dikte, aantallen, tekst, lagen voor snijden en graveren, unieke hash; technische SVG/DXF-validatie.
- Eerste opdrachten altijd handmatig controleren; pas automatische vrijgave nadat defectvrije proeforders zijn gedocumenteerd en eigenaar akkoord geeft.
- Hergebruik Habbekrats-infrastructuur alleen na controle van toegangsrechten en zonder andere projecten te verstoren. Mogelijke stack: bestaande Pages/Supabase-patronen; **geen bestaande WooCommerce/Supabase/paymentintegratie als feit aannemen**.
- Geen secrets of persoonsgegevens in publieke repository; minimale klantgegevens, toegangscontrole en bewaartermijnen.

## 7. Voorbeeld kostenmodel — uitsluitend SCHATTING
QR-bordje testprijs €24,95 incl. 21% btw → circa **€20,62 excl. btw**.

| Post | Schatting per order |
|---|---:|
| Verkoop excl. btw | €20,62 |
| Hout plus snijden en graveren | -€3,00 |
| Verpakking | -€0,75 |
| Betalingskosten | -€0,50 |
| **Resterende bijdrage vóór overige kosten** | **€16,37** |

**Dit is geen winst.** Verzendkosten, arbeid, marketing, proefsnedes, afkeur, retouren, klachten, overhead en belastingen niet meegenomen. €3 en €0,50 zijn **niet geverifieerde leverancierstarieven**. Maak straks laag/basis/hoogscenario met de echte offerte en test of prijzen rendabel zijn zonder veel klantwerk.

## 8. Opdracht voor Claude: eerstvolgende zelfstandige stappen
**A. Nu toegestaan: offline voorbereiding zonder kosten, geen externe wijzigingen**
1. Neem deze overdracht als voorlopig projectdossier; schrijf een beknopt beslislog en een checklist met open aannames.
2. Maak **15 eigen concepttemplates** (5 per productfamilie) met versiebeheer, productafmetingen als parameters, allemaal `draft`. Gebruik geen merken/logo's of auteursrechtelijk beschermde personages.
3. Bouw een **responsive lokale demo**, met categorieën, bibliotheek, beperkte naam/tekstpersonalisatie, live preview, winkelmand en **nepcheckout**. Geen echte bestellingen of betaalverzoeken.
4. Bouw pure validatie/export-functies voor veilige SVG en werkbon, en tests op lange/onveilige tekst, verkeerde lettertypen, mislukte betaling, dubbele webhook, QR-URL en niet-productiegeschikte tekeningen.
5. Lever een productiespecificatie-vragenlijst voor eigenaar/Wihamij en een spreadsheet of JSON-calculator met duidelijk gemarkeerde aannames.
6. Geef overzicht van onopgeloste blokkades; markeer ieder ontwerp als draft tot fysieke proef en acceptatie.

**B. Alleen na toestemming**
7. Ontvang technische machineparameters en schriftelijke prijsindicatie; ontwerp pas dan machinecompatible exports.
8. Laat drie fysieke prototypes maken **alleen na goedgekeurd budget**; test QR-scans, passing, stabiliteit, splinters, montage en maatvoering.
9. Registreer/controleer juiste zakelijke identiteit, productveiligheid, BTW, voorwaarden, privacy, retourrecht, fabrikantgegevens en verantwoordelijkheid.
10. Betaalprovider, e-mails, hosting, orderflow en livegang pas na expliciet eigenaar-GO; eerst sandbox end-to-end testen.

**Geen automatische uitbreidingen naar andere repos of infrastructuur.** Geen betalingen, accountregistraties, productpublicatie of commerciële claims.

## 9. Wat alleen de eigenaar kan doen / autoriseren
- Afspraken over productie, materiaal, kosten, levertijden en gebruik van de naam Wihamij.
- Aankopen, prototypebestellingen, contracten, bedrijfsregistratie/handelsnaam, verzekeringen, betalingsprovider en fiscale inrichting goedkeuren.
- Rechten tot GitHub, hosting, domein, e-mail, betaalprovider en administratie verlenen.
- Fysieke prototypes testen/accepteren en definitieve verkoopprijzen/levertijden/voorwaarden goedkeuren.
- Livegang expliciet autoriseren.

## 10. Wettelijke risico's en realistische verwachtingen
- **GPSR** algemene productveiligheid geldt ook voor houten accessoires; productrisicoanalyse, traceerbaarheid en juiste online informatie vóór verkoop controleren.
- **Speelgoed**: voor kinderen bedoeld speelgoed vraagt afzonderlijke regelgeving/CE-beoordeling; MVP sluit dit uit.
- **Retourrecht**: 'made to order' is op zichzelf **niet** automatisch uitgezonderd van herroepingsrecht. Verschil tussen standaardproduct op bestelling en werkelijk gepersonaliseerd product per SKU juridisch beoordelen.
- Controleer actuele Nederlandse regels over verplichte retour-/herroepingsfunctie voor webshops en informatieplicht.
- Gravure is niet automatisch veilig of goed leesbaar; machines en fysieke producten moeten door verantwoordelijke mens getest worden.
- Maximaal circa één uur per week handmatig beheer is een **doel**, geen bewezen operationele capaciteit; evalueer na 10 testorders.
- Naam WoodLab en templates kunnen onder oudere rechten vallen; beschikbaarheid nog niet gecontroleerd.

## 11. Externe bronnen (oriëntatie, bronvermeldingen gedateerd 17-11-2026)
Dit zijn verwijzingen voor controle; ze bevestigen **geen** commerciële productieafspraak of kosten.

| Bron | URL | Relevant / beperking |
|---|---|---|
| Wihamij (officieel) | https://www.wihamij.com/ | Bedrijf in Zevenbergen; geen bevestiging van lasersnijservice voor dit project |
| Wihamij: over | https://www.wihamij.com/over-wihamij/ | Hout-/palletproductie; geen prijs of productieafspraak |
| Europese Commissie, productveiligheid | https://ec.europa.eu/safety-gate/screen/pages/productSafetyLegislation | Algemene productveiligheidsregels; geen certificering voor WoodLab |
| ACM, bedenktijd | https://www.acm.nl/nl/verkoop-aan-consumenten/klantenservice/bedenktijd | Herroepingsregels en uitzonderingen; uitzonderingsstatus per product controleren |
| KVK, webshop beginnen | https://www.kvk.nl/starten/een-webwinkel-starten-begin-hier/ | Nederlandse webshopverplichtingen |
| Mollie, tarieven | https://www.mollie.com/nl/pricing | Indicatieve tarieven, geen gecontracteerd WoodLab-tarief |

Er is **geen bewijs** voor eerder genoemde persoonsnamen, familiebanden, speelgoedmerken of exclusieve leveranciersovereenkomsten; daarom niet overnemen of publiceren.

## 12. Acceptatie vóór commerciële verkoop
- Minimaal 3 fysiek goedgekeurde prototypes en echte technische snijbestanden.
- QR gegraveerd en betrouwbaar scanbaar; organizer stabiel en veilig; deurbord veilig gemonteerd en afgewerkt.
- Definitieve kostprijs/doorlooptijd van producent, inclusief uitval en retourreserve.
- Correcte juridische entiteit, btw, fabrikantgegevens, voorwaarden, privacy, risicoanalyse en herroeping.
- Betalingswebhook, idempotency, foutafhandeling, orderstate, werkbon, menselijke review, verzending en klantmails end-to-end getest.
- Schriftelijk GO eigenaar voor livegang.

**CLAUDE: werk nu uitsluitend aan de offline/demo-voorbereiding onder §8A.** Publicatie van deze overdracht is geen toestemming voor publicatie van website, apps of producten, noch voor bestellingen, kosten of accountregistraties.
