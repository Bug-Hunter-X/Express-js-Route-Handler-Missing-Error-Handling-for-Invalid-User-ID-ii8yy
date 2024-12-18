# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the example shows a route that retrieves a user by ID.  If the ID is not a valid number, the application will crash.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides a corrected version with appropriate error handling.

## Bug

The primary issue is the lack of error handling when parsing the user ID.  If the `req.params.id` is not a valid number, `parseInt(userId)` will return `NaN`, causing the `users.find` method to fail silently or throw an error depending on the implementation details. 

## Solution

The solution involves adding error handling to check if the parsed ID is a number and returning an appropriate error response if it's not.