# plugin-in-wordpress
Wordpress Plugin with Composer, React and OOP PHP

### Project setup
- Created a `composer.json` file, put valid `json` content then run the following
> `composer install`


### Install WordPress with Composer

Using [A Webroot Composer Library Installer](https://github.com/fancyguy/webroot-installer)

> The last two lines copied mean the following :-
> This would install the defined wordpress/wordpress package in the wordpress directory of the project.

- Add all the `json` from the above link into `composer.json` file.

- Run `composer install` 

- Run `composer update` incase there's already infor in the `composer.json` file.


- Reference [Giving Wordpress its Own Directory](codex.wordpress.org/Giving_Wordpress_Its_Own_Directory)
  
> Your root wordpress folder won't have `wp-content` folder that contains `plugins` and `themes`.

> ` Do the following command and edit some files `.

- Copy `index.php` and `wp-config-sample.php` files from the `wordpress` folder and put them on the root
> `cp wordpress/index.php  wordpress/wp-config-sample.php  .`

- Edit both these files
  - index.php
> last line `require('./wordpress/wp-blog-header.php')`, add wordpress to the path. It shows we're loading it from the subdirectory.

- Move `wp-config-sample.php` into `wp-config.php`
> `mv wp-config-sample.php  wp-config.php`

- Edit `wp-config.php`
> `vim wp-config.php`
  - Set the /**Absolute path to the Wordpress directory */ as `'/wordpress/'`
  - and save these files

- Copy `wp-content` folder from the wordpress folder into the roo( `.` in the commands is the `root`)
> `cp -R wordpress/wp-content . `

### Set the wp Skeleton
[wp Skeleton](https://github.com/markjaquith/WordPress-Skeleton)
- Go to the above link, copy 2 lines from his  `wp-config.php` (under the //== custom content directory ==)
- Paste these lines in the wp-config.php after database specification
> define( 'WP_CONTENT_DIR', dirname( __FILE__) . '/wp-content' );
> define( 'WP_CONTENT_URL', 'HTTP://' . $_SERVER['HTTP_HOST'] . '/wp-content' );  

### Files managed by the composer are put in .gitignore