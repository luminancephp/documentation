## Installing Luminance

Luminance is designed for web developers and designers to get off the ground running, we've combined a ton of useful features such powerful HTTP routing, PSR4 autoloading, caching, and more.

### Requirements

In order to install Luminance, you need PHP 7.1 and a web server such as Apache. 

You need to rewrite all HTTP requests to /index.php/, as they will be picked up in the REQUEST_URI string, a default .htaccess file is provided for those using Apache2. Please ensure to enable mod_rewrite.

### Cloning from github

The only way to install right now, is to clone or download a compressed zip folder from github of the framework release. You can run the following command to clone from Github:

```shell
git clone https://github.com/luminancephp/framework.git
```

Or, if you prefer a zipped copy, you can download one here:

https://github.com/luminancephp/framework/archive/master.zip

Please extract the zip file into a folder, for this installation we call the folder **luminance**.

### Setting up your application configuration

Luminance comes with two application configuration files out of the box, they are located in the app/Configuration folder. One is an application configuration, one is a database configuration file. We'll now set these up with some variables, such as re-written routes, and application information. 

Start by opening app/Configuration/application.php, you should see something like this:

```php
<?php
/**
 * ------------------------------------------
 * - Default Application Configuration File -
 * ------------------------------------------
 *
 * This file defines a few important details,
 * namely the default routes, and additional
 * re-mapped URLs that will be picked up
 * by the router and routed as written
 * which will skip the automagic
 * routing by default
 */

return [
    /**
     * Application Name
     */
    "app_name" => "HelloWorld",
    /**
     * Base URL
     */
    "base_url" => "https://luminance.local/",
    /**
     * Default route
     *
     * @note This is used exclusively by the router
     */
    "default_route" => "HelloWorld/index",
    /**
     * Routes List
     *
     * @note This remaps the request URI's to
     * specific controllers, ie:
     *
     * "/example" => array(
     *  "controller" => "Test/examplePage"
     * )
     */
    "routes" => array(
        "/example" => array(
            "controller" => "Test/examplePage"
        )
    )
];
```

You'll notice we define an app_name, a base_url, and a default_route - the most important here is the default_route, it's what happens if we head to YourWebsite.com/ - the index page, we tell it what controller to route to, and what method to call. In this case, call controller "HelloWorld" and method "index".

Down in the routes list, we offer a convinent way for you to re-map URL addresses, for this example above, we have the route "YourWebsite.com/example" mapping to Test controller, and examplePage method. Right now the methods accept both GET, and POST. In your controller you must define restrictions by calling ```$this->request->is{Type}()```

### Setting up your database configuration

The database configuration file is straight forward, we request the DB_HOST, DB_NAME, DB_USER, DB_PASS, DB_ENABLED fields. If the DB_ENABLED is false, yet the configuration is filled out, the ORM table classes will not work as expected, as a connection object with PDO will never be created.

[Let's make a test controller](/our-first-controller.md)