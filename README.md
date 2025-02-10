# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input parameters. Specifically, this example shows a route that fetches a user by ID, but fails to handle cases where the ID is not a valid number.

## Bug

The `bug.js` file contains the faulty code.  It attempts to parse the user ID as an integer without any checks. If the ID is not a number (e.g., a string or undefined), `parseInt()` will return `NaN`, causing the `users.find()` method to fail silently or throw an error depending on the implementation of the `users` array. This may lead to unexpected behavior or server crashes.

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It includes input validation to ensure the `userId` is a valid number before attempting to use it.  If the ID is invalid, it returns a 400 Bad Request response to inform the client about the error.

This solution showcases the importance of robust input validation and error handling to build reliable and secure web applications.