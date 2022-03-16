---
description: >-
  De basis voor alle (technische) interacties in Koppeltaal 2.0 is op FHIR
  RESTful API gebaseerd. Hierdoor worden de interacties vereenvoudigd door een
  algemene interface toe te passen.
---

# BAI - Basis Interacties

### De basis principes van REST

* REST geeft elke **resource** een ID (identifier). Alles wat identificeerbaar moet zijn, moet een ID hebben. REST noemt deze identificeerbare dingen 'resources'. Op internet is er een uniek concept voor ID's: de URL. URL's vormen een globale naam en het gebruik van URL's om de belangrijkste resources te identificeren, betekent dat ze een unieke, globale ID krijgen.
* REST is een **client-server**-architectuur. De server manipuleert en slaat informatie op en stelt deze op efficiënte wijze ter beschikking aan gebruikers. De client of afnemer van een dienst neemt die informatie over en toont deze aan de gebruiker en/of gebruikt deze om latere informatie verzoeken uit te voeren. Deze scheiding van taken stelt zowel de client als de server in staat om onafhankelijk verder te evolueren, omdat het hier alleen vereist wordt dat de interface hetzelfde blijft.
* REST zorgt voor een **uniforme interface** tussen de (systeem)componenten. Dit vereenvoudigt de architectuur, omdat alle componenten dezelfde regels volgen om met elkaar te praten. Het maakt het ook gemakkelijker om de interacties tussen de verschillende (systeem)componenten te begrijpen. Om dit goed te bereiken hebben we een aantal randvoorwaarden nodig. Zie de basis CRUD verderop.
* REST gebruikt meerdere **representaties.** Een representatie is een formaat waarin de gegevens worden getransporteerd tussen client-server. Met behulp van HTTP-protocollen kan een client vragen om een weergave in een bepaald formaat. REST staat meerdere representaties voor een resource toe. JSON en XML zijn de gebruikte representaties binnen Koppeltaal.
* REST is **stateless**. Dat betekent dat de communicatie tussen de client en de server altijd alle informatie bevat die nodig is om een aanvraag uit te voeren. Er is geen sessiestatus op de server, deze wordt volledig aan de kant van de client bijgehouden. Als toegang tot een resource authenticatie vereist, dan moet de client zichzelf bij elk verzoek authentiseren, d.m.v. een toegangstoken.

Basis interacties met een server of andere applicatie moeten volledig worden aangestuurd door hypermedia (links-URLs). De client heeft geen voorkennis van de dienst nodig om deze te gebruiken, behalve een toegangspunt (endpoint) en natuurlijk basiskennis van het mediatype van de representaties, in ieder geval voldoende om hyperlinks en linkrelaties te vinden en te identificeren.

Het volgend interactiediagram, beschrijft een data-uitwisselingspatroon waar _alle_ functionele interacties op gebaseerd zijn:

![Basis Interacties](../.gitbook/assets/BasisInteracties.jpg)
