# CSS Layout.


##  Highlights of how to control where each element sits on a page and how to create attractive page layouts.
### You can position elements in different ways using :
1. ##### normal flow.
2. ##### relative positioning.
3. ##### absolute positioning and floats.


### Key Concepts in Positioning Elements.
#### -Building Blocks.
##### CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.
###### Block-level boxes start on a new line and act as the main building blocks of any layout, while inline boxes flow between surrounding text.


#### -Containing Elements.
##### If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.
##### It is common to group a number of elements together inside a (div) (or other block-level) element,The (div) element that contains this group of elements is then referred to as the containing element.


#### -Controll ing the Position of El ements.
##### CSS has the following **positioning schemes** that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the _position_ property in CSS. You can also float elements using the _float_ property.
1. ###### Normal flow (position:static): Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one.
2. ###### Relative Positioning (position:relative): This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed.
3. ###### Absolute positioning (position:absolute): This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up).
4. ###### Fixed Positioning (position:fixed): This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element.
5. ###### Floating Elements (float): Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.
##### Overlapping El ements (z-index): When you move any element from normal flow, boxes can overlap. The _z-index_ property allows you to control which box appears on top.

#### -Using Float to Place Elements Side-by-Side
##### A lot of layouts place boxes next to each other. The float property is commonly used to achieve this. When elements are floated, the height of the boxes can affect where the following elements sit.
##### Setting the height of the paragraphs to be the same height as the tallest paragraph would solve this issue, but it is rarely suited to real world designs where the amount of text in a paragraph or column may vary. It is more common to use the clear property to solve this issue.
#### -Clearing Floats (clear):
##### The _clear_ property allows you to say that no element (within the same containing element) should touch the left or righthand sides of a box. It can take the following values:
1. ###### left.
2. ###### right.
3. ###### both.
4. ###### none.
#### -Parents of Floated Elements:Problem
##### If a containing element only contains floated elements, some browsers will treat it as if it is zero pixels tall.
#### -Parents of Floated Elements:Solution
##### Traditionally, developers got around this problem by adding an extra element after the last floated box (inside the containing element). A CSS rule would be applied to this additional element setting the clear property to have a value of both. But this meant that an extra element was added to the HTML just to fix the height of the containing element.
##### More recently, developers have opted for a purely CSS-based solution because it means that there is no need to add an extra element to the HTML page after the floated elements. The pure CSS solution adds two CSS rules to the containing element :
1. The overflow property is given a value auto. 
2. The width property is set to 100%.
#### -Craeting Multi-Column Layouts with Floats
##### Many web pages use multiplecolumns in their design. This is achieved by using a <div> element to represent each column. The following three CSS properties are used to position the columns next to each other:
1. width: This sets the width of the columns.
2. float: This positions the columns next to each other.
3. margin: This creates a gap between the columns.


### Screen Sizes
#### Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.
### Screen Resolution
#### Resolution refers to the number of dots a screen shows per inch. Some devices have a higher resolution than desktop computers and most operating systems allow users to adjust the resolution of their screens.
### Page Sizes
#### Because screen sizes and display resolutions vary so much, web designers often try to create pages of around 960-1000 pixels wide (since most users will be able to see designs this wide on their screens).
### Fixed Width Layouts
#### Fixed width layout designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.
### Liquid Layouts
#### Liquid layout designs stretch and contract as the user increases or decreases the size of their browser window. They tend to use percentages.
