package initialize;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.By.ById;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.edge.EdgeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;

public class SpiceJet {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		WebDriver driver = new EdgeDriver();
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
		driver.get("https://www.spicejet.com");


	driver.findElement(By.id("ctl00_mainContent_ddl_originStation1_CTXTaction")).click();
	driver.findElement(By.linkText("Mumbai (BOM)")).click();
	Thread.sleep(3000);
	driver.findElement(By.id("ctl00_mainContent_ddl_destinationStation1_CTXTaction")).click();
	driver.findElement(By.linkText("Delhi (DEL)")).click();
	Thread.sleep(3000);

	Actions act = new Actions(driver);
	act.moveToElement(driver.findElement(By.linkText("19"))).build().perform();
	driver.findElement(By.linkText("19")).click();
	Thread.sleep(3000);

//	act.moveToElement(driver.findElement(By.linkText("25"))).build().perform();
//	driver.findElement(By.linkText("25")).click();
	
	driver.findElement(By.className("paxinfo")).click();
    for(int i=0;i<=3;i++)
    {  
	driver.findElement(By.id("hrefIncAdt")).click();
	i=i+1;
    }	
    Thread.sleep(3000);
    driver.findElement(By.id("btnclosepaxoption")).click();
    
   Select sc=new Select(driver.findElement(By.id("ctl00_mainContent_DropDownListCurrency")));
   sc.selectByValue("AED");
   Thread.sleep(3000);
   driver.findElement(By.id("ctl00_mainContent_btn_FindFlights")).click();
   
	}

}
