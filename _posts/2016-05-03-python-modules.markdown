---
layout: post
title: Python Modules
date : 2016-05-03
categories : python-modules
---

## xlsxwriter

Python module `xlsxwriter` can be used to create new Microsoft 
excel file. It is important to note that, xlsxwriter can only 
create new Microsoft excel file. It cannot be used to read 
existing excel file. Here we will see how this module can be 
used to create simple excel file.

```python

import xlsxwriter as xls

## Create an empty xlsx file called book.xlsx
book = xls.workbook("book.xlsx")
## add a sheet to the workbook, default name for the sheet is sheet1
sheet1 = book.add_worksheet()
## add another sheet, but this time lets rename it to "raw_data" 
sheet2 = book.add_worksheet("raw_data")
```

Once the workbook and worksheet are created, we can start adding data.

```python

## lets add a string to first cell
sheet1.write(0, 0, "Day")
## this can also be written by specifying the cell number
## for the 0, 0 case the cell is A1. xlsxwriter uses 0 based indexing
sheet1.write("A1", "Day")
```

It should ideally create a Microsoft excel file named "book.xlsx" file. 
Sometimes (for the reason not known) you won't see this file created. 
Close the workbook object explicitly to create "book.xlsx" file.

```python
book.close()
```

## HTMLParser

Python HTMLParser module can be used to remove HTML entities.   

```python
In [29]: import HTMLParser
In [30]: html_parser = HTMLParser.HTMLParser()

In [31]: html_parser.unescape("&lt; &amp; &quot; &apos; &gt;")
Out[31]: u'< & " \' >'

In [34]: html_parser.unescape("&quot;between quotes&quot; and 3 &gt; 1")
Out[34]: u'"between quotes" and 3 > 1'
```


