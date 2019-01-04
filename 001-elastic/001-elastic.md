# Elastic

"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

---

## Uvoz podatkov
Uvoz podatkov je narejen iz CSV datotek, ki jih je dal AKOS.
Poženejo se 1x, lahko se ponovno ob re-importu (treba najprej pobrisat indexe).

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
