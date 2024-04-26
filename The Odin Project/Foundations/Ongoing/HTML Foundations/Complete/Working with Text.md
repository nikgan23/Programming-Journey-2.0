### [Introduction](https://www.theodinproject.com/lessons/foundations-working-with-text#introduction)

Most content on the web is text-based, so you will find yourself needing to work with HTML text elements quite a bit.

In this lesson, we will learn about the text-based elements you are likely to use the most.

### [Lesson overview](https://www.theodinproject.com/lessons/foundations-working-with-text#lesson-overview)

This section contains a general overview of topics that you will learn in this lesson.

- How to create paragraphs.
- How to create headings.
- How to create bold text.
- How to create italicized text.
- The relationships between nested elements.
- How to create HTML comments.

### [Paragraphs](https://www.theodinproject.com/lessons/foundations-working-with-text#paragraphs)

What would you expect the following text to output on an HTML page?

```html
<body>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.

  Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
  nisi ut aliquip ex ea commodo consequat.
</body>
```

Copy

It looks like two paragraphs of text, and so you might expect it to display in that way. However, that is not the case, as you can see in the output below:

When the browser encounters new lines like this in your HTML, it will compress them down into one single space. The result of this compression is that all of the text is clumped together into one long line.

If we want to create paragraphs in HTML, we need to use the paragraph element, which will add a new line after each of our paragraphs. A paragraph element is defined by wrapping text content with a `<p>` tag.

Changing our example from before to use paragraph elements fixes the issue:

### [Headings](https://www.theodinproject.com/lessons/foundations-working-with-text#headings)

Headings are different from other HTML text elements: they are displayed larger and bolder than other text to signify that they are headings.

There are 6 different levels of headings starting from `<h1>` to `<h6>`. The number within a heading tag represents that heading’s level. The largest and most important heading is h1, while h6 is the tiniest heading at the lowest level.

Headings are defined much like paragraphs. For example, to create an h1 heading, we wrap our heading text in an `<h1>` tag.

Using the correct level of heading is important as levels provide a hierarchy to the content. An h1 heading should always be used for the heading of the overall page, and the lower level headings should be used as the headings for content in smaller sections of the page.

### [Strong element](https://www.theodinproject.com/lessons/foundations-working-with-text#strong-element)

The `<strong>` element makes text bold. It also semantically marks text as important; this affects tools, like screen readers, that users with visual impairments will rely on to use your website. The tone of voice on some screen readers will change to communicate the importance of the text within a strong element. To define a strong element we wrap text content in a `<strong>` tag.

You can use strong on its own:

But you will probably find yourself using the strong element much more in combination with other text elements, like this:

Sometimes you will want to make text bold without giving it an important meaning. You’ll learn how to do that in the CSS lessons later in the curriculum.

### [Em element](https://www.theodinproject.com/lessons/foundations-working-with-text#em-element)

The `<em>` element makes text italic. It also semantically places emphasis on the text, which again may affect things like screen readers. To define an emphasised element we wrap text content in an `<em>` tag.

To use `<em>` on its own:

Again, like the strong element, you will find yourself mostly using the `<em>` element with other text elements:

### [Nesting and indentation](https://www.theodinproject.com/lessons/foundations-working-with-text#nesting-and-indentation)

You may have noticed that in all the examples in this lesson we indent any elements that are within other elements. This is known as nesting elements.

When we nest elements within other elements, we create a parent and child relationship between them. The nested elements are the children and the element they are nested within is the parent.

In the following example, the body element is the parent and the paragraph is the child:

Just as in human relationships, HTML parent elements can have many children. Elements at the same level of nesting are considered to be siblings.

For example, the two paragraphs in the following code are siblings, since they are both children of the body tag and are at the same level of nesting as each other:

We use indentation to make the level of nesting clear and readable for ourselves and other developers who will work with our HTML in the future. It is recommended to indent any child elements by two spaces.

The parent, child, and sibling relationships between elements will become much more important later when we start styling our HTML with CSS and adding behavior with JavaScript. For now, however, it is just important to know the distinction between how elements are related and the terminology used to describe their relationships.

### [HTML comments](https://www.theodinproject.com/lessons/foundations-working-with-text#html-comments)

HTML comments are not visible to the browser; they allow us to _comment_ on our code so that other developers or our future selves can read them and get some context about something that might not be clear in the code.

In order to write an HTML comment, we just enclose the comment with `<!--` and `-->` tags. For example:

**VSCode keyboard shortcut**

If you find typing out the comments syntax tiring, the following shortcut will help you quickly create a new comment, convert any line to a comment, or uncomment any line:

- Mac Users: Cmd + /
- Windows and Linux Users: Ctrl + /

### [Assignment](https://www.theodinproject.com/lessons/foundations-working-with-text#assignment)

1. Watch Kevin Powell’s [HTML Paragraph and Headings Video](https://www.youtube.com/watch?v=yqcd-XkxZNM).
2. Watch Kevin Powell’s [HTML Bold and Italic Text Video](https://www.youtube.com/watch?v=gW6cBZLUk6M).
3. To get some practice working with text in HTML, create a plain blog article page which uses different headings, uses paragraphs, and has some text in the paragraphs bolded and italicized. You can use [Lorem Ipsum](https://en.wikipedia.org/wiki/Lorem_ipsum) to generate dummy text, in place of real text as you build your sites. VS Code includes a shortcut to generate lorem ipsum for you. To trigger the shortcut, type `lorem` on the line where you want the dummy text, then press the Enter key, and voila, you have generated dummy text without a hitch.

### [Knowledge check](https://www.theodinproject.com/lessons/foundations-working-with-text#knowledge-check)

This section contains questions for you to check your understanding of this lesson on your own. If you’re having trouble answering a question, click it and review the material it links to.

- [How do you create a paragraph in HTML?](https://www.theodinproject.com/lessons/foundations-working-with-text#create-paragraph-element)
- [How do you create a heading in HTML?](https://www.theodinproject.com/lessons/foundations-working-with-text#headings)
- [How many different levels of headings are there and what is the difference between them?](https://www.theodinproject.com/lessons/foundations-working-with-text#different-heading-levels)
- [What element should you use to make text bold and important?](https://www.theodinproject.com/lessons/foundations-working-with-text#strong-element)
- [What element should you use to make text italicized to add emphasis to it?](https://www.theodinproject.com/lessons/foundations-working-with-text#em-element)
- [What relationship does an element have with any nested elements within it?](https://www.theodinproject.com/lessons/foundations-working-with-text#nested-relationship)
- [What relationship do two elements have if they are at the same level of nesting?](https://www.theodinproject.com/lessons/foundations-working-with-text#elements-same-level)
- [How do you create HTML comments?](https://www.theodinproject.com/lessons/foundations-working-with-text#html-comments)

### [Additional resources](https://www.theodinproject.com/lessons/foundations-working-with-text#additional-resources)

This section contains helpful links to related content. It isn’t required, so consider it supplemental.

- [The semantic difference between <strong> and <b> or <em> and <i> tags and when to use them.](https://medium.com/@zac_heisey/when-to-use-strong-b-em-and-i-tags-in-your-markup-fa4d0af8affb)
- [An interactive HTML text formatting article](https://www.w3schools.com/html/html_formatting.asp)




