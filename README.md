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

public class Main {

    public static void main(String[] args) {
    
        WebDriver driver = new ChromeDriver();
        
        driver.manage().window().maximize();
        
        driver.get("https://www.example.com");
        
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));
        
        driver.findElement(By.id("CookieOptinAllowAll")).click();

(I will keep adding information...).
