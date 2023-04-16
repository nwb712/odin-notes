# HTML Foundations


## Introduction to HTML and CSS
HTML and CSS work together to create everything that you see when you look at something on the internet.
It is not technically accurate to refer to them as programming languages as they are not used to program logic.

### Reading: HTML vs. CSS vs. Javascript: What's the Difference
- HTML: Content and Layout
- CSS: Styling + Look and Feel
- Javascript: Interactive Elements

### Knowledge Check
- What do HTML and CSS stand for?
    - HTML is Hypertext Markup Language and CSS is Cascading Style Sheets
- Between HTML and CSS, which would you use for putting paragraphs of text on a webpage?
    - You would use HTML
- Between HTML and CSS which would you use for changing the font and background color of a button?
    - You would use CSS
- What is the difference betwen HTML, CSS, and Javascript?
    - HTML is content, CSS is presentation, and Javascript is interactivity


## Elements and Tags
Most elements on an HTML page are just content wrapped in tags
Tags are structuted `<keyword>content</keyword>`
A few elements do not have a closing tag. Ex. `<br />` or `<img>`
HTML has a large list of predefined tags. Using correct tags can effect SEO and accessability

### Knowledge Check
- What is an HTML tag?
    - HTML tags are containers for content with opening and closing tags
- What are the three parts of an HTML element
    - An HTML elements is comprised of an opening tag, content, and a closing tag 


## HTML Boilerplate
All HTML documents have the same basic structure or boilerplate

### The DOCTYPE
Every HTML page starts with a doctype declaration
For HTML 5 it is `<!DOCTYPE html>`

### HTML Element
The `<html>` element is known as the root element. 

#### The `lang` attribute
This specifies the language of the text content in that element

### Head Element
The `<head>` element is where meta-information about the webpage lives.
Should not use any element that displays content inside the `<head>` element

#### The Charset Meta Element
The element, `<meta charset="utf-8">` sets the charset encoding of the webpage
Setting the encoding ensures that the webpage will correctly display special symbols and characters

#### Title Element
The `<title>` element should always be included in the head as it is used to title the webpage's tab
It defaults to the name of the html file if not specified

### The Body Element
The final element needed in the HTML boilerplate is the `<body>` element.
All content displayed to users goes here

### Knowledge Check
- What is the purpose of the doctype declaration?
    - The doctype tells the browser what version of HTML to use
- What is the HTML Element?
    - The html element is the root element which contains all other elements of the HTML document
- What is the purpose of the head element?
    - The head element contains meta information about the document
- What is the purpose of the body element?
    - The body element contains all of the content of the webpage


## Working With Text

### Paragraphs
The `<p>` element is used to create paragraphs

### Headings
The elements `<h1>` through `<h6>` are used to create headings by level

### Strong Element
The `<strong>` element makes text bold, as well as semantically marking it important; this effects the way that accessability tools present the text.
This element will usually be wrapped around text within other text elements

### Em Element
The `<em>` element makes text italic. Also semantically marks important

### Nesting and Indentation
Elements within other elements are indented one level higher than the element which contains them.

### HTML Comments
Comments should be enclosed in `<!-- comment -->`

### Knowledge Check
- How do you create a paragraph in HTML?
    - Use the `<p>` 
- How do you create a heading in HTML?
    - Use tags `<h1>` through `<h6>`
- How many different levels of headings are there and what is the difference between them?
    - There are six levels of heading which are displayed differently and rank importance of the heading
- What element should you use to make text bold and important?
    - Use the `<strong>` 
- What element should you use to make text italicized to add emphasis to it?
    - Use the `<em>`
- What relationship does and element have with any nested elements within it?
    - Nested elements are children of the tag which contains them (the parent)
- What relationship do two elements have if they are at the same level of nesting?
    - Elements at the same level of nesting are siblings
- How do you create HTML comments? 
    - Use `<!-- Comment -->`

## Lists

### Unordered Lists
Unordered lists are created using the `<ul>` element, while the items in the list are created using the `<li>` element.
Each item in the list begins with a bullet point

### Ordered Lists
Ordered lists are created using the `<ol>` element, while list items use the `<li>` element
Each item in the list begins with a number

### Knowledge Check
- What HTML element is used to create an unordered list?
    - Use the `<ul>` element
- What HTML element is used to create a  ordered list?
    - Use the `<ol>` element
- What HTML element is used to create list items within both unordered and ordered lists?
    - Use the `<li>` element: 

## Links and Images

### Anchor Elements
To create a link use the anchor element `<a>` wrapped around the text or other element we to be a link 
The link must be given a destination using the HTML attribute href like `<a href="<URL>">`
The href stands for hyperlink reference. Attributes usually have a name and value but some only have a name.
By default elements wrapped in the `<a>` tag without the href attribute will appear as plain text

### Absolute and Relative Links
Generally will create two types of links:
    1. Links to pages on other websites on the internet
    2. Links to pages located on our own websites

#### Absoute Links
Links to pages on other websites on the internet are called absolute links.
They are structured: `protocol://domain/path`

#### Relative Links
Links to other pages within our own website are called relative links. They only include the file path to the other page relative to the page that the link is created on.
They are sctructred `./<path_to_page>`

### Images
Use the `<img>` element to display images in html. This element is self-closing
`<img>` embeds an image into the page using a src attribute which tells the browser where the image file is located.
Ex. `<img src="<image_path">`

### Parent Directories
If a page not located in the parent directory needs to access an asset in another folder, you can use "../" in the relative filepath to reference the parent directory

### Alt Attribute
Besides the src attribute, every image element should also have an alt attribute
This attribute is used to describe the image, and should be used for accessability reasons
The alt text will be used in place of the image should it fail to load

### Reading: Image Formats
Four main image formats are used on the web

#### JPG Images
Designed for handling large color palettes but does not suport transparency.
Good for images with lots of gradients

#### GIF Images
Good for simple animations, but limited in color palette and transparency is binary

#### PNG Images
Good for anything that's not a photo or animated. Deal with opacity well.
Often used for diagrams, icons, logos, etc.
Generally a png of a photo would be larger than the equivalent jpg

#### SVG Images
Vector format images which can be scaled to any size without loss of detail.
Work well for most of the same use cases as PNG

#### Image Dimensions
The `<img>` element uses the inherit dimensions of its image file by default
Can manually adjust dimensions using the `width` and `height` attributes
Usually better to set images sizes with css so they can be altered with media queries

#### Text Alternatives
Using the `alt` attribute with your images is always best practice.

#### More HTML Attributes
1. Document Language:
    - `<html lang="en">`
2. Character Sets:
    - `<meta charset="utf-8">`

#### HTML Entities
HTML Entities are special characters which can't be represented as plain text in HTML.
Entities always begin with an ampersand and end with a semicolon.

##### Reserved Characters
The characters: `'<', '>', '&'` are reserved characters because they cannot be inserted into an HTML document without being encoded.
To encode these characters use: `'&lt;', '&gt;', '&amp;'`

##### Quotes
Use the following for quotes:
```
&ldquo; -> "<text>...
&rdquo; -> ...<text>"
&lsquo; -> '<text>...
&rsquo; -> ...<text>'
```
These quotes need to hug the text unlike straight quotes

##### UTF-8 and HTML Entities
Should be able to insert and UTF-8 directly into an HTML document

### Knowledge Check
1. What element is used to create a link?
    - Use `<a>` with the href attribute
2. What is an attribute?
    - Attributes supply additional info to HTML elements and always go in the opening tag
3. What attribute tells links where to go?
    - The href attribute
4. What is the difference between an absolute and relatve link?
    - Absolute links use a full web address 
5. Which element is used to display an image?
    - Use the `<img>` element
6. What two attributes do images always need to have?
    - The `<img>` element should always have the elements src and alt
7. How do you access the parent directory in a filepath?
    - Use `"../"`
8. What are the four main image formats that you can use for images on the web?
    - JPG, GIF, PNG, SVG

## Commit Messages

### Reasons That Commit Messages Are Important
- When applying for jobs, employers will look through your GitHub projects. Having good commits will help you stand out.
- Having a good commit message history will allow you (or others) to quickly see what changes were made and why.
- Good commits are also helpful when returning to a project after stepping away for a while.

### When to Commit
You should commit every time you have a meaningful change to your code. For example when you get a piece of new code functioning, fix a typo, or fix a bug.
This makes it much easier to track your progress and revert if something breaks unexpectedly.

### Reading: How to Write a Git Commit Message

#### The Seven Rules of a Great Git Commit Message
1. Separate subject from body with a blank line
    - Especially simple commits may have only a subject line
2. Limit the subject line to 50 characters
    - Not a hard limit but a rule of thumb. 72 characters is the hard limit. If you're having a hard time summarizing you may be commiting too many changes at once.
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

### Knowledge Check
1. What are two benefits of having well-written commit messages and a good commit history?
    - Good commits allow one to easily understand the project history and why things were changed. They also make it easy to revert code when an issue is encountered.
2. How many characters should the subject line of your commit message be?
    - The subject line should be 50 characters generally and never more than 72.

