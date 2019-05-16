[< Back](../README.md)

# Printable CSS Stylesheets
My first article will be about printable stylesheets. During the course css-to-the-rescue-1819 we where allowed to choose our own assignment. I choose to create a print stylesheet for a magazine because I found this a very interesting topic. Using CSS to create and be able to print a physical magazine? Madness I say! Or is it?

## But Why?
A printable stylesheet is used when a user prints out a webpage. Situations where this may be applied are for example a confirmation page of a webshop or a recipe from an online cookbook. A lot of times we completely forget about these user scenarios.

See for example this [tweet](https://twitter.com/AaronGustafson/status/788073583528538112/photo/1?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E788073583528538112&ref_url=https%3A%2F%2Fuxdesign.cc%2Fmedia%2F870afac2877e8d6462bfb5dfe5e1b099%3FpostId%3Df1e6604cfd6) form Aaron Gustafson. He wanted to print out the order details but the page comes out completely messed up!

We spent so much time optimising our webpages for devices in all shapes and sizes that we forget about print. Maybe because we rarely do it ourselves or because we see print as a dying medium.

Now you don't have to go optimise your entire webpage. Just think about certain webpages that could benefit from a printable stylesheet.

## The Basics
Print media uses concepts are foreign to the web. For example: page numbers, chapter titles, break content, cross-references and footnotes, indexes and tables of content.

But first lets start with understanding the page model. The page model separates a page into 16 boxes.

![Page margin box definitions](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/05d0cb51-22ec-4eaf-93c0-222f16de6136/1-image-margin-boxes-large-opt.jpg)
> Page model

To be able to manipulate the page model is where printable CSS styles come in. The `@page` rule lets you specify various aspects of a page. For example, you will want to specify the size, margin and bleed of your pages.

```css
@page {
  size: landscape;
  margin: 10mm;
  bleed: 3mm;
}
```

You can also style pages individually using:

* `@page:fist`: Allows you to style the first page, most of the time the cover.
* `@page:left`: Allows you to style all left pages.
* `@page:right`: Allows you to style all right pages.

Here is an example of a CSS print selectors: `@top-center`, `@bottom-left` and `@bottom-right`. These declerations allow you to select different boxes of the page model.

```css
@page:first {

  @top-center{
    content: none;
  }

  @bottom-left {
    content: normal;
  }

  @bottom-right {
    content: normal;
  }
}
```
Here we have a perfect example of a CSS printable stylesheet decleration, `content: counter(page);`. By doing this we add the page number automatically to the `@bottom-left` box of the `@page:left`.

Same goes for `content: 'ADD NONSENSE';` of the `@bottom-right` box.

```css
@page:left {

  @bottom-left {
    content: counter(page);
  }

  @bottom-right {
    content: 'ADD NONSENSE';
  }
}
```
We also have a need little decleration called `page-break`. This decleration can be used to do multiple things: you can set a `page-break-before: always` to always start on a new page before that selected element.

Or you can use a `page-break-avoid` to avoid a page break inside that element.

```css
main, section, section:first-of-type p:first-of-type {
  page-break-before: always;
}

h1, h2, h3, h4, h5 {
  page-break-after: avoid;
}

h3:first-of-type {
  page-break-before: always;
}

figure {
  page-break-inside: avoid;
}
```
And finally lets finish with `widows` and `orphans`. `widows` and `orphans` allow you to control the number of lines at the beginning and end of a page.

* A widow is a paragraph-ending line that falls at the beginning of the following page, and is separated from the rest of the text.

* A orphan is a paragraph-opening line that appears by itself at the bottom of a page, and is separated from the rest of the text.

You can control them in CSS by doing the following:

```css
p {
  orphans: 3;
  widows: 3;
}
```

## Prince
To actually create a PDF using this CSS, you’ll need a user agent that supports it. Like [Prince](https://www.princexml.com/). When you want to use decelerations like `content: counter(page);` or `@page:fist` it wont work when you print directly from your browser. Because that is not how the browser works.

You can use Prince to export your HTML page and turn it into a PDF. When you do this you will see that things like page numbers and page specific styles are being applied.

## Conclusion
