<link href="/Users/wport/DevonThink_Data/css/pure.css" rel="stylesheet"></link>

# The `<div>` and `<span>` tags Unravelled!   

## Using block and inline containers, styled entirely from an external stylesheet.  

HTML contains 2 tags generally used as "containers".

> The `<div>` is the first of the two and its use is as a block-level container.  

> The second, `<span>` is an inline container.

Think of a container as an individual part or section of a web page, with content within it of some sort. The container can be styled wholly with CSS, thus separating style from content and being standards compliant at the same time.

The `<div>` tag is wrapped around a whole section of content, or block (hence, block level) and `<span>` is wrapped around content which is on just one line, (or inline).

`<div>` tags can contain as much content as you like - a block can have as much or little within it as is necessary.   

`<span>` tags, generally use very small & specific parts of content.

When combined with CSS, this can be put to good use for styling areas of content. For example, you create a CSS class, .header, and you setup some background colours, font styles & weights, margins, padding and so on. You then simply place in your page the following code:

`<div class="header">Your content</div>`

All the styling is handled by your external stylesheet file and all that is left is for you to put your content (I.e. text and images) within the start and end tags. The `<span>` tag can also be put to good use with css. For example, you have a CSS class called .alt_text which contains style information for text in a slightly larger font, which is italic and dark green in colour. Simply wrap your text within the following code and this is then created:   

`<span class="alt_text">Your text</span>`  

The following example illustrates a more advanced look at block and inline containers, styled heavily and entirely with an external stylesheet file. The illustration is explained in the next paragraph. Fig 1: Block and inline containers, styled and positioned with CSS. (View as web page in a new window) Lets look into the code which creates the above. If we split it up into parts we can see that there is a header section, body section and footer section. Within the body section are 3 different sets of text and there is also what i've called a "floating blob" which floats around the page as you resize it. The header The code for the header looks like this:  

`<div class="header">My header</div>`

As you can see, all there is is a container, which has the CSS class, "header" applied to it. The text "My header" is between the tags and is what appears on the page. The CSS for the "header" class looks like this: 


	DIV.header {
	BACKGROUND-COLOR: #b0c4de; 
	BORDER-BOTTOM: #87ceeb 1px solid;
	BORDER-LEFT: #87ceeb 1px solid;
	BORDER-RIGHT: #87ceeb 1px solid;
	BORDER-TOP: #87ceeb 1px solid;
	COLOR: #191970; 
	FONT-FAMILY: Verdana, Arial; 
	FONT-SIZE: x-large;
	FONT-STYLE: normal;
	FONT-VARIANT: normal;
	FONT-WEIGHT: bolder;
	MARGIN: 2px 10% 10px;
	PADDING-BOTTOM: 2px;
	PADDING-LEFT: 2px;
	PADDING-RIGHT: 2px;
	PADDING-TOP: 2px;
	TEXT-ALIGN: left;
	TEXT-DECORATION: none;
	TEXT-TRANSFORM: none;
	}

* The classname .header is prefixed with DIV, so that it can only be applied to the `<div>` tag. 
* The border of the container is set as #87ceeb, with a 1 pixel border width that is solid in style. 
* The font family has been declared as Verdana, with Arial as an alternative, the font-size has been set to x-large which is a relative measurement, so the size is in the users control and they can adjust it via their web browser and the font-weight is also set to a relative measurement, bolder, which means that the text will be bolder than normal text. 
* The padding of all four corners of the container is set to 2 pixels, ensuring the content has some seperation from the edges of the element. 
* The positioning of the header section is achieved using margin. 
* Margin provides space between the edge of the element and any other elements, or the edges of the screen. 
* The margin at the top of the header is set to 2 pixels, so there is 2 pixels width between the top blue border and the absolute top of the page. 
* The margin on the left and the right is 10%, which is how the element achieves a centered appearance, with 10% of the total width on the left and right hand side as clear space. 
* The margin at the bottom is set to 10 pixels, creating a gap between the bottom of the header and the next `<div>` . 
* The body Lets look at the body container. 

## Let's put it all to use

First the HTML:

`<div class="body"><span class="normal">Some normal text</span> <span class="float">Some text floating on the right</span> <span class="alt_text">Some different text</span></div>`

A little bit more HTML this time round, as we have a the block level container with the classname "body" along with some inline containers, each containing some text with different classes applied. Its useful to note at this point that `<div>` and `<span>` tags, like lots of other HTML tags, can be nested within each other. (Within reason!) Lets examine the classname "body". 

	DIV.body { 
	BACKGROUND-COLOR: #ffffff;
	BORDER-BOTTOM: #808080 2px solid;
	BORDER-LEFT: #808080 2px solid;
	BORDER-RIGHT: #808080 2px solid;
	BORDER-TOP: #808080 2px solid;
	COLOR: #000000;
	FONT-FAMILY: 'Courier New', Courier, 'Times New Roman';
	FONT-SIZE: medium;
	FONT-WEIGHT: lighter;
	HEIGHT: 80px;
	MARGIN: 16px 2%;
	PADDING-BOTTOM: 2px;
	PADDING-LEFT: 2px;
	PADDING-RIGHT: 2px;
	PADDING-TOP: 2px;
	TEXT-DECORATION: none;
	} 

