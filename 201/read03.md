# Links
## Links are the defining feature of the web because they allow you to move from one web page to another.
### Types of links:
1. ##### Links from one website to another.
2. ##### Links from one page to another on the same website.      
3. ##### Links from one part of a web page to another part of the same page.
4. ##### Links that open in a new browser window.
5. ##### Links that start up your email program and address a new email to someone.


#### Links are created using the (a) element. Users can click on anything between the opening (a) tag and the closing (/a)tag. You specify which page you want to link to using the href attribute.
example : ``` <a href="http://www.ABCD.com">ABCD</a> ```

### -Linking to Other Sites.
#### Links are created using the (a) element which has an attribute called href. The value of the href attribute is the page URL.
#### Users can click on anything that appears between the opening (a) tag and the closing (/a) tag and will be taken to the page specified in the href attribute.

### -Linking to Other Pages on the Sa me Site.
#### When you are linking to other pages within the same site, ou do not need to specify the domain name in the URL. You can use a shorthand known as a **relative** URL.
#### If all the pages of the site are in the same folder, then the value of the href attribute is just the name of the file.



### -Email Links(mailto) .
#### To create a link that starts up the user's email program and addresses an email to a specified email address, you use the (a) element. However, this time the value of the href attribute starts with _mailto:_ and is followed by the email address you want the email to be sent to.

example : ``` <a href="mailto:AA@example.org">Email AA</a> ```

### -Opening Links in a New Window (target).
#### If you want a link to open in a new window, you can use the target attribute on the opening (a) tag. The value of this attribute should be _blank.
example : ``` <a href="http://www.ABCD.com" target="_blank"> ABCD </a>```



### -Linking to a Sp ecific Part of the Sa me Page.
#### Before you can link to a specific part of a page, you need to identify the points in the page that the link will go to. You do this using the id attribute (which can be used on every HTML element).
#### To link to an element that uses an id attribute you use the (a) element again, but the value of the href attribute starts with the # symbol, followed by the value of the id attribute of the element you want to link to.
example : ``` <h1 id="top">ABCD Cite, Welcome her </h1>..........THE PAGE................ <p><a href="#top">Top</a></p>```


### -Linking to a Sp ecific Part of Another Page.
#### As long as the page you are linking to has id attributes that identify specific parts of the page, you can simply add the same syntax to the end of the link for that page.
#### Therefore, the href attribute will contain the address for the page (either an absolute URL or a relative URL), followed by the # symbol, followed by the value of the id attribute that is used on the element you are linking to.
example : ``` <a href="http:/www.ABCD.com/#bottom">```


# Highlights of how to control where each element sits on a page and how to create attractive page layouts.
### You can position elements in different ways using :
1. ##### normal flow.
2. ##### relative positioning.
3. ##### absolute positioning and floats.


## Key Concepts in Positioning El ements.
### -Building Blocks.
#### CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.
##### Block-level boxes start on a new line and act as the main building blocks of any layout, while inline boxes flow between surrounding text.


### -Containing Elements.
#### If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.
##### It is common to group a number of elements together inside a (div) (or other block-level) element,The (div) element that contains this group of elements is then referred to as the containing element.


### -Controll ing the Position of El ements.
#### CSS has the following **positioning schemes** that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the _position_ property in CSS. You can also float elements using the _float_ property.
1. ##### Normal flow (position:static): Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one.
2. ##### Relative Positioning (position:relative): This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed.
3. ##### Absolute positioning (position:absolute): This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up).
4. ##### Fixed Positioning (position:fixed): This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element.
5. ##### Floating Elements (float): Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.
#### Overlapping El ements (z-index): When you move any element from normal flow, boxes can overlap. The _z-index_ property allows you to control which box appears on top.


# Function :Functions let you group a series of statements together to perform a specific task. If different parts of a script repeat the same task, you can reuse the function (rather than repeating the same set of st atements).
# Objects : Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and functions take on new names




# 6 Reasons for Pair Programming.
## While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator.
### The Driver is the programmer who is typing and the only one whose hands are on the keyboard.
### The Navigator uses their words to guide the Driver but does not provide any direct input to the computer.
## 6 Reasons for Pair Programming :
1. ### Greater efficiency.
2. ### Engaged collaboration.
3. ### Learning from fellow students.
4. ### Social skills.
5. ### Job interview readiness.
6. ### Work environment readiness.

