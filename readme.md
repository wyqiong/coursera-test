browser-sync start --server --directory --files "*"

# HTML
stackoverflow.com
jsfiddle.net panes of <HTML CSS JS >
codepen.io(css-tricks.com)

**Relevant History of HTML**
www.w3.org/TR/html5/
caniuse.com/
validator.w3.org
www.w3schools.com

**block-level/inline elements**
```
<div>/<span>
```
---->> HTML 5 >> ----
flow/phrasing

**semantic html elements**
```
<section> </section>
```
**lists**
```
<ul> <li>
<ol> <li>
```
**HTML character entity reference**
```
<     >    &
&lt; &gt; &amp;

&nbsp : non breaking space//between the words you don't want separated
&copy : @
&quot : "

```
**creating links**
```
external/internal/sections of a doc
<a href="url/html/<section>" target=" " title=" ">url</a> flow+phrasing == block+inline
target = "_black" : open a link in a new window or tab
```
**displaying images**
```
<img src="url" width= height= alt= > inline
wight&height : save space for jumping when internet is slow
```
# CSS
## CSS Basics
csszengarder.com

**selectors : element, class, & id**
```
element selector:
	p{}
class selector:
	.blue{}
id selector:
	#name{}
grouping selectors:
	div,  .blue{}
```
**combining selectors**
```
	p.big{}
	article > p{}  direct child of article
	article p {}   every p that is inside at any level of article
	div p{}		   any p that inside div
	.colored p{}   every p that is inside an ele with class="colored"
	article > .colored   every ele with class="colored" that is a direct 					 child of aritcle ele	
``` 
**pseudo-class selecters**
```
	:link
	:visited
	:hover
	:active
	:nth-child(...)

	a:link, a:visited{}
	a:hover, a:active{}
	header li:nth-child(3/odd):hover{}
```
## CSS Rules Conflict Resolution and Text Styling
**style placement**
inline
external stylesheet
**conflict resolution**
rules:
> Last Delclaration Wins
> Declarations Merge
> Inheritance

specificity
> Most Specific Selector Combination Wins

method: score
[https://www.coursera.org/learn/html-css-javascript-for-web-developers/lecture/5OuBt/lecture-17-part-2-conflict-resolution](https://www.coursera.org/learn/html-css-javascript-for-web-developers/lecture/5OuBt/lecture-17-part-2-conflict-resolution)`
```
{color : green !important;} //avoid this
```
**styling text**
```
.style{
	font family:
	color: #0000ff; //RGB
	font-style:
	font-weight:
	font-size:
	text-transform:capitalize/lowercase/uppercase;
	text-align:right;
}
body{
font-size: 120%/2em/.5em;
}
```
## The Box Model and Layout
**The Box Model**
```
* { //not inherit,universal selector
	box-sizing: border-box; 
}
body{
	margin: 0;
	padding: 0;
}
#box{
	padding: 10px 10px 10px;
	border: 5px solid black;
	margin: 40px;
	width: 300px;
	box-sizing: border-box/content-box;//border-box in Bootstrap(Prefer) whole 300px
	height: ; //less to spill out
	overflow: visible/hidden/auto(scroll bar)/scroll(always show);
}
h1{
	margin-bottom: 30px;
}

Cumulative and collapsing Margins
Spill over with overflow

```
**The background Property**
```
#bg {
	background-color: blue;
	background-image: url("yaakov.png");
	background-repear: no-repeat;
	background-position: bottom right/(center) right;
	
	background: blue url("yaakov.png") no-repeat right-center;
}
```
Positioning Elements by Floating
```
div {
	backgound-color: #00ffff;
}
p {
	width: 50px;
	height: 50px;
	border: 1px solid black;
}

#p1 {
	background-color: #A52A52A;
	float: left;
}
#p2 {
	background-color: #A52A52A;
	float: right;
}
#p3 {
	background-color: #A52A52A;
	clear: left/right/both;
}

section {
	clear: left;//nothing should be allowed to flow to the left of it
}
```

```
* {
	box-sizing: border-box;
}
div {
	backgound-color: #00ffff;
}
p {
	width: 50%;
	//border: 1px solid black;
	float: left;
	padding: 10px;
}

#p1 {
	background-color: #A52A52A;

}
#p2 {
	background-color: #A52A52A;

}

section {
	clear: left;//nothing should be allowed to flow to the left of it
}
```
**Relative and Absolute Element Positioning**
```
Positioning CSS(offset) properties are:
	top,bottom,left,right

div #container {
	position: relative;
	top: 60px;
}
#p1 { 
	position: relative;
	top: 50px;
	left: 50px;
}
#p2 {
	to: 0;
	from: 0;
}
```
## Introduction to Responsive Design
**Media Queries**
```
/*start with base styles*/
p { ...}
@media (media feature)logical operator (media feature) {
	p{
		...
	}
}

/***** Large devices *****/
@media (min-width: 1200px) {
	#p1 {
		width:80%;
	}
	#p1 {
		width: 150px;
		height: 150px;
	}
}
/***** Medium devices *****/
@media (min-width: 992px) and (max-width: 1199px){
	#p1 {
		width:50%;
	}
	#p1 {
		width: 100px;
		height: 100px;
	}
}
```
**Responsive Design(Layout)**
Desktop + Mobile
> Responsive Web Site : 
> + Site's layout adapts to the size of the device
> + Content verbosity or its visual delivery may change

12-Colum Grid Responsive Layout
+ use % to achieve fliud width(wrt browser width)
![](http://www.uisdc.com/wp-content/uploads/2014/04/21-a-better-photoshop-grid-for-responsive-web-design.jpg)

```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

# Bootstrap
getbootstrap.com
getbootstrap.com/css/#grid
## Introduction to Twitter Bootstrap
> Mobile First == PLAN mobile from the start
> CSS Framework is mobile ready

**The Bootstrap Grid System**
```
class="container" //Must be inside container(or container-fluid)
class="row"		  //Creates horizontal groups of cols; Applies nagative left/right margins
class="col-SIZE-SPAN" 
//SIZE: Screen width range identifier,Cols will collapse(i.e.,stack)below that width Unless another rule applies
//SPAN: How many cols element should span, Values: 1 through 12 
if no other rules apply,specifying col-xs-...
```
Why Negative Row Margin?
[https://www.coursera.org/learn/html-css-javascript-for-web-developers/lecture/e2lrH/lecture-26-part-1-the-bootstrap-grid-system](https://www.coursera.org/learn/html-css-javascript-for-web-developers/lecture/e2lrH/lecture-26-part-1-the-bootstrap-grid-system "Why Negative Row Margin?")

