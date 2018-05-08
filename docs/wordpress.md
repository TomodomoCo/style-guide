# WordPress

For all WordPress projects, use the WordPress Core Coding Standards as a base, with the following exceptions:

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

…follow our [JavaScript standards](javascript).

Note that inline JavaScript should _always_ follow [WordPress Core JavaScript Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/javascript/).
