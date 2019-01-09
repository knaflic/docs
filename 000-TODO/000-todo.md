# TODO

Tukaj je seznam manjkajočih stvari za analitiko:


1. treba je narediti API, UI za dodajanje vrednosti za
  - population Surs
  - households Surs
  - households Eurostat

    potem to shranit v tabelo in pri importu upoštevati te vrednosti (trenutno so hardcodane) (Z169)

2. trenutno je narejen import ob close-u case samo za vprašalnike. Treba je narediti se za poročila (incidenti, obvestila)

3. ocenjena vrednost je trenutno narejena samo za četrletne vprašalnike. Treba je narediti še za letne, in UI (Z144)

4. pivot table (vrtilne tabele) - treba nabavit plugin in integrirat (Z154)

5. generiranje in shranjevanje poročil (Z160)

6. izvozi poročil (docx, xlsx, html, txt, jpg, pdf) + uvoz (Z162)

7. združitve in prevzemi, preimenovanja, API, UI (operater/operaterOrig, davcna/davcnaOrig) (Z166, Z167)

8. skupine operaterjev, API, UI (operaterSkupina) (Z168)

9. User management - SearchGuard plugin - file based (YML) configuration, API, UI (Z149, Z170)
  - problem uporabniki operaterja, zaradi index-based security
  - skrbi me, da free varianta ne bo dovolj (field-level security, Audit Logging, Compliance za Elastic)
