# Eisen (en aanbevelingen)



1. De basis interacties zijn op FHIR RESTful API gebaseerd. Zie: [http://hl7.org/fhir/http.html](http://hl7.org/fhir/http.html).&#x20;
2. FHIR Koppeltaal resource profielen gebaseerd op R4. Zie [https://simplifier.net/koppeltaalv2.0/\~resources?category=Profile](https://simplifier.net/koppeltaalv2.0/\~resources?category=Profile)
3. De Koppeltaal FHIR Resource Provider ondersteunt:
   1. de basis FHIR interacties (Create, Retrieve, Update en Delete) op FHIR Koppeltaal resources profielen, om informatie uit te wisselen
   2. search of zoek opdrachten op FHIR resource content (minimaal op basis van een gegeven identifier)
      1. Sorteren. Zie [https://www.hl7.org/fhir/search.html#\_sort](https://www.hl7.org/fhir/search.html#\_sort)
      2. Beperkingen op aantal. Zie [https://www.hl7.org/fhir/search.html#count](https://www.hl7.org/fhir/search.html#count)
      3. FHIR Paging (navigatie). Zie [https://www.hl7.org/fhir/http.html#paging](https://www.hl7.org/fhir/http.html#paging)
   3. formaat ondersteuning (XML en JSON) op de FHIR resource content. Zie [https://www.hl7.org/fhir/http.html#mime-type](https://www.hl7.org/fhir/http.html#mime-type)
   4. validatie op de content van de FHIR resources (content is zowel JSON als XML) m.b.v. de Koppeltaal profielen. Zie [https://simplifier.net/koppeltaalv2.0/\~resources?category=Profile\&sortBy=RankScore\_desc](https://simplifier.net/koppeltaalv2.0/\~resources?category=Profile\&sortBy=RankScore\_desc)
   5. abonnement registratie (Subscribe) en signalering (via RestHook notificatie)
   6. (entry of audit) logging m.b.v. FHIR AuditEvent Resource. Voor FHIR AuditEvent Resource aparte FHIR Store inrichten.
   7. opvragen van FHIR server specificaties waaraan voldaan MOET worden, zoals:
      1. overzicht van ondersteunende (FHIR) resources
      2. overzicht van ondersteunende zoek parameters
      3. FHIR REST Endpoints
      4. FHIR Security Endpoints (authenticiteit, access token en introspectie)
   8. **NIET trial versies van FHIR interacties in huidige Koppeltaal 2.0 ondersteunen, zoals Patch en conditionele operaties, totdat er meer ervaring is opgedaan met gebruik ervan. De status (wijziging) zal worden beoordeeld in toekomstige versies van FHIR.**
4. Security (beveiliging)
   1. authenticatie minimaal op basis van de "client credential flow" van OAuth 2.0 voor systemen. Zie: [https://datatracker.ietf.org/doc/html/rfc6749#section-4.4](https://datatracker.ietf.org/doc/html/rfc6749#section-4.4)   &#x20;
   2. autorisatie gebaseerd op SMART on FHIR scopes en launch context  ([http://docs.smarthealthit.org/authorization/best-practices/](http://docs.smarthealthit.org/authorization/best-practices/)) minimaal gebaseerd op Role-Based Access Control (RBAC)
   3. gebruik kunnen maken van reverse proxy's en (HTTP) load-balancing voor het verlichten van de load bij de aanroep van web services
   4. HIPAA compliant (en OWASP top tien lijst [https://owasp.org/www-project-top-ten/](https://owasp.org/www-project-top-ten/))
      1. toegangscontrole
      2. integriteit
      3. entiteit authenticatie
      4. unieke identificatie
      5. audit control
      6. transmissie beveiliging
      7. toegangsprocedure voor noodgevallen
