Forked from: https://github.com/ckeditor/ckeditor5-build-classic

Here the ckeditor.js is modified with the **simple upload adapter**:

Below are the modifications of the src/ckeditor.js file which were made by me:

```javascript
import SimpleUploadAdapter from '@ckeditor/ckeditor5-upload/src/adapters/simpleuploadadapter';   
// for image resizing
import ImageResize from '@ckeditor/ckeditor5-image/src/imageresize';

ClassicEditor.builtinPlugins = [ /* ... */, 
SimpleUploadAdapter,
ImageResize
];

// Editor configuration.
ClassicEditor.defaultConfig = {
	/*... */ ,
	simpleUpload: {
		uploadUrl: 'http://localhost:3001/upload'
	},
	/* for image positioning */
		image: {
		toolbar: [
			'imageTextAlternative',
			'|',
			'imageStyle:alignLeft',
			'imageStyle:full',
			'imageStyle:alignRight',
		],
		styles: [
			'full',
			'alignLeft',
			'alignRight'
		]
	},

};

```
then build the file with: `yarn run build`

After the bundle is created, include it in your project.

This repository contains a link to a sample node-js backend server which handles the image upload on localhost.

[CKEDITOR5-NodeJS-Image-Server](https://github.com/kolomu/ckeditor5-nodejs-image-server)
