---
layout: default
---


## TOC

- [Elastic](001-elastic/001-elastic.md/#elastic)
  * [Uvoz podatkov](001-elastic/001-elastic.md#uvoz-podatkov)
    + [Četrtleti vprašalniki](001-elastic/001-elastic.md#%C4%8Detrtletni-vpra%C5%A1alniki)
    + [Letni vprašalniki](001-elastic/001-elastic.md#letni-vpra%C5%A1alniki)
    + [Incidenti poročila](001-elastic/001-elastic.md#incidenti-poro%C4%8Dila)
    + [Obvestila poročila](001-elastic/001-elastic.md#obvestila-poro%C4%8Dila)


---
---
---



## Styling

This is the Markdown styling used in this book. If you plan to contribute, please use it.

### Chapter title

```markdown
# This is a chapter title

```

### Chapter part

```markdown
---

## A chapter part title is preceded by an horizontal line
```

### Chapter subpart

```markdown
### A level 1 subpart
#### A level 2 subpart
```

### Images

```markdown
![An image should have an alt text](use/a/relative.link)
```

### Code:

```markdown
An `inline code block` goes like this
```

API calls go the Curl way

```bash
curl -X POST "localhost:9200/_search" -H 'Content-Type: application/json' -d'
{
    "query" : {
        "match_all" : {}
    },
    "stats" : ["group1", "group2"]
}
'
```

Yaml code is expanded for more readability
```yaml
---
some:
  value:
    goes: "like this"
```

### Links

```markdown
[An internal link](has/a/relative.path)
[An external link](https://has.an.absolute/path)
```

### Lists

Urdered lists:

```markdown
Only one line break between a paragraph and

* An
* unordered
* list
	* with
	* subitems
```

Ordered lists:

```markdown
1. An
2. Ordered
3. List
	1. With
	2. subitems
```








Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [](#header-1)Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## [](#header-2)Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### [](#header-3)Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [](#header-4)Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [](#header-5)Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [](#header-6)Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
