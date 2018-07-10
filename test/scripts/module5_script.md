In this module we will uses the Express Router to break out the routes into services and accounts. 

Create a routes directory at the root of src.

In the new routes directory, create a new file called accounts.js.

Open accounts.js and require the express framework. Create a constant called router and set it equal to a call to the express.Router() function.
Use object destructuring to create one constant called accounts while requiring our data library.

In app.js locate the savings, checking, and credit get routes, cut and paste these below the require statement in accounts.js Make these routes a part of the router by changing app to router. 

Export the router using module.exports.

Right click on the routes directory, and create a new file called services.js.

In services.js require the express framework. And create a router by calling express.Router. 
Create two constant one called accounts the other writeJSON, while requiring our data library.

Switch over to app.js and find the transfer and payment routes. Move them to services.js.
Make these routes a part of the router by changing app to router. 

Use module.exports to export the router.

In app.js require the routes/accounts.js file and store a reference to it in a const called accountRoutes.

Next do the same with services, require the routes/services.js file and store a reference to it in a const called servicesRoutes.

To wire everything up call app.use with two arguments. The first argument should be '/account' and the second is the accountRoutes constant.
Include the services routes with a call to app.use. The first argument should be '/services' and the second is the servicesRoutes constant.

Because we have now changed the URL paths for some routes lets update our views to bring them in sync.

In src/views/index.ejs change href="transfer" to href="/services/transfer"
In src/views/summary.ejs change href="<%= account.unique_name %>" to href="/account/<%= account.unique_name %>"
In src/views/transfer.ejs change action="/transfer" to action="/services/transfer"
In src/views/payment.ejs change action="/payment" to action="/services/payment"