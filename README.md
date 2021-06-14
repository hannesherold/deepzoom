Deepzoom
==
This is a modified fork of [jeremytubbs/deepzoom](https://github.com/jeremytubbs/deepzoom), a tile Generator for use with [OpenSeadragon](https://openseadragon.github.io/). 
<br>
It supports automatic watermark insertion.

### Basic watermark support

To automatically add a watermark image to tiles, we use the `insert()` method of the Intervention Image library. 
<br>
Users can specify the image-file and the zoom-level from which on the watermark should be applied.
<br>
This alpha version was tested with imagick image library only.

### Example implementation 
```php
   require_once __DIR__ . '/vendor/autoload.php';

   $options = [
      'path'           => 'tiles',
      'format'         => 'jpg',
      'watermarkFile'  => 'watermark.png',
      'watermarkLevel' => 10,
   ];
   $source = 'images/test.jpg';
   $folder = null;
   $file = null;

   // Setup Deepzoom
   $deepzoom = Hherold\Deepzoom\DeepzoomFactory::create($options);

   // folder, file are optional and will default to filename
   $response = $deepzoom->makeTiles($source, $folder, $file);

```



___path___
<br>
The export path for tiles.
<br>
_required_

___format___
<br>
The export format for tiles. Watermark support was only tested with jpg files.
<br>
_Default: jpg_

___watermarkFile___
<br>
If you want the module to automatically add a watermark to the tiles, specify the file here. Transparent PNG works best. 
<br>
_Default: null_

___watermarkLevel___
<br>
Specify from which zoom-level on the watermark should be applied.
<br>
_Default: 10_

### Supported Image Libraries
Originally Deepzoom supports Imagick and gd. This module however is only tested with Imagick (>=6.5.7), which is therefore set default.

### FYI:
Filenames for JSONP must not start with a number and should not contain hyphen therefore filename spaces and hyphens will be converted to underscores. Folder name spaces will be converted to hyphens. If you would like to avoid this auto-naming declare your 'folder' and 'file' within the maketiles method. 

License
-------

MIT
