# Kibana

"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

---

## Index Patterni

Z index patterni v Kibani združujemo več indexov skupaj za raziskovanje.
Index pattern se lahko ujema z enim indexom, ali pa vsebuje wildcard (*), da zajeme več indexov.

Index pattern [akos_quarterly_*] bo tako zajel četrtletne indexe za vsa leta, za vsa četrtletja, tako resnične R kot ocenjene E (akos_quarterly_e_2018_q3, akos_quarterly_r_2007_q3, ...).


## KIBANA API

### Get Object
[link](https://www.elastic.co/guide/en/kibana/current/saved-objects-api-get.html)

rabis met dejanski ID

```
GET /api/saved_objects/<type>/<id>
```

type (required)
   (string) Valid options, include: visualization, dashboard, search, index-pattern, config, and timelion-sheet



```
curl -X GET "http://localhost:5601/api/saved_objects/index-pattern/62e20b60-ff83-11e8-b870-2bdb873f83c7" -H 'kbn-xsrf: true'
```


#### Get Dashboard By Id

```
curl -X GET "http://localhost:5601/api/saved_objects/dashboard/77091a90-1dcc-11e9-9168-13a0b89e44e8" -H 'kbn-xsrf: true'
```
Response

vsebuje attributes

eden je [panelsJSON]
notri je Array vizualizacij/searchov, ki so v dashboardu


#### Get Visualization By Id
```
curl -X GET "http://localhost:5601/api/saved_objects/visualization/947e69f0-1dcb-11e9-9168-13a0b89e44e8" -H 'kbn-xsrf: true'
```

Response
vsebuje

visState - lastnosti vizualizacije

savedSearchId

#### Get Search By Id

```
curl -X GET "http://localhost:5601/api/saved_objects/search/823af180-1dc3-11e9-9168-13a0b89e44e8" -H 'kbn-xsrf: true'
```
Response

searchSourceJSON

### Find Objects
[link](https://www.elastic.co/guide/en/kibana/current/saved-objects-api-find.html)

```
GET /api/saved_objects/_find
```


```
curl -X GET "http://localhost:5601/api/saved_objects/_find?type=index-pattern&search_fields=title&search=my*" -H 'kbn-xsrf: true'
```

### GET Data

IZ INSPECTA REQUEST ZA VSAK GRAF POSEBEJ, oneliner, se potem posta na http://localhost:5601/elasticsearch/_msearch
