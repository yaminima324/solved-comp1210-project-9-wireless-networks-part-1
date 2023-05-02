Download Link: https://assignmentchef.com/product/solved-comp1210-project-9-wireless-networks-part-1
<br>



Files to submit to Web-CAT:

<ul>

 <li>java</li>

 <li>java, WiFiTest.java</li>

 <li>java, CellularTest.java</li>

 <li>java, LTETest.java</li>

 <li>java, FiveGTest.java</li>

 <li>(Optional) WirelessNetworksPart1.java, WirelessNetworksPart1Test.java</li>

</ul>

This project is the first of three that will involve the monthly cost and reporting for wireless networks.  You will develop Java classes that represent categories of wireless networks including WiFi, cellular, LTE, and 5G. You may also want to develop an optional driver class with a main method. As you develop each class, you should create the associated JUnit test file with the required test methods to ensure the classes and methods meet the specifications.  You should create a jGRASP project upfront and then add the source and test files as they are created.  All of your files should be in a single folder.  Below is the UML class diagram for the required classes which shows the inheritance relationships.




<strong>You should read through the remainder of this assignment before you start coding.</strong>




<h2>        •    WirelessNetwork.java</h2>




<strong>Requirements</strong>: Create an <em>abstract</em> WirelessNetwork class that stores wireless network data and provides methods to access the data.




<strong>Design</strong>:  The WirelessNetwork class has fields, a constructor, and methods as outlined below.




<ul>

 <li><strong>Fields</strong>:</li>

</ul>

<strong>instance variables (<em>protected</em>) </strong>for: (1) name of type String, (2) bandwidth of type double, and (3) monthly fixed cost of type double.  <strong>class variable (<em>protected static</em>)</strong> for the count of WirelessNetwork objects that have been created; set to zero when declared and then incremented in the constructor. <u>These are the only fields that this class should have</u>.




<ul>

 <li><strong>Constructor</strong>: The WirelessNetwork class must contain a constructor that accepts three parameters representing the instance variables (name, bandwidth, and monthly fixed cost) and then assigns them as appropriate. Since this class is abstract, the constructor will be called from the subclasses of WirelessNetwork using <em>super</em> and the parameter list. The count field should be incremented in the constructor.</li>

</ul>




<ul>

 <li><strong>Methods</strong>: Usually a class provides methods to access (or read) and modify each of its instance variables (known as get and set methods) along with any other required methods. At minimum you will need the following methods. o getName:  Accepts no parameters and returns a String representing the name.  o setName: Accepts a String representing the name, sets the field, and returns nothing.

  <ul>

   <li>getBandwidth: Accepts no parameters and returns a double representing the bandwidth in Mbps.</li>

   <li>setBandwidth: Accepts a double representing the bandwidth in Mbps, sets the field, and returns nothing.</li>

   <li>getMonthlyFixedCost: Accepts no parameters and returns a double representing monthly fixed cost.</li>

   <li>setMonthlyFixedCost: Accepts a double representing the monthly fixed cost, sets the field, and returns nothing.</li>

   <li>getCount: Accepts no parameters and returns an int representing the count.  Since count is <em>static</em>, this method should be <em>static</em> as well.</li>

   <li>resetCount: Accepts no parameters, resets count to zero, and returns nothing. Since count is <em>static</em>, this method should be <em>static</em> as well.</li>

   <li>toString: Returns a String describing the WirelessNetwork object.  This method will be inherited by the subclasses.  For an example of the toString result, see the WiFi class and Cellular class below.  <u>Note that you can get the class name for an instance c by</u> <u>calling c.getClass() [or if inside the class, this.getClass()]</u>.</li>

   <li>monthlyCost: An <em>abstract</em> method that accepts no parameters and returns a double representing the monthly cost of a wireless network. Since this is abstract, each nonabstract subclass must implement this method.</li>

  </ul></li>

</ul>




<strong>Code and Test:  </strong>Since the WirelessNetwork class is abstract you cannot create instances of WirelessNetwork upon which to call the methods.  However, these methods will be inherited by the subclasses of WirelessNetwork.  You should consider first writing skeleton code for the methods in order to compile WirelessNetwork so that you can create the first subclass described below.  At this point you can begin completing the methods in WirelessNetwork and writing the JUnit test methods for your subclass that tests the methods in WirelessNetwork.




<h2>        •    WiFi.java</h2>




<strong>Requirements</strong>: Derive the class WiFi.java from WirelessNetwork.




<strong>Design</strong>:  The WiFi class has fields, a constructor, and methods as outlined below.




