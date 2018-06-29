In this module we will configure an express server to run on port 3000. First require the built-in libraries fs and path.
Next require the express framework. To use express we will create an app const set equal to the the express function.
Configure the views folder and the view engine using app.set. 

All of the project css/js is located in a directory called public. Let tell express how to find this directory.

Now that the views and static settings have been configured let create a view file for the default route. 
In this new view file add the ejs markup to include the header.ejs file. We will then create a container div for the title and the menu.
Add a link to the transfer route. Finally include the footer.
We can now display this index view with a get route using app.get. app.get accepts a
URL path and a callback. This callback is passed a request and a response. We can use the response to render the index view.

To wrap things up lets add a call to the app.listen function, which accepts a port and a callback.