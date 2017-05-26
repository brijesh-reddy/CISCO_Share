Java 
Banu Prakash C
banuprakashc@yahoo.co.in
banu@advantech-global.com
-------------------------
Softwares Required:
1) Install jdk 8 [ oracle.com ]
2) Eclipse for JEE (NEO) [ eclipse.org ]
3) MySQL (Community Edition) <-- can install on third day
----------------------------------------------------------------

OOP
	Object Oriented Paradigm?

	SOLID Design Principle.

	S ---> Single Responsibility
	O ---> Open Close Principle
		 Every Component/Object should be closed for a change but open for extension.
	L ---> Liskov Substitution Principle.
			Relationship : Generalization and Specialization relationship between Objects

	I ---> Interface Seggregation
		 Expose relavent interfaces to objects
	D ---> Dependency Injection ( Inversion of Control )
-------------------------------------------------------------------------------

What is Java?
 Java is a technology
 	Platform
 		Java Runtime Environment
 		+
 		APIs

 Java programming language

 ------------------------------------

 Primitive 												Reference type
 [reside on stack ]										[ Heap area]
 byte													array
 short 													class			
 int 
 long

 float
 double

 char [unicode character set : Example: 2308 ]
 boolean [ true or false ]
------------------------------------------------------------------------

	Objects and classes

	Objects contain state and behaviour

	---------------------------

	Methods of Classloader:
	1) findLoadedClass()
	2) loadClass()
	3) findSystemClass()
	4) defineClass()

	--------

	constructors have same name as that of class name with no explicit return type.
	constructors are invoked implicitly when object is created

	---------------
	Object equality
		== vs equals()

		== is used to compare refrences
		equals() is for comparing content
------------------------------------------------------------------------------------------

 Arrays
 	: Reference type

 	int data[4]; // error

 	int[] data = new int[4]; //prefer
 	int data[] = new int[4];

 	int[] data = {3,5,67,2};


 	int[][] values = new int[3][2];

	int[][] values = new int[3][];

	values[0] = {4,6,6};
	values[1] = {33,2};

	---------

	Testing AAA
	Assemble Action Assert

-----------------------------------------------------------------

	Types of classes organized logically:

	1) entity classes / domain classes / model classes
	2) DAO classes
		contains Code for CRUD [create read update delete ] operations
	3) Business classes
	4) service classes
	5) Utility classes
	6) exception classes
	7) UI classes
	....


	packages are used for logically grouping classes.
	packages helps in class namespace identification
	packages can be reused

	How to name a package:

	com.cisco.prj.dao
	com.cisco.prj.service
-----------------------------------------------

Relationsip between Objects:
1) Generalization and Specialization
2) Realization
3) Association
4) Uses A Relationship



	CheckStyle: NamingConventions, Formatting, Comments

		CamelCase		customerName
		SnakeCase		CUSTOMER_NAME
		SpineCase		CUSTOMER-NAME

	PMD and FindBugs: Coding Stds.
		DRY [ Don't Repeat Yourself ]
		Copy Paste Code

-----------------------------------------


	public class Product {

		public Product() {
			s.o.p("p1");
		}

		public Product(double p){
			s.o.p("p2");
		}
	}

	public class Mobile extends Product {
		public Mobile() {
			s.o.p("m1");
		}
		public Mobile(double price, String connectivity) {
			super(price);
			s.o.p("m2");
		}
	}


	new Mobile(); // p1 m1

	new Mobile(73000.00, "4G LTE"); // p2 m2
	------------------------


	public class Product {

		public double  getPrice() {
				return 100;
		}
	}

	public class Mobile extends Product {
		 	
		public double  getPrice() {
				return 999;
		}

		public String getConnectivity() {
			return "4G";
		}
	}

	Mobile m = new Mobile(); 
	m.getPrice(); //999
	m.getConnectivity(); // 4G
	Product p = new Mobile(); // upcasting
	p.getPrice(); //999		// Dynamic binding Runtime binding
	p.getConnectivity(); // ERROR Product does not contain getConnectivity Behavior
------------------------

Comments
	
	Programming comments:
		// single line

		/*
			multiline comments

		*/

	JavaDoc Comments

	/**
		API comments
	*/

	-------
	Generalization and Specialization
	1) extends is a keyword used for Inheritance.
	2) Java does not support multiple inheritance
	class Mobile extends Product, Toy // error
	3) Upcasting [ Having a base class reference to specialized objects]
	4) Downcasting [ getting specialized reference from gerneralized one]
	5) Override
		redefine a method which already exists in base type [ Generalized type ]
	6) In Java Dynamic binding takes place whenever a method is called.
	7) abstract classes can't be instantiated
	8) abstract methods should be compulsolry overriden in inherited class, else
		the inherited class also should be marked as abstrct

------------------------------------------------------------

	Realization Relationship

	A component will realize the behavior specified by other in order to communicate


	Contract is defined using an interface:

	interface interfaceName {
		behavior()
	}

	interface helps in:
		1) DESIGN
		2) DEVELOPMENT
		3) TESTING
		4) INTEGRATION
-----------------------

Class loader loads a class.

Programmatically also you can load a class:

Class.forName("com.cisco.prj.dao.ProductDaoCloudImpl");


Class.forName("com.cisco.prj.dao.ProductDaoCloudImpl").newInstance();
--------------------------------------------------
 interface Swim {									Fight f = new Hero();
 	void swim();									f.fight();
 }													f.swim(); //error
 													Swim s = (f);
 interface Dance {									s.swim(); 
 	void dance();
 }

 interface Fight {
 	void fight();
 }

 class Actor implements Dance {
 	public void dance() {

 	}
 }
 
 public class Hero extends Actor implements Fight, Swim {
 	public void fight() { }
 	public void swim() { }
 }

-----------------

Abstract class 											interface
1) can have state 										can't
2) Partial implementation 								complete abstract
3) class extends Abstract class 						class implements interface
4) single inheritance 									can implements many 
5) IS A Relationship 									realizes


	interface Fly {
		fly();
	}

	class Bird implements Fly {					class AeroPlane implemets Fly {
		fly()  { }										fly() { }
	}											}

----------------------------------------------------------
	
	Writing code which is Closed for change [ OCP ]

	"Jack" , "Angelina", "Brad", "Smith"

	12,45,80,3,5

---------------

	Create Book class with id, title

	BookClient
	creates 4 books
	sort() them by calling Utility.sort(books); // sort based on title
	print	

	HINT: 
		int compareTo(String str)
---------------------------------------------------------------------------------
	Exception Handling
	------------------

	Exception: Abnormal condition that arises during program execution

	In Java Exception is represented as object. Object gives me the
	follwoing info:
	1) What went wrong
	2) Where
	3) Why

	Error and Exception:

	Excpetion types:

	Unchecked Type 							Checked Type
1) Compiler does not enforce you 			compiler forces you to handle
    to handle	
   Example: Arithmetic, ArrayIndex 			ClassnotFoundException, SQLException,
   											IOException

 2) handle using conditional stmt 			use try-catch

 3) Reason for Excepion is within JRE 		Reason is outside JRE [ database, OS, etc]


 ------

 	try {
 		actual code to execute
 	} catch(IOException ex) {
 		// excpetion handling code
 	} catch(SQLException ex) {
 		// excpetion handling code
 	}

  optinally you can have finally block


  try {
 		actual code to execute
 	} catch(IOException ex) {
 		// excpetion handling code
 	} catch(SQLException ex) {
 		// excpetion handling code
 	} finally {
 		// compulsory execute code like resource release
 	}
---------------------------------------------------

	Generics

	public class Rectangle {
		int width;
		int breadth;
		//
	}

	Rectangle r1 = new Rectangle(4,5);

	public class DRectangle {
		double width;
		double breadth;
		//
	}
	DRectangle r2 = new DRectangle(2.4,5.5); 


	Solution:
	public class Rectangle<T> {
		T width;
		T breadth;
		//
	}
	Rectangle<Integer> r1 = new Rectangle<Integer> (4,5);
	Rectangle<Double> r2 = new Rectangle<Double>(2.4,5.5); 

	Limitation of Genrics is we can use only objects and not primitivies

	Integer is a type wrapper for int.
	Double is a type wrapper for double.

	double d = 1.3;
	Double dd = d; 

	public class Rectangle<T> {     ===> public class Rectangle {
		T width;								Object width;
		T breadth; 								Object breadth;	
		//
	}


	public class Registry<U,V> {
		U key;
		V value;
	}

	Registry<String,String> empRegistry = ...
	Registry<IPAddress,String> domainRegistry = ...
	-------------------------------------------------------------

	Java Collection Framework (JCF)
		provides data containers

	Arrays are data containers.
	Arrays size is fixed, add / remove operations from arbitrary pos is difficult
	Arrays needs contiguos memory

	In JCF, we have:
		1) interfaces
		2) implementation classes
		3) Algorithm classes










"Jackie" , "Angelina", "Brad", "Smith"

Sorted:
	"Angelina", "Brad", "Jackie" , "Smith"

Why Not:
	"Brad", "Smith", "Jackie" , "Angelina"

----------------

interface Flyable {
		void fly();
}

class Bird implements Flyable {
		fly();
}
Flyable f = new Flyable(); // erro
Flyable f = new Bird(); //  valid

Flyable f = new Flyable() {
		fly() {
			// code
		}
	
};
-------------------------
List 								Set

1) supports duplciate 				unique 
2) supports index operations 		does not
  get(index)						does not
  add(index, object)
  remove(index)
3) ordered
4) re-ordered

	----------

	ArrayList list = new ArrayList();
	List list = new ArrayList();
	List list = new LinkedList();


		List list = new ArrayList(); // AVOID --> not typesafe
		list.add("A");
		list.add(new Movie());
		list.add(22);


		List<Movie> movies  = new ArrayList<Movie>();

		list.add("A"); // not allowed
		list.add(new Movie());
 --------
 	HashCode

 	1) Numerical representation of an object

 	Rule:
 		Similar Objects should have same hashcode
 		disimilar objects can also have same hashcode


 	class Rectangle {

 		int hashCode() {
 			return 2 pow 1 * w  +  2 pow 2 * 2b;
 		}
 	}

 	5 x 4 == 20
 	20 x 1 == 20
--------
HashSet uses hashCode() and equals() for object identity and positioning of objects in collection

TreeSet is a SortedSet, uses Comparable or Comparator for object identity and pos.

----------------------------------------------------------------------------------------

	Annotations are Metadata and can be used by:
		1) Compiler
		2) ClassLoader
		3) JRE

	Example:

	class A {
		void test() {

		}
	}

	class B extends A {
		@Override
		void tests() {

		}
	}
	---------------

	@Mobile(os="andriod")
	public class PokemonGo extends Game {

	}

	-----------

	@URI("/employees")
	public class EmployeeService {

	}

	http://server:port/employees
	----------------

	Let's create Annotations to generate DDL and DML statments


	@Table(name="BOOKS")
	public class Book {

		@Column(name="BOOK_ID", type="NUMERIC(12)")
		id
		@Column(name="BOOK_TITLE")
		title
		@Column(name="AMOUNT", type="NUMERIC(12,2)")
		price
	}


	CREATE TABLE BOOKS (BOOK_ID NUMERIC(12), BOOK_TITLE VARCHAR(255), AMOUNT NUMERIC(12,2))



	List<Integer> list = new ArrayList<Integer>();
	list.add(2);
	list.add(4);


	List<?> ol = list;

	ol.get(0); // 2
	ol.add(33); // error
	-------------------------------------------------------------------------

	Java Concurrent Programming [ Multithreaded applications]

	Single threaded application.

	Process needs a unit of work [ thread ]. Main thread entry point is main() method

	interface Runnable {
		void run();
	}

	run() method is an entry point for user defined threads

	Notepad is single threaded

	Word, Excel, Eclipse examples of multithreaded application

	Why do we need multithreaded applications?
	a) optimal utilization of resources [ CPU Idle time, using multiple CPUs]
	b) Avoid starvation



	Java Provides "Thread" class for controlling life cycle of a thread:

	start()
	sleep(long ms)
	yield()
	join()
	interrupt()

	deprecated methods:
	stop()
	suspend()
	resume()
-------------------------------------------------------------------------

	Thread Safety
	-----------
	A member is said to be thread safe if it does not get corrupted in
	multi threaded env.

	1) local variables are thread safe
		local var reside in stack, each thread has a seperate stack
	2) instance variables are not safe
		instance variables reside in HEAP area, heap area is shared between threads
		[Objects are shared between threads]
	3) static variabels are not safe
		reside in Class data. loaded classes are shared.
	4) volatile variables are thread safe.

		public class SomeClass {
			private volatile boolean flag = false;

			setFlag() {}
			getFlag() {}
		}

		volatile keyword is used to specify that the CPU should not cache the member
		in its registry.

		volatile can be used only for atomic variables.
		-------------------------


		class Account {

		}

		public class BankingService {

			public  void transferFunds(Account from, Account to, double amt) {
				synchronized(from) {
					synchronized(to) {
						// transfer funds code
					}
				}
			}
		}


		transferFunds(a1, a2, 5000);
-----------------------------------------------------

ThreadPools
	
Callable and Future interfaces

	interface Callable<T> {
		T call() throws Exception;
	}

	instaead of:

	interface Runnable {
		void run();
	}
-----------------------------------------------------
	
	Java 8 features:
	functional style of programming and lambda expression

	OOP contains methods which depend on the state of object.

	Functional style of programming contains functions which are not coupled to
	objects.
	Functional style of programming  uses HIGH order functions.
	High order functions are functions which accept other functions are arguments.

	Common HIGH order functions:
	1) MAP
		takes a collection / stream and modifies it 
	2) FILTER
		takes a collection and return filtered collection based on predicate function
	3) REDUCE
		takes a collection and returns a aggregate [ sum, count , max, avg]
	4) ITERATOR

	-----------------------

	Functional interface

	Functional interface is an interface which contains only one method to implement


	Thread t = new Thread(new Runnable() {
		public void run() {
			for(int i = 0; i < 5; i++) {
				s.o.p("HEllo " + i);
			}
		}
	});
	t.start();

	With Java 8:

	Thread t = new Thread(() => {
			for(int i = 0; i < 5; i++) {
				s.o.p("HEllo " + i);
			}
		});
--------------------------------------------------------------
	Java Database Connectivity

	Database : MySQL install

	sudo /usr/local/mysql/support-files/mysql.server stop

	sudo mysqld_safe --skip-grant-tables
	
	mysql -u root

	UPDATE mysql.user SET Password=PASSWORD('password') WHERE User='root';
	
	FLUSH PRIVILEGES;
	
	sudo /usr/local/mysql/support-files/mysql.server start

