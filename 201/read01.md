# Tags in HTML.
### By using tags (known as markup) we providing extra meaning and allow browsers to show usesr the appropirate structure for the page.

## There is to kinds of markup:
1. structural markup : _the elements that you can use to describe both headings and paragraphs_.
2. semantic markup : _elements that add extra information to the pages_.

### Structural markup:
1. h1 , h2 , h3 ... up to ...h6 tags:
#### -h1 is the main heading , as the number beside _h_ is increaseing up to 6 , the font size well be smaller (subheadings and section under sub headings).
 example : ```<h1> hi </h1> ``` 


2. p tag :
  #### -used to create paragraph .
example : ```<p> nice to meet you </p>```

3. b and i tags:
#### -b used to make some words of the paragrph **bold** , i used to make some words of the paragrph _italic_.
example : ``` <b>nice</b> to meet <i>you</i> ```

4. sup and sub tags: 
#### -sup used to contain characters that should be superscript such as the suffixe of date os mathematical concept (but a number to a power) , sub used to contain the characters that should be subscript.(commonly used in chemical formulas).
examples : ``` my birthday is 5<sup>th</sup> of jun  ``` .... ``` to day i have leared about H<sub>2</sub>O ``` 

5. br and hr tags: 
#### -br used to add a line break insid the paragraph , hr used to add horaizontal line or rule between sections or paragraphs.
 examples: ```<p> nice to <br />meet you </p>``` ...... ```<p> nice to meet you </p> <hr/> <p> hi , how are you?</p>```


 ### Semantic markup :
 1. strong and em:
 #### -strong is the same of b **bold** , but it's used to indicates that its content has strong importance.
 #### -em (emphasis) is the same of i _italic_ , but it's used to indicates emphasis that subtly changes the meaning of a sentence.

2. Qoutations (blockquote and q):
#### -blockquote is used for longer quotes that take up an entire paragraph , and it's have an attribute (cite) to link the sourse of the quotation
example : ``` <blockequote cite-"https://en.wikipedia.org/wiki/BMW">  <p> Bayerische Motoren Werke AG, commonly referred to as BMW , is a German multinational corporation which produces luxury vehicles and motorcycles</p>  </blockquote> ```
#### -q is used for shorter quotes that sit within a paragraph.
example :``` <p> <q>Bayerische Motoren Werke AG</q>, commonly referred to as BMW , is a German multinational corporation which produces luxury vehicles and motorcycles</p> ```


3. Abbreviations (abbr) and Acronyms (acronym) :
#### -whin we use an abbreviation or acronym of a word we will use <abbr title -"Clarification of the word that was abbreviated" > or (<acronym title -"Clarification of the word that was abbreviated">),
example : ``` <p> The number of casualties in <abbr title-"World War II">WW2</abbr> was 60 million people </p> ```,
#### -the _acronym_ used the same way.


4. Citations (cite) and Definitions (dfn):
#### -(cite) is used to indicate where the citation is from , when you are referencing a piece of work such as a book, film or research paper , the content of it will appere in italic.
#### -(dfn) is used to indicate the defining instance of a new term , like the first time you explain some new terminology (perhaps an academic concept or some jargon) in a document, it is known as the defining instance of it.
example : ``` <p>  <cite>Interstellar</cite> is a 2014 British-American epic science fiction film co-written, directed and produced by Christopher Nolan</p> ``` 
example : ``` <p> A <dfn>neutron star</dfn> is the collapsed core of a massive supergiant star, which had a total mass of between 10 and 25 solar masses, possibly more if the star was especially metal-rich. </p> ```


5. Auth or Details (address):
#### -The (address) element has quite a specific use , it's to contain contact details for the author of the page. #### -It can contain a physical address, but it does not have to. for example, it may also contain a phone number or email address.
#### -The content od (address) will be displayed in italic.
example :``` <address> <p><a href="mailto:homer@example.org"> homer@example.org</a></p> <p>742 Evergreen Terrace, Springfield.</p> </address> ``` 


6. Changes to Content (ins)+(del)+(s) :
#### -(ins) is used to show content that has been inserted into a document.
#### -(del) is used to show text that has been deleted from it.
example : ``` <p> It was the <del>bad</del> <ins>good</ins> idea to buy this car .</p> ```
#### -(s) is used to indicates something that is no longer accurate or relevant (but that should not be deleted).
#### -The content of (s) will  be displayed with a line through the center.
example : ``` <p>BMW Car:</p> <p><s>Was $5600</s></p> <p>Now only $4300</p> ```


# Introducing to CSS

### CSS allows you to create rules that specify how the content of an element should appear.
### The key to understanding how CSS works is to imagine that there is an invisible box around every HTML element , css allows you to create rules that control the way that each individual box (and the contents of that box) is presented.
#### -CSS works by associating rules with HTML elements , which is contains two parts ,  **selector** and  **declaration**.
#### -CSS declarations sit inside curly brackets and each is made up of two parts ,  _property_ and  _value_, separated by a colon. You can specify several properties in one declaration, each separated by a semi-colon.

## Useing External CSS :
#### -In order to use an external css file we should link it in the HTML document to tell the browser where to find the CSS file used to style the page , to do this we should use (link) tag in the **(head)** of th HTML code or page.
example : ```<link href="css/styles.css" type="text/css" rel="stylesheet" />```
#### -The _href_ attribute specifies the path to the CSS file.
#### -The _type_ attribute specifies the type of document being linked to and the value should be text/css.
#### -The _rel_ attribute specifies the relationship between the HTML page and the file it is linked to , and the value should be stylesheet when linking to a CSS file.

## Useing Internal CSS :
#### -In order to use an internal css file we should use (style) tag inside the **head** of the HTML code or page ang the CSS ruls will be placed inside the (style) tag or element.









