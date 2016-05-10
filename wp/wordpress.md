### Common wordpress theme  files 

- Index.php 
- Page.php 
- Functions.php
- style.css 
- single.php 
- header.php 
- footer.php 

### Linking and enqueueing stylesheets and javascript files 

```
function wp_theme_styles(){
	//stylesheets
	wp_enqueu_style('main_css', get_template_directory_uri().'/style.css');
	wp_enqueu_style('foundation_css', get_template_directory_uri().'/css/foundation.css');
} add_action('wp_enqueue_scripts','wp_theme_styles');

function wp_theme_js(){
	
	wp_enqueue_script('modernizer_js',get_template_directory_uri().'/js/modernizer.js','','',false); // false to load in header
	wp_enqueue_script('foundation_js',get_template_directory_uri().'/js/modernizer.js',array('jquery'),'',true); // true to load at footer
}add_action('wp_enqueue_scripts','wp_theme_js');


```

### using jquery in wordpress 

```
jQuery(document).ready(function($){
	
	$(".navbar-toggle").hide();
})
```

### TItle for page 

```
<?php wp_title(); ?>
```

### blog_info()

-Url 

```
<? php blog_info('url'); ?>
```

- Title 
```
<? php blog_info('name'); ?>
```

### The Loop 

```
<?php  if(have_posts() ) : while (have_posts() ) :  the_post(); ?>

		  //the content
<?php  endwhile; else:?>
        //throw error message
<?php endif; ?>

```

### wordpress content tags 

- Title 
```
<?php the_title() ; ?>
```

- The content 

``` 
<?php the_content(); ?>
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