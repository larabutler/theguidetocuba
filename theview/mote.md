Mote
====

Mote is a fast template engine that allows us to put Ruby code into any
plain text document, like HTML.

A very simple example is this:

```ruby
require "mote"

template = Mote.parse("The value of pi is {{ Math::PI }}")
template.call
# => The value of pi is 3.141592653589793
```

Mote can recognize two tags to evaluate Ruby code: `%` and `{{}}`. The
difference between them is that the latter prints the result in the
template.

```
% # This is a comment.
% x = 2
% y = 1
<p>The value of x is {{ x }}</p>
<p>The value of x is {{ y }}</p>
<p>The sum of x and y is {{ x + y }}</p>
```

Following the above example, the result will be this:

```html
<p>The value of x is 2</p>
<p>The value of x is 1</p>
<p>The sum of x and y is 3</p>
```