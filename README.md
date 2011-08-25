# node-imageinfo

This is a small package for node.js to allow the analysis of image data in a Buffer, and return mime-type, and image dimensions for the data.

It is designed to be fast, completely written in javascript and have no dependencies on external packages or libraries.

Currently it supports Png, Jpeg, Gif and Swf analysis.

## Usage:

	var imageinfo = require('imageinfo'),
		fs = require('fs');

	fs.readFile('testimage', function(err, data) {
		if (err) throw err;

		info = imageinfo(data);
		console.log("Data is type:", info.mimeType);
		console.log("  Size:", data.length, "bytes");
		console.log("  Dimensions:", info.width, "x", info.height);
	});

