erdiko-wordpress
================

Run WordPress headless

You can use this module with any composer based php framework.


Installation
------------

* Install wordpress in /lib/wordpress folder

* Add the erdiko-wordpress package using composer

	composer require erdiko/wordpress 0.1.*

These additional instructions work for Erdiko, Laravel and certain other frameworks. You would need to modify slightly if you are using another framework.  If you don't care about media uploads you could ignore this alltogether.

* Add a symlink for the uploaded files

	mkdir -p public/wp-content
	cd public/wp-content
	ln -s ../../../lib/wordpress/wp-content/uploads uploads


Erdiko Demo
-----------

If you are using this module with Erdiko, add the following lines to route.json to enable the wordpress controller:

```
"/wordpress/": "\erdiko\wordpress\controllers\Example",
"/wordpress/:alpha": "\erdiko\wordpress\controllers\Content",
"/wordpress\/([a-z0-9 \-]+)\/([a-z0-9 \-\/]+)": "\erdiko\wordpress\controllers\Content"
```

You may also add the following lines if you want the wordpress controller to be the base url:

```
"/": "\erdiko\wordpress\controllers\Example",
"/:alpha": "\erdiko\wordpress\controllers\Content",
"/\/([a-z0-9 \-]+)\/([a-z0-9 \-\/]+)": "\erdiko\wordpress\controllers\Content"
```

Views in this module use relative url to implement routes. You would need to modify route.json and url in views if you would like to use your own url.

Themes
-----------
Themes include all supporting javascript and css files.

To create a carousel/slider for your wordpress image gallery, use:
css/slick.css
css/slick-theme.css
css/fonts
css/slickstyle.css
js/slick.min.js
js/slickstyle.js

To create a videoplaylist/audioplaylist for your wordpress video/audio, use:
js/audioplaylist.js
js/videoplaylist.js


