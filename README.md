# firsttestkatalon
package com.example.tests;

import java.util.regex.Pattern;
import java.util.concurrent.TimeUnit;
import org.testng.annotations.*;
import static org.testng.Assert.*;
import org.openqa.selenium.*;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;

public class FirstTestKatalon {
  private WebDriver driver;
  private String baseUrl;
  private boolean acceptNextAlert = true;
  private StringBuffer verificationErrors = new StringBuffer();

  @BeforeClass(alwaysRun = true)
  public void setUp() throws Exception {
    driver = new FirefoxDriver();
    baseUrl = "https://www.katalon.com/";
    driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
  }

  @Test
  public void testFirstTestKatalon() throws Exception {
    driver.get("http://automationpractice.com/index.php?controller=authentication&back=my-account");
    driver.findElement(By.linkText("Sign in")).click();
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Email address'])[1]/following::span[1]")).click();
    driver.findElement(By.id("email_create")).click();
    driver.findElement(By.id("email_create")).clear();
    driver.findElement(By.id("email_create")).sendKeys("nv.butko.nv@gmail.com");
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Email address'])[1]/following::span[1]")).click();
    driver.findElement(By.id("id_gender2")).click();
    driver.findElement(By.id("customer_firstname")).click();
    driver.findElement(By.id("customer_firstname")).clear();
    driver.findElement(By.id("customer_firstname")).sendKeys("Natali");
    driver.findElement(By.id("customer_lastname")).click();
    driver.findElement(By.id("customer_lastname")).clear();
    driver.findElement(By.id("customer_lastname")).sendKeys("Butko");
    driver.findElement(By.id("email")).click();
    driver.findElement(By.id("passwd")).click();
    driver.findElement(By.id("passwd")).clear();
    driver.findElement(By.id("passwd")).sendKeys("natali91");
    driver.findElement(By.id("days")).click();
    new Select(driver.findElement(By.id("days"))).selectByVisibleText("regexp:2\\s+");
    driver.findElement(By.id("days")).click();
    driver.findElement(By.id("months")).click();
    new Select(driver.findElement(By.id("months"))).selectByVisibleText("regexp:March\\s");
    driver.findElement(By.id("months")).click();
    driver.findElement(By.id("years")).click();
    new Select(driver.findElement(By.id("years"))).selectByVisibleText("regexp:2005\\s+");
    driver.findElement(By.id("years")).click();
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Sign up for our newsletter!'])[1]/following::label[1]")).click();
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Date of Birth'])[1]/following::label[1]")).click();
    driver.findElement(By.id("firstname")).click();
    driver.findElement(By.id("lastname")).click();
    driver.findElement(By.id("company")).click();
    driver.findElement(By.id("company")).clear();
    driver.findElement(By.id("company")).sendKeys("Балтелектрон");
    driver.findElement(By.id("address1")).click();
    driver.findElement(By.id("address1")).clear();
    driver.findElement(By.id("address1")).sendKeys("Ukraine");
    driver.findElement(By.id("address2")).click();
    driver.findElement(By.id("address2")).clear();
    driver.findElement(By.id("address2")).sendKeys("testtex");
    driver.findElement(By.id("city")).click();
    driver.findElement(By.id("city")).clear();
    driver.findElement(By.id("city")).sendKeys("Запоріжжя");
    driver.findElement(By.id("id_state")).click();
    new Select(driver.findElement(By.id("id_state"))).selectByVisibleText("Arizona");
    driver.findElement(By.id("id_state")).click();
    driver.findElement(By.id("postcode")).click();
    driver.findElement(By.id("postcode")).clear();
    driver.findElement(By.id("postcode")).sendKeys("1111`");
    driver.findElement(By.id("id_country")).click();
    driver.findElement(By.id("id_country")).click();
    driver.findElement(By.id("phone_mobile")).click();
    driver.findElement(By.id("phone_mobile")).clear();
    driver.findElement(By.id("phone_mobile")).sendKeys("80981163722");
    driver.findElement(By.id("phone_mobile")).click();
    driver.findElement(By.id("phone_mobile")).clear();
    driver.findElement(By.id("phone_mobile")).sendKeys("+380981163722");
    driver.findElement(By.id("alias")).click();
    driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='DNI / NIF / NIE'])[1]/following::span[1]")).click();
    driver.findElement(By.id("address1")).click();
  }

  @AfterClass(alwaysRun = true)
  public void tearDown() throws Exception {
    driver.quit();
    String verificationErrorString = verificationErrors.toString();
    if (!"".equals(verificationErrorString)) {
      fail(verificationErrorString);
    }
  }

  private boolean isElementPresent(By by) {
    try {
      driver.findElement(by);
      return true;
    } catch (NoSuchElementException e) {
      return false;
    }
  }

  private boolean isAlertPresent() {
    try {
      driver.switchTo().alert();
      return true;
    } catch (NoAlertPresentException e) {
      return false;
    }
  }

  private String closeAlertAndGetItsText() {
    try {
      Alert alert = driver.switchTo().alert();
      String alertText = alert.getText();
      if (acceptNextAlert) {
        alert.accept();
      } else {
        alert.dismiss();
      }
      return alertText;
    } finally {
      acceptNextAlert = true;
    }
  }
}
