# General PHP Recommendations

These recommendations apply to both [WordPress](wordpress.md) and [Non-WordPress](php.md) PHP projects.

## Documentation

With a number of folks shifting in and out of projects, inline documentation is critical to help future team members understand the code we write.

### Docblocks

All functions and methods should have an associated docblock. For functions that don't return anything, use `void` as your return type in the docblock for clarity (even if you are not using the actual PHP 7.1 [void return type](http://php.net/manual/en/migration71.new-features.php#migration71.new-features.void-functions)).

### Inline comments

Inline comments are strongly encouraged. **Almost every function can benefit from at least one inline comment.** Unless it is explicitly clear what is happening (due to well-named functions, because the function is a simple wrapper, etc.) you will help future generations by including inline comments.

Including links (to Stack Overflow, blog posts about a particular coding decision, /r/PHP threads, etc.) are strongly encouraged as well.

## Arrays

Always use short array syntax (`[]` over `array()`) unless you need to write something for PHP 5.3, for some strange reason.

## Ternary Operators

While they shouldn't be entirely avoided, think twice before using a ternary operator, especially as the complexity/length of your conditional increases.

A good rule of thumb is that if you need more than ~50 characters, or multiple lines, you are probably better using a standard conditional block.

Here's an example of a ternary designed to turn an array into comma-separated list of items, with an "and" (and an Oxford comma) before the last item. It's a little difficult to read because…

1. It spans multiple lines
2. It nests ternaries
3. It mixes in several function calls along the way, impacting readability

```php
$message = count( $items )
	? implode( ', ', $items ) . ( count( $items ) >= 2 ? ',' : '' ) . ' and ' . $last_item
	: $last_item;
```

While more verbose, the following is easier to read, especially for new developers:

```php
$message = '';

if ( count( $items ) ) {
	// Initial word(s)
	$message .= implode( ', ', $items );

	// Maybe add an Oxford comma
	$message .= count( $items ) >= 2 ? ',' : '';

	// add that "and"
	$message .= ' and ';
}

// Always add the last item
$message .= $last_item;
```

This is easier to read because the discrete parts are separated, and also because this separation makes it easier to step through the various actions with inline comments.

## Null Coalescing Operator

Use of the null coalescing operator is almost always encouraged, but avoid other actions on the same line.
