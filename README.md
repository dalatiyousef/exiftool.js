exiftool.js
===========

A pure javascript implementation of exiftool.

This extends the great work started by [Jacob Seidelin](http://www.nihilogic.dk/labs/exifjquery/)


Usage
=====

Use jQuery:

```js
$(this).getExifFromUrl(url, function(exif) {
    console.log("Make is : " + exif["Make"]);
});

```

Or you can read from a local file (like drag and drop)

```js
var binaryReader = new FileReader();
binaryReader.onloadend = function() {
    var exif = $(this).findEXIFinJPEG(binaryReader.result);
    console.log("Make is : " + exif["Make"]);
}
binaryReader.readAsBinaryString(file);

```


Coverage
========

You can view exactly how the results from this library fair verses the perl library against images from 5,000 different camera models here:
[Coverage report](http://mattburns.github.io/exiftool.js/report/)

I see no reason why this library can't match (and exceed!) the parsing capabilities of the orginal perl library but I need your help. Please fork this repo, create pull request and issue, whatever. You can just play with making improvements to the code so that the coverage goes up. It's easy to see how much your changes are improving this thanks to the coverage report above. To regenerate this simply run:

```sh
node testWithNode.js
```

This will thrash every sample image through the perl exiftool and also through exiftool.js then generate the report files to compare the output.
