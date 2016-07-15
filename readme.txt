@FunctionalInterface
interface Some {
	public doTask(int x);

	default public another() {
		//code
	}
}

node.js
-------

Why Node.js?
1) PRODUCTIVITY
	PAYPAL
2) Performance
	Walmart
	2014 Black Friday
3) API on JSON DATA [ ObjectDB ---> MongoDB / NoSQL ]

4) Traditional Web Application ( Can Use )
	like connecting to ORacle/ MySQL
--------------------------------------------------

nodeJS use CommonJS module system for loading module

Write a module and use:

module.exports = moduleName;


Using the Module

require('moduleName');

npm addUser

npm login

npm publish

---------------------------------------

Events
-----------------

mongodb
1) download mongodb  

Add to path: C:\Program Files\MongoDB\Server\3.0\bin

mongod.exe --dbpath "d:\test\data"
this will set ur data path







you ' ll get a "connection open" msg.. keep that cmd open and open another cmd prompt


C:\>mongo // for db console


--------------------------------------------------









To import JSON array into mongodb
c:\>mongoimport --jsonArray --file g:\one.json --collection customers --db mydb


---------------------------------------

RDMBS									MongoDB
Database								Database
Table									Collections
Columns									fields
rows									documents


Mongodb stores data in BSON format [Binary Script Object Notation]
Does not understand Relationship

No Foreign Key.
Primary key is "_id" is of type ObjectId
-------------------------------------------

> use mydb
> db.products.insert({});

> db.products.insertOne({});
> db.products.insertMany({},{},{});
> db.products.find(); // returns all documents [ select statement ]

> db.products.findOne() ; // first document

> db.products.find().pretty();  // returns only 20 documents at a time
> it 

> var data = db.products.find();

> data.forEach(function(product) { });

> db.products.find({"name":"Laptop"});

> db.products.find({"$gt":["price":1000]});

> db.products.find({},{"name":1,"price":1});


> db.products.find().sort({"price":1})



> db.products.find().sort({"price": -1})


> db.products.find().limit(5)


------------------------------
NodJS and MongoDB integration:
mongod librarires
mongoose

-------------------------

[
    {
      "id": 1,
      "firstName": "Rajesh",
      "lastName": "Kumar",
      "gender": "male",
      "address": "My Address",

    },
    {
      "id": 2,
      "firstName": "Suresh",
      "lastName": "Kumar",
      "gender": "male",
      "address": "Some Address"
    },
    {
      "id": 3,
      "firstName": "Smitha",
      "lastName": "Sharma",
      "gender": "female",
      "address": "Some Address"
    },
    {
      "id": 4,
      "firstName": "Geetha",
      "lastName": "Kumari",
      "gender": "female",
      "address": "Some Address"
    },
    {
      "id": 5,
      "firstName": "Parthiv",
      "lastName": "Raox",
      "gender": "male",
      "address": "Some Address"
    }
  ]


 orders 
 http://server/customers/1/orders



 [
 	{"product":"","qty":1,"customer_id": 1}
 ]

----------------------------------------------------------

Web application 

http, https ==> Send Representaion to client


Web Application Framework : Express

Express uses JADE/EJS templates for rendering 


npm modules required:
1) express
2) express-generator [ Optional]

npm install express -g
npm install express-generator -g


	---------------

  complete flow:
  PART 1
  1) http://localhost:9000/index.html
  2) Since it is static content
    app.use(express.static(path.join(__dirname, 'public')));

    Express sends index.html to the browser
  3) in index.html we have
    <link>
    <scrpti src="">
    This will force to get other static contents from public floder

PART 2:
U click on "customers" link

URL changes to:  http://localhost:9000/index.html/#/customers

Angular Router[ RouteProvider]

checks 
$routeProvider.when('/customers', {
  

});

Connects to CustomerService.getCustomers = function() {
  
    $http.get("/customers").then();
}

MAkes a call to  http://localhost:9000/customers

Invokes Express Router and fetches JSON data from MongoDB
and sends it as JSON response

Angular sends this data to custoemrs.html page
Angular renders this page with data sent from Express

------------------------------------------------------------------

Node JS provides:

child-process module using which we can exec() other process

exec is a process executes and returns a value

Child-process module contains spawn(),
child sends buffered events to the master.

 
fork() method replicates master process and executes

----

fork() using clusters
create child process which shares the master modules

Master and Child will start communicating using same port and by IPC

---------------------------------------------------------------------

ANT/ MAKE Build file

==> Grunt and Gulp

--------------------------

HTML 5
------
1) New Sementics
   <header>
   <footer>
   <nav>
   <section>
   <aside>

   MicroData

2) Offline APIs
  http://caniuse.com/

  a) LocalStorage
  b) SessionStorage // in Place of Cookies
  c) WebSQL //
  d) Application Cache

3) Other APIs
    a) History API
    b) GEO Location
    c) Drag - Drop
    d) File Handling

4) Client - Server Communication
    a) Server Side Events
    b) WebSockets [ Full Duplex ]
    c) WebWorker [ To Start Threads in Client ]

5) Canvas and SVG for Graphics

  Canvas is pixel based and needs JS code to create graphics
  // dynamically creating graphics
  // Display Sprite Images

  SVG scalar Vector graphics [ XML ] < -- Animation
------------------------------------------------------------


Use HTML5Shiv and Moderinzr

<!--[if lt IE 9]>
<script src="//html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->

CSS
nav {
  background-color:red;
}

<header>
  <nav>

  </nav>
</header>




