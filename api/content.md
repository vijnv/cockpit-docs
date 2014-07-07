### API - Content


Let's access the content we manage in the Cockpit backend:

#### Regions

Render your regions at any position on your site:

    <?php echo cockpit("regions")->render(regionname); ?>

Or use the shortcut function:

    <?php region(regionname);?>


<hr>

#### Collections


To get the items of any collection you can use the following commands:


    <?php $items = cockpit("collections")->collection(collectionname)->find()->toArray(); ?>

Shortcut version:

    <?php $items = collection(collectionname)->find()->toArray(); ?>

You can also filter items:

    <?php $items = collection("posts")->find(["public"=>true])->sort(["created"=>1])->toArray(); ?>

Filter via callback

    <?php 
      $items = collection("posts")->find(function($post){
        return ($post["public"] === true && preg_match('/anyquery/i', $post["title"]));
      })->toArray();
    ?>

Pagination
  
    <?php $items = collection("posts")->find()->limit(10)->skip(10)->toArray(); ?>

Loop through collection:

    <?php foreach(collection("posts")->find() as $item): ?>
       <div>
           <?php echo $item["title"];?>
       </div>
    <?php endforeach;?>

Just one item

    <?php $item = collection("posts")->findOne(["title"=>"Hello world!"]); ?>