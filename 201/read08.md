# Forms
## Traditionally, the term 'form' has referred to a printed document that contains spaces for you to fill in information.
## HTML borrows the concept of a form to refer to different elements that allow you to collect information from visitors to your site.
## The best known form on the web is probably the search box that sits right in the middle of Google's homepage.
### -Form Controls
#### There are several types of form controls that you can use to collect information from visitors to your site.
##### Adding text:
1. Text input (single-line).
2. Password input.
3. Text area (multi-line).
##### Making Choices:
1. Radio buttons.
2. Checkboxes.
3. Drop-down boxes.
##### Submitting Forms:
1. Submit buttons.
2. Image buttons.
##### Uploading Files:
1. File upload.
### -How Forms Work:
#### 1. A user fills in a form and then presses a button to submit the information to the server.
#### 2.The name of each form control is sent to the server along with the value the user enters or selects.
#### 3.The name of each form control is sent to the server along with the value the user enters or selects.
#### 4.The server creates a new page to send back to the browser based on the information received.
### -Form Structure
#### (form): Form controls live inside a (form) element. This element should always carry the action attribute and will usually have a method and id attribute too.
#### (input): The (input) element is used to create several different form controls. The value of the type attribute determines what kind of input they will be creating.
#### type="text": When the type attribute has a value of text, it creates a singleline text input
#### name: When users enter information into a form, the server needs to know which form control each piece of data was entered into.
#### maxlength: You can use the maxlength attribute to limit the number of characters a user may enter into the text field. 
#### size: The size attribute should not be used on new forms. It was used in older forms to indicate the width of the text input (measured by the number of characters that would be seen).
### -Password Input (input)
#### type="password": When the type attribute has a value of password it creates a text box that acts just like a single-line text input, except the characters are blocked out.
#### name: The name attribute indicates the name of the password input, which is sent to the server with the password the user enters.
#### size, maxlength: It can also carry the size and maxlength attributes like the the single-line text input.
### -Text Area
#### (textarea): The (textarea) element is used to create a mutli-line text input. Unlike other input elements this is not an empty element. It should therefore have an opening and a closing tag.
### -Radio Button(input)
#### type="radio": Radio buttons allow users to pick just one of a number of options.
#### name: The name attribute is sent to the server with the value of the option the user selects.
#### value: The value attribute indicates the value that is sent to the server for the selected option.
#### checked: The checked attribute can be used to indicate which value (if any) should be selected when the page loads. The value of this attribute is checked.
### -Checkbox(input)
#### type="checkbox": Checkboxes allow users to select (and unselect) one or more options in answer to a question.
#### name: The name attribute is sent to the server with the value of the option(s) the user selects.
#### value: The value attribute indicates the value sent to the server if this checkbox is checked.
#### checked: The checked attribute indicates that this box should be checked when the page loads. If used, its value should be checked.
##### **for more information read this book Chapter 7: “Forms” (p.144-175) [HTML CSS](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).**
# Lists, Tables and Forms
### There are several CSS properties that were created to work with specific types of HTML elements, such as lists, tables, and forms.
#### **for more information read this book Chapter 14: “Lists, Tables & Forms” (pp.330-357) [HTML CSS](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).**
#### You will learn about :
##### Specify the type of bullet point or numbering on lists.
1. Bullet Point Styles (list-style-type).
2. Images for Bullets (list-style-image).
3. Positioning the Marker (list-style-position).
4. List Shorthand (list-style).
 ##### Add borders and backgrounds to table cells.
1. Table Properties
2. Border on Empty Cells (empty-cells).
3. Gaps Between Cells (border-spacing, border-collapse).
4. Styling Text Inputs.
5. Styling Su bmit Buttons.
6. Styling Fieldsets and Legends.
##### Control the appearance of form controls.
1. Alignin Form Controls: Problem and Solution.
2. Cursor Styles (cursor).
# Events
## When you browse the web, your browser registers different types of events. It's the browser's way of saying, "Hey, this just happened." Your script can then respond to these events.
### -Different event types
#### Here is a selection of the events that occur in the browser while you are browsing the web. Any of these events can be used to trigger a function in your JavaScript code:
##### UI Events: Occur when a user interacts with the browser's user interface (UI) rather than the web page
1. load: Web page has finished loading
2. unload: Web page is unloading (usually because a new page was requested)
3. error: Browser encounters a JavaScript error or an asset doesn't exist
4. resize: Browser window has been resized
5. scroll: User has scrolled up or down the page
##### Keyboard Events: Occur when a user interacts with the keyboard (see also input event)
1. keydown: User first presses a key (repeats while key is depressed)
2. keyup :User releases a key
3. keypress: Character is being inserted (repeats while key is depressed)
##### Mouse Events: Occur when a user interacts with a mouse. trackpad, or touchscreen
1. click: User presses and releases a button over the same element
2. dbl click: User presses and releases a button twice over the same element
3. moused: own User presses a mouse button while over an element
4. mouseup: User releases a mouse button while over an element
5. mousemove: User moves the mouse (not on a touchscreen)
6. mouseover: User moves the mouse over an element (not on a touchscreen) 
7. mouseout: User moves the mouse off an element (not on a touchscreen)
##### And More
### -How Events Trigger JavaScript Code
#### When the user interacts with the HTML on a web page, there are three steps involved in getting it to trigger some JavaScript code. Together these steps are known as event handling.
1. Select t he element node(s) you want the script to respond to.
2. Indicate which event on the selected node(s) will trigger the response.
3. State the code you want to run when the event occurs.
### -Three Ways To Bind An Event To An Element
#### Event handlers let you indicate which event you are waiting for on any particular element. There are three types of event handlers.
1. HTML EVENT HANDLERS
2. TRADITIONAL DOM EVENT HANDLERS
3. DOM LEVEL 2 EVENT LISTENERS
## Event Listeners
#### Event listeners are a more recent approach to handling events. They can deal with more than one function at a time but they are not supported in older browsers.
##### Here is the syntax to bind an event to an element using an event listener, and to indicate which function should execute when that event fires:
``` element .addEventlistener('event', functionName [, Boolean]) ;  ```

### -The Event Object
#### When an event occurs, the event object tells you information about the event, and the element it happened upon.
#### **for more information read this book Chapter 6: “Events” (pp.243-292) [JS](https://drive.google.com/file/d/1L74jU_Js5jSjbi2hg87TNyT-hnVkoXwJ/view).**