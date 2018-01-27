## Our very first controller

Now that we've installed Luminance, we're ready to write a controller. Luminance comes with two methods for routing, the default is automagically, which means we will guess the controller name and method based off of the user supplied link.

Take this route for example: /HelloWorld/index

Our system will explode this link, and determine "HelloWorld" is a controller, and "index" is a method on the controller and call it accordingly. If this process does not succeed, it will render a 404 File Not Found error page.

### Writing our example controller

Out of the box, we already re-map the /example url to Test@examplePage. We'll create this Test controller now, and see the results of the re-mapped url.

Let's create a new file in app/Controllers, and name it Test.php - do note, the file name and class name must be an exact match for this system to work.

Let's put this inside our test controller, we'll define the examplePage method to print out "this came from Test controller":

```php
<?php
/**
 * This is our sample controller, made while learning Luminance
 *
 * @author Your Name <yourname@youremail.com>
 * @namespace Luminance\Controllers
 * @license MIT
 * @version 1.0.0
 * @package YOUR_APP_NAME
 */

namespace Controllers;

use Luminance\Controllers\BaseController;

class Test extends BaseController
{
    public function examplePage()
    {
        echo "this came from Test controller";
    }
}
```

Now, we can access this page one of two ways... the first, if we access the ```/example``` route, we will see this examplePage message, or, if we browse to ```/Test/examplePage``` it will also render the same result. The former is a pre-defined and named route, the latter is an automagic route.

