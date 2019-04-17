package test;

import java.time.Duration;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.edge.EdgeDriver;
import org.openqa.selenium.interactions.Actions;

public class OpenEmr {
	public static void main(String[] args) throws InterruptedException{
		WebDriver driver = new EdgeDriver();
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(20, TimeUnit.SECONDS);
		driver.get("https://demo.openemr.io/d/openemr/interface/login/login.php?site=default");
		driver.findElement(By.id("authUser")).sendKeys("admin");
		Thread.sleep(2000);
		driver.findElement(By.id("clearPass")).sendKeys("pass");
		Thread.sleep(2000);
		driver.findElement(By.className("btn btn-default btn-lg")).click();
		Actions act = new Actions(driver);
		act.moveToElement(driver.findElement(By.xpath("//div[text()='Patient/Client']"))).build().perform();
		act
			.keyDown(Keys.CONTROL)
			.pause(Duration.ofSeconds(1))
			.build()
			.perform();
		driver.findElement(By.xpath("//div[text()='New/Search']")).click();
		driver.switchTo().frame(driver.findElement(By.name("pat")));
		//firstname
		driver.findElement(By.name("form_fname")).sendKeys("Prasad");
		//lastname
		 driver.findElement(By.name("form_lname")).sendKeys("Jangam");
		 driver.findElement(By.name("form_fname")).sendKeys("Prasad");
		driver.findElement(By.id("form_DOB")).sendKeys("2019-04-17");
		//gender		
		driver.findElement(By.id("form_sex")).sendKeys("Male");
		driver.findElement(By.id("create")).click();
		driver.switchTo().defaultContent();
		driver.switchTo().frame(driver.findElement(By.id("modalframe")));
		driver.findElement(By.xpath("//input[@value='Confirm Create New Patient']")).click();
		   Thread.sleep(3000);
		    driver.switchTo().alert().accept();
		    driver.findElement(By.xpath("//div[@class='closeDlgIframe']")).click();
		    act.moveToElement(driver.findElement(By.xpath("//div[@class='menuSection userSection']"))).build().perform();
		    driver.findElement(By.xpath("//ul//li[text()='Logout']")).click();		
		
	}

}
