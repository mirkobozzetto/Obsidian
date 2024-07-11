Tag:  #daily #wordpress #back-end #php 

## Fichiers obligatoire dans le dossier du nom du theme 

```
index.php 
function.php 
header.php
footer.php
screenshot.png 
style.css
```

et dans le style.css ceci est obligatoire

```css
/*

Theme Name: Twenty Twenty-Four

Theme URI: 

Author URI: 

Description: 

License URI: 

Text Domain: 

Tags: 

*/
```

dans le fichier index.php
```php
<?php

get_header();

get_template_part('loop');

get_footer();

?>
```
cela va permettre appeler les fichier header, footer etc...

va jeter un coup d oeil sur ce site:

https://medium.com/@doublekien/create-a-custom-theme-for-wordpress-c9869f4a1bd5

