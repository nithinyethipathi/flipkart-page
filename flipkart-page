import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class FlipkartPage {
public static WebDriver driver;
	

    @BeforeTest
    public void setUp() {
       System.setProperty("webdriver.chrome.driver","c:\\chromedriver.exe");
        driver = new ChromeDriver();
        
        driver.manage().window().maximize();
    }

    @Test
    public void loginPage() 
    {
       driver.get("https://www.flipkart.com/");
       
       try {
    	   WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(60));
    	   
    	   WebElement searchBox = wait.until(ExpectedConditions.elementToBeClickable(By.name("q")));
           searchBox.sendKeys("Apple iPhone 15plus (128GB) - Blue");
       
           WebElement searchButton = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//button[@type='submit']")));
           searchButton.click();
           
           WebElement result = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//a[contains(@href, 'iphone-15-plus')]")));
           
   		
           String iphonePrice = getIphonePrice();
           System.out.println("Price from Flipkart: " + iphonePrice);
    }
    catch(Exception ex)
	{
    	 System.out.println("Error: " + ex.getMessage());
	}
       finally {
           driver.quit(); 
       }
    }
   
    public String getIphonePrice() {
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(60));

        try {
            
           
            WebElement priceElement = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//div[@class='Nx9bqj _4b5DiR']")));

            System.out.println("Found the price element: " + priceElement.getText());
            return priceElement.getText();
		}
		catch (Exception e) {
            System.out.println("Price element not found: " + e.getMessage());
            return "Price not found";
		}
    }
   
    }    
