<h1>Fixing laravel 403 stuff</h1>

```
Create and put this .htaccess file in your laravel installation folder.

<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{REQUEST_URI} !^public
    RewriteRule ^(.*)$ public/$1 [L]
</IfModule>
```

<h4>Making writing files to folders accessible</h4>
```
#now, change the owner of the project directory to www-data using the following command:


sudo chown -R www-data:www-data /var/www/path/to/your/project/
```

<h3>After installing the app  </h3>
ever set a directory to 777. you should change directory ownership. so set your current user that you are logged in with as owner and the webserver user (www-data, apache, ...) as the group. You can try this:
```
sudo chown -R $USER:www-data storage
sudo chown -R $USER:www-data bootstrap/cache
```

then to set directory permission try this:

```
chmod -R 775 storage
chmod -R 775 bootstrap/cache
```
