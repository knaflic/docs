# Elastic

This chapter is for people who have not used Elasticsearch yet. It covers Elasticsearch basic concepts and guides you into deploying and using your first single node cluster. Every concept explained here are detailed further in this book.

In this introduction chapter you will learn:

- The basic concepts behind Elasticsearch
- What's an Elasticsearch cluster
- How to deploy your first, single node Elasticsearch cluster on the most common operating systems
- How to use Elasticsearch to index documents and find content
- Elasticsearch configuration basics
- What's an Elasticsearch plugin and how to use them

---

## Uvoz podatkov
Uvoz podatkov je narejen iz CSV datotek, ki jih je dal AKOS.
Poženejo se 1x, lahko se ponovno ob re-importu (treba najprej pobrisat indexe).

---

### Četrtletni vprašalniki

Klic se mora izvesti za vsako leto posebej. Za vsako leto se naredijo 4 indexi, za vsako četrtletje svoj:
* akos_quarterly_r_2008_q1
* akos_quarterly_r_2008_q2
* akos_quarterly_r_2008_q3
* akos_quarterly_r_2008_q4

```
POST /api/searchEngine/csvDataQuarterly/{year}/_importHardcoded
```

### Letni vprašalniki
```
POST /api/searchEngine/csvDataYearly/_importHardcoded
```

### Incidenti poročila
```
POST /api/searchEngine/csvDataIncidenti/_importHardcoded
```

### Obvestila poročila
```
POST /api/searchEngine/csvDataObvestila/_importHardcoded
```
