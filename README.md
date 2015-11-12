# Preditor (Presentation Editor)
A convenient editor for making presentation slideshows in plain-text
(Markdown, HTML).

Use the [issue tracker](https://github.com/WebmonkeysUIUC/preditor/issues) to post
and discuss ideas, request features and report bugs.

Use the [Wiki](https://github.com/WebmonkeysUIUC/preditor/wiki) to document agreed-upon
features, design decisions, implementation ideas, and lay out the project roadmap.

## Motivation

### Advantages of HTML Presentations
There is a growing trend of creating presentations/slideshows as HTML applications,
especially among developers.

There are many advantages of making slideshows as web applications:
* Slides could be viewed in a web-browser --- people do not need any special software
  to view them
* Slides can be hosted on any static web server (especially GitHub Pages) to be viewed publicly.
  This allows links (and not files) to be distributed, which means updates to the slides are simple
* Slides can be styled using familiar and standard HTML and CSS technologies

In addition, slides can be written in [Markdown](https://daringfireball.net/projects/markdown/),
an easy-to-read, easy-to-write plain text format with minimal syntax. This has many advantages:
* Plain text can be edited in any editor of choice
* Plain text can be version-controlled (using, for example, Git), which allows maintaining
  revision history and enables better collaboration
* Writing in Markdown allows focusing on content and structure, without worrying about styling

### HTML Presentation Frameworks
There are several frameworks for creating HTML presentations, including:
* [remark](https://github.com/gnab/remark),
* [reveal.js](https://github.com/hakimel/reveal.js),
* [Cleaver](https://github.com/jdan/cleaver)
* [impress.js](https://github.com/impress/impress.js)
* [Flowtime.js](https://github.com/marcolago/flowtime.js)

### Problems with these frameworks
These frameworks provide a lot of flexibility, but it is often hard or time-consuming to get
started with a presentation. Either they require creating an HTML template to contain the slides
(like remark and reveal.js), require using a command line tool (like cleaver), or both.

Customization is also time-taking, and almost any kind of theming requires tweaking CSS, which
comes with its own problems like reading documentation, figuring out the right class names, etc.

Also, each of these frameworks has its own way of configuration, slide markup, themes, and styling.

None of the major frameworks are interoperable with PowerPoint or Keynote. One of the main advantages
of using PowerPoint or Keynote is that most official templates, communications, etc are distributed
in their formats.

### This project
This project aims to address the problems above by providing a web-based editor made specifically
for creating HTML presentations. Some features envisioned are:
* Work with these existing frameworks, not create another one, providing a consistent interface to
  for users to create slides, write content, and control styling
* Purely client-side --- no backend servers or databases, no logging in, etc.
* A Markdown editor designed specifically for making slides (so, for example, it'll provide buttons
  for creating new slides, previewing a current slide, etc)
* Live preview of current slide next to the editor
* Themes and template support
* Ability to import templates and presentations from PowerPoint or Keynote, and also export
  to their formats
* One-click publish to a web server or GitHub Pages, or ability to download an archive which can then
  be served from a static web server.
* PDF export
* Integration with version control, especially Git
* Ability to embed analytics into the presentations

## Existing similar projects
* [Editable HTML5 Slides](https://github.com/Bobby-Seidensticker/html5slides) is a simple
  editor for Google's HTML5 Slides framework, with real time editing. It is very close to what
  this project aims to be, however, it only supports one framework, the editor is very barebones,
  it does not have markdown support, and is tied to [pageforest](http://www.pageforest.com/).
* [Slides](https://slides.com/) is a graphical slide creator, and uses reveal.js (it is created by
  the original author of reveal.js). It is a great service, however, it is proprietary, paid (free
  only for public presentations), is tied to reveal.js, and is by default a graphical tool (although
  it has a "developer mode") for advanced users.
* [Swipe](https://www.swipe.to/) is a great service, uses Markdown for slide creation, has lots of
  templates, and has many other features such as analytics. It is probably the closest to our project
  in terms of features and functionality, and is free (although it charges for some advanced features).
  However, it is proprietary, and probably uses its own HTML presentation framework instead of those
  mentioned above.

## License
Current &copy; 2015, Neelabh Gupta.

The project will be licensed once some work is done on the project, after which
the contributors can arrive on a consensus.
