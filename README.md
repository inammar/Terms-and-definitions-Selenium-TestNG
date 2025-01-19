# Terms-and-definitions

I found a lot of definitions and terms about Selenium Webdriver and TestNG on the Internet, but not all of them were understandable to me as a beginner. It took a time to find ones that would be explained simply and clearly. Therefore, I created this repository to have all the definitions in one place so that I could check them if necessary. The definitions are not mine, they were all found on the Internet. 

________________________________________________________________________________________________________________________________________________________________________________________
## Terms and definitions of Selenium Webdriver and TestNG

### 1. Selenium Webdriver definition

Selenium Webdriver is an open source web automation tool, that allows to automate web browser interactions. It allows testers to automate browser actions such as navigating through web pages, clicking buttons, entering text, and validating expected outcomes.

### 2. Locators

Locators are one of the essential components of Selenium infrastructure, which help Selenium scripts in uniquely identifying the web elements (such as text box, button, etc.) present of the web page. Shortly, a locator is a way to identify and interact with elements on a page.

To use these locators, Selenium provides the By class, which locates elements within the DOM (The Document Object Model (DOM) is a programming interface for XML and HTML documents. It states the logical structure of the document and the way it is accessed and manipulated).
There are different locators like className, cssSelector, id, linkText, name, partialLinkText, tagName, and XPath, etc., which can identify the unique or specific element based on various attributes. 

### 3. POM file

In Java, there are dependency management and build solution tools. Maven and Gradle are the most common for Selenium. 

The Maven solution introduces a project object model file - POM file which is an XML structure file. Every time a change is made to the project code, it updates the build status and continuously maintains and monitors the framework components (various parts and libraries that your project depends on) and build (compilation of tests, dependancy management). It ensures everything is set up correctly for you to run your tests smoothly. Maven "continuously maintains and monitors" this setup to make sure your project builds successfully every time changes are made.

### 4. How to start

public class Main { // Declares a class named 'Main'

    public static void main(String[] args) { // Main method where program execution starts
    
        WebDriver driver = new ChromeDriver(); // Creates a new instance of the ChromeDriver, a WebDriver implementation for Chrome
        
        driver.manage().window().maximize(); // Maximizes the browser window
        
        driver.get("https://www.example.com"); // Navigates to the specified URL ("https://www.example.com")
        
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5)); // Sets an implicit wait of 5 seconds, allowing WebDriver to wait for elements to appear before throwing an exception (error)
        
        driver.findElement(By.id("CookieOptinAllowAll")).click(); // Locates an element with the ID "CookieOptinAllowAll" and simulates a click action on it

### 5. Common methods

#### 5.1. Browser Control

       manage() - interacts with the browser's settings and capabilities. It provides access to manage things like window size, cookies, timeouts, and other browser-level operations.

       findElement() - finds the first element using the given selector.

       findElements() - finds all elements within the current page using the given locator.

       getTitle() - gets the title of the current page.

       close() - closes the current window and if it is the last window, closes the browser.

       quit() - terminates the driver closing all associated window.

#### 5.2. Basic interactions that can be done on a web element

       sendKeys(string) - enters the string or characters that is specified in the element.

       click() - clicks on the element.

       getText() - retrieves the text present in the element.

       clear() - clears the text present in the element.

#### 5.3. Waits

Implicit Wait is a global wait, applied to all elements in a script, causing Selenium WebDriver to wait for a certain amount of time before throwing a NoSuchElementException.

           Example: driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));

Explicit Wait is a conditional wait, applied to specific elements, making the WebDriver wait until a certain condition is met.

           Example: 

           WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(5)); 

           wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("example Id")));

Difference: Implicit Wait is set once and applies throughout the script, whereas Explicit Wait is specified for individual elements.

#### 5.4. XPath

What is XPath? XPath is a language used to locate elements on a web page.

There are two main types of XPath: Absolute XPath and Relative XPath.

        Absolute XPath: Starts from the root node and follows a specific path to the element, which we want to identify. It's less flexible because any change in the path will break 
        the XPath.
        The key characteristic of XPath is that it begins with the single forward slash (/).

        Relative XPath: Starts from any node and allows for more flexible paths. A relative XPath starts with the // symbol. It is mainly used for automation since even if an element is
        removed or added in the DOM, the relative XPath is not impacted.

An absolute XPath is long and difficult to maintain (html/body/tagname/…). While a relative XPath is short (//*[@attribute='value']).

Example of html: 


![image](https://github.com/user-attachments/assets/0c05abb0-4c6a-4523-9d8b-3add17d4b8d4)

Example of XPaths:

•	Absolute XPath to the paragraph:

    /html/body/div[1]/div/p
    
•	Relative XPath to the paragraph:

    //div[@id='container']//p
    
•	XPath using text for the link:

    //a[contains(text(),'Click here')]
    
    WebElement link = driver.findElement(By.xpath("//a[contains(text(),'Click here')]"));
                          
•	XPath using attribute for the div with class "content":

    //div[@class='content']
                        
    WebElement contentDiv = driver.findElement(By.xpath("//div[@class='content']"));

### 6. TestNG definition

TestNG is a testing framework for the Java programming language. The design goal of TestNG is to cover a wider range of test categories: unit, functional, end-to-end, integration, etc., with powerful and easy-to-use functionalities.

A TestNG xml file is a configuration file used in the TestNG framework to organize and run your test cases. It allows you to define:

          - test suites, 

          - test classes,

          - test methods, 

and making it easier to manage and execute your tests.

### 7. TestNG installation

When you install TestNG in your project, the TestNG configuration XML file does not automatically appear. You need to create the TestNG XML file manually. It allows you to customize and organize your tests according to your specific requirements. You can name it whatever you like, typically something like testng.xml, and place it in your project directory. Then, you can configure it as needed using the < suite >, < test >, and < class > tags.

       •	Suite: Represents a collection of tests and is defined by the <suite> tag.

       •	Test: Represents a group of test classes and is defined by the <test> tag.

       •	Class: Represents a Java class containing test methods and is defined by the <class> tag.

       •	Test Method: Represents individual test methods annotated with @Test in your Java class.

Example of a simple TestNG XML file:

     <!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
        <suite name="MySuite">
          <test name="MyTest">
            <classes>
               <class name="com.example.MyTestClass"/>
            </classes>
          </test>
       </suite>
          
This file defines a suite named "MySuite" with a single test named "MyTest," which includes one test class "com.example.MyTestClass."

### 8. TestNG features

TestNG offers a wide range of properties and features that make it a powerful framework. Here are some:

     Parallel Execution: TestNG supports parallel execution of tests by configuring the parallel attribute in the XML file. You can run tests in parallel at the suite, test, class, or 
     method level.

     Reports: TestNG generates detailed HTML and XML reports by default, which provide insights into the test execution and results.

     Assertions: TestNG provides a rich set of assertions that help validate test results.

     Annotations: TestNG provides a variety of annotations such as @Test, @BeforeClass, @AfterClass, @BeforeMethod, @AfterMethod, etc., to control the test flow.

#### 8.1. Main Annotations

@Test: Marks a method as a test method. This method will run as a test case.

@BeforeClass: Runs once before any test methods in the class. Used for one-time setup, like initializing resources.

@AfterClass: Runs once after all test methods in the class. Used for one-time cleanup, like releasing resources.

@BeforeMethod: Runs before each test method. Used for setting up preconditions for tests.

@AfterMethod: Runs after each test method. Used for cleanup after tests.



(I will keep adding information...).
