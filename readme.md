
# Env

```sh
npm install -g jello
npm install -g fis-parser-less fis-parser-coffee-script fis-parser-jade fis-postprocessor-pleeease fis-prepackager-csswrapper fis-prepackager-ousiri-async-build
```

# Run

## on local server

```sh
cd src
jello server start
jello release -wL
```

## build to release

```sh
cd src
jello release -ompDd dist
```
# Features

- [Jade](http://jade-lang.com/) as HTML Template Engine. Support extend, include and mixin
- [Less](http://lesscss.org/) as CSS preprocessor, extend the css syntax
- [Pleeease](http://pleeease.io/) as CSS postprocessor, simplify the css file
- [CoffeeScript](http://coffeescript.org/) as Javascript compiler
- Full modularization
  - Writing JS in Node.js way
  - Autoload the CSS file when the JS file is loaded if they have the same name
  - Easy to lazyload JS module, Just use `require.async`
- CSS Sprite Supported
- Easy to integrate multiple frameworks

# Architecture
 
 - src - where to put soucecode
	 - page - where to put the business logic
		 - index - page Name. DIR
			 - img - images in this page
			 - index.jade - main file has the same name with dir
			 - index.inline.coffee - JavaScript that used to inline in the HTML
			 - index.coffee - main entrance
			 - index.less - main style sheet
			 - subIndex - you can even write modules here 
	 - static - files that loaded in plain script tag
		 - mod.js - module to handle file load
	 - widget
		 - common - widget name. DIR
			 - img - images in this widget
			 - common.coffee - widget main file
			 - common.less - widget main style sheet
			 - common.jade - widget template
			 - subWidget - sub-widget
 - dist - where to put the generated code