-------------------------------------------------------------------

	JDBC : Java Database Connectivity
		is an integration API to connect to RDBMS

	Type 1 Driver:

	Java Application <---> JDBC <---> JDBC ODBC Bridge <---> ODBC <---> Database

	ODBC --> Open database connectivity is an integration API provided by Microsoft

	Type 2:

	Java Application <---> JDBC <---> Native Drivers <---> Database

	Native Drivers are provided by database vendors

	Type 3:
	Java Application <---> JDBC <---> NET Drivers <---> Database

	Middle Tier server manages DB related connections


	Type 4:
	Java Application <---> JDBC <---> Socket Connection <---> Database


	-----------------------------------------------------------

	Java APIs contains only interfaces, implementation classes
	are provided by database vendors

	Steps involved in connecting to database:

	1) load vendor provided classes

		Class.forName(....);

	2) Establish a database connection

	Connection con = DriverManager.getConnection(URL, USERNAME, PWD);

	URL exmaples:
		jdbc:mysql://192.168.0.122:3306/employeedb
		jdbc:oracle:@192.168.0.122:1521:employeedb

	3) Send SQL statements [ DML]
		interfaces for sending SQL:
		a) Statement
			for SQL without parameters
			Example: SELECT ID, NAME FROM PRODUCT
		b) PreparedStatement [ Parameterized / precompiled ]
			for SQL with PARAMETERS
			EXAMPLE:
				INSERT INTO PRODUCT values (?,?)

		c) CallableStatement	
			used to invoke stored procedures of database


	mysql> create database cisco_sample_db;
	mysql> use cisco_sample_db;
	mysql> 
	create table Product 
	(id int primary key AUTO_INCREMENT,
	name varchar(100), price double,
	category varchar(15));


	mysql> insert into product values(0,'HP Laptop',45000.00,'computer');
	mysql> insert into product values(0,'Sony Bravia',95000.00,'tv');
	mysql> select * from product;

	---------------

	MAVEN
		is a build tool.
		Similar to ANT, GRADLE, IVY
	MAVEN is also an tool to manage dependecies
--------------------------------------------------------------

	java.io package

	Java's IO is based on stream. Stream is a communication channel along
	which data flows. Streams can be classifed as byte(8) and character(16) stream

	Serialization:
		Serialization is a process of replicating the state of object 
		to a stream

	Only self contained objects can be replicated.

	Serializable is a marker interface to specify that
	the objects of a given class is self contained and inform JVM 
	to allow the object to be written to a stream.

	public class A {
		 
	}

	public class B implements Serialzible {
		 
	}

	Objects of B are allowed to be written to a stream but not A objects
	-----------------------------------------------------------------------
	Building RESTful WebServices using Spring Boot framework,
	Using JPA ( Java Persistence API ) for CRUD operations on database.


	Java Persistence API is a framework on top of ORM frameworks
	for database operations

	ORM [ Object Relational Mapping ]
	ORM frameworks: Hibernate, Toplink, KODO, openJPA, ....

	@Table(name="CUSTOMERS")
	@Entity
	public class Customer {
		@Id
		@Column(...)
		private int id;

	}

	----------------------------------------

	RESTful Web Services

	REPRESENTATIONAL STATE TRANSFER

	Resource on server can be served to the client in various representations

	Common Representations of Resource are:
	XML, JSON, HTML, RSS, ATOM
	XML
	<customers>
		<customer>
			<id>1</id>
			<name>Smith</name>
		</customer>
		<customer>
			<id>2</id>
			<name>Peter</name>
		</customer>
	</customers>
	JSON: JavaScript Object Notation
		[
			{
				"id": 1,
				"name": "smith"
			},
			{
				"id": 2,
				"name": "peter"
			}
		]
	-----------------------------------------------------
	REST stds:
	URL identifies a Resource
	HTTP method is used to identify the action
	Examples:

	1) Fetch all employees
	GET
	http://cisco.com/api/employees

	2) Fetch employee whose ID is 100

	GET
	http://cisco.com/api/employees/100


	3) Add a new employee

	POST
	http://cisco.com/api/employees

	Payload contains the new employee data.



	4) Update existing employee

	PUT
	http://cisco.com/api/employees/120
	Payload contains the new info


	PATCH
	http://cisco.com/api/employees/120

	partial data

	5) DELETE
	DELETE
	http://cisco.com/api/employees/120

	Query Params for finding based on other that ID

	GET
	http://cisco.com/api/employees?place=bengaluru

	GET
	http://cisco.com/api/employees?start=1&end=10

	------------

	Spring Framework:
	----------------
	Spring FW is a lightweight container for building enterprise application

	Spring provides:
		1) Dependecy Injection ( Inversion Of Control )
		2) AOP ( Aspect Oriented Programming )
		3) APIs for Enterprise application integration
		4) Simplifes Web development
		5) Simplifies RESTful services

	





































































	
























































	


























































































































































































	






















































































































































































	