<ul>

 <li><strong>Field</strong>: <em>instance </em>variable for modemCost of type double. This variable should be declared with the <em>private</em> access modifier.  <u>This is the only field that should be declared in this class</u>.</li>

</ul>




<ul>

 <li><strong>Constructor</strong>: The WiFi class must contain a constructor that accepts four parameters representing the three instance fields in the WirelessNetwork class (name, bandwidth, and monthlyFixedCost) and the one instance field modemCost declared in WiFi. Since this class is a subclass of WirelessNetwork, the super constructor should be called with field values for WirelessNetwork.  The instance variable modemCost should be set with the last parameter.   Below is an example of how the constructor could be used to create an WiFi object:</li>

</ul>

WiFi n1 = new WiFi(“My Wifi”, 450, 40.00, 5.00);




<ul>

 <li><strong>Methods</strong>: Usually a class provides methods to access (or read) and modify each of its instance variables (known as get and set methods) along with any other required methods. At minimum you will need the following methods. o getModemCost:  Accepts no parameters and returns a double representing modemCost.

  <ul>

   <li>setModemCost: Accepts a double representing the modemCost, sets the field, and returns nothing.</li>

   <li>monthlyCost: Accepts no parameters and returns a double representing the monthlyCost for the WiFi network calculated as the sum of monthly fixed cost and modem cost.</li>

   <li><strong><u>There is no </u></strong><u>toString<strong> method in this class</strong></u>. When toString is invoked on an instance of WiFi, the toString method inherited from WirelessNetwork is called.  Below is an example of the toString result for WiFi n1 as it is declared above.</li>

  </ul></li>

</ul>

My Wifi (class WiFi) Cost: $45.00

Bandwidth: 450.0 Mbps




<strong>Code and Test</strong>: As you implement the WiFi class, you should compile and test it as methods are created.  Although you could use interactions, it should be more efficient to test by creating appropriate JUnit test methods. You can now continue developing the methods in WirelessNetwork (parent class of WiFi).  The test methods in WiFiTest should be used to test the methods in both WirelessNetwork and WiFi.  Remember, WiFi<em> is-a</em> WirelessNetwork which means WiFi inherited the instance method defined in WirelessNetwork.  Therefore, you can create instances of WiFi in order to test methods of the WirelessNetwork class.  You may also consider developing WirelessNetworksPart1 (page 7) in parallel with this class to aid in testing.




<h2>        •    Cellular.java</h2>




<strong>Requirements</strong>: Derive the class Cellular from WirelessNetwork.




<strong>Design</strong>:  The Cellular class has a field, a constructor, and methods as outlined below.




<ul>

 <li><strong>Fields: </strong></li>

</ul>

<strong>instance variables (<em>protected</em>) </strong>: (1) time of type double and (2) data limit of type double.

These variables should be declared with the <em>protected</em> access modifier.

<strong>constant (<em>public</em> <em>static final</em>)</strong> COST_FACTOR of type double set to 1.0, which can be referenced as Cellular.COST_FACTOR.

<u>These are the only field that should be declared in this class</u>.




<ul>

 <li><strong>Constructor</strong>: The Cellular class must contain a constructor that accepts five parameters rep<strong>r</strong>esenting the three instance fields in the WirelessNetwork class (name, bandwidth, and monthly fixed cost) and the two instance fields (time and data limit) declared in Cellular. Since this class is a subclass of WirelessNetwork, the super constructor should be called with field values for WirelessNetwork.  The instance variables time and data limit should be set with the last two parameters.   Below is an example of how the constructor could be used to create an Cellular object:</li>

</ul>

Cellular n2 = new Cellular(“My Note”, 5.0, 20.00, 1200, 1.0);




<ul>

 <li><strong>Methods</strong>: Usually a class provides methods to access (or read) and modify each of its instance variables (known as get and set methods) along with any other required methods. At minimum you will need the following methods.  o getTime:  Accepts no parameters and returns a double representing time.

  <ul>

   <li>setTime: Accepts a double representing the time in seconds, sets the field, and returns nothing.</li>

   <li>getDataLimit: Accepts no parameters and returns a double representing the data limit in GB.</li>

   <li>setDataLimit: Accepts a double representing the data limit in GB, sets the field, and returns nothing.</li>

   <li>dataUsage: Accepts no parameters and returns a double representing the data usage in GB for the network calculated as bandwidth / 8000 * time. Note that dividing by 8000 converts bandwidth in Mbps to GB.</li>

   <li>monthlyCost: Accepts no parameters and returns a double representing the monthly cost for the cellular network as follows.  If data usage is less than or equal to the data limit, return the monthly fixed cost.  Otherwise, return (monthly fixed cost + (data usage – data limit) * Cellular.COST_FACTOR).</li>

   <li>toString: Returns a String describing the Cellular object by calling parent’s toString method, super.toString() and then appending the lines for time, data limit, and data usage.</li>

  </ul></li>

