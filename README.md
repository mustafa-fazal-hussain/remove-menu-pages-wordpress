# remove-menu-pages-wordpress
Remove menu pages from WordPress dashboard sidebar user role based.
if you don't want to show wordpress dashboard menu page to users other then administrator then use this code 

# past the below code in your theme function.php file 

function remove_my_menu_pages() {

	global $user_ID;
	
  // You can also use this code for differerent user's role like editor contributor just replace administrator with your desire one. 
  
	if (!current_user_can( 'administrator' ) ) 
	{
	
		remove_menu_page( 'edit.php' );                  //Posts
		remove_menu_page( 'upload.php' );                //Media
		remove_menu_page( 'edit.php?post_type=page' );   //Pages
		remove_menu_page( 'edit-comments.php' );         //Comments
		remove_menu_page( 'themes.php' );                //Appearance
		remove_menu_page( 'plugins.php' );               //Plugins
		remove_menu_page( 'users.php' );                 //Users
		remove_menu_page( 'tools.php' );                 //Tools
		remove_menu_page( 'options-general.php' );       //Settings
		remove_menu_page( 'widgets.php' );		 //Widgets
		remove_menu_page('revslider');			//Revolution Slider	
		remove_menu_page('wpcf7');	                //Contact Form 7
		remove_menu_page('admin.php?page=CF7DBPluginSubmissions' ); //Contact Form 7 CFDB
 
		
	}
		
add_action( 'admin_menu', 'remove_my_menu_pages' );
