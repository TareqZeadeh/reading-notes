# Lists 
## There are three different types of lists provided by HTML:
1. ### Ordered lists : are lists where each item in the list is numbered .  
2. ### Unordered lists : are lists that begin with a bullet point.
3. ### Definition lists : are made up of a set of terms along with the definitions for each of those terms.

## Ordered lists (ol) and (li):
1. The ordered list is created with the (ol) element.
2. Each item in the list is placed between an opening (li) tag and a closing (/li) tag.

example : 
``` <ol> <li>first item</li> <li>second item</li> ........... and so on </ol> ```


## Unordered lists (ul) and (li):
1. The unordered list is created with the (ul) element.
2. Each item in the list is placed between an opening (li) tag and a closing (/li) tag.

example : 
``` <ul> <li>first item</li> <li>second item</li> ........... and so on </ul> ```

## Definition lists (dl),(dt)and(dd):
1. The definition list is created with the (dl) element.
2. (dt) is used to contain the term being defined.
3. This is used to contain the definition.

 example : 
``` <dl><dt> HTML <dd> Hyper Text Markup Language used to describe the structure of a web page</dd></dt>   <dt> CSS <dd>  Cascading Style Sheets used to define styles for your web pages, including the design, layout and variations in display for different devices and screen sizes.   </dd></dt> </dl> ```



#### Nested lists : You can put a second list inside an <li> element to create a sublist or nested list.


# Boxes 
## CSS treats each HTML element as if it lives in its own box ,and we can set several properties that affect the appearance of these boxes.
### -Box Dimensions (width)(height).
#### To set your own dimensions for a box you can use the height and width properties.
#### The most popular ways to specify the size of a box are to use pixels, percentages, or ems.
### -Limiting Width (min-width)(max-width).
#### The (min-width) property specifies the smallest size a box can be displayed at when the browser window is narrow. 
#### The max-width property indicates the maximum width a box can stretch to when the browser window is wide.

### -Limiting Height (min-height)(max-height).
#### In the same way that you might want to limit the width of a box on a page, you may also want to limit the height of it. This is achieved using the min-height and max-height properties.
### -Overflowing Content (overflow).
#### The overflow property tells the browser what to do if the content contained within a box is larger than the box itself. It can have one of two values:
1. hidden: This property simply hides any extra content that does not fit in the box.
2. scroll This property adds a scrollbar to the box so that users can scroll to see the missing content.
### -Every box has three available properties that can be adjusted to control its appearance:
1. #### Border: Every box has a border (even if it is not visible or is specified to be 0 pixels wide). The border separates the edge of one box from another.
2. #### Margin: Margins sit outside the edge of the border. You can set the width of a margin to create a gap between the borders of two adjacent boxes.
3. #### Padding: Padding is the space between the border of a box and any content contained within it. Adding padding can increase the readability of its contents.
#### **If you specify a width for a box, then the borders, margin, and padding are added to its width and height**.

### -Border Widht (border-widht).
#### The border-width property is used to control the width of a border. The value of this property can either be given in pixels or using one of the following values:
1. thin.
2. medium.
3. thick.
#### You can control the individual size of borders using four separate properties:
1. border-top-width.
2. border-right-width.
3. border-bottom-width.
4. border-left-width.

### -Border Style (border-style).
#### You can control the style of a border using the border-style property. This property can take the following values:
1. solid.
2. dotted.
3. dashed.
4. double.
5. groove.
6. ridge.
7. inset.
8. outset.
9. hidden / none.
#### You can individually change the styles of different borders using:
1. border-top-style.
2. border-left-style.
3. border-right-style.
4. border-bottom-style.

### -Border Color (border-color).
#### You can specify the color of a border using either RGB values, hex codes or CSS color names.
#### It is possible to individually control the colors of the borders on different sides of a box using:
1. border-top-color.
2. border-right-color.
3. border-bottom-color.
4. border-left-color.
### -Shorthand (border).
#### The border property allows you to specify the width, style and color of a border in one property (and the values should be coded in that specific order).
### -Padding (padding).
#### The value of this property is most often specified in pixels (although it is also possible to use percentages or ems). 
#### If a percentage is used, the padding is a percentage of the browser window (or of the containing box if it is inside another box).
#### **If a width is specified for a box, padding is added onto the width of the box**.
#### You can specify different values for each side of a box using:
1. padding-top.
2. padding-right.
3. padding-bottom.
4. padding-left.

### -Margin (margin).
#### The margin property controls the gap between boxes. Its value is commonly given in pixels, although you may also use percentages or ems.
#### If one box sits on top of another, margins are collapsed , which means the larger of the two margins will be used and the smaller will be disregarded.
#### **If the width of a box is specified then the margin is added to the width of the box.**
#### You can specify values for each side of a box using:
1. margin-top.
2. margin-right.
3. margin-bottom.
4. margin-left.
#### If you want to center a box on the page (or center it inside the element that it sits in), you can set the (left-margin) and (right-margin) to (auto).



#### In order to center a box on the page, you need to set a width for the box (otherwise it will take up the full width of the page). Once you have specified the width of the box, setting the **left and right margins** to _auto_ will make the browser put an equal gap on each side of the box. This centers the box on the page (or within the element that the box sits inside).

### -Change Inline/Block (display).
#### The display property allows you to turn an inline element into a block-level element or vice versa, and can also be used to hide an element from the page.
#### The values this property can take are:
1. inline.
2. block.
3. inline-block.
4. none.


### -Hiding Boxes (visibility).
#### The visibility property allows you to hide boxes from users but It leaves a space where the element would have been. This property can take two values:
1. hidden.   
2. visible.
### -(CSS3) Border Images (border-image).
#### The border-image property applies an image to the border of any box. It takes a background image and slices it into nine pieces. **You can google it for more infomation.**


### -(CSS3) Border Shadows (box-shadow).
#### The box-shadow property allows you to add a drop shadow around a box.

## -Using Quotes Inside a String.
#### To use double quotes in the string, we should surround the entire string in single quotes.
#### To use single quotes in the string, we should surround the string in double quotes.
#### We can also use a technique called escaping the quotation characters. This is done by using a backslash before any type of quote mark that appears within a string.


## -Using a Variable To Store a Boolean.
#### Booleans are used when the value can only be true/ fa 1 se. You could also think of these values as on/off or 0/1: true is equivalent to on or 1, fa 1 se is equivalent to off or 0.
#### Booleans are used when your code can take more than one path. Remember, different code may run in different circumstances (The path the code takes depends on a test or condition)