</ul>

Below is an example of the toString result for Cellular n2 as it is declared above.

My Note (class Cellular) Cost: $20.00

Bandwidth: 5.0 Mbps

Time: 1200.0 seconds

Data Limit: 1.0 GB

Data Used: 0.75 GB




<strong>Code and Test</strong>: As you implement the Cellular class, you should compile and test it as methods are created.  For example, as soon you have implemented and successfully compiled the constructor, you should create an instance of Cellular in a JUnit test method in the CellularTest class and then run the test file. If you want to view your objects in the Canvas, set a breakpoint in your test method the run <em>Debug</em> on the test file.  When it stops at the breakpoint, step until the object is created.  Then open a canvas window using the canvas button at the top of the Debug tab. After you drag the instance onto the canvas, you can examine it for correctness. If you change the viewer to “toString” view, you can see the formatted toString value.  You can also enter the object variable name in interactions and press ENTER to see the toString value.  <em>Hint: If you use the same variable names for objects in the test methods, you can use the menu button on the viewer in the canvas to set “Scope Test” to “None”.  This will allow you to use the same canvas with multiple test methods</em>. You may also consider developing WirelessNetworksPart1 (page 7) in parallel with this class to aid in testing.




<h2>        •    LTE.java</h2>




<strong>Requirements</strong>: Derive the class LTE from Cellular.




<strong>Design</strong>:  The LTE class has a field, a constructor, and methods as outlined below.




<ul>

 <li><strong>Field</strong>: <strong>constant (<em>public</em> <em>static final</em>)</strong> COST_FACTOR of type double set to 4.0, which can be referenced as LTE.COST_FACTOR outside the class.</li>

</ul>

<u>These are the only fields that should be declared in this class</u>.




<ul>

 <li><strong>Constructor</strong>: The LTE class must contain a constructor that accepts five parameters rep<strong>r</strong>esenting the three instance fields in the WirelessNetwork class (name, bandwidth, and monthly fixed cost) and the two instance fields (time and data limit) declared in Cellular. Below is an example of how the constructor could be used to create a LTEobject:</li>

</ul>

LTE n3 = new LTE(“My iPad”, 20.0, 30.00, 1200, 2.0);

<ul>

 <li><strong>Methods</strong>: Usually a class provides methods to access (or read) and modify each of its instance variables (known as get and set methods) along with any other required methods. At minimum you will need the following methods. o monthlyCost:  Accepts no parameters and returns a double representing the monthly cost for the LTE network as follows.  If data usage is less than or equal the data limit, return the monthly fixed cost.  Otherwise, return (monthly fixed cost + (data usage – data limit) * LTE.COST_FACTOR * 2).</li>

</ul>

o <strong><u>There is no </u></strong><u>toString<strong> method in this class</strong></u>.  When toString is invoked on an instance of LTE, the toString method inherited from Cellular is called.  Below is an example of the toString result for LTE n3 as it is declared above.

My iPad (class LTE) Cost: $38.00

Bandwidth: 20.0 Mbps

Time: 1200.0 seconds

Data Limit: 2.0 GB

Data Used: 3.0 GB




<strong>Code and Test</strong>: As you implement the LTE class, you should compile and test it as methods are created.  For details, see <strong>Code and Test</strong> above for the WiFi and Cellular classes. You may also consider developing WirelessNetworksPart1 (page 7) in parallel with this class to aid in testing.




<h2>        •    FiveG.java</h2>




<strong>Requirements</strong>: Derive the class FiveG from class Cellular.




<strong>Design</strong>:  The FiveG class has a field, a constructor, and methods as outlined below.




<ul>

 <li><strong>Field</strong>: <strong>constant (<em>public</em> <em>static final</em>)</strong> COST_FACTOR of type double set to 5.0, which can be referenced as FiveG.COST_FACTOR outside the class.</li>

</ul>

<u>This is the only field that should be declared in this class</u>.




<ul>

 <li><strong>Constructor</strong>: The FiveG class must contain a constructor that accepts five parameters rep<strong>r</strong>esenting the three instance fields in the WirelessNetwork class (name, bandwidth, and monthly fixed cost) and the two instance fields (time and data limit) declared in Cellular. Below is an example of how the constructor could be used to create a FiveG object:</li>