The only new styling that has been applied here (compared to the CSS for the header) is the height declaration, which has been set to 80px. The rest of the declarations are the same as have been applied to the header. (Described above) The 3 inline styles that are within the body section are as follows: 

	.normal {
	COLOR: #000000;
	FONT: lighter small Verdana, Arial, 'MS Sans Serif';
	MARGIN: 2px;
	PADDING-BOTTOM: 2px;
	PADDING-LEFT: 2px;
	PADDING-RIGHT: 2px;
	PADDING-TOP: 2px;
	TEXT-ALIGN: left;
	TEXT-DECORATION: none;
	TEXT-TRANSFORM: none;
	} 

Again, there are no new declarations indicated here. The classname has not been prefixed with SPAN in this instance, meaning that other HTML tags could use this class. If you wanted to apply something to a paragraph tag `<p>` but also `<div>` and `<span>` tags, you would just name the class `.classname`, so that it is available to all tags. The classes "float" and "alt_text" are as follows:
	
	SPAN.float {
	FLOAT: right;
	POSITION: static;
	}
The float style is applied to this class, which will "float" the text within the container, on its right hand side. The position is set to static. 

	SPAN.alt_text { 
	COLOR: #8fbc8b;
	FONT-FAMILY: Arial;
	FONT-SIZE: medium;
	FONT-STYLE: italic;
	FONT-WEIGHT: lighter;
	}  

This is the alternative text class, which makes the text appear with a different font style, colour and style (italic). 

## The floating blob 

The next part is the "floating blob", which hovers around the page as you resize it. The HTML for this is as follows:

`<div class="floating_blob">My floating blob</div>`

The CSS for the floating blob looks like this: 
	
	DIV.floating_blob {
	BACKGROUND-COLOR: #ffb6c1;
	BORDER-BOTTOM: #a52a2a 3px solid;
	BORDER-LEFT: #a52a2a 3px solid;
	BORDER-RIGHT: #a52a2a 3px solid;
	BORDER-TOP: #a52a2a 3px solid;
	FLOAT: none; 
	MARGIN: 2px;
	PADDING-BOTTOM: 3px;
	PADDING-LEFT: 3px;
	PADDING-RIGHT: 3px;
	PADDING-TOP: 3px;
	POSITION: absolute;
	TOP: 21%;
	VISIBILITY: visible;
	Z-INDEX: 1; LEFT: 50%;
	}  

As this container is floating on the page, some new definitions are included as part of this class. Position is set to absolute, and the top and left are defined as 21% and 50% respectively, meaning that the element will hover 21% from the top of the page and 50% from the left. The Z-Index of this container is defined as being 1, although for the purposes of the actual page its inclusion is trivial. The visibility of the class is set as visible. The class is also set not to float. 

## The footer 

The final part of the page is the footer, which is pretty similar in its make up to the header, but is obviously at the foot of the page. The HTML for the footer looks like this:

`<div class="footer">My footer</div>`

As before, just the `<div>` tag with the classname "footer" applied to it, with the text "My footer" being the content. The CSS for the footer looks like this:

	DIV.footer { 
	BACKGROUND-COLOR: #ff4500;
	BORDER-BOTTOM: #4169e1 1px solid;
	BORDER-LEFT: #4169e1 1px solid;
	BORDER-RIGHT: #4169e1 1px solid;
	COLOR: #dcdcdc;
	FONT-FAMILY: Verdana, Arial;
	FONT-STYLE: normal;
	FONT-VARIANT: normal;
	PADDING-LEFT: 2px; FONT-WEIGHT: lighter; FONT-SIZE: x-small; PADDING-BOTTOM: 2px; MARGIN: 3px 6px 10px;
	PADDING-RIGHT: 2px; BORDER-TOP: #4169e1 1px solid;
	PADDING-TOP: 2px;
	TEXT-ALIGN: right;
	TEXT-DECORATION: none;
	TEXT-TRANSFORM: none;
	} 

Nothing new to explain here except that the text-align property is set to right instead of left, which is what makes the text appear on the right hand side.  

## Summary
 
 Containers vastly unclutter your HTML pages and make the code very clean. Web standards are adhered to, valid XHTML and CSS for future browsers means the pages will appear as expected on current and future browsers. Using CSS gives you excellent control of page elements in terms of visual style and position CSS classes held within an external stylesheet makes for excellent consistency and changes can be made in seconds by altering class definitions rather than lots of HTML pages. 
 


