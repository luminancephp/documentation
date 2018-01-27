# Template Parser Class

Luminance comes with a very basic and lightweight template parser for those who need to do some quick templating without a giant engine such as Twig by their side. This can be useful for most situations.

You can pass the template into the constructor, and replacements can be passed in constructor, in using ```setReplacements``` method.

Example:

```php
$template = new Luminance\Template\Parser("test_template", array("myname" => "Bob Smith"));
$template->render();
```

*Note:* Render can return data, by passing an optional boolean in it's function parameters, ie: ```$rendered_template = $template->render(true);```

Syntax used in template parser:

```
{{ VARIABLE_NAME }}
```

**Note:** Spaces are manditory for the basic parser between ```{{```, and variable name, then ```}}```

Methods exposed can be seen [here](https://github.com/luminancephp/framework/blob/master/vendor/Luminance/Template/Parser.php)

**Note:** This documentation is a work in progress.