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

# Release Notes

v1.1.0

Added updated assert.deepEqual. The old deepEqual would throw 
exceptions if one of the two objects passed in were undefined or null.
The part of object equality checking which checks if the objects are
primitives would dereference the objects to call their valueOf()
methods. Of course, you can't dereference undefined or null, so the
exception would get thrown.
