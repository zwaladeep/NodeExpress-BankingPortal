In this module we will gather data from two HTML forms. One is found in transfer.ejs and the other is found in payment.ejs. We will perform some calculations on the data and write it back to the file accounts.json.

Open app.js and near the other app.use statement add another call to the app.use function, pass in the express.urlencoded middleware. Pass an object to the express.urlencoded with the extended key set to true. **F1**

To provide access to the transfer HTML form, create a get route that points to the '/transfer' URL path. Use res.render to render the transfer view. **F2**

We need to adjust the HTMLM form just slightly, open the transfer.ejs view, find the form with an id of transferForm and add an action of '/transfer' and a method of `POST`. **F3**
Next add name and id attributes to the first select. Set the value of both attributes to 'from' **F11**
Set the same attributes of the second select to the value 'to' **F12**

Switch back to app.js and create a post route that points to the /transfer URL path. **F4**

In the function body of the post route we are going to calculate the new balances for the account we are transferring from.

**F5** Set accounts[req.body.from].balance to accounts[req.body.from].balance - req.body.amount

**F6** Next Set accounts[req.body.to].balance to accounts[req.body.to].balance plus req.body.amount. We are going to convert each of these to an int using parseInt

**F7** Create a constant called accountsJSON set it equal to the results of a call to the JSON.stringify() function with the parameters accounts, null, 4.

**F8** Use the writeFileSync function of the fs library to write the accountsJSON constant to the file accounts.json in the json directory.

**F9** Once we have written the changes back to the accounts.json file we are going to display a confirmation message. Use res.render to render the transfer view, pass an object with the key value pair: message: "Transfer Completed"

**F10** The payment feature of the application is similar to the transfer feature.

Below the transfer routes, create a get route with a URL path of /payment that renders the payment view, pass in an object with a key value pair of account: accounts.credit.
Next create a payment post route with a URL path of /payment, in the function
Next subtract the payment amout from the balance and save it back: accounts.credit.balance minus-equals req.body.amount
Add req.body.amount to accounts.credit.available and save it back: accounts.credit.available plus-equals parseInt(req.body.amount, 10).
Convert the accounts javascript object to a JSON string and save it to a variable called accountsJSON
Write accountsJSON to a file using the writeFileSync function.
Render the payment view and pass an object with the key value pairs, { message: "Payment Successful", account: accounts.credit }
