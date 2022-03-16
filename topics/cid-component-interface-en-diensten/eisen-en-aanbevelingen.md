# Eisen (en aanbevelingen)

1. De Koppeltaal voorzieningen zijn zo beschreven dat deze in verschillende (zorg) contexten gebruikt kunnen worden, als afzonderlijke en herbruikbare diensten. De volgende Koppeltaal voorzieningen onderscheiden we:
   1. Toegangsbeheer:
      1. Bevoegdheden (rollen en rechten)
      2. Autorisatie (toegang verlenen)
   2. Stelsel Register (Identiteit- en authenticatiebeheer)
   3. Stelsel Log
   4. FHIR Resource Provider (FHIR Store)
2. De Koppeltaal voorzieningen maken maximaal gebruik maken van (open) standaarden, om zo min mogelijk drempels te werpen voor gebruik.
3. De Koppeltaal voorzieningen en Koppeltaal applicaties zijn geregistreerd en opvraagbaar bij het Stelsel Register.
4. De Koppeltaal voorzieningen vult andere diensten aan en overlapt deze niet.
5. De Koppeltaal voorzieningen en Koppeltaal applicaties zijn gebaseerd op FHIR Resources, FHIR REST APIs en SMART on FHIR en SMART App Launch standaarden
   1. FHIR resources, zoals vastgelegd in [https://simplifier.net/Koppeltaalv2.0/\~resources?fhirVersion=R4](https://simplifier.net/Koppeltaalv2.0/\~resources?fhirVersion=R4)
   2. FHIR REST APIs, zoals (generiek) vastgelegd in [https://www.hl7.org/fhir/http.html](https://www.hl7.org/fhir/http.html), en geprofileerd voor Koppeltaal. Zie [https://simplifier.net/Koppeltaalv2.0](https://simplifier.net/Koppeltaalv2.0).
   3. SMART on FHIR en SMART APP Launch standaarden, zoals vastgelegd in [http://hl7.org/fhir/smart-app-launch/index.html](http://hl7.org/fhir/smart-app-launch/index.html)
6. De onweerlegbaarheid van informatie uitwisseling wordt gegarandeerd door wederzijdse authenticatie tussen Koppeltaal voorziening en Koppeltaal applicatie. Zie [tools.ietf.org/html/rfc6749#section-4.4](https://tools.ietf.org/html/rfc6749#section-4.4).
7. Beschikbaarheid van de Koppeltaal voorzieningen voldoet aan de met de afnemer gemaakte continuïteitsafspraken.
8. De integriteit van informatie uitwisseling en systeemfuncties wordt gegarandeerd door
   1. validatie en beheersing van gegevensverwerking en
   2. geautoriseerde toegang tot gegevens en systeemfuncties, door scheiding van systeemfuncties, door controle op communicatiegedrag en gegevensuitwisseling en door beperking van functionaliteit.
9. De Koppeltaal voorzieningen verschaft alleen geautoriseerde aanbieders en afnemers (Koppeltaal applicaties) toegang tot vertrouwelijke gegevens.
