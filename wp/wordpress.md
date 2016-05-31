### Common wordpress theme  files 

- Index.php 
- Page.php 
- Functions.php
- style.css 
- single.php 
- header.php 
- footer.php 
- archive.php

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

### calling the excerpt

```
<?php the_excerpt() ?>
```

```
<?php echo strip_tags(get_the_excerpt()); ?>
```
### the avatar

```
<?php echo get_avatar(get_the_author_meta('ID'), 24 //24 is the size) ?>
```

or 

```
<?php the_avatar() ?>

```
### the author 

```
<?php the_author() ?>
```
or getting author link 

```
<?php the_author_posts_link(); ?>
```

### The category 

```
<?php the_category();?>
```

```
<?php the_category(' , ');?>
```

### the date

```
<?php the_date(); ?>
```


```
<?php the_time('F j, Y'); ?>
```

### Featured image with post thumbnail 

```
<?php the_post_thumbnail('large'); //small,medium,large ?>
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

### simple wordpress pagination with next and previous

```
 <ul>
          <li> <?php previous_posts_link('<span class="fa fa-arrow-circle-left"> </span>'); ?> </li>

          <li> <?php next_posts_link('<span class="fa fa-arrow-circle-right"> </span>'); ?> </li>
  </ul>
```

### comments

example

```
<?php comments_template( $file, $separate_comments); ?>

//or 

<?php comments_template(); ?>

```

- custom comment -> comments.php 

### Archives archive.php 

similar to home 

### Wp_query

```

$num_posts = (is_front_page() ) ? 4 : -1;

$args= array(
     'post_type' => 'portfolio',
     'post_per_page'=> $num_posts
);

$query = new wp_query( $args );
?>


<?php if ($query -> have_posts()) : while( $query->have_posts()) : $query -> the_post(); ?>

  //


<?php endwhile; endif; wp_reset_postdata(); ?>

```


### Custom post type with andvanced custom fields and custom post time UI

After installing those 2 plugins, to retrieve the data in the fields.

```
<?php the_field('description') ?>

```

## WP Customizer API


### Settings

wordpress settings are save in the customizer using the following code 

```
//adding settings 
$wp_customize -> add_setting();


//geting settings 

$wp_customize -> get_setting();

```

### Controler 

the controler shows the result of the setting. it's the actual html element 

- text controler 
- color controler 
- image controler 
- upload controler 


```
// adding controler 
$wp_customize -> add_control(  class );

```

### Sections and Panels

Sections are the different areas of the theme customizer  and a panel is a group of sections

```
//adding section 
$wp_customize -> add_section();
```

### Transport 

Parameter for setting and determine how message should be displayed

- Refresh (need page refresh)
- Post (updates live)


```
$wp_customize -> add_setting( class, array(
        'transport'-> 'Refresh'
    
))

``` 

### Customizer function 

``` function koofi_theme_customizer($wp_customize){

//customizing title and tagline section and lagels

$wp_customize->get_section('title_tagline')->title = __('Site Name and Description', 'koofi');
$wp_customize->get_control('blogname')->label=__('Site Name','koofi');
$wp_customize->get_control('blogdescription')->label=__('Site Description','koofi');
$wp_customize->get_setting('blogname')->transport='postMessage';
$wp_customize->get_control('blogdescription')->transport ='postMessage';

    
}add_action('customize_register','koofi_theme_customizer');

```


### Hack to make image responsive 

```
if(has_post_thumbnail()) {                    
    $image_src = wp_get_attachment_image_src( get_post_thumbnail_id(),'full' );
     echo '<img src="' . $image_src[0]  . '" width="100%"  />';
} 
```
