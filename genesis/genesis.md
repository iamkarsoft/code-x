### Creating the theme folder

- Create a folder

-- Create a style.css

--- Style theme header
--- Theme name
--- Theme URi
--- Author name and URI
--- Template: genesis
--- Version
--- License and License URI
--- Tags
--- Text Domain: Embriyon

- Functions.php

--Theme customization doc block
``` /***@package theme-name
*@author Karsof
*@link http://kofi.work
*@copyright
*@GPL-2.0
**/```

- Initializing Genesis framework

``` //Loading text domain function
load_child_theme_textdomain('embriyon');
//Hook into genesis
add_action('genesis_setup','embriyon_setup', 15)

//Creating our setup function
Function embriyon_setup(){


}

//Description for adding site functionality

/**
*Theme setup
*attach all of site-wide functions
*
*@since 1.0.0
*/ put this above setup function```

### Page

#### Front-page.php

- Doc-block

- Call genesis function

``` genesis(); //Call it in all the pages
//Defining some constant in the child theme to referene later
//define them constant in function
define('CHILD_THEME_NAME','embriyon');
define('CHILD_THEME_URL','http://embriyon.com');
define('CHILD_THEME_VERSION','1.0.0');

//Add themes support from genesis folder(html5, genesis-responsive-viewport,genesis-accessibility)
//Add theme support for footer widgets
add_theme_support('genesis-footer-widgets',3);

//Removing Layout
genesis_unregister_layout('content-sidebar-sidebar'); //i.e
unregister_sidebar('');

//Creating widget areas in function or in another file
genesis_register_sidebar(array(
'id'=>'home-welcome',
'name'=>__('home welcome'),
'description'=>__('This is a home widget area that will show on the front page','embriyon');```








