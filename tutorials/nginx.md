### Nginx setup


Just add the following rules to your server config:

````

# Change "cockpit" to the folder name containing cockpit files.

location /cockpit {
     try_files $uri $uri/ /cockpit/index.php;
}

location ~ .sqlite$ {
    deny all;
}
````