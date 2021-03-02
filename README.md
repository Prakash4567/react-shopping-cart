Introduction

Introduction
Fully-Functional Shopping Cart
Instant Feedback
Animated and Intuitive Design
List Products
Sort Products By Price High or Low
Filter Products by Size
Open Modal By Click on Product
Add Product To Cart using Animation
Handle Multiple Click By Adding More Items
Remove Product
Show Checkout Form
Create Order with user friendly id
Admin Section to see list of products
Using postman to add or remove products and orders
Tools and Technologies
JavaScript (arrow functions, array functions, spread Operators, ...)
React (react-touter-dom, react-reveal, react-modal)
Redux (react-redux, redux-thunk)
Node (express, body-parser, Environment Variables, nodemon)
MongoDB ( mongoose, shortid)
VS Code (ES6 Snippets, ES7 React Extension, ESLint Extension,CSS Peek)
Chrome ( React Developer Tools, Redux Developer Tools)
Git (create repo, commit, remote, create and push branch)
Github (create repo, connect to local repo, pull request and merge)
Postman ( send get, post, put and delete requests to apis)
Deployment ( Heroku, MongoDB Atlas Cloud)
Create React App
Open VS Code and open terminal
cd Desktop
npx create-react-app react-shopping-cart
Remove unused files
Convert App.js Class Component
Add header, main and footer
Update index.css to add grid
Project Development Workflow
Create Google Spreadsheet
Add columns Feature, Description, State, and Duration
Enter Products Component, Show list of products, Open, 2
Add Time ? Hours, Rate 30 USD/Hours, Cost ? USD
Add All Features
Create Github account
Create new repository
Add it as remote repository in VS Code
Commit changes
Push changes on github
Start => create new feature Feature 1 in google spreadsheet
Create a new branch feature-1 for test the workflow
Add "// branch feature 1" in App.js Line 1
Commit with message "feature 1"
Click publish changes
Open repository page on github
Create pull request
Merge pull request
In VS Code switch to master and Sync changes
End => Loop from step 11 for next feature
React

