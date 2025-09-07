# lyrics-generation-steps
This repository lists the steps for generation of initial files for lyrics of Bethesda Songs Android App

### Other Repositories

1. https://github.com/tejeshwar-p/lyrics-content-generator
2. https://github.com/tejeshwar-p/telugu-lipi-editor/
3. https://github.com/tejeshwar-p/lyrics-android-app

### Tools required

1. GraalVM - version 17+ - (https://www.oracle.com/java/technologies/downloads/#graalvmjava17)
2. Git - https://git-scm.com/downloads
3. Github account - Create or login to your GitHub account.
4. TeluguLipi UniCode Editor - http://www.sirigina.com/TeluguLipiUnicodeSetupv1.21.exe
                               OR
                               https://github.com/tejeshwar-p/telugu-lipi-editor/releases/download/v1.0.0/v1.0.0.0.zip
                               OR
                               https://github.com/tejeshwar-p/telugu-lipi-editor/releases/download/v1.0.0/v1.2.0.0.zip
5. IntelliJ IDEA community edition
    *  For Intel Chips - https://www.jetbrains.com/idea/download/download-thanks.html?platform=mac&code=IIC
    * For Apple Silicon - https://www.jetbrains.com/idea/download/download-thanks.html?platform=macM1&code=IIC

### Part A - Manual Process

1. Open **Songs.xlsx** file and duplicate the **Bethesda Songs** sheet at bottom.
2. Rename the new sheet to **Bethesda Songs 2** or **Bethesda Songs \<Current date\>** whatever works for you.
3. Use the **TeluguLipi UniCode Editor** to create new songs and paste them as new row at the end of the new sheet.
4. Make sure to manually check all the details in the row as per existing format. DO NOT MISS ANY COLUMN DATA.
5. Just increment Song Number column. It might be more than S.No which is fine.
6. Double check all the data of the new song row.
7. Repeat steps 3 to 6 for adding other new songs one by one.

### Part B - Lyrics Generation using new Songs.xlsx sheet 

1. Download GraalVM - (https://www.oracle.com/java/technologies/downloads/#graalvmjava17)

2. Extract GraalVM compressed archive to a new local folder.

3. Checkout the code from the GitHub repo into your local folder -> https://github.com/tejeshwar-p/lyrics-content-generator

4. Setup GraalVM location if your IDE is not able to find automatically by following below steps - 
    * In IDE, Go to **Main Menu** (📄) -> **File** -> **Project Structure**
    * In **Project Structure** -> **Project Settings** -> **Project** -> **SDK**
    * In **SDK** -> Click on dropdown and add the path to your GraalVM extracted directory.

5. Open IntelliJ IDEA and open the above lyrics-content-generator project.

6. In `LyricsApplication.java` ->
comment these two lines -
```java
/*HtmlToXlsxConverter.convert();
		Thread.sleep(1000);*/
```

7. In `ScriptGenerator.java` ->
   - modify inputFilePath to your local location to Songs.xlsx file.
   - modify sheetName to the new sheet name within Songs.xlsx.

8. Run `LyricsApplication.java` using Run button (▶️) in IDE.

9. An SQL file will be generated in the project folder with name - SongsDDLAndDMLScripts.sql

10. Share that new **SQL file** and **Songs.xlsx** sheet through email.
