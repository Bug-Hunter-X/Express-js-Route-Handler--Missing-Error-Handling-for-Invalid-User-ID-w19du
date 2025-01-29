# Express.js Route Handler: Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The example shows a route that fetches a user by ID.  If the ID is not a valid number, the code crashes without providing an informative error message.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version with improved error handling.

## Bug
The original code fails to handle cases where `req.params.id` is not a valid integer.  Attempting to parse a non-numeric string with `parseInt()` will not throw an error, but it will result in `NaN`.  Subsequently, the `find` method will not locate the user, resulting in an implicit failure, which is not a robust behavior.