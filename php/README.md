# PHP

All code should follow [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) with the below modifications.

PHP 7.1 is the minimum supported PHP version for all _new_ projects.

## Modifications

We have a few changes from the standard PSR-2 format:

+ Lines may be up to 100 characters long
+ Always use short array syntax (`[]`), _never_ long array syntax (`array()`) unless required for PHP version compatibility

## WordPress Rules

In a WordPress context, there are a few additional rules:

+ When defined procedurally (outside of a class), `add_action` and `add_filter` should always be called immediately _after_ the function they call is defined, with an empty line between the closing `}` and the hook function call
+ Hooks (`do_action` or `apply_filters`) should be named in the format `FullNamespace\(functionName\)?hookName` using the current file's namespace, the name of the function call containing the hook (when the hook is called from within a function), and a descriptive camelCased hook name
+ Hooks should be documented with a phpdoc docblock that describes the purpose of the hook, available parameters, and the return type (for filters)

## Additional Recommendations

We also make the following recommendations and suggestions:

+ When your return type is `void`, the function should explicitly call `return;`. Never omit a `return`. (The only exception is for cases where the code calls `exit`; we consider that stylistically equivalent to `return`.)
+ Inline documentation is always encouraged.
+ Ternaries are cool, but keep them small. If you need more than ~40 characters, a standard conditional block may be easier to read.
+ When possible, we love the null coalescing operator.
