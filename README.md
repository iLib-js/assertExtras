# assertExtras

Used to extend the assertion types available in nodeunit. To use, simply call:

```javascript
var assert = require("nodeunit/lib/assert");
require("assertextras")(assert);
```

At the top of you test suite, and it will monkey-patch the assertions in nodeunit
to add the following types of assertions:

- equalIgnoringOrder: compare the contents of arrays without regard to the order
of the array elements
- roughlyEqual: compare two numbers within a threshold amount. Used mostly for
floating point numbers to make sure they are close enough
- contains: make sure all the properties in the expected object also exist
in the actual object. The actual object may have more properties. The ones
in the expected object must exist, and anything else is optional.
