Parchment
=========

Parchment is the Interactive Fiction player for the web. For more information see [our Google Code site](http://code.google.com/p/parchment). To play a story with it, go to <http://iplayif.com>!

Parchment is BSD licenced, but please help the community by sharing any changes you make with us.

Parchment for Inform 7
----------------------

[Inform 7](http://inform7.com/) includes Parchment, allowing you to produce [personal websites for your stories](http://inform7.com/learn/man/doc394.html). If you want to update the version of Parchment used by Inform 7, grab [parchment-for-inform7.zip](https://raw.github.com/curiousdannii/parchment/master/lib/parchment-for-inform7.zip) and unzip it into the Templates subfolder of your project's Materials folder.

Building Parchment
-----------------

We use [Node.js](http://nodejs.org/) and [Grunt](http://gruntjs.com/) to build and test Parchment. Install Node.js, and then install the grunt-cli package:

```
npm install -g grunt-cli
```

Then from the Parchment directory install our dependencies:

```
npm install
```

To build everything run the following:

```
grunt
```
How to include a story into single html file
-----------------
Create and serve from a webserver this html file:
```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Parchment</title>
	<script src="lib/jquery.min.js"></script>
	<script src="lib/parchment.debug.js"></script>
	<script src="lib/zvm.debug.js"></script>
	<link rel="stylesheet" href="lib/parchment.min.css">
	<meta name="viewport" content="width=device-width,user-scalable=no">
	<script>
		parchment_options = {
		    default_story: [ 'MYFILE.z5.js' ],
        storyData: '..base64 encoded content of the story..'
		};
	</script>
</head>
<body>
	<div id="about">
		<h1>Parchment</h1>
		<p>is an interpreter for Interactive Fiction. <a href="https://github.com/curiousdannii/parchment">Find out more.</a></p>
		<noscript><p>Parchment requires Javascript. Please enable it in your browser.</p></noscript>
	</div>
	<div id="parchment" aria-live="polite" aria-atomic="false" aria-relevant="additions"></div>
</body>
</html>
```
Verify the file is correctly loaded.
Install [inliner](https://github.com/remy/inliner) package:
```
npm install inliner
```
Launch it to create a single html file without dependencies to run the story:
```
./node_modules/.bin/inliner -m http://myserver/myfile.html > mystory.html
```
