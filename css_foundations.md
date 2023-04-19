# CSS Foundations


## Introduction

### Basic Syntax
CSS is made up of various rules with a selector and a semi-colon separated list of declarations. 
Each declaration is made up of a property:value pair

### Selectors
Selectors refer to the HTML elements to which CSS rules apply

#### Univeral Selector
The universal selector selects elements of any type and is denoted with an asterisk
```css
* {
    color: purple;
}
```

#### Type Selectors
A type selector with select all HTML elements of a given type; the syntax is simply the name of the element.
```css
div {
    color: white;
}
```

#### Class Selectors
Class selectors will select all elements of a given class, which is just an attribute placed on an HTML element.
```html
<!-- index.html -->

<div class="alert-text">
    Please agree to our terms of service
</div>
```
```css
/* styles.css */

.alert-text {
    color: red;
}
```
The syntax for class selectors is a period followed by the case-sensitive value of the class attribute. 
You may also add mutiple classes to a single element as a space-separated list: `class="alert-text severe-alert"`

#### ID Selectors
ID Selectors select an element with the given ID, which is another attribute you place on an HTML element. 
```html
<!-- index.html -->

<div id="title">My Awesome 09's Page</div>
```
```css
/* styles.css */

#title {
    background-color: red;
}
```
ID Selectors use a hashtag immediatly followed by the case-sensitive value of the ID attribute. 
ID's should be used sparingly. An element can only have one ID.

#### Grouping Selector
You can group selectors together as a comma-separated list
```css
.read,
.unread {
    color: white;
    background-color: black;
}
```

#### Chaining Selectors
You can also chain selectors as a list without any separation. For example:
```html
<div>
    <div class="subsection header">Latest Posts</div>
    <p class="subsection preview">This is where a preview for a post might be</p>
</div>
```
If you want to apply styling to elements that have "subsection" and "header":
```css
.subsection.header {
    color: red;
}
```
This selects any element that has both the `subsection` and `header` classes. 
It works for any combination of selectors, except for chaining more than one type selector.
You can also chain a class and an ID:
```html
<div>
    <div class="subsection header">Latest Posts</div>
    <p class="subsection" id="preview">This is where a preview for post might go.</p>
</div>
```
```css
.subsection.header {
    color: red;
}

.subsection#preview {
    color: blue;
}
```
In general, you can't chain more than one type selector since an element can't be two different types at once.

#### Descendant Combinator
Combinators allow us to combine multiple selectors differently than either grouping or chaining them.
There are four types of combinators in total. A descendant combinator is represented in CSS by a single space between selectors.

So `.ancestor .child` would select an element with the class `child` if it has an ancestor with the class `ancestor`. 
`child` will only be selected if it is nested inside of `ancestor`, no matter how deep.
For example:
```html
<div class="ancestor"> <!-- A -->
    <div class="contents"> <!-- B -->
        <div class="contents"> <!-- C -->
        </div>
    </div>
</div>

<div class="contents"></div> <!-- D -->
```
```css
/* styles.css */

.ancestor .contents {
    /* some declarations */
}
```
In the above example, B and C would be selected, but not D. You can add as many combinators to a rule as you would like. 
For example: `.one .two .three .four` would be valid, although this level of nesting should generally be avoided.

### Properties to Get Started Started With

#### Color and Background-Color
The `color` property sets an elements text color; the `background-color` sets the background color. 
These properties can accept several kinds of values: keywords like `red` or `transparent`, HEX, RGB, HSL.
```css
p {
    /* hex example */
    color: #1100ff;
    /* rgb example */
    color: rgb(100, 0, 127);
    /* hsl example */
    color: hsl(15, 82%, 56%);
}
```

#### Typography Basics and Text-Align
`font-famliy` can be a single value or comma-separated list of values that determine what font and element uses.
Each font will either be a "font family name" like `"DejaVu Sans"` or a "generic family name" like `sans-serif`. 
Generic family names never use quotes. If a browser cannot find/does not support the first font in a list, it will use the next one, and so on.
Best practice is to have a generic family as a fallback: `font-famlily: "DejaVu Sans", sans-serif;`

`font-size` is used to set the size of the font. The value should not contain any whitespace. 
Ex: `font-size: 22px;`

`font-weight` effects the boldness of text. The value can be a keyword such as `font-weight: bold;` or a number between 1 and 1000. 
Usually numeric values will be increments of 100 up to 900. 

`text-align` will align text horizontally within an element. Ex: `text-align: center;` 

#### Image Height and Width
Image's height and width values will default to the same values as the image file, but can be adjusted with the `height` and `width` properties. 
You can adjust size without losing proportions by setting one property to `auto`.
```css
img {
    height: auto;
    width: 500px;
}
```
It is best practice to specify both properties even if one does not plan to adjust them.

### The Cascade of CSS
The cascade is what detirmines which rules get applied to the HTML. 

#### Specificity
CSS declarations which are more specific take precedence over less specific ones. 
Specificity will be taken into account only when an element has multiple conflicting declarations targeting it. 
ID selectors will always beat out any number of class selectors, and a class selector will always beat out any number of type selectors, and type selectors will beat out any number of anything less specific. 
When no declaration has a selector with heigher specificity, the declaration with a larger amount of a single selctor will win. 

