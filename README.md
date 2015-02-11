# Wiki
### Divitis and Classitis

Divitis is the overuse of div tags in HTML. This scripting style is mainly seen in programmers who are relatively new to HTML & CSS. Divitis makes it difficult for search engines to crawl through the page and it also adds code which is not required.

Classitis is the use of class name for almost every element in the markup. Classitis reduces the performance of the page by adding unnecessary weight.


### Example

1. A markup with divitis:

'''html
<div id="header">
	<div class="bold">Heading</div>
</div>
<div id="subheader">
	<div class="bold">Sub Heading</div>
</div>
<div>This is the content</div>
'''

The above markup without divitis

'''html
<h1>Heading</h1>
<h2>Sub Heading</h2>
<p>This is the content</p>
'''

2. A markup with classitis:

'''html
<ul>
	<li><a class="link" href="#">Link1</a></li>
	<li><a class="link" href="#">Link2</a></li>
	<li><a class="link" href="#">Link3</a></li>
	<li><a class="link" href="#">Link4</a></li>
	<li><a class="link" href="#">Link5</a></li>
	<li><a class="link" href="#">Link6</a></li>
</ul>
'''

The above markup without classitis:

'''html
<ul id="nav">
	<li><a href="#">Link1</a></li>
	<li><a href="#">Link2</a></li>
	<li><a href="#">Link3</a></li>
	<li><a href="#">Link4</a></li>
	<li><a href="#">Link5</a></li>
	<li><a href="#">Link6</a></li>
</ul>
'''

3. A markup full of divitis and classitis:
	http://www.bobdylan.com/songs/my-back-pages


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

