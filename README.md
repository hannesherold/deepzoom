Deepzoom
==
Tile Generator for use with OpenSeadragon.

https://openseadragon.github.io/

### Watermark support (alpha version) 

Makes use of `insert()` method of Intervention Image library to add a watermark image to tiles. 
User can specify the image-file and the zoom-level at which the watermark should be applied.

#### Example implementation 
```php
   require_once __DIR__ . '/vendor/autoload.php';

   $options = [
      'path'           => 'tiles',           // Export path for tiles
      'driver'         => 'imagick',         // Choose between gd and imagick support. Default: gd
      'format'         => 'jpg',             // Default: JPG
      'watermarkFile'  => 'watermark.png',   // Default: null
      'watermarkLevel' => 7,                 // Default: 7 (level 0 = zoom level 0)
   ];
   $source = 'images/test.jpg';
   $folder = null;
   $file = null;

   // Setup Deepzoom
   $deepzoom = Jeremytubbs\Deepzoom\DeepzoomFactory::create($options);

   // folder, file are optional and will default to filename
   $response = $deepzoom->makeTiles($source, $folder, $file);

```


### Supported Image Libraries
- GD Library (>=2.0)
- Imagick PHP extension (>=6.5.7)

### FYI:
Filenames for JSONP must not start with a number and should not contain hyphen therefore filename spaces and hyphens will be converted to underscores. Folder name spaces will be converted to hyphens. If you would like to avoid this auto-naming declare your 'folder' and 'file' within the maketiles method. 

License
-------

MIT
