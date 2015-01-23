[![npm version](https://badge.fury.io/js/prez.svg)](http://badge.fury.io/js/prez)
[![Dependency Status](https://david-dm.org/lmtm/prez.png)](https://david-dm.org/lmtm/prez)

## prez

Opiniated Reveal slideshow generator.

Work in progress.

### Why?

I had a mission: print slideshows *with* notes. So I had to customize the print output, make notes visible, struggle with the contents in `<aside>` (not really markdown, not really html, deal with it), and finally throw it all.

Frustrated by `Reveal`'s dumb way of handling side notes from markdown files (yes, that's an edge case), I needed to generate a full `index.html` from a set of `Markdown` files.

`yo reveal` could have done the trick, but its complexity failed me.

Beside, I don't want final result to be bloated with stupid Gruntfile.

### How?

#### Install

```sh
npm install -g prez
```

#### Initialize sample workspace

```sh
mkdir sandbox
cd sandbox

prez --init
```

This will create a full workspace with `js`, `images`, etc… where you'll put your custom content. In reality the only required folder is `slides`.

#### Build

```sh
prez
```

This will create a `build` folder with your slideshow.

#### Show

At this time, you must serve folder yourself. `lr-http-server` does the job well, with live-reload included.

```sh
npm install -g lr-http-server
cd build
lr-http-server
```

### TODO

* `prez --serve=8080`: Serve `build` folder (with live-reload?)
* `prez --watch`: Automatically rebuild when something changes in source folder
* `prez --print=output.pdf`: Print to `output.pdf` (should work with watch mode)
* `prez --print=output.pdf --with-notes`: Special mode where notes appear in final pdf
