### API - Cockpit.js

Sometimes you need to access content via Javascript / Ajax. Cockpit provides a simple js api for that.


<div class="uk-alert uk-alert-warning">
    Please generate an api token first in the cockpit settings (Settings > General > Api).
</div>


**Embed javascript api:**

Add the following snippet to your page:

    <head>
        ...
        <?php cockpit_js_lib() ?>
        ...
    </head>

Or define a script tag

    <head>
        ...
        <script src="/cockpit/index.php/rest/api.js?token={api_token}"></script>﻿
        ...
    </head>


Now you can request regions, collections and galleries;

    <script>

        // get region

        Cockpit.request('/regions/get/{regionname}').success(function(content){
            // update the dom with region content
        });

        // get gallery images
        Cockpit.request('/galleries/get/{galleryname}').success(function(images){
            // array of images
        });

        Cockpit.request('/collections/get/{collectionname}').success(function(items){
            // array of collection items
        });

    </script>

#### Direct REST calls

    GET /cockpit/index.php/rest/api/regions/get/{regionname}?token={yourtoken}

    GET /cockpit/index.php/rest/api/galleries/get/{galleryname}?token={yourtoken}

    GET /cockpit/index.php/rest/api/collections/get/{collectionname}?token={yourtoken}