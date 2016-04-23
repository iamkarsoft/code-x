
### Modular Mobile First 

### Folder Structure
- Index.php
- Single.php
- Page.php
- Header.php
- Footer.php
- Content.php
- Sidebar.php
- archive.php
- search.php
- 404.php
- inc/
- layouts/
- js/
- template-parts/
- languages/

### Template hiearachy
- i.e Singular.php > Single-post.php or single.php > index.php

### plugins
- Show Current Template

### Styling 
- Elements
- ALignment
- Screen reader

### FUnctions


###  Device width
- 360px

### Media queries
 ```
 @media-screen and (min-width: 40 em){

 	.site-main{
 		max-width:40px;
 		margin: 1.8em auto;
 	}
 }
 ```

 ### Header

 ```
 .site-header{
 }

 .site-branding{
 }

 .site-title{

 }
 ```

 ### adding header image to template
 ```
 <?php if(get_header_image() ) :?>
 	<a href="<?php ech esc_url(home_url('/')) ;?>" rel ="Home">
		<img src="<?php header_image(); ?>" width="<?ph echo esc_attr(get_header_image()) ?>" />	
 	</a>
 <?php endif; ?>
 ```

 ### registering menus
 ```
 register_nav_menus(
	'primary'=>esc_html__('Primary Menu','embriyon'),
	// adding additional menus
	'secondary'=> esc_html__('Secondary Menu', 'embriyon')
 )
 ```

 ### placing menu into theme
 ```
 <?php wp_nav_menu( array(
	'theme_location'=>'Primary Menu', 'menu_id'=>'primary-menu', menu_class=> 'nav-menu'
 )) 