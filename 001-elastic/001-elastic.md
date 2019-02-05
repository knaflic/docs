# Elastic

[Elasticsearch 6.x Cheatsheet](https://elasticsearch-cheatsheet.jolicode.com/)

---

## Uvoz podatkov
Uvoz podatkov je narejen iz CSV datotek, ki jih je dal AKOS.
Poženejo se 1x, lahko se ponovno ob re-importu (treba najprej pobrisat indexe).
Treba jih je importat po vrsti zaradi prejšnjih vrednosti
---

### Četrtletni vprašalniki

Klic se mora izvesti za vsako leto posebej. Za vsako leto se naredijo 4 indexi, za vsako četrtletje svoj:
* [akos_quarterly_r_2008_q1]
* [akos_quarterly_r_2008_q2]
* [akos_quarterly_r_2008_q3]
* [akos_quarterly_r_2008_q4]

```
POST /api/searchEngine/csvDataQuarterly/{year}/_importHardcoded
```

Lahko se naredi import tudi za posamezno cetrtletje v letu
```
POST /api/searchEngine/csvDataQuarterly/{year}/{quarter}/_importHardcoded
```

### Letni vprašalniki
Naredi se en index za vsako leto:
* [akos_yearly_r_2011]

```
POST /api/searchEngine/csvDataYearly/_importHardcoded
```

### Incidenti poročila
Vsi incidenti so v indexu [akos_report_incident]

```
POST /api/searchEngine/csvDataIncidenti/_importHardcoded
```

### Obvestila poročila
Vsa obvestila so v indexu [akos_report_notification].

```
POST /api/searchEngine/csvDataObvestila/_importHardcoded
```

---

## Ocenjena vrednost


Ocenjena vrednost za četrtletje se naredi tako, da se vzame index nekega obstoječega četrtletja in se ga "skopira"
z novim imenom (korak 1).
Nato se v tem novem indexu popravi vrednosti, ki so specifične (korak 2):
  * datum
  * isEstimate=true
  * kvartal
  * leto
  * obdobje
  * vrednostPrejsnja=0.0
  * vrednostSprememba=1.0


  Ime indexa z ocenjenimi vrednostmi (estimates) se razlikuje od indexa z resničnimi vrednostmi (real) po črki v imenu:
  * index z ocenjenimi vrednostmi vsebuje črko [e]: [akos_quarterly_e_2018_q2]
  * index z resničnimi vrednostmi vsebuje črko [r]: [akos_quarterly_r_2018_q2]

korak 1
```
POST /api/searchEngine/quartery/_createEstimate
```

korak 2
```
POST /api/searchEngine/quartery/_initializeEstimate
```

Koraka lahko nekaj časa trajata, zato korak 2 poženi šele, ko si prepričan, da je korak 1 končal.

Ob importu resničnih vrednosti (store case data) se ocenjena vrednost izbriše iz E indexa, resnična pa vpiše v R index.

Za demo lahko uporabiš:

```
POST /api/searchEngine/csvDataQuarterly/{year}/{quarter}/_updateEstimatesHardcoded
```

---

## Združitve, prevzemi, preimenovanja

Podatki v elastiku imajo dva property-a, in sicer [operaterOrig] in [davcnaOrig], ki so ob importu napolnjeni z istimi podatki kot [operater] in [davcna]
  * Če nek operater prevzame drugega operaterja, se podatkom prevzetega operaterja property-ja [operater] in [davcna] poupdate-ata z vrednostmi prevzemnika, [operaterOrig] in [davcnaOrig] pa ostaneta od originala.
  S tem omogočimo pripravo poročil za združene podatke oz. za nezdružene.

  ```
POST /api/searchEngine/_mergeTakeover
  ```

  * Če se dva operaterja združita pod novim imenom in davčno številko, se jima na vseh podatkih  [operater] in [davcna] poupdate-ata z novim imenom in davčno


  * Če se operater preimenuje, se vsem podatkom poupdejta polje [operater], v polju [operaterOrig] pa ostane stara vrednost
