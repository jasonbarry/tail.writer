tail.writer
============
[![plainJS](https://s.pytes.net/cb2d2d94)](https://s.pytes.net/305f45f2)
[![npm Version](https://s.pytes.net/79c4dbb4)](https://s.pytes.net/f6deba28)
[![npm Downloads](https://s.pytes.net/d84c0033)](https://s.pytes.net/f6deba28)
[![License](https://s.pytes.net/8257ac72)](LICENSE.md)
[![Author](https://s.pytes.net/5542d1fa)](https://s.pytes.net/5be37d0a)

The **tail.writer** script is a neat, powerful, highly extend- and translatable Markup Editor,
written in Vanilla JavaScript. It currently supports the [GitHub Flavored] Markdown, BBCode and
Textile Markup languages.

[Wanna see **tail.writer** in action?](https://github.pytes.net/tail.writer)

[Wanna translate **tail.writer** in your language?](https://github.com/pytesNET/tail.writer/wiki/Help-Translating)

Features
--------
-   Compatible with all modern browsers, and also for **IE >= 9**.
-   WriteFlow supportive Features & Functions
-   A Translation API to use your websites-native language
-   An extensive Markup API to use custom Markup languages and actions
-   Hooks, Event Listeners & Key-Bindings for your own code
-   No dependencies, just include and use it (except the Preview-Action)!
-   Bindings for the jQuery and MooTools library and usable as **AMD**.
-   3 beautiful Designs and many settings!

### WYSIWYG vs. Markup
The tail.writer script is **not a WYSIWYG** (What you see is what you get) editor, it's a Markup
editor. The difference is the presentation of the written text: A WYSIWYG editor shows a bold text
directly as **bold text**, while a Markup editor shows only the Markup syntax: \*\*bold text\*\*.
(The shown syntax depends on the used Markup language, of course!)

However, you still have the possibility to add a Preview toolbar action to each single Markup
language. The Preview View is not editable and requires an additional JavaScript parser depending
on the used Markup language. We currently support the following libraries:

-   [GF] Markdown - [marked](https://github.com/markedjs/marked)
-   [GF] Markdown - [showdown](https://github.com/showdownjs/showdown)
-   Textile - [textile.js](https://github.com/borgar/textile-js)
-   BBCode - [tail.BBSolid](https://github.com/pytesNET/tail.BBSolid)

You can also use your own (or a not supported) parser library, of course. Check out the option
[`previewConverter`](https://github.com/pytesNET/tail.writer/wiki/Available-Options#previewconverter),
which allows you to pass your own parser callback function !

Install & Embed
---------------
The master branch will always contain the latest Version (incl. not-released updates), which you can
download directly here as [.tar](https://github.com/pytesNET/tail.writer/tarball/master) or as
[.zip](https://github.com/pytesNET/tail.writer/zipball/master) archive, or just visit the Releases
Page on GitHub directly. You can also be cool and using npm, Yarn or bower:

```markup
npm install tail.writer --save
```

```markup
yarn add tail.writer --save
```

```markup
bower install tail.writer --save
```

### Using a CDN
You can also use the awesome CDN services from jsDelivr or UNPKG.

```markup
https://cdn.jsdelivr.net/npm/tail.writer@latest/
```

```markup
https://unpkg.com/tail.writer/
```

Real-World Examples
-------------------
Do you use **tail.writer** in one of your project? Don't wait, write us at info@pytes.net and get
listed below too!

### [Bludit](https://github.com/bludit/bludit)
The [**tail.writer**](https://github.com/bludit-plugins/tail.writer) Markup Editor is available for
the awesome Flat-File Content Management System [Bludit](https://github.com/bludit/bludit).

Thanks To
---------
-   [Octicons](https://octicons.github.com/) for the cute Icons
-   [jsCompress](https://jscompress.com/) for the Compressor
-   [prismJS](https://prismjs.com) for the Syntax highlighting library
-   [MenuSpy](https://github.com/lcdsantos/menuspy) for the Menu Navigation

Documentation
-------------
The Documentation has been moved to [GitHubs Wiki Pages](https://github.com/pytesNET/tail.writer/wiki),
but I will keep a table of contents list here and some basic instructions.

-   [Install & Embed](https://github.com/pytesNET/tail.writer/wiki/Instructions)
-   [Default Usage](https://github.com/pytesNET/tail.writer/wiki/Default-Usage)
-   [Available Options](https://github.com/pytesNET/tail.writer/wiki/Available-Options)
-   [Available Methods](https://github.com/pytesNET/tail.writer/wiki/Available-Methods)
-   [Events & Callbacks](https://github.com/pytesNET/tail.writer/wiki/Callback-Handler)
-   [Internal Variables & Methods](https://github.com/pytesNET/tail.writer/wiki/Internal)
-   [HowTos, Tips & Tricks](https://github.com/pytesNET/tail.writer/wiki/How-Tos)

### Extended Docs
-   [Markup Overview](https://github.com/pytesNET/tail.writer/wiki/Markup%3A-Overview)
-   [Markup API](https://github.com/pytesNET/tail.writer/wiki/Markup%3A-API)
-   [Plugin API](https://github.com/pytesNET/tail.writer/wiki/Plugin%3A-API)

### Files
The **tail.writer** package contains many files and directories, which may confuse. The `less`
folder can be ignored, unless you want to write a completely own design using the icon set or
one of our designs as basic template.

Basically the `css` and `js` folders (and the `markups` / `langs` directories maybe too) contains
the main files, which you need to embed on your website. The content within the `css` folder should
be self explanatory, the other the other folders contain these files:

-   `js/tail.writer(.min).js` - Contains the main script, WITHOUT any markup language.
-   `js/tail.writer-<markup>(.min).js` - Contains the main script, INCLUDING the named markup language.
-   `js/tail.writer-full(.min).js` - Contains the main script, INCLUDING ALL markup and interface languages.
-   `langs/tail.writer-all.js` - Contains all available interface languages.
-   `langs/tail.writer-<lang_code>.js` - Contains just the named interface language.
-   `markups/tail.markup-all.js` - Contains all available markup languages.
-   `markups/tail.markup-<markup>.js` - Contains just the named markup language.

So this mean, if you include just the `js/tail.writer(.min).js` file, nothing will happen, because
you **NEED** to embed a single markup language too. Now you can include the markup syntax itself
using one of the files within the `markups` folder OR you include a direct bundle from the `js`
folder, so `js/tail.writer-markdown.min.js`, for example, which contains the Markdown markup.

### Basic Instructions
It's highly recommended to load the Stylesheet within your HTML Header, while you pass the
desired JavaScript files after the opened `<body>` tag (you can also include them before the
closing `</body>` tag, of course). Please make sure you load the Markup and Interface languages as
well as all plugins AFTER the main script. the `tail.writer()` function should be called within
the "DOMContentLoaded" event.

You can pass up to 2 arguments to the **tail.writer** constructor, the first parameter is required
and need to be an `Element`, a `NodeList`, a `HTMLCollection`, an `Array` with `Element` objects or
just a single selector as `String`, which calls the `.querySelectorAll()` method on its own.
The second parameter is optional and, if set, MUST be an `object` with your **tail.writer** options.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />

        <link type="text/css" rel="stylesheet" href="css/tail.writer-white.min.css" />
    </head>
    <body>
        <script type="text/javascript" src="js/tail.writer-{markup}.min.js"></script>
        <!-- <script type="text/javascript" src="langs/tail.writer-{lang}.js"></script> -->

        <textarea></textarea>

        <script type="text/javascript">
            document.addEventListener("DOMContentLoaded", function(){
                tail.writer("textarea", { /* Your Options */ });
            });
        </script>
    </body>
</html>
```

### Default Options
Please check out [GitHubs Wiki Pages](https://github.com/pytesNET/tail.writer/wiki/Available-Options)
to read more about each single option!

```javascript
tail.writer("textarea", {
    classNames: null,               // New in 0.4.0
    debug: false,                   // New in 0.4.0
    disabled: false,                // New in 0.4.0
    doubleLineBreak: false,         // New in 0.4.0
    fullscreenParent: d.body,       // New in 0.4.0
    height: [200, 500],
    indentTab: false,
    indentSize: 4,
    locale: "en",                   // New in 0.4.0
    markup: null,                   // New in 0.4.0
    preventBindings: false          // New in 0.4.0
    previewConverter: null,         // New in 0.4.0
    readonly: false,                // New in 0.4.0
    resize: true,
    statusbar: true,
    toolbar: [],
    toolbarMultiLine: true,         // New in 0.4.0
    toolbarScrollable: true,        // New in 0.4.0
    tooltip: "top",
    width: "100%"
});
```

Copyright & License
-------------------
Published under the MIT-License; Copyright © 2015 - 2019 SamBrishes, pytesNET
