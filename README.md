
# Markdown Viewer / Firefox Extension


# Features

- Supports multiple markdown parsers
- Full control over the [compiler options][compiler-options] ([marked][marked] or [remark][remark])
- Themes support (including [GitHub theme][themes0]) ([jasonm23][themes1], [mixu][themes2], [cobalt][themes3])
- Supports [GitHub Flavored Markdown][gfm]
- Syntax highlighted code blocks ([prism][prism])
- Generates Table of Contents (TOC)
- Settings synchronization
- Raw and rendered markdown views
- Free and Open Source


# Compiler Options

## Marked

Option          | Default | Description
:---            | :---    | :---
**breaks**      | `false` | Enable GFM [line breaks][gfm]. This option requires the gfm option to be true.
**gfm**         | `true`  | Enable GFM [GitHub Flavored Markdown][gfm].
**pedantic**    | `false` | Conform to obscure parts of markdown.pl as much as possible. Don't fix any of the original markdown bugs or poor behavior.
**sanitize**    | `false` | Sanitize the output. Ignore any HTML that has been input.
**smartLists**  | `false` | Use smarter list behavior than the original markdown. May eventually be default with the old behavior moved into pedantic.
**smartypants** | `false` | Use "smart" typographic punctuation for things like quotes and dashes.
**tables**      | `true`  | Enable GFM [tables][gfm-tables]. This option requires the gfm option to be true.

## Remark

Option          | Default | Description
:---            | :---    | :---
**breaks**      | `false` | Enable GFM [line breaks][gfm]. This option requires the gfm option to be true.
**commonmark**  | `false` | Toggle CommonMark mode.
**footnotes**   | `false` | Toggle reference footnotes and inline footnotes.
**gfm**         | `true`  | Enable GFM [GitHub Flavored Markdown][gfm].
**pedantic**    | `false` | Conform to obscure parts of markdown.pl as much as possible. Don't fix any of the original markdown bugs or poor behavior.
**sanitize**    | `false` | Sanitize the output. Ignore any HTML that has been input.


<<<<<<< HEAD
=======
# Content Options

Option          | Default | Description
:---            | :---    | :---
**emoji**       | `false` | Convert emoji :shortnames: into EmojiOne images
**scroll**      | `true`  | Remember scroll position
**toc**         | `false` | Generate Table of Contents
**mathjax**     | `false` | Render TeX and LaTeX math blocks

## Scroll

- When enabled, the `scroll` option remembers the current scroll position and scrolls back to it after page load.
- When disabled, the `scroll` option either scrolls to the top of the document or to a certain header (anchor) if a hash URL fragment is present.

## TOC

- Generates Table of Contents (TOC) based on the headers found in the markdown document.

## MathJax

The following `mathjax` delimiters are supported:

- inline math: `\(math\)` and `$math$`
- display math: `\[math\]` and `$$math$$`

The following rules apply to your content when `mathjax` is enabled:

- Regular dollar sign `$` in text that is not part of a math formula should be escaped: `\$`
- Regular markdown escaping for parentheses: `\(` and `\)`, and brackets: `\[` and `\]` is not supported. MathJax will convert anything between these delimiters to math formulas, unless they are wrapped in backticks: `` `\(` `` or fenced code blocks.

> The MathJax support currently works only for local file URLs and remote origins without strict *Content Security Policy (CSP)* set. For example it won't work for files hosted on GitHub.

## Emoji

- Emoji shortnames like: `:sparkles:` will be converted to :sparkles: using [EmojiOne][emojione] images.
- Currently unicode symbols like `✨` and ASCII emoji like `:D` are not supported.

> The Emoji support currently works only for local file URLs and remote origins without strict *Content Security Policy (CSP)* set. For example it won't work for files hosted on GitHub.


# Advanced Options