Products Component
Create data.json {products:[{_id, title, ...}]
Update App.js to import data.json
div.content {flex, wrap}
div.main {flex: 3 60rem}
div.sidebar {flex: 1 20rem;}
Create components/Products.js component
Add it to div.main in App.js and set products props
ul.products {flex,center, center,warp, p:0,m:0, style:none}
this.props.products.map(p => li.key={p._id} {flex, p:1, m:1, none,h:47}
div.product { flex, column, space-between, h:100%}
a href="#" > img {max-width, max-height:37} + p {p.title}
div.product-price > div.product.price + button.button.primary Add to cart
product-price {flex, space-between, center}
div {p.price} flex: 1; align: center; size: 2rem
button.button.primary Add To Cart
Filter Component
Create components/Filter.js
Add it above Products component in App.js
Update Filter.js render
div.filter {flex, wrap, p,m:1rem, border-bottom: .1rem}
filter-result {this.props.filteredProducts.length}
filter-sort {flex:1}
label Order select value=this.props.sort
onChange= this.props.sortProducts(e.t.value)
option lowestprice Lowest, ...
filter-size {flex:1}
label Filter select value=this.props.size
onChange= this.props.filterProducts(e.t.value)
option "" ALL, XS, S, M, L, XL, XXL
App.js
Add Filter Component


Cart Component
Set Active Task Management Spreadsheet
Create branch cart-component
Product.js
Handle "Add To Cart" to this.props.addToCart(product)
App.js
Add cartItems to state as []
Create addToCart(product)
Slice, Check product existance, add to cartitems
Cart.js
Define cartItems from this.props
Check cartItems.length and show message
List cartItems {cartItems.length > 0 && (}
index.css
Style cart, cart-header, cart-items (img, li),
Publish changes
Pull request, merge, change to master
Task Management Spreadsheet set it done
Checkout Form
Set Active Task Management Spreadsheet
Create branch checkout-form
Cart.js
Make cart items persistent
Use LocalStorage on App constructor to load cart items (JSON.parse)
Use LocalStorage on addToCart to save cart items (JSON.stringify)
Handle Click on Proceed
Update showCheckout state to true on click
Conditional rendering Checkout Form
Get Email, Name and Address required input
Define handleInput function
Add Checkout Button
Handle onSubmit Form Event by this.createOrder
Create order object and pass to parent to handle it
Commit and Publish changes
Pull request, merge, change to master
Task Management Spreadsheet set it done
Add Modal and Animation
Set Active Task Management Spreadsheet
Create branch animation-modal
Show Animation
Install react-reveal
Create fade effect from bottom for products
Create fade left for add to cart
Create fade right for show checkout form
Open Modal by click on product image
Install react-modal
Products.js
Import Modal
Set state for product to null
Define openModal and closeModal
Show Modal if product exist
Create Modal
Create zoom effect for modal
index.css
Style Product Details
Commit and Publish changes
Pull request, merge, change to master
Task Management Spreadsheet set it done
Node.JS

Create Products Backend
Install nodemon globally
Add server.js
Install express body-parser mongoose shortid
Install MongoDB
app = express()
app.use(bodyParser.json())
mongoose.connect()
create Product model
app.post("/api.products")
Postman send post request
route.get("/api/products")
route.delete("/api/products/:id")
Redux

Add Redux
what is redux (diagram)
update task on spreadsheet
create branch add-redux-products
npm install redux react-redux redux-thunk
create types
types.js
define FETCH_PRODUCTS
actions/productActions.js
declare fetchProducts
create reducers
reducers/productReducers.js
define case FETCH_PRODUCTS
create store
store.js
import redux
set initial state
define initialState
create store
import productReducers
combine reducers
Use store
App.js
import store
wrap all in Provider
connect products
components/Products.js
connect to store
import fetchProducts
fetch products on did mount
package.json
set proxy to http://127.0.0.1:5000
npm run server
check products list
commit and publish
send pull request and merge
update spreadsheet
Add Redux To Filter
Updte task and branch
types.js
create FILTER_PRODUCTS_BY_SIZE
create ORDER_PRODUCTS_BY_PRICE
actions/productActions.js
create filterProducts
move app.js filterProducts logic here
create sortProducts
move app.js filterProducts logic here
reducers/productReducers.js
case FILTER_PRODUCTS_BY_SIZE
case ORDER_PRODUCTS_BY_PRICE
Filter.js
connect props: size, sort, items and filteredItems
connect actions: filterProducts and sortProducts
show loading if no filteredProducts
App.js
remove Filter props
check result
update task and branch
Add Redux To Cart
Updte task and branch
types.js
create ADD_TO_CART
create REMOVE_FROM_CART
actions/cartActions.js
create addToCart
create removeFromCart
reducers/cartReducers.js
case ADD_TO_CART
case REMOVE_FROM_CART
Cart.js
connect props: cartItems
connect actions: removeFromCart
Product.js
add action addToCart
App.js
remove Cart props
store.js
set initial cartItems to localStorage
check result
update task and branch
Advanced Topics

Create Order
Backend
server.js
create order modal
get /api/orders
post /api/orders
delete /api/orders/:id
Frontend
create types
types.js
CLEAR_ORDER, CLEAR_CART, CREATE_ORDER
create actions
actions/orderActions.js
createOrder(order)
clearOrder()
create reducers
reducers/orderReducers.js
case CREATE_ORDER
case CLEAR_ORDER
Update Cart Component
components/Cart.js
connect order, createOrder, clearOrder
form onSubmit={this.createOrder}
createOrder() this.props.createOrder(order)
closeModal() this.props.clearOrder()
render()
const { cartItems, order } = this.props;
{order && (}
Manage Orders
Add new page
Install react-router-dom
App.js
Import BrowserRouter, Route, Link
render()
BrowserRouter
Route path="/admin" component={AdminScreen}
Route path="/" exact={true} component={HomeScreen}
HomeScreen.js
AdminScreen.js
components/Orders.js
render()
Orders
Backend
server.js
app.get("/api/orders")
app.delete("/api/orders/:id")
Frontend
types.js
FETCH_ORDERS
actions/orderActions.js
fetchOrders()
reducers/orderReducers.js
case FETCH_ORDERS {orders: action.payload}
components/Orders.js
connect orders, fetchOrders
componentDidMount() fetchOrders
render()
!orders
Loading...
table orders
index.css
style orders
Deploy Website

Create MongoDB Cloud Database
Login to https://www.mongodb.com/cloud
Add database user
Left sidebar> Select Security > Database Access
Select Add New User button
Enter user name and password and click Add User
Add IP whitelist
Left sidebar > Select Security > Network Access
Select Add IP Address
Enter 0.0.0.0/0 in Whitelist Entry and click Confirm
Get connection string
Left sidebar > Select Altas > Cluster
Click Connect
Click Connect to your application
Click Copy button
Step 2: Deploy On Heroku
Create git repository in amazona folder using git init
Create Heroku Account at heroku.com
Heroku
Create Heroku account on heroku.com
Install Heroku cli https://devcenter.heroku.com/articles/heroku-cli
Open Terminal
heroku login
heroku apps:create react-shopping-cart-best
Edit package.json
"engines": { "node": "12.4.0", "npm": "6.9.0"}
Create Procfile
web: node server.js
Set MongoDB connection string in Heroku
Open Heroku apps https://dashboard.heroku.com/apps/
Select your apps, open Setting Tab and click Reveal Config Vars
Add key MONGODB_URL
Enter copied connection string from the previous step
Update database name and username and password
Add key NODE_MODULES_CACHE and value false
app.use("/", express.static(__dirname + "/build"));
app.get("/", (req, res) => res.sendFile(__dirname + "/build/index.html"));
git add . && git commit -m "publish"
git push heroku