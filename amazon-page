import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class AmazonPage 
{

	
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
       driver.get("https://www.amazon.in/");
       
       try {
    	   WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(60));
    	   
    	   WebElement searchBox = wait.until(ExpectedConditions.elementToBeClickable(By.id("twotabsearchtextbox")));
           searchBox.sendKeys("iPhone 15plus (128GB) - Blue");
       
           WebElement searchButton = wait.until(ExpectedConditions.elementToBeClickable(By.id("nav-search-submit-button")));
           searchButton.click();
           
           WebElement result = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//span[contains(text(),'iPhone 15plus (128GB) - Blue')]")));
           result.click();
           
   		
           String iphonePrice = getIphonePrice();
           System.out.println("Price from Amazon: " + iphonePrice);
    }
    catch(Exception ex)
	{
    	 System.out.println("Error: " + ex.getMessage());
	}
       finally {
           driver.quit(); 
       }
    }
   
       public String getIphonePrice() 
       {
           
		WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(60));
		
		try
		{
            //WebElement WholePriceElement = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//span[@class='a-price-whole']")));
 WebElement priceElement = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//span[contains(@class, 'a-price')]")));
            
            // Print out the price element and its text content to debug
            System.out.println("Found the price element: " + priceElement.getText());
            return priceElement.getText();
		}
		catch (Exception e) {
            System.out.println("Price element not found: " + e.getMessage());
            return "Price not found";
		}
    }
   
    }    
