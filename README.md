# HTML Coding Guideline
1. [Divitis and Classitis](#divitis-and-classitis)
2. [Tables - For data rendering - Not for layout](#tables---for-data-rendering---not-for-data-structuring)
3. [Use UTF-8 Charset](#utf-8-charset)

## Divitis and Classitis

Divitis is the overuse of div tags in HTML. This scripting style is mainly seen in programmers who are relatively new to HTML & CSS. Divitis makes it difficult for search engines to crawl through the page and it also adds code which is not required.

Classitis is the use of class name for almost every element in the markup. Classitis reduces the performance of the page by adding unnecessary weight.


### Examples

####A markup with divitis:

```html
<div id="header">
	<div class="bold">Heading</div>
</div>
<div id="subheader">
	<div class="bold">Sub Heading</div>
</div>
<div>This is the content</div>
```

*The above markup without divitis:*

```html
<h1>Heading</h1>
<h2>Sub Heading</h2>
<p>This is the content</p>
```

####A markup with classitis:

```html
<ul>
	<li><a class="link" href="#">Link1</a></li>
	<li><a class="link" href="#">Link2</a></li>
	<li><a class="link" href="#">Link3</a></li>
	<li><a class="link" href="#">Link4</a></li>
	<li><a class="link" href="#">Link5</a></li>
	<li><a class="link" href="#">Link6</a></li>
</ul>
```

*The above markup without classitis:*

```html
<ul id="nav">
	<li><a href="#">Link1</a></li>
	<li><a href="#">Link2</a></li>
	<li><a href="#">Link3</a></li>
	<li><a href="#">Link4</a></li>
	<li><a href="#">Link5</a></li>
	<li><a href="#">Link6</a></li>
</ul>
```

####A markup full of divitis and classitis:

* http://www.bobdylan.com/songs/my-back-pages


###Recommended

1. Use divs only when grouping of various elements is required.
2. Divs can be used to segregate the page into various sections.
3. Use different elements.
4. Use ancestor selectors instead of using classes in CSS.


###Not recommended

1. Using divs to define everything instead of using other elements.
2. Using classes everywhere to select elements.

###Further reference
* http://css-tricks.com/css-beginner-mistakes-1/
* http://adam.kahtava.com/journal/2009/07/15/cronic-divitis-and-classitis-what-is-it/
* http://www.steveworkman.com/html5-2/standards/2009/classitis-the-new-css-disease/
* https://csscreator.com/divitis


## Tables - For data rendering - Not for data structuring

### Explanation

#### Tables for data renedering

1. Tables have been part of HTML almost since HTML began. The idea was to make it possible to display tabular data, equivalent to a spreadsheet.
2. This purpose is still valid. Using tables for tabular data is perfectly standards-compliant and makes a lot of sense from an accessibility standpoint.
3. HTML tables should only be used for rendering data that belongs naturally in a grid, in other words where the data describe a number of objects that have the same properties.


#### Tables for data layout

1. As the internet progressed and as people started doing more things online, designers started using tables to create multi-column website layouts.
2. This was never the intention of those who created HTML standards, but it quickly caught on and table-based layouts became the norm online.
3. Tables are less flexible than divs - Table contains different tags: the table tag being the wrapper, tr for each row and td for each cell. For readability, each tag is normally given its own line of code, with indention. Any developer maintaining that page in future has to go through a lot of code to understand its structure.
4. Nested tables are code smell that a website is stuck in table hell. The number of lines of code is endless, and the complexity is overwhelming. Tables are far from clean code and don’t bring anything semantic to the content unless you’re dealing with actual tabular data.
5. Excess code slows down development and raises maintenance costs.
More lines of code mean larger file sizes, which mean longer download times. Because tables increase the code base, such structures likely contain more bugs than layouts with less code lines.


###Recommended

*Tables should be used for data rendering: Why?*

* HTML tables should only be used for rendering data that belongs naturally in a grid, in other words where the data describe a number of objects that have the same properties.
* Tables should be used whenever you have tabular data to display.This could include charts of data or statistics, as well as things like price charts, product lists etc.
* Use CSS for layout, it has its own advantage over tables as explained in the following example.

###Not Recommended
*Tables should never be used for layout: Why?*
1. Tables are semantically incorrect markup for layout.
2. Tables prevent certain layouts from working within them (like height:100% for child elements of td tag).
3. Tables make life difficult for those using screen readers.
4. Tables lock you into the current design and make redesigns much harder.

###Example 

To make html tables :
`index.html`
```html 
<table cellpadding="0" cellspacing="0" border="0">
  <tr>
    <td colspan="3" height="120px">....</td>
  </tr>
  <tr>
    <td class="menu" valign="top">...</td>
    <td class="content" valign="top">...</td>
    <td class="aSide" valign="top">...</td>
  </tr>
  <tr>
    <td colspan="3">...</td>
  </tr>
</table>
</table>
```

To make css work like tables :
`index.html`
```html 
<div id="header">...</div>
<div id="menu">...</div>
<div id="content">...</div>
<div id="aSide">...</div>
<div id="footer">...</div>
```
###Further Readings
1. http://www.noupe.com/design/better-ui-design-proper-use-of-tables.html
2. http://phrogz.net/css/WhyTablesAreBadForLayout.html#incorrectsemantics
3. http://www.vanseodesign.com/css/css-divs-vs-tables/
4. http://www.chromaticsites.com/blog/13-reasons-why-css-is-superior-to-tables-in-website-design


##UTF-8 charset

Some character encodings cannot directly represent all characters an author may want to include in a document, HTML offers other mechanisms, called character references, for referring to any character. As there are huge number of characters, representing meaning, around the globe, proper care must be taken when representing these in HTML documents.

If you have any non-ASCII text in your CSS file, for example non-ASCII characters in font names, in values of the content property, in selectors, etc., you need to be sure that the CSS parser knows how to transform the bytes into characters correctly, so that it understands your CSS code.

###Example
<meta charset="utf-8">
`"&amp;"` represents &.

`"&#97;"` represents a.

`"&#35;"` represents #.

`"&#169;"` represents copyright symbol.

###Recommended
* Define meta encoding in HTML file not in CSS file.
* Use the character special code to print in the html document, e.g write the code `"&lt;"` instead of ">" to avoid the conflict. 

###Not Recommended
```html
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
```
* The reason to go with the short one is that it matches other instances where you might specify a character set in markup.
* Do not directy insert the special character, use charater code instead.

###Further references
[Getting Started](http://www.w3.org/International/getting-started/characters)
[Stackoverflow comparison between long and short form](http://stackoverflow.com/questions/4696499/meta-charset-utf-8-vs-meta-http-equiv-content-type)

