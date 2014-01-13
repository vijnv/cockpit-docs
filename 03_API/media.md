### API - Media


#### Thumbnails


Cockpit provides a handy function to generate thumbnails for you on the fly.


    cockpit("mediamanager")->thumbnail("path/To/Image.png", $width, $height);

Or use the shortcut function:

    thumbnail("path/To/Image.png", $width, $height);

##### Usage:

    <?php thumbnail("myimage.jpg", 200, 120);?>
