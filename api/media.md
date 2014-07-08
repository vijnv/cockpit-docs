### API - Media


#### Thumbnails


Cockpit provides a handy function to generate thumbnails for you on the fly.


    $thumburl = cockpit("mediamanager")->thumbnail("path/To/Image.png", $width, $height);


Or use the shortcut function:

    $thumburl = thumbnail_url("path/To/Image.png", $width, $height);


##### Genrate thumbnail and echo image tag:

    <?php thumbnail("myimage.jpg", 200, 120);?>
