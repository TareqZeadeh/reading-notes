# Images
### -controlling sizes of images in CSS:
#### You can control the size of an image using the _width_ and _height_ properties in CSS, just like you can for any other box.
### -Aligning images Using CSS:
#### Rather than using the <img> element's align attribute, web page authors are increasingly using the float property to align images. There are two ways that this is commonly achieved:
1. The float property is added to the class that was created to represent the size of the image.
2. New classes are created with names such as align-left or align-right to align the images to the left or right of the page. These class names are used in addition to classes that indicate the size of the image.
### -Centering images Using CSS:
#### By default, images are inline elements, Once it has been made into a block-level element, there are two common ways in which you can horizontally center an image:
1. On the containing element, you can use the text-align property with a value of center.
2. On the image itself, you can use the use the margin property and set the values of the left and right margins to auto.
### -Background Images (background-image):
#### The background-image property allows you to place an image behind any HTML element. This could be the entire page or just part of the page. By default, a background image will repeat to fill the entire box.
### -Repeating Images (background-repeat background-attachment):
#### The background-repeat property can have four values:
1. repeat The background image is repeated both horizontally and vertically (the default way it is shown if the backgroundrepeat property isn't used).
2. repeat-x The image is repeated horizontally only (as shown in the first example on the left).
3. repeat-y The image is repeated vertically only.
4. no-repeat The image is only shown once.
#### The background-attachment property specifies whether a background image should stay in one position or move as the user scrolls up and down the page. It can have one of two values:
1. fixed The background image stays in the same position on the page.
2. scroll The background image moves up and down as the user scrolls up and down the page.
### -Background Position (background-position):
#### When an image is not being repeated, you can use the background-position property to specify where in the browser window the background image should be placed.
#### This property usually has a pair of values. The first represents the horizontal position and the second represents the vertical.
1. left top
2. left center
3. left bottom
4. center top
5. center center
6. center bottom
7. right top
8. right center
9. right bottom
### -shorthand (background):
#### The background property acts like a shorthand for all of the other background properties you have just seen, and also the background-color property.
#### The properties must be specified in the following order, but you can miss any value if you do not want to specify it.
1. background-color
2. background-image
3. background-repeat
4. background-attachment
5. background-position

##### **for more information read this book Chapter 16: “Images” (pp.406-427) [HTML CSS](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).**

# Practical Information
### -Search Engine Optimization(SEO)
#### SEO is a huge topic and several books have been written on the subject. The following pages will help you understand the key concepts so you can improve your website's visibility on search engines.
1. The Basics: Search engine optimization (or SEO) is the practice of trying to help your site appear nearer the top of search engine results when people look for the topics that your website covers.
2. On-Page Techniques: On-page techniques are the methods you can use on your web pages to improve their rating in search engines.
3. Off-Page Techniques: Getting other sites to link to you is just as important as on-page techniques. Search engines help determine how to rank your site by looking at the number of other sites that link to yours.
### -On-Page SEO:
#### In every page of your website there are seven key places where keywords (the words people might search on to find your site) can appear in order to improve its findability.
1. Page Title
2. URL / Web Address
3. Headings
4. Text
5. Link Text
6. Image Alt Text
7. Page Descriptions
### -How to Identify Keywords and Phrases
#### Determining which keywords to use on your site can be one of the hardest tasks when you start to think about SEO. Here are six steps that will help you identify the right keywords and phrases for your site.
1. Brainstorm
2. Organize
3. Research
4. Compare
5. Refine
6. Map
### -Analytics: Learning about your Visitors
#### As soon as people start coming to your site, you can start analyzing how they found it, what they were looking at and at what point they are leaving. One of the best tools for doing this is a free service offered by Google called Google Analytics.
##### **for more information read this book Chapter 19: “Practical Information” (476-492) [HTML CSS](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).**

# Video and Audio APIs
### HTML5 comes with elements for embedding rich media in documents (video) and (audio) which in turn come with their own APIs for controlling playback, seeking, etc. This article shows you how to do common tasks such as creating custom playback controls.
### -HTML5 video and audio:The (video) and (audio) elements allow us to embed video and audio into web pages. As we showed in Video and audio content, a typical implementation looks like this:
``` <video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>  

```
#### You can review what all the HTML features do in the article linked above; for our purposes here, the most interesting attribute is controls, which enables the default set of playback controls.
##### **for more information Visit this Page [Video and Audio APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs).**