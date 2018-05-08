# WordPress

For all WordPress projects, use the WordPress Core Coding Standards as a base, with the following exceptions and additions:

## JavaScript

JavaScript can be handled a few different ways.

For inline JavaScript and linked JavaScript that will not be going through a build step, follow the [WordPress Core JavaScript Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/).

For JavaScript that will go through a build step, follow our [JavaScript standards](javascript.md).

## Hooks & Filters

When writing procedural (non-OOP) code, functions should be defined above the hook call, with an empty line separating the two.

```php
/**
 * This is a phpdoc

 * @return void
 */
function my_function() {
	// Does stuff
}

add_action( 'hook_name', 'my_function' );
```

## Documentation

All functions and methods should have an associated docblock. For functions that don't return anything, use `void` as your return type in the docblock for clarity (even if you are not using the actual PHP 7.1 [void return type](http://php.net/manual/en/migration71.new-features.php#migration71.new-features.void-functions)).
