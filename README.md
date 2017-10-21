
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
- Open source


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

  [file-urls]: https://i.imgur.com/eqiwzEz.png
  [add-origin]: https://i.imgur.com/56zWesT.png
  [all-origins]: https://i.imgur.com/GiLeftR.png
  [header-detection]: https://i.imgur.com/EYdmbSd.png
  [path-regexp]: https://i.imgur.com/e06U6J2.png
