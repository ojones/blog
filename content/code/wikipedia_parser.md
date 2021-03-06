+++
date = "2015-10-02T19:25:22-08:00"
title = "Better Wikipedia Parser"
menu = "code"
vanity = "https://github.com/ojones/wikipedia_parser"

+++

```git
$ pip install wikipedia_parser
```

## Synopsis

Uses Wikipedia API to store page id, title, html, wiki text, expanded templates, categories, page links, and summary in one class object for easy reference.  Also parses infobox data from wiki text, including page name, template name, image name, image url, and labeled key value data.

## Code Example

Instantiate Wikipedia API object with page name or id:
```python
from wikipedia_parser.wikipedia_api import WikipediaAPI
# wikipedia search id can be digit or name (redirects are handled :)
search_id = 'Ada_Lovelace'
wiki_api = WikipediaAPI(search_id)
```
Here is the print list of available api resources 
```python
> print(dir(wiki_api))
[   ...
    'categories',
    'expanded_html',
    'html',
    'page_id',
    'page_links',
    'search_id',
    'summary',
    'title',
    'wiki_text']
```
If an infobox is present on page, you can parse the infobox data:
```python
from wikipedia_parser.infobox import Infobox
# wiki text can be from anywhere, does not need to come from WikipediaAPI object
wiki_text = wiki_api.wiki_text
infobox = Infobox(wiki_text)
```
Here is the print list of available attributes 
```python
> print(dir(infobox))
[   ...
    'data',
    'image_filename',
    'image_url',
    'page_name',
    'template_name']
```
Infobox "data" is a dict with keys and values from wikipedia page's infobox (if page has infobox). 
<br>Each key field in data returns a dict with values for 'plain_text', 'raw_text', and 'wiki_links'.
<br>Compare with <a href="https://en.wikipedia.org/wiki/Ada_Lovelace" target="_blank">Ada_Lovelace</a>
```python
# infobox.data for "Ada_Lovelace" returns:
{u'birth_date': {
    'plain_text': u'',
    'raw_text': u'{{birth date|1815|12|10|df=yes}}',
    'wiki_links': []},
u'birth_name': {
    'plain_text': u'The Hon. Augusta Ada Byron',
    'raw_text': u'The Hon. Augusta Ada Byron',
    'wiki_links': []},
u'birth_place': {
    'plain_text': u'London, England',
    'raw_text': u'London, England',
    'wiki_links': []},
u'caption': {
    'plain_text': u'Ada, Countess of Lovelace, 1840',
    'raw_text': u'Ada, Countess of Lovelace, 1840',
    'wiki_links': []},
u'children': {
    'plain_text': u'',
    'raw_text': u'{{plainlist |\n* [[Byron King-Noel, Viscount Ockham|Byron King-Noel, Viscount Ockham and 12th Baron Wentworth]]\n* [[Anne Blunt, 15th Baroness Wentworth]]\n* [[Ralph King-Milbanke, 2nd Earl of Lovelace]]}}',
    'wiki_links': [u'Byron King-Noel, Viscount Ockham',
                   u'Anne Blunt, 15th Baroness Wentworth',
                   u'Ralph King-Milbanke, 2nd Earl of Lovelace']},
u'death_date': {
    'plain_text': u'',
    'raw_text': u'{{death date and age|1852|11|27|1815|12|10|df=yes}}',
    'wiki_links': []},
u'death_place': {
    'plain_text': u'Marylebone, London, England',
    'raw_text': u'[[Marylebone]], London, England',
    'wiki_links': [u'Marylebone']},
u'field': {
    'plain_text': u'Mathematics, computing',
    'raw_text': u'Mathematics, computing',
    'wiki_links': []},
u'image': {
    'plain_text': u'Ada Lovelace portrait.jpg',
    'raw_text': u'Ada Lovelace portrait.jpg',
    'wiki_links': []},
u'name': {
    'plain_text': u'Ada, Countess of Lovelace',
    'raw_text': u'Ada, Countess of Lovelace',
    'wiki_links': []},
u'parents': {
    'plain_text': u'',
    'raw_text': u'{{plainlist |\n* [[Lord Byron|George Gordon Byron, 6th Baron Byron]]\n* [[Anne Isabella Byron, Baroness Byron|Anne Isabella Milbanke, 11th Baroness Wentworth]]\n  }}',
    'wiki_links': [u'Lord Byron', u'Anne Isabella Byron, Baroness Byron']},
u'resting_place': {
    'plain_text': u'Church of St. Mary Magdalene, Hucknall, Nottingham, England',
    'raw_text': u'[[Church of St. Mary Magdalene, Hucknall]], Nottingham, England',
    'wiki_links': [u'Church of St. Mary Magdalene, Hucknall']},
u'spouse': {
    'plain_text': u'William King-Noel, 1st Earl of Lovelace',
    'raw_text': u'[[William King-Noel, 1st Earl of Lovelace]]',
    'wiki_links': [u'William King-Noel, 1st Earl of Lovelace']},
u'title': {
    'plain_text': u'Countess of Lovelace',
    'raw_text': u'Countess of Lovelace',
    'wiki_links': []}}
```
## Motivation

<a href="https://github.com/spencermountain/wtf_wikipedia" target="_blank">wtf_wikipedia</a> and <a href="https://github.com/earwig/mwparserfromhell" target="blank">mwparserfromhell</a> were the best wikipedia parsers I could find.  This one is better. 

## Installation

Currently only works on Python 2.7 :(
```git
$ pip install wikipedia_parser
```
or
```git
git clone https://github.com/ojones/wikipedia_parser.git
```

## Tests

```git
$ py.test
```

## Contributors

Don't be shy.  Needs a couple updats for Python 3. Could use more functions to parse wiki templates such as "{{plainlist}}"

## License

MIT
