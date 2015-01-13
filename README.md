ezdz-multiple
=============

jQuery File Input plugin ezdz multiple files and grid preview

It is based on Ezdz jQuery File Input plugin. new features have been added as follows.
  1. support multiple file upload.
  2. support grid preview of image.

All other settings pls refer to ezdz documentation https://github.com/jaysalvat/ezdz

index.html file demostrates multiple file upload features and preview of image features.

remember add `multiple` attribute to input tag.

Sample Usage
=============

in the html head section

```html
<link rel="stylesheet" href="src/jquery.ezdz.css">
<script type="text/javascript" src= "node_modules/jquery/dist/jquery.min.js"></script>
<script src="src/jquery.ezdz.js"></script>
```

in the body section, simply add normal input tag, the plugin will automatically convert it into dropzone.

```html
<input type="file" name="file_upload[]" accept="image/png, image/jpeg" multiple/>  
```

add javascript pointing to input tag, add customize configuration.

```javascript
$('input[type="file"]').ezdz({
    			text: 'drop cover photos',
	            validators: {
	                maxWidth:  2000,
	                maxHeight: 2000,
	                maxNumber: 6
	            },
	            reject: function(file, errors) {
	                if (errors.mimeType) {
	                    alert(file.name + ' must be an image.');
	                    return;
	                }

	                if (errors.maxWidth) {
	                    alert(file.name + ' must be width:2000px max.');
	                    return;
	                }

	                if (errors.maxHeight) {
	                    alert(file.name + ' must be height:2000px max.');
	                    return;
	                }

	                if (errors.maxNumber) {
		                alert('you can upload maximum of 6 images');
		                return;
	                }
	            }
    	});
```

if you looking for modify preview image grid, editing `jquery.ezdz.css`, for example, the code represent 3 columns grid.

```css
.image-g li {
	float: left;
	max-width: 32%;
	max-height: 48%;
	padding: 0.10em;
}
				
.image-g li:nth-child(3n+1) {
	clear: left;
}
```

Release Note
=============
  
  v0.4.2 the repository update to mirror ezdz 0.4.2
 
  v0.4.2 add example to Ezdz plugin
  
License
=============

The MIT License (MIT)