Detecting and rendering [local file URLs](#local-files) can be enabled by using the `Allow access to file URLs` option for the extension.

Access to remote URLs however, needs to be enabled manually.


## Add Origin

Here is how you can enable the extension for the `https://raw.githubusercontent.com` origin:

![add-origin]

The origin consists of *protocol* part and *domain* part. The *protocol* can be either `https`, `http`, or a `*` to match both `https` and `http`.

Enable the above origin and play around with the extension options [here][syntax].

## Add All Origins

In case you really want to you can enable the extension for **all** origins:

![all-origins]

Alternatively you can use the `Allow All` button.

> Note that the remote origins should either provide a valid HTTP header (see [Header Detection](#header-detection)) and/or valid URL path (see [Path Matching](#path-matching)). Otherwise you'll have to add the origin explicitly and set its [Path Matching](#path-matching) regular expression.

## Header Detection

When this option is enabled the extension will check for the `text/markdown` and `text/x-markdown` *content-type* header before trying to match the path:

![header-detection]

## Path Matching

If the header detection is disabled or a proper *content-type* header is missing, the extension will check if the URL is ending with a markdown file extension:

![path-regexp]

It's a simple regular expression that matches URLs ending with:

- markdown file extension: `\.(?:markdown|mdown|mkdn|md|mkd|mdwn|mdtxt|mdtext|text)`
- and optionally anchor or querystring after that: `(?:#.*|\?.*)?`

> The `?:` used in `(?:match)` stands for *non-capturing group* and it's there for performance reasons.

You can modify the path matching regular expression for each enabled origin individually. The settings are being updated as you type.

## Remove Origin

At any point click on the small `x` button next to the origin that you want to remove. This actually removes the permission itself so that the extension is no longer able to inject scripts into that origin.

Note that the Chrome's consent popup shows up only when you add the origin for the first time. In case you re-add it you'll no longer see that popup. That's a Chrome thing and it's not controllable through the extension.

## Refresh Origin

The extension synchronizes your preferences across all your devices using Google Sync. The list of your allowed origins is being synced too, but the actual permissions that you give using the Chrome's consent popup cannot be synced.

In case you've recently added a new origin on one of your devices you'll have to explicitly allow it on your other devices. The little refresh button next to each origin is used for that.


>>>>>>> cc9c8a927eaace2facde13c897074d99a9664219
# Markdown Syntax and Features

A few files located in the [test] folder of this repo can be used to test what's possible with Markdown Viewer:

- Navigate to the test files: [syntax][test-syntax], [mathjax][test-mathjax], [yaml][test-yaml], [toml][test-toml] and play around with the `Compiler` and `Content` options
- Use the `Markdown/HTML` button to switch between raw markdown and rendered HTML
- At any point click on the `Defaults` button to reset back the compiler options


# License

The MIT License (MIT)

Copyright (c) 2013-2017 Simeon Velichkov <simeonvelichkov@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


  [chrome-store]: https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
  [donate]: https://img.shields.io/badge/paypal-donate-blue.svg?style=flat-square (Donate on Paypal)
  [paypal]: https://www.paypal.me/simeonvelichkov

  [marked]: https://github.com/chjj/marked
  [remark]: https://github.com/wooorm/remark
  [showdown]: https://github.com/showdownjs/showdown
  [markdown-it]: https://github.com/markdown-it/markdown-it
  [remarkable]: https://github.com/jonschlinkert/remarkable
  [commonmark]: https://github.com/jgm/commonmark.js
  [markdown-js]: https://github.com/evilstreak/markdown-js

  [emojione]: https://emojione.com
  [mathjax]: https://www.mathjax.org

  [gfm]: https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown
  [compiler-options]: #compiler-options
  [themes0]: https://github.com/sindresorhus/github-markdown-css
  [themes1]: https://github.com/jasonm23/markdown-css-themes
  [themes2]: https://github.com/mixu/markdown-styles
  [themes3]: https://github.com/nWODT-Cobalt/markown-utilities
  [prism]: http://prismjs.com/
  [gfm-tables]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables
  [syntax]: https://raw.githubusercontent.com/simov/markdown-viewer/master/test/syntax.md
  [compilers]: https://github.com/simov/markdown-viewer/tree/compilers
  [test]: https://github.com/simov/markdown-viewer/tree/master/test

  [test-syntax]: https://raw.githubusercontent.com/simov/markdown-viewer/master/test/syntax.md
  [test-mathjax]: https://raw.githubusercontent.com/simov/markdown-viewer/master/test/mathjax.md
  [test-yaml]: https://raw.githubusercontent.com/simov/markdown-viewer/master/test/yaml.md
  [test-toml]: https://raw.githubusercontent.com/simov/markdown-viewer/master/test/toml.md

  [file-urls]: https://i.imgur.com/rNS9ADW.png
  [add-origin]: https://i.imgur.com/GnKmkRG.png
  [all-origins]: https://i.imgur.com/4GH3EuP.png
  [header-detection]: https://i.imgur.com/bdz3Reg.png
  [path-regexp]: https://i.imgur.com/jSrLDAM.png
