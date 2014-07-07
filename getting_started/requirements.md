### Cockpit requirements

- PHP >= 5.4
- PDO with SQLite support ( or MongoDB )
- GD extension enabled

<hr>

<span class="uk-badge">And that's it.</span> No database server is required. No generation or build scripts, no heavyweight PHP libraries or dependencies.
Cockpit was succesfully tested on Apache. Nginx, or whatever web server you choose should also work out of the box.


<div class="uk-alert">
    <strong><i class="uk-icon-lightbulb"></i> Tip</strong>
    <br><br>
    To quickly check if your server passes the requirements, just create a file on your server with the following content:
</div>

    <?php

    try {
        if((version_compare(PHP_VERSION, '5.4.0') >= 0) && extension_loaded('pdo')) {
            $test = new PDO('sqlite::memory:');
            echo "Congratulations! Your server pass the Cockpit requirements. ";
        } else {
            throw new Exception("PDO with SQLite support is missing");
        }
    } catch(Exception $e) {
        echo "Sorry, your server doesn't pass the Cockpit requirements.";
    }
