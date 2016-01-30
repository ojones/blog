+++
date = "2016-10-21T19:25:22-08:00"
title = "Best HTML Table Parser"
menu = "code"
vanity = "https://github.com/ojones/html_table_parser"

+++

```
git clone https://github.com/ojones/html_table_parser.git
```

## Synopsis

Transform html tables into usable data structures.  Using beautiful soup table object, return 2D array structure, dictionary, or array of column data.  Imputes cell values from row and col spans :)

## Code Example

Given an html table (with or without row and col spans). You can make a 2D array
```python
soup = bs(YOUR_HTML_TABLE, "html.parser")
test_table = soup.find('table')
twod_array = parse.make2d(test_table)

# print 2D array
print(twod_array)
```
Use that 2D array to return column data by heading name
```python
# print column data by col heading name (case insensitive)
print(parse.twod_col_data(twod_array, 'first name'))
print(parse.twod_col_data(twod_array, 'lAst naMe'))
```
Or transform the soup table object (test_table) into a dictionary
```python
# row data begins on first row after col headings
# so rowstart is 1
print(parse.make_dict(test_table, 1))
```


## Motivation

I looked everywhere for the code to transform html tables with row and col spans into a 2D array and couldn't find it.  So I thought how hard could it be to quickly write my own.  It was actally kinda hard, so here it is for the next guy.

## Installation

So far html_table_parser is just a module with parser functions.  It works on Python 2.7 and Python 3.4.

## Tests
```
> py.test
```
## Contributors

Don't be shy.

## License

MIT