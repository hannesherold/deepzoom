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

This library is licensed under the [MIT] license.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[MIT]: https://spdx.org/licenses/MIT.html
