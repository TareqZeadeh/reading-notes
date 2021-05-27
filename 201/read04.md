# Images
## -Adding Images (img).
#### To add an image into the page you need to use an (img) element. This is an empty element (which means there is no closing tag).
#### src: This tells the browser where it can find the image file.
#### alt: This provides a text description of the image which describes the image if you cannot see it.
#### title You can also use the title attribute with the (img) element to provide additional information about the image.\
## -Height and Width of Images.
#### height: This specifies the height of the image in pixels.
#### width: This specifies the width of the image in pixels.
EX:``` <img src="images/quokka.jpg" alt="A family of quokka" width="600" height="450" /> ```

## -Three Rules for Creating Images:
1. #### Save images in the right format.
2. #### Save images at the right size.
3. #### Use the correct resolution.





# Text
### -There are several ways to use fonts other than those listed on the previous page. However, typefaces are subject to copyright, so the techniques you can choose from are limited by their respective licenses.
1. #### font-family: The user's computer needs the typeface installed. CSS is used to specify the typeface.
2. #### font-face: CSS specifies where a font can be downloaded from if it is not installed on the computer.
3. #### Service-based Font-Face: Commercial services give users access to a wider range of fonts using @font-face.


##### **for more information read this book Chapter 11: Chapter 12: “Text” (pp.264-299) [HTML CSS](https://wtf.tw/ref/duckett.pdf).**


# Color 
### -Foreground Color (color). 
#### The color property allows you to specify the color of text inside an element. You can specify any color in CSS in one of three ways:
1. ##### rgb values: These express colors in terms of how much red, green and blue are used to make it up. For example: rgb(100,100,90).
2. ##### hex codes: These are six-digit codes that represent the amount of red, green and blue in a color, preceded by a pound or hash # sign. For example: #ee3e80.
3. ##### color names: There are 147 predefined color names that are recognized by browsers. For example: DarkCyan.

### -Background Color (background-color).
#### CSS treats each HTML element as if it appears in a box, and the background-color property sets the color of the background for that box.

##### **for more information read this book Chapter 11: “Color” (pp.246-263) [HTML CSS](https://wtf.tw/ref/duckett.pdf).**

# JPEG vs PNG vs GIF — which image format to use and when?
### -There is three most commonly used image formats in websites and mobile applications — JPEG, PNG and GIF.
### -Several statistics reports, including the one from HTTP Archive, indicate that these 3 formats together comprise of more than 95% of all images loaded on websites.
### -These 3 image formats have significant differences amongst themselves thus making each of them suitable for specific use cases.

### **Use JPEG format for all images that contain a natural scene or photograph where variation in colour and intensity is smooth.**
### **Use PNG format for any image that needs transparency or for images with text & objects with sharp contrast edges like logos.**
### **Use GIF format for images that contain animations.**
