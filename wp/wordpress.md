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

 ### Wordpress theme support function 

 ```
 function theme_support(){
		add_theme_support('title-tag');
		add_theme_support('automatic-feed-links');
		add_theme_support('menus');
    add_theme_support('post-thumbnails');
  add_image_size('featured-image',500,315,false);

} add_action('after_setup_theme','theme_support');

```

### wordpress widget creation

```
function theme_widgets_init(){

      register_sidebar( array(
          'name' => __( 'Seul Widget', 'Seul' ),
          'id' => 'widget-1',
    'before_widget'=>'<div class="main-widgets">',
        'after_widget'=>'</div>',

        'before_title'=>'<h1 class="widget-title">',
        'after_title'=>'</h1>'
      ) );


      }

  add_action( 'widgets_init', 'theme_widgets_init' );

  ```

  ### wp excerpt 

  ```
  function new_excerpt_length($length){
  return 60;
}
add_filter( 'excerpt_length', 'new_excerpt_length',999);

    function new_excerpt_more( $more ) {
  return '<br><br> <a class="read-more" href="'. get_permalink( get_the_ID() ) . '">' . __(' <span class="fa fa-arrow-circle-right"></span> Read More', 'your-text-domain') . '</a>';
}
add_filter( 'excerpt_more', 'new_excerpt_more' );

```

### Creating custom page template

```
<?php 
/*
Template Name: Left Sidebar 

*/
```
### Wordpress navigation 

wp_nav_menu()

- Add theme support for menus in function.php
```
add_theme_support('menus');
``

- now calling the navigation in the location we want 
```
<?php
$args = array(
'container'=> false, // container
'theme_location'=>'primary-menu', // location
'menu-class'=>'no-bullet' // class givent to ul);
 
 wp_nav_menu($args); ?>

```

- lets create the menu function in the functions file 

```
function register_theme_menus(){
  register_nav_menus(
  array(
     'primary-menu' =>__('Primary Menu'),
     'social-networks' =>__('social Links')
  )

  );
}add_action('init','register_theme_menus');
```