# WordPress

For all WordPress projects, use the WordPress Core Coding Standards as a base, with the following exceptions and additions:

## PHP Version

For all public/open source projects, PHP 5.6 is the lowest version we support. Internally, use aim for PHP 7.1 if possible, falling back to 7.0 and 5.6 as appropriate.

## JavaScript

For inline JavaScript and linked JavaScript that _isn't_ going through a build step, follow the [WordPress Core JavaScript Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/).

For JavaScript that _will_ go through a build step, follow our [JavaScript standards](javascript.md).

## Hooks & Filters

When writing procedural (non-OOP) code, functions should be defined above the hook call, with an empty line separating the two.

```php
/**
 * This is a phpdoc
 *
 * @return void
 */
function my_function() {
	// Does stuff
}

add_action( 'hook_name', 'my_function' );
```
