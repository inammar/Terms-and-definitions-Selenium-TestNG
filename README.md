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

### 3. How to start

public class Main { // Declares a class named 'Main'

    public static void main(String[] args) { // Main method where program execution starts
    
        WebDriver driver = new ChromeDriver(); // Creates a new instance of the ChromeDriver, a WebDriver implementation for Chrome
        
        driver.manage().window().maximize(); // Maximizes the browser window
        
        driver.get("https://www.example.com"); // Navigates to the specified URL ("https://www.example.com")
        
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5)); // Sets an implicit wait of 5 seconds, allowing WebDriver to wait for elements to appear before throwing an exception (error)
        
        driver.findElement(By.id("CookieOptinAllowAll")).click(); // Locates an element with the ID "CookieOptinAllowAll" and simulates a click action on it

### 4. Common methods

manage() - interacts with the browser's settings and capabilities. It provides access to manage things like window size, cookies, timeouts, and other browser-level operations.

findElement() - finds the first element using the given selector.

findElements() - finds all elements within the current page using the given locator.

getTitle() - gets the title of the current page.

close() - closes the current window and if it is the last window, closes the browser.

quit() - terminates the driver closing all associated window.



(I will keep adding information...).
