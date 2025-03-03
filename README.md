# PDF [![Build Status](https://github.com/mozilla/pdf/workflows/CI/badge.svg?branch=master)](https://github.com/mozilla/pdf/actions?query=workflow%3ACI+branch%3Amaster)

[PDF](https://mozilla.github.io/pdf/) is a Portable Document Format (PDF) viewer that is built with HTML5.

PDF is community-driven and supported by Mozilla. Our goal is to
create a general-purpose, web standards-based platform for parsing and
rendering PDFs.

## Contributing

PDF is an open source project and always looking for more contributors. To
get involved, visit:

+ [Issue Reporting Guide](https://github.com/mozilla/pdf/blob/master/.github/CONTRIBUTING.md)
+ [Code Contribution Guide](https://github.com/mozilla/pdf/wiki/Contributing)
+ [Frequently Asked Questions](https://github.com/mozilla/pdf/wiki/Frequently-Asked-Questions)
+ [Good Beginner Bugs](https://github.com/mozilla/pdf/issues?direction=desc&labels=good-beginner-bug&page=1&sort=created&state=open)
+ [Projects](https://github.com/mozilla/pdf/projects)

Feel free to stop by our [Matrix room](https://chat.mozilla.org/#/room/#pdfjs:mozilla.org) for questions or guidance.

## Getting Started

### Online demo

Please note that the "Modern browsers" version assumes native support for
features such as optional chaining, nullish coalescing,
and private `class` fields/methods; please also see [this wiki page](https://github.com/mozilla/pdf/wiki/Frequently-Asked-Questions#faq-support).

+ Modern browsers: https://mozilla.github.io/pdf/web/viewer.html

+ Older browsers: https://mozilla.github.io/pdf/legacy/web/viewer.html

### Browser Extensions

#### Firefox

PDF is built into version 19+ of Firefox.

#### Chrome

+ Build Your Own - Get the code as explained below and issue `gulp chromium`. Then open
Chrome, go to `Tools > Extension` and load the (unpackaged) extension from the
directory `build/chromium`.

## Getting the Code

To get a local copy of the current code, clone it using git:

    $ git clone https://github.com/mozilla/pdf.git
    $ cd pdf

Next, install Node.js via the [official package](https://nodejs.org) or via
[nvm](https://github.com/creationix/nvm). You need to install the gulp package
globally (see also [gulp's getting started](https://github.com/gulpjs/gulp/tree/master/docs/getting-started)):

    $ npm install -g gulp-cli

If everything worked out, install all dependencies for PDF:

    $ npm install

Finally, you need to start a local web server as some browsers do not allow opening
PDF files using a `file://` URL. Run:

    $ gulp server

and then you can open:

+ http://localhost:8888/web/viewer.html

Please keep in mind that this requires a modern and fully up-to-date browser; refer to [Building PDF](https://github.com/mozilla/pdf/blob/master/README.md#building-pdfjs) for non-development usage of the PDF library.

It is also possible to view all test PDF files on the right side by opening:

+ http://localhost:8888/test/pdfs/?frame

## Building PDF

In order to bundle all `src/` files into two production scripts and build the generic
viewer, run:

    $ gulp generic

If you need to support older browsers, run:

    $ gulp generic-legacy

This will generate `pdf` and `pdf.worker.js` in the `build/generic/build/` directory (respectively `build/generic-legacy/build/`).
Both scripts are needed but only `pdf` needs to be included since `pdf.worker.js` will
be loaded by `pdf`. The PDF files are large and should be minified for production.

## Using PDF in a web application

To use PDF in a web application you can choose to use a pre-built version of the library
or to build it from source. We supply pre-built versions for usage with NPM and Bower under
the `pdfjs-dist` name. For more information and examples please refer to the
[wiki page](https://github.com/mozilla/pdf/wiki/Setup-pdf-in-a-website) on this subject.

## Including via a CDN

PDF is hosted on several free CDNs:
 - https://www.jsdelivr.com/package/npm/pdfjs-dist
 - https://cdnjs.com/libraries/pdf
 - https://unpkg.com/pdfjs-dist/

## Learning

You can play with the PDF API directly from your browser using the live demos below:

+ [Interactive examples](https://mozilla.github.io/pdf/examples/index.html#interactive-examples)

More examples can be found in the [examples folder](https://github.com/mozilla/pdf/tree/master/examples/). Some of them are using the pdfjs-dist package, which can be built and installed in this repo directory via `gulp dist-install` command.

For an introduction to the PDF code, check out the presentation by our
contributor Julian Viereck:

+ https://www.youtube.com/watch?v=Iv15UY-4Fg8

More learning resources can be found at:

+ https://github.com/mozilla/pdf/wiki/Additional-Learning-Resources

The API documentation can be found at:

+ https://mozilla.github.io/pdf/api/

## Questions

Check out our FAQs and get answers to common questions:

+ https://github.com/mozilla/pdf/wiki/Frequently-Asked-Questions

Talk to us on Matrix:

+ https://chat.mozilla.org/#/room/#pdfjs:mozilla.org

File an issue:

+ https://github.com/mozilla/pdf/issues/new

Follow us on Twitter: @pdfjs

+ https://twitter.com/pdfjs
