
Java

Banu Prakash C
banuprakashc@yahoo.co.in
-------------------------

Softwares Required:

JDK 1.8
Eclipse for JEE (Mars or latest)
MySQL DB / HSQLDB

---------------------------------

	OOP ( Object oriented Paradigm)

	Writing programs which resemble real world application

	SOLID Design Principles:

	S ---> Single Resposnibility
	O ---> Open Close Principle
	L ---> Liskov Substitution Principle
	I ---> Interface segreggation
	D ---> Dependency Injection ( Inversion Of Control )

	------------

	What is Java?

		Java is a Technology.

		Java provides the platform to execute byte code.

		ByteCode is a compiled code

		Source Code ---> compile ----> Byte Code

		.java  --------> javac  ----> .class

		.groovy  ------> groovy -----> .class

----------------------------------------------------------------------------

	Example.java

	public class Example {
		public static void main(String[] args) {
			int x = 10;
			int y = 15;
			doTask(x,y);
		}

		public static void doTask(int a, int b) {
			int result = a + b;
			System.out.println("Result : " + result);
		}
	}


	$ javac Example.java

	Example.class is generated

	$ java Example
------------------------------------

Primitive type 										Reference Type

byte  ( 1 byte)											Array
short ( 2 )												Object
int (4 )
long  (8)

float ( 4)
double ( 8)

char ( 2 )
boolean ( 1 )


	byte b = 10;
	byte c = 15;

	byte d = (byte) (b + c);

------------------------------------------------------------------

	Arrays are reference type.
	Memory is allocated on Heap area and its pointers are on stack.
	Every array contains a "length" member which holds the size of array.


	int[] values  = new int[3];

	int[] data = {4,6,266,2};


--------------------------------------------------------------------

	Object oriented Programming with Java.

	Object holds state and behavior

	State of an object is represented by its instance variables
	Behaviours are exposed as actions/ methods of object

	Every object contains state and behavoir
	Class is an template to hold this information

	public class Account {
		// state of object
		private String accNo;
		private double balance;
	}


	Account rahulAcc = new Account();
	Account swethaAcc = new Account();

	rahulAcc.balance = 5000.00; // error [ private ]

	General practice in OOP is make state private and behaviour public.


	Adding Behaviour



	public class Account {
		// state of object
		private String accNo;
		private double balance;

		public  void deposit(double amt) { // public  void deposit(Account this, double amt) {
			balance += amt;					// this.balance += amt;
		}
	}


	Account rahulAcc = new Account();
	Account swethaAcc = new Account();

	// before the period operator is the context,
	// after the period operator is the behavior
	rahulAcc.deposit(4500.00); // deposit(rahulAcc, 4500.00);

---------------------------------------------------------------

	Logical grouping of classes

	1) entity / domain / model classes 
	2) exception classes
	3) Business Classes
	4) DAO [ Data Access Object ] class
	5) Service classes
	6) Utility classes [ Helpers]
	7) UI [ User Interface ]
---------------------------

	Comments

	Programmer comments

	/*
			Multiline

	*/


	// single line


	API comments / JavaDoc Comments

	/**


	*/
-------------------------------------

	== Vs equal()

	equals() is for comparing state of object

	== is comparing references [ Same ]
---------------------------------------------------------------

	Naming Conventions:

	Use Camel case for class, methods and variables

	Use Snake case for Constants MAX_AGE

	Class name should start with Uppercase character
	methods and var should start with lowercase


	public Tea getMeTea() {


	}


	public Tea getmetea() {

	}
---------------------------------------------------------------------------------------------

 Day 2:
 ------
 Relationship between objects

 1) Generalization and Specialization
 2) Realization
 3) Assoication
 4) Uses A Relationship

 ---------------------------

 	public class Product {

 	}

 	public class Mobile extends Product {

 	}

 	Product p = new Product();

 	Product p = new Mobile(); // valid Upcasting


 	Mobile m = new Product(); // not valid [ Downcasting]
 	-----------------

 	public class Product {
 		public Product() {
 			prints p1
 		}
 		public Product(int id, String name) {
 			prints p2
 		}
 	}

 	public class Mobile extends Product {
 		public Mobile() {
 			prints m1
 		}

 		public Mobile(int id, String name, String camera) {
 			prints m2
 		}
 	}


 	new Mobile(); // p1 and m1

 	new Mobile(1,"MotoG", "12MP"); // p1 and m2


 	public Mobile(int id, String name, String camera) {
 			super(id,name);
 			prints m2
 		}
 	new Mobile(1,"MotoG", "12MP"); // p2 and m2

 ---------------------------------------------------------------


 	public class Product {
 		protected double getPrice () {
 			return 100;
 		}
 	}

 	public class Mobile extends Product {
 		public String getCamera() {
 			return "12MP";
 		}
 		protected double getPrice () { //override
 			return 200;
 		}
 	}

 	Mobile m = new Mobile();
 	m.getPrice(); // 200
 	m.getCamera(); // 12MP

 	Product p = new Mobile();
 		p.getPrice(); //  200
 		p.getCamera(); //  ERROR

-----------------------------------------------------------------------------
Visibility
private : only within the class
public : any where
protected: visible within the class, inhereited class and anywhere within the same package
default: within the package [ package private ]


public class Document {
		private Document() {
			//code
		}

		public static Document getDocument() {
			Document d = new Document();
			d.setThat();
			d.setThis();
			d.doSomeThingElse();
			return d;
		}
}

Document d = Document.getDocument();

Document d= new Documnet(); // error
---------------------------------------------------------------

Realization RelationShip

A component will realize the behavior specifed by other in order to communicate.

Realization RelationShip is done using interface.


	interface Flyable {
		fly();
	}


	class Bird implements Flyable {
		fly() {
			// logic
		}
	}

	class AeroPlance implements Flyable {
			fly() {
				//logic
			}
	}

	class SuperMan implements Flyable {
		fly() {
				//logic
			}
	}

	---------------------------------------------

	Why Program to interface?

		a) DESIGN
		b) IMPLEMENTATION
		c) TESTING
		d) INTEGRATION


	package : com.cisco.prj.dao

	Name: MobileDao


	package: com.cisco.prj.dao

	class: MobileDaoDbImpl

	interface : MobileDao


	class: MobileDaoCloudImpl
	interface : MobileDao
-------------------------------------------------------------------


	ClassLoader loads the class

	Rectangle r = new Rectangle();

	String s;

	String str="com.ciso.prj.dao.MobileDaoCloudImpl";

	return Class.forName(str).newInstance();


	dbconfig.properties
-----------------------------------------

 interface Swim {									Swim s = new Hero();
 	swim();												s.swim();
 }														s.fight(); // error

 													Fight f = (Fight) s;
 														 f.fight(); // valid
 interface Dance {
 	dance();
 }

 interface Fight {
 	fight();
 }

 class Actor implements Dance {
 	dance() {
 		// code
 	}
 }

 class Hero extends Actor implements Swim, Fight {
 	swim() { }
 	fight() { }
 }

 ------------------------------------------------------

 OCP ( open close principle)
 	Code is closed for a change but open for extension


 	interface IComparable {
 		int difference(Object obj);
 	}


 	void sort(IComparable[] elem) {
 		for(i = 0 ; .... ){
 			for( j = .....) {
 				if(elem[i].difference(elem[j]) > 0 ) {
 					swap code
 				}
 			}
 		}
 	}

 	class Book implements IComparable {
 			int difference(Object obj) {
 				// logic
 			}
 	}


 	package: com.cisco.prj.util