---
description: >-
  Beschrijft Koppeltaal op het hoogste abstracte niveau, en beschrijft iets dat
  waarde toevoegt aan zijn gebruikers.
---

# CID - Component, Interface en Diensten

Koppeltaal 2.0 bestaat uit _componenten_ (in ArchiMate een EA modelleer taal wordt hier de term "applicatie component" gebruikt) die andere componenten _functies_ en _diensten (component instanties)_ aanbiedt, zonder die andere component te belasten met hoe dat precies gebeurt. De functies of aangeboden diensten wordt ontsloten of aangeboden via _interfaces_. De interfaces zijn dus de koppelvlakken tussen de verschillende componenten. Bij elke interfaces is er sprake van een _aanbieder_ die volgens de interface specificaties functies of (gegevens) diensten aanbiedt aan _afnemers_.

In de doelstelling van stichting Koppeltaal is middels het woord ‘_interne_’ een beperking voor de interfaces en de daarbij behorende Koppeltaal diensten opgenomen. Met deze beperking wordt bedoeld dat de interfaces aangeboden worden onder de verantwoordelijkheid van **één zorgaanbieder (domein)**. De dienstverlenende componenten worden geleverd door verschillende **leveranciers.** Deze leveranciers kunnen hun componenten ontsluiten via het Koppeltaal platform onder de verantwoordelijkheid van de zorgaanbieder (domein).

### Componenten

Koppeltaal 2.0 bestaat uit de volgende componenten en collaboraties:

* "Koppeltaal domein": Het geheel van samenwerking tussen de Koppeltaal voorziening en - platform onder de verantwoording van een zorgaanbieder.
* "Koppeltaal voorziening" : Alle producten, functies en diensten die nodig zijn om de informatiestromen tussen (zorg) toepassingen op een veilige manier tot stand te brengen in de context van "Blended Care" (combinatie tussen traditionele therapie en digitale therapie/interventies)
* "Koppeltaal platform" : Een platform geeft toegang tot een palet aan gestandaardiseerde informatiesystemen en technologie. Het platform kan gebruik maken van, of diensten verlenen aan een applicatie of eHealth module.
* "Portaal" : Een toegangspoort of -(verzamel)punt tot informatie over een bepaald onderwerp die een gebruiker een uniforme toegang biedt naar achterliggende systeem componenten. Het kan ook worden beschouwd als een bibliotheek met gepersonaliseerde en gecategoriseerde inhoud voor een groep personen die toegang krijgen tot functionaliteiten over of het gebruik van activiteiten. Een portaal handelt HTTP berichten af.
* "Client Applicatie":  Is een zelfstandige (software) programma module die rechtstreeks met de gebruikers communiceert en gebruik maakt van de Koppeltaal voorziening om met andere eHealth modules gegevens uit te kunnen wisselen, in het zorgproces. &#x20;
* &#x20;"eHealth Module":  Software dat een eHealth toepassing is, dat aangeboden wordt aan cliënten zonder tussenkomst van behandelaren, met als doel de gezondheid van de cliënten te ondersteunen en te verbeteren.
* "Bevoegdheden": Het component dat bevoegdheden aan concrete component instanties (diensten) toekent en het verklaren daarvan, tot aan het intrekken (verwijderen) van bevoegdheden.
* "Toegangscontrole": Het component dat besluit of een concreet component instantie toegang krijgt tot de FHIR Resource Provider. Gebaseerd op het OAuth 2.0 autorisatie raamwerk ([RFC6749](https://tools.ietf.org/html/rfc6749)).
* "Identiteit & Authenticatie": Het component dat de identiteit van concrete component instanties (diensten) tot stand brengt (en onderhoud en actualiseert) met de daarbij behorende authenticatie middelen.&#x20;
* "FHIR Resource Provider": Het component die de benodigde gegevens afschermt en reageert op verzoeken om gegevens beschikbaar te stellen en te bewaren met gebruikmaking van toegangstokens.
* "Logging": Het component die alle uitvoerende handelingen vastlegt, zoals bedoeld in de AVG (Algemene Verordening Gegevensbescherming) en[ NEN7513:2018](https://www.nen.nl/nen-7513-2018-nl-245399). Daarnaast wordt er functionaliteit aangeboden om de geregistreerde handelingen te kunnen opvragen.

### Interfaces

De Koppeltaal 2.0 Interfaces:

* "FHIR REST API" : Worden gegevens op een consistente manier uitgewisseld op basis van de [HL7 FHIR R4](https://www.hl7.org/fhir/R4/history.html) - specificaties.&#x20;
* "OAuth2" : Een Open Autorisatie protocol dat gebruikt wordt om toegang te krijgen tot beveiligde resources via (FHIR) REST API's.
* "AppRegistratie": Worden gegevens van een concrete component instantie op een consistente en veilige manier vastgelegd.&#x20;
* "LogEntry" : Het vastleggen van een FHIR REST API interactie (tussen de componenten) in een logregel.
* "Subscription Channel": Een abonnementskanaal voor het versturen van notificaties door de FHIR Resource Provider bij bepaalde gebeurtenissen. De componenten kunnen zelf de gebeurtenis (criteria) aangeven waarin zij geïnteresseerd zijn.

### Diensten

De volgende Koppeltaal 2.0 diensten (concrete component instanties) kunnen door één of meerdere leveranciers, of in combinatie met leveranciers, aangeboden en vervuld worden (en zullen moeten worden geregistreerd):

* "Zorg ondersteuning": Is een beveiligde product die de ondersteuning levert voor de GGZ instelling, zoals het opvoeren van patiënten en behandelaren.
* "Rapportage": Is het kunnen leveren van verschillende (Management) rapportages over de werking en het gebruik van Koppeltaal 2.0.
* "Clientportaal": Is een beveiligde online omgeving waarin een cliënt (de patiënt of derde) inzage heeft in de 'eigen' gegevens die in het informatiesysteem van één zorgverlener staan.
* "Behandelaarsportaal": Is een beveiligde online omgeving waarin een behandelaar (zorgverlener) inzage heeft in de voortgang en resultaten van een uitgezette (zorg)behandeling.
* "eHealth Module": Is een module (eventueel ontsloten via een ander platform) die gebruikt of ingezet wordt voor of tijdens een bepaalde behandeling.

Het beheer van de Koppeltaal voorzieningen gebeurt via de dienst:

* "Beheerdersportaal": Is een beveiligde online omgeving waarin beheerders (technische) configuraties voor Koppeltaal kunnen doorvoeren en beheren, zoals identiteiten, authenticatie middelen en bevoegdheden.

{% hint style="info" %}
De Koppeltaal 2.0 diensten, zoals hierboven beschreven, kunnen afwijken of gecombineerd worden. De mogelijkheden (rol beschrijving) van een dienst wordt in een [Autorisatie matrix](https://confluence.vzvz.nl/pages/viewpage.action?pageId=90876067) vastgelegd en zijn meestal gebaseerd op het "need-to-know" principe.
{% endhint %}

![\`Koppeltaal 2.0](<../../.gitbook/assets/Koppeltaal 2.0 2.jpg>)
