ConsoleBundle
=============

This bundle allows you accessing the Symfony2 console via your browser.

Features
--------

 * Colored output
 * Autocompletion for command names
 * Local command history (localStorage)
 * ```cache:clear``` works

Installation
------------

0. Make sure you have php 5.5 or newer installed. Make sure your composer file does not override the required php version of your project with in older one via the `config.plattform.php` setting.

1. Add to composer repository

    ```json
   "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/saif-88/ConsoleBundle"
        }
    ]
   ```
   
2. Install the latest version via composer:

	```sh
	composer require coresphere/console-bundle:0.6.0
	```

   3. Register the bundle in you AppKernel in the development section

        ```php
       // config/bundle.php
       return [
       	...
       	CoreSphere\ConsoleBundle\CoreSphereConsoleBundle::class => ['dev' => true],
       ];

       ```

4. Add the bundle's route to your app/config/routing_dev.yml

	```yaml
	# config/routes/coresphere_console.yml

	# ...
	when@dev:
    coresphere_console:
        resource: '@CoreSphereConsoleBundle/Resources/config/routing.yml'

	```


5. run the assets:install command to install the css and js files

	```sh
	./bin/console assets:install
	```

Tips
----

 * Type ```.clear``` to clear the console window

Preview
-------

<img src="http://static.laszlokorte.de/github/coresphere_console.png" width="900" alt="Screenshot" />

Dependencies
------------

 * jQuery
 * Twig

Compatibility
-------------

Tested with:

 * Chrome
 * Firefox 4
 * Opera 11
 * Safari 5
