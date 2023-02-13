# HTML Notes

- HTML is the standard markup language for Web pages. With HTML you can create your own Website.
- Html code

<!DOCTYPE html>

<html>

<head>

<title>Page Title</title>

</head>

<body>

<h1>This is a Heading</h1>

<p>This is a paragraph.</p>

</body>

</html>

| https://www.w3schools.com/tags/tag_html.asp | Defines the root of an HTML document |
| --- | --- |
| https://www.w3schools.com/tags/tag_body.asp | Defines the document's body |
- HTML Headings

HTML headings are defined with the `<h1>` to `<h6>` tags.

`<h1>` defines the most important heading. `<h6>` defines the least important heading:

<h1>My First Heading</h1>

- html paragraph

<p>My first paragraph.</p>

- html links

<a href="[https://www.w3schools.com](https://www.w3schools.com/)">This is a link</a>

- html images

<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">

- HTML is Not Case Sensitive

HTML tags are not case sensitive: `<P>` means the same as `<p>`.

- Style attribute

<p style="color:red;">This is a red paragraph.</p> 

<body style="background-color:powderblue;">

<h1 style="font-family:verdana;">This is a heading</h1>

size=<h1 style="font-size:300%;">This is a heading</h1>

text alignment;

<h1 style="text-align:center;">Centered Heading</h1>

<p style="text-align:center;">Centered paragraph.</p>

- Text formatting;
- `<b>` - Bold text
- `<strong>` - Important text
- `<i>` - Italic text
- `<em>` - Emphasized text
- `<mark>` - Marked text
- `<small>` - Smaller text
- `<del>` - Deleted text
- `<ins>` - Inserted text
- `<sub>` - Subscript text
- `<sup>` - Superscript text

eg;<b>This text is bold</b>

- single or doublr quotes-Both can be used.

<p title='John "ShotGun" Nelson'>
Or vice versa:

<p title="John 'ShotGun' Nelson">

- HTML Line Breaks-The HTML `<br>` element defines a line break.

<p>This is<br>a paragraph<br>with line breaks.</p>

- The HTML `<q>` tag defines a short quotation.

<p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_formatting_q)

- Html <abbr> tag;

<p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>

- Html <address> tag;

<address>

Written by John Doe.<br>

Visit us at:<br>

Example.com<br>

USA

</address>

- Html <cite> tag;

<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>

- Html <bdo>tag;

<bdo dir="rtl">This text will be written from right to left</bdo>

- Html comment ;

<!-- Write your comments here --

- Html color;

<h1 style="color:Tomato;">Hello World</h1>

<h1 style="background-color:rgb(255, 99, 71);">...</h1>

<h1 style="order:2px solid Tomato;">Hello World</h1>

# **HTML Styles - CSS**

CSS stands for Cascading Style Sheets.It can control the layout of multiple web pages all at once.

Tip; The word **cascading** means that a style applied to a parent element will also apply to all children elements within the parent. So, if you set the color of the body text to "blue", all headings, paragraphs, and other text elements within the body will also get the same color (unless you specify something else)!

- **Inline css;**

<h1 style="color:blue;">A Blue Heading</h1>

<p style="color:red;">A red paragraph.</p>

- **Internal CSS;**

An internal CSS is used to define a style for a single HTML page.

<head>

<style>

body {background-color: powderblue;}

h1   {color: blue;}

p    {color: red;}

</style>

</head>

- **External CSS;**

An external style sheet is used to define the style for many HTML pages.

<head>

<link rel="stylesheet" href="styles.css">

</head>

- HTML Table Tags

| Tag | Description |
| --- | --- |
| https://www.w3schools.com/tags/tag_table.asp | Defines a table |
| https://www.w3schools.com/tags/tag_th.asp | Defines a header cell in a table |
| https://www.w3schools.com/tags/tag_tr.asp | Defines a row in a table |
| https://www.w3schools.com/tags/tag_td.asp | Defines a cell in a table |
| https://www.w3schools.com/tags/tag_caption.asp | Defines a table caption |
| https://www.w3schools.com/tags/tag_colgroup.asp | Specifies a group of one or more columns in a table for formatting |
| https://www.w3schools.com/tags/tag_col.asp | Specifies column properties for each column within a <colgroup> element |
| https://www.w3schools.com/tags/tag_thead.asp | Groups the header content in a table |
| https://www.w3schools.com/tags/tag_tbody.asp | Groups the body content in a table |
| https://www.w3schools.com/tags/tag_tfoot.asp | Groups the footer content in a table |