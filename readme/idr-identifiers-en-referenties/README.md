---
description: >-
  Elke resource moet uniek identificeerbaar zijn door de business en technische
  systemen. Hypermedia/links kunnen hierbij gebruikt worden om referenties of
  verwijzingen naar resources te gebruiken.
---

# IDR - IDentifiers en Referenties

### Logische ID

Elke resource heeft een id element dat de "logische ID" (logical ID) bevat van de resource die toegewezen MOET worden door de FHIR Resource Provider, die verantwoordelijk is voor het opslaan en beheren van de resource. Wanneer een nieuwe resource wordt aangemeld bij de FHIR Resource Provider, geeft de FHIR Resource Provider een nieuwe uniek logische id af binnen het domein van alle resources van hetzelfde type op dezelfde FHIR Resource Provider. Eenmaal toegewezen door de FHIR Resource Provider, wordt de "logische id" NOOIT gewijzigd.

De locatie van een resource-instantie is een absolute (locatie) URL die is samengesteld uit het basisadres waarop de instantie is gevonden, het resourcetype en de logische ID, zoals: https:/vzvz.fhir.nl/Patient/123 (waarbij 123 de logische id is van een patiënt).

Wanneer een resource wordt gekopieerd van de ene provider naar een andere provider, kan de kopie al dan niet dezelfde logische id op de nieuwe server behouden. Dit is afhankelijk van replicatie en beleid.

### Bedrijf Identifier

Naast de "logische ID" (logical ID) moet bij de resource ook minimaal één "bedrijf identifier" (business identifier) element gebruikt worden, die door de cliënt applicatie worden toegekend, die het originele bronsysteem is. Een "bedrijf identifier" wordt gebruikt om resources uniek te kunnen identificeren met (andere) systemen, die in andere omgevingen/domeinen aanwezig zijn. Bijvoorbeeld elke patiënt kan men identificeren a.d.h.v. een e-mail adres (geregistreerd bij IRMA) of een BSN. Een zorgverlener kan men identificeren via zijn AGB code. Een taak kan men identificeren aan een Taaknummer.

Met de hulp van de "bedrijf identifier" kan je altijd achterhalen of de resource instantie al aanwezig en bekend is. Hiermee kan men vervolgens ook de  "logische ID" achterhalen, als deze resource instantie bij de FHIR Resource Provider is aangemeld.

Voorbeeld: Patient.identifier

```
{
  "resourceType":"Patient",
  "id": "4497",
  "identifier":[
   {
      "use":"usual",
      "system":"https://irma.app/email",
      "value":"bard.klein@vzvz.nl"
   },
   {
      "use": "official",
      "system": "urn:oid:2.16.840.1.113883.2.4.6.3",
      "value": "123456789"
   }
  ]
}
```

{% hint style="success" %}
De applicatie die een nieuwe resource instantie creëert en publiceert MOET het bedrijf identifier element ([Identifier ](https://www.hl7.org/fhir/datatypes.html#identifier)type) specificeren, als het identifier element in de resource instantie beschikbaar is. &#x20;
{% endhint %}

### Referenties

De "logische ID" (logical ID) wordt gebruikt als referentie in resources, omdat een eenmaal toegewezen  "logische id" NOOIT wijzigt.&#x20;

Voorbeeld: Task.for.reference

```
{
  "resourceType": "Task",
  "for":
  {    
    "reference": "Patient/61",
    "type": "Patient"
  }
}
```

### Referentie Integriteit

Aanname is dat de gebruikte FHIR (Resource) Provider referentie integriteit afdwingt, waardoor resources altijd moeten worden aangeboden in zo'n volgorde dat referenties verwijzen naar reeds bestaande resources. In het geval dat er een eHealth Taak wordt aangeboden, zullen dus eerst de eHealth Activiteit (ActivityDefinition) en Patient resource waar naar deze eHealth Taak verwijst moeten bestaan.
