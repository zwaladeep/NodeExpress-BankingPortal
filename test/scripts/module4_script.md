In this module we will move all the data related code to a library that can be required in several files across the application.

To start, create a new file in the root of the src directory. Call this file data.js

Open data.js and require the builtin libraries fs and path.

Open app.js and locate the lines that read from the accounts.json file. Copy then and then move back to data.js and paste them below the require statements.

In app.js locate the lines that read from users.json and copy them to data.js below the accounts constant.

Below the users constant create a function called writeJSON.

In app.js find the lines that write the accounts object to a file. Copy these lines to the body of the writeJSON function in the data.js file.

Using module.exports export an object containing the constants accounts, users, and the writeJSON function.

Switch back to app.js require data.js. Use object destructing to create three constants for accounts, users, and writeJSON when requiring data.js. Remove the lines code that reads the accounts and users files they are now brought in by the require statement.

In the transfer post route replace the writefilesync and json.stringify lines with a call to the writeJSON function.

Finally, use the new writeJSON function.