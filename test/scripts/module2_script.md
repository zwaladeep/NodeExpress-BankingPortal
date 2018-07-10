In this module we will read the contents of two files and then display information from these files across 4 get routes.
Above the default get route lets read the contents of the accounts.json file and store it in a constant called accountData. **opt+1**
The readfilesync accepts two arguments the absolute path to the file and the encoding. **cmd+1**
To work with this data lets convert it to a javascript object using JSON.parse.

**opt+2** Read the contents of the users.json file, again using the readfilesync function. Don't for get the encoding.
Next convert userData to a javascript object using JSON.parse.

The account constant now contains information about three accounts. Lets display a summary of each account on the homepage.
**opt+3** Update the object that is passed in to the res.render function. Change the title to Account Summary and add the accounts object.

Now that the index view has access to the accounts object adjust the index.ejs view to display a summary of each account
**opt+4** Include the summary view three time one for each account adjusting the object passed to the include. accounts.savings, accounts.checking, accounts.credit.

Summary view contains a link to the transactions of each account. To show these transactions create a get route with **opt+5** app.get, provide the URL path '/savings' and a callback. In the callback call res.render passing in the **account** view and an object with a key value pair account: accounts.savings.

**opt+6** The checking and credit routes are similar to the savings route. The URL path for the first is '/checking', and the account passed in is accounts.checking. For 'credit' we will have '/credit' and accounts.checking

For maintenance the HTML for listing transactions has been moved to its own view. Open the account.ejs view file and **opt+7** include the transactions view. Pass the include function an object with the key-value pair: account: account.

Lets now move to the user profile page. Create a file in the views directory called profile.ejs.

In profile.ejs include the common header add a title of Profile. In a div display the users information each on a new line.
user.name, user.username, user.email user.phone, user.address Link back to the account summary page and include the common footer.

Switch back to app.js and add the profile get route **opt+0**, add the URL path of '/profile', in the callback res.render the profile view and add an object with a key-value pair user: users sub 0.