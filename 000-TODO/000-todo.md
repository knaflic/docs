# TODO

Tukaj je seznam manjkajočih stvari za analitiko:


* Z169 -  treba je narediti UI za dodajanje vrednosti za
  * population Surs
  * households Surs
  * households Eurostat

    potem to shranit v tabelo in pri importu upoštevati te vrednosti (trenutno so hardcodane)

* trenutno je narejen import ob close-u case samo za vprašalnike. Treba je narediti se za poročila (incidenti, obvestila)

* ocenjena vrednost je trenutno narejena samo za četrletne vprašalnike. Treba je narediti še za letne (Z144)

* pivot table (vrtilne tabele) - treba nabavit plugin in integrirat (Z154)

* generiranje in shranjevanje poročil (Z160)

* izvozi poročil (docx, xlsx, html, txt, jpg, pdf) (Z162)

* združitve in prevzemi, preimenovanja, API, UI (operater/operaterOrig, davcna/davcnaOrig) (Z166, Z167)

* skupine operaterjev, API, UI (operaterSkupina) (Z168)

* User management - SearchGuard plugin - file based (YML) configuration (Z149, Z170)
  - skrbi me, da free varianta ne bo dovolj (field-level security, Audit Logging, Compliance za Elastic)
