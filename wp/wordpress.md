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