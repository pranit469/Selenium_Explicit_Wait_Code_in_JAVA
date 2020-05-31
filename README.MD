import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
 
public class ExplicitWaitDemo {
 
	public static void main(String[] args) {
 
		  // Start browser
		  WebDriver driver = new ChromeDriver();
 
		  // Start application
		  driver.get("http://seleniumpractise.blogspot.in/2016/08/how-to-use-explicit-wait-in-selenium.html");
      driver.findElement(By.xpath("//button[text()='Click me to start timer']")).click();
			WebDriverWait wait = new WebDriverWait(driver, 20);
			WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocate			d(By.xpath(“//p[text()=‘WebDriver’]”)));
			boolean status = element.isDisplayed();
 
			if (status) {
			System.out.println("===== WebDriver is visible======");
			}
			else {
			System.out.println("===== WebDriver is not visible======");
			}
		}
	}