</ul>

FiveG n4 = new FiveG(“My Phone”, 80.0, 50.00, 1200, 10.0);

<ul>

 <li><strong>Methods</strong>: Usually a class provides methods to access (or read) and modify each of its instance variables (known as get and set methods) along with any other required methods. At minimum you will need the following methods.  o monthlyCost:  Accepts no parameters and returns a double representing the monthly cost for the FiveG network as follows.  If data usage is less than or equal the data limit, return the monthly fixed cost.  Otherwise, return (monthly fixed cost + (data usage – data limit) * FiveG.COST_FACTOR * 3).</li>

</ul>

o <strong><u>There is no </u></strong><u>toString<strong> method in this class</strong></u>.  When toString is invoked on an instance of LTE, the toString method inherited from Cellular is called.  Below is an example of the toString result for FiveG n4 as it is declared above.

My Phone (class FiveG) Cost: $80.00

Bandwidth: 80.0 Mbps

Time: 1200.0 seconds

Data Limit: 10.0 GB

Data Used: 12.0 GB




<strong>Code and Test</strong>: As you implement the FiveG class, you should compile and test it as methods are created.  For details, see <strong>Code and Test</strong> above for the WiFi and Cellular classes.  You may also consider developing WirelessNetworksPart1 (page 7) in parallel with this class to aid in testing.




<h2>        •    WirelessNetworksPart1.java (Optional)</h2>

<strong>Requirements</strong>: Driver class with main method is optional but you may find it helpful.




<strong>Design</strong>:  The WirelessNetworksPart1 class only has a main method as described below.




The main method should be developed incrementally along with the classes above.  For example, when you have compiled WirelessNetwork and WiFi, you can add statements to main that create and print an instance of WiFi.  [Since WirelessNetwork is abstract you cannot create an instance of it.]  When main is completed, it should contain statements that create and print instances of WiFi, Cellular, LTE, and FiveG.  Since printing the objects will not show all of the details of the fields, you should also run WirelessNetworksPart1 in the canvas (or debugger with a breakpoint) to examine the objects.  Between steps you can use interactions to invoke methods on the objects in the usual way.  For example, if you create n1, n2, n3, and n4 as described in the sections above and your main method is stopped between steps after n4 has been created, you can enter the following in interactions to get the rating for the FiveG object.

M¼MMn4.monthlyCost()

MMMM80.0

The output from main assuming you create print the four objects n1, n2, n3, and n4 as described in the sections above is shown as below.  Note that a new line was added in main before each object to achieve the spacing between objects.




My Wifi (class WiFi) Cost: $45.00

Bandwidth: 450.0 Mbps




My Note (class Cellular) Cost: $20.00

Bandwidth: 5.0 Mbps

Time: 1200.0 seconds

Data Limit: 1.0 GB

Data Used: 0.75 GB




My iPad (class LTE) Cost: $38.00

Bandwidth: 20.0 Mbps

Time: 1200.0 seconds

Data Limit: 2.0 GB

Data Used: 3.0 GB




My Phone (class FiveG) Cost: $80.00

Bandwidth: 80.0 Mbps

Time: 1200.0 seconds

Data Limit: 10.0 GB

Data Used: 12.0 GB




<strong> </strong>

<strong>Code and Test</strong>: After you have implemented the WirelessNetworksPart1 class, you should create the test file WirelessNetworksPart1Test.java in the usual way.  The only test method you need is one that checks the class variable <em>count </em>that was declared in WirelessNetwork and inherited by each subclass.  In the test method, you should reset <em>count</em>, call your main method, then assert that <em>count</em> is four (assuming that your main creates four objects from the WirelessNetwork hierarchy).  The following statements accomplish the test.




WirelessNetwork.resetCount();

WirelessNetworks1.main(<strong>null</strong>);

Assert.assertEquals(<strong>“WirelessNetwork count should be 4. “</strong>,

4, WirelessNetwork.getCount());




<strong>Canvas for WirelessNetworkPart1 </strong>




Below is an example of a jGRASP viewer canvas for WirelessNetworkPart1 that contains a viewer for the class variable WirelessNetwork.count and two viewers for each of n1, n2, n3, and n4.  The first viewer for each is set to Basic viewer and the second is set to the toString viewer.  The canvas was created dragging instances from the debug tab into a new canvas window and setting the appropriate viewer.  Note that you will need to unfold one of the instances in the debug tab to find the static variable <em>count</em>.