#### Inheritance
Inheritance refers to certain CSS properties which are inherited by an elements descendents even if no explicit rule was written for the descendants. 
Typography based properties are usually inherited (`color`, `font-size`, `font-family`, etc.) while most others are not. 
Exception is when directly targeting an element. For example: 
```html
<!-- index.html -->

<div id="parent">
    <div class="child"></div>
</div>
```
```css
/* styles.css */

#parent {
    color: red;
}

.child {
    color: blue;
}
```
The child would have the color blue as it is being directly targeted, while red is only inherited. 

#### Rule Order
When a tie-breaker is needed for any element which has conflicting declarations, the last rule defined is the winner. 
```css
/* styles.css */

.alert {
    color: red;
}

.warning {
    color: yellow;
}
```
For an element with both the `alert` and `warning` classes, the `warning` class would be applied.

### Adding CSS to HTML

#### External CSS
External CSS is the most common, and involves creating a separate file for the CSS and linking it inside the HTML's opening and closing `<head>` tags using a `<link>` element:
```html
<!-- index.html -->

<head>
    <link rel="stylesheet" href="styles.css">
</head>
```
```css
/* styles.css */

div {
    color: white;
    background-color: black;
}

p {
    color: red;
}
```
The `href` attribute specifies the location of the CSS file, and the `rel` attribute (req.) specifies the relationship between the HTML and the linked file.

#### Internal CSS
Internal CSS involves adding the CSS within the HTML file instead of creating a separate file. 
With this method, rules are placed inside a pair of opening and closing `<style>` tags, which are then placed inside the `<head>` tag:
```html
<head>
    <style>
        div {
            color: white;
            background-color: black;
        }

        p {
            color: red;
        }
    </style>
</head>
```
This method can be useful for adding styles to a single page, but can start to bloat the HTML file if there are many CSS declarations.

#### Inline CSS
Inline CSS lets one add styles directly to HTML elements, though this method is not reccommended.
```html
<body>
    <div style="color: white; background-color: black;">...</div>
</body>
```
No selector is needed as the styles are being added directly to the div tag. This method should only be used to add a unique style to a single element. 

This method is not reccommended for the following reasons:
- The HTML can become messy if adding a lot of declarations to a single element.
- If you wanted multiple elements to have this style, it would have to be copy-pasted to each individual element.
- Inline CSS overwrites the other two methods potentially causing unexpected results.

### Knowledge Check
1. What are the main differences between external, internal, and inline CSS?
    - External CSS is contained in a separate file and added using the `<link>` element, internal CSS is contained in the HTML between the tags of the `<style>` element, and inline css is added directly to an element using the `style` attribute.
2. What is the syntax for class and ID selectors?
    - Class selectors use `.<class_name>` and ID selectors use `#<id_name>`.
3. How would you apply a single rule to two different selectors?
    - You can apply a single rule to different selectors using a comma-separated list.
4. Given an element that has an id of `title` and a class of `primary`, how would you use both attributes for a single rule?
    - A single rule would use `#title.primary` to specify the element with ID title and the class primary.
5. What does the descendant combinator do?
    - The descendant combinator allows one to specify a rule for an element which is the descendant or child of another element; this is done by putting a space between the selectors.
6. Between a rule that uses one class selector and a rule that uses three type selectors, which rule has the higher specificity?
    - A class selector will always have higher specificity than any number of type selectors.

## Inspecting HTML And CSS
This lesson is a walkthrough of the Chrome Dev Tools, which allow one to see detailed information about HTML elements, CSS rules, and code.

### The Inspector
To open the inspector you can right click any element and click inspect, or hit the F12 key.

### Inspecting Elements
In the elements pane, you can see the entire HTML structure of the page. You can click any specific element to select or use the blue icon hover any element on the page.

When an element is selcted, the styles tab shows any currently applied styles as well as any that are being overwritted (indicated by a strikethrough).

### Testing Styles in the Inspector
The styles pane also allows editing styles directly in the browser. The webpage will update the changes in real time, but the source of the page will not be affected. 
This is useful for quickly testing out attributes and values.

### Assignment: Chrome Dev Tools Docs

#### Overview
- Device Mode: Simulate Mobile Devices
- Elements Panel and CSS: View and change the DOM and CSS
- Console Panel: View messages and run JavaScript from the Console
- Sources Panel: Debug JavaScript, presist changes made in DevTools across page reloads, save and run JavaScript snippets, save changes made in DevTools to disk.
- Network Panel: View and debug network activity
- Recorder Panel: Record, replay, and measure user flows
- Performance Panel: Find ways to improve load and runtime performance
- Memory Panel
- Application Panel: Inspect all resources that are loaded, included IndexedDB or Web SQL databases, local and session storage, cookies, Application Cache, images, fonts, and stylesheets.
- Security Panel: Debug mixed content issues, certificate problems, and more.

#### Open Chrome Dev Tools
- Dev tools shortcuts:
    - Elements: Ctrl + Shift + C
    - Console: Ctrl + Shift + J
    - Your Last Panel: Ctrl + Shift + I
- Auto-open DevTool on every new tab:
    - Quit any running chrome instance
    - Use `google-chrome --auto-open-devtools-for-tabs`

### Knowledge Check

