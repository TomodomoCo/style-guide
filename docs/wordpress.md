# WordPress

For all WordPress projects, use the WordPress Core Coding Standards as a base, with the following exceptions and additions:

## JavaScript

JavaScript can be handled a few different ways.

### "Simple" Projects

For projects with…

+ no external JavaScript dependencies (excluding jQuery and jQuery plugins)
+ fewer than ~100 lines of JavaScript code
+ inline JavaScript (inside a `<script>` tag)

…follow the [WordPress Core JavaScript Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/).

For these projects, avoid transpiling and a compilation step.

### "Complex" Projects

For projects with…

+ external JavaScript dependencies (excluding jQuery and jQuery plugins)
+ more than ~100 lines of JavaScript code

…follow our [JavaScript standards](javascript.md).

Note that inline JavaScript should _always_ follow [WordPress Core JavaScript Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/).

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
