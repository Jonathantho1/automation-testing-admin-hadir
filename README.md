# Automation Testing for Web Admin Hadir

**This program build to do automation testing for Admin Hadir Website. The Framework that used to build this automation testing are TestNG, Selenium, Cucumber, Common.io, and Extend-report.**

**Note: Only change some part that told to change on this noted for the website and the program. Other than that, do not change it.**

## Changes
### Codes
**Notes:**

**- test files path:** automation-testing-admin-hadir\src\test\java\com\juaracoding    

**- pages files path:** automation-testing-admin-hadir\src\main\java\com\juaracoding\pages

**- change input here:** place to update

1. Assert change for "Data berhasil ditambahkan ke unit setting" on TestManagementUnitSetting.java
```
update assertion to the newest date
Example date: today date is November 3rd, 2023 change to 3 Nov 2023

@Then("Data berhasil ditambahkan ke unit setting")
    public void data_berhasil_ditambahkan_unit_setting(){
        Assert.assertEquals(managementUnitSettingPage.getNamaDepartment(),"ABC Compe");
        Assert.assertEquals(managementUnitSettingPage.getTanggalBuat(),"Change input here");
        Assert.assertEquals(managementUnitSettingPage.getTanggalUpdate(),"Change input here");
        extentTest.log(LogStatus.PASS,"Data berhasil ditambahkan ke unit setting");
    }
```
2. Assert change for "Data client upliner terbuat" and input change "Upload foto client upliner" on TestManagementUnitSetting.java and locator change for "tanggalDiBuat" on ManagementClientUplinerPage.java
```
update locator to the  newest  date
Example date: today date is November 3rd, 2023 change to 3 Nov 2023

@FindBy(xpath = "//h6[normalize-space()='Change input here']")
private WebElement tanggalDiBuat;
```
```
update assertion to the  newest  date
Example date: today date is November 3rd, 2023 change to 3 Nov 2023

@Then("Data client upliner terbuat")
    public void data_client_upliner_terbuat(){
        Assert.assertEquals(managementClientUplinerPage.getNama(),"John Doe");
        Assert.assertEquals(managementClientUplinerPage.getEmail(),"JohnDoe@yahoo.com");
        Assert.assertEquals(managementClientUplinerPage.getUnit(),"ABC Compe");
        Assert.assertEquals(managementClientUplinerPage.getTanggalDiBuat(),"Change input here");
        extentTest.log(LogStatus.PASS,"Data client upliner terbuat");
    }
```
```
put your photo's path on setInputPathImage

@And("Upload foto client upliner")
    public void upload_foto(){
        managementClientUplinerPage.setInputPathImage("Put path's photo here must less than 2MB");
        extentTest.log(LogStatus.PASS,"Upload foto client upliner");
    }
```

3. Assert change for "Mendapatkan data input" on TestManagementPosisi.java
```
noted: if the program failed, you need to change the assertion to the latest        
       updated date. If not, don't need to change anything to this program
Example date: today date is November 3rd, 2023 change to 3 Nov 2023

@Then("Mendapatkan data input")
    public void mendapatkan_data_input(){
        Assert.assertEquals(managementPosisiPage.getNamaDivisi(),"ABC HRD");
        Assert.assertEquals(managementPosisiPage.getTanggalBuat(),"13 Nov 2023");
        Assert.assertEquals(managementPosisiPage.getTanggalUpdate(),"Change input here");
        extentTest.log(LogStatus.PASS,"Klik search posisi");
    }
```
### Website
**Notes:** do these steps if the files exist. the red circle mean delete the data, for the blue circle mean update the data to do so just click the kebab button on that data. 

Website: https://staging-hadir.ptkta.com/authentication/login username: admin@hadir.com password: admin@hadir

#### 1. management - Unit
![Unit](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/d4ce8849-d1ed-40d9-bd00-69e73fd6edf5)

#### 2. management - Posisi
Noted: if you see ABC IT Team change it to ABC HRD
![Posisi](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/7018eb8c-8598-40e6-bde7-d908b699f149)

#### 3. management - Client Upliner
![Client Upliner](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/595efef6-ad67-4aee-940f-dcc5b893ee46)

### WebDriver Path
   1. go to this path if you using Chrome (automation-testing-admin-hadir\src\main\java\com\juaracoding\drivers\strategies\Chrome.java)
   ```
       @Override
    public WebDriver setStrategy() {
        String path = "put your WebDriver path here";
        System.setProperty("webdriver.chrome.driver",path);
        ChromeOptions options = new ChromeOptions();
        options.setExperimentalOption("useAutomationExtension",false);
        options.addArguments("--no-sandbox");
        return new ChromeDriver(options);
    }
   ```
   2. go to this path if you using Mozilla FireFox (automation-testing-admin-hadir\src\main\java\com\juaracoding\drivers\strategies\Firefox.java)
   ```
   @Override
    public WebDriver setStrategy() {
        System.setProperty("webdriver.gecko.driver"," 'path to webdriver firefox' ");
        WebDriver driver = new FirefoxDriver();

        return driver;
    }
   ```
## Run the Program
go to automation-testing-admin-hadir\src\test\java\com\juaracoding\RunnerTest.java and run it

## Result
to see the result after running the program you can go to automation-testing-admin-hadir\target\cucumber-report.html or automation-testing-admin-hadir\target\extend-report.html

### Cucumber-report.hmtl
![image](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/6ffd7f2f-44fc-4355-8580-ad7e9c3cc2b3)
### extend-report.html
![image](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/cbf2216f-ba86-4ee0-8ab6-d70a7f5f1bbb)
![image](https://github.com/Jonathantho1/automation-testing-admin-hadir/assets/98079109/cd9f1755-011c-41b3-a5d8-a90c2da20e35)

## Notes
1. There's three **Failed Test** Input Nama Departement yang Sudah Ada Unit, Hidupkan Selfie Unit Setting, Invalid Nama Position Tanpa Divisi Posisi.
2. If you got any problem when running the program please to contact me on jonathantho13@gmail.com

   
