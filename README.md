Forked from: https://github.com/ckeditor/ckeditor5-build-classic

Here the ckeditor.js is modified with the **simple upload adapter**:

```javascript
import SimpleUploadAdapter from '@ckeditor/ckeditor5-upload/src/adapters/simpleuploadadapter';   

ClassicEditor.builtinPlugins = [ /* ... */, SimpleUploadAdapter];

// Editor configuration.
ClassicEditor.defaultConfig = {
	/*... */ ,
	simpleUpload: {
		uploadUrl: 'http://localhost:3001/upload'
	}
};

```
then I build the file with: `yarn run build`

After I build the bundle I included it in my project.

This repository contains a link to a sample node-js backend server which handles the image upload on localhost.

[CKEDITOR5-NodeJS-Image-Server](https://github.com/kolomu/ckeditor5-nodejs-image-server)
