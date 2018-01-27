# Request Class

The Request class, seen at vendor/Luminance/Http/Request.php is responsible for handling all user and server input. It exposes the $_GET data, $_POST data, $_SERVER data, and $_FILES. They are accessed respectively like so:

```php
$this->request->query->{method}(); // GET data
$this->request->request->{method}(); // POST data
$this->request->files->{method}(); // FILES data
$this->request->server->{method}(); // SERVER data
```

The methods aforementioned all expose get/set methods, with default values available on get. Example:

```php
$username = $this->request->request->get('username', 'Guest'); // field, default
```

Methods exposed can be seen [here](https://github.com/luminancephp/framework/blob/master/vendor/Luminance/Http/Response.php)

**Note:** This documentation is a work in progress.