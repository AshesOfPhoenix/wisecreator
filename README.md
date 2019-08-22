# WiseCreator

You can create wordwise enabled .mobi files for Amazon Kindle by using
- either [standalone executables](#standalone) or
- [pure python script](#script) (runs faster)

---

## standalone

1. You need to have [calibre](https://calibre-ebook.com/) on your device.
2. If you are on windows, download [executables/wisecreator.exe](https://github.com/tmilovanov/wisecreator/blob/master/executables/wisecreator.exe)
3. If you are on linux, download [executables/wisecreator](https://github.com/tmilovanov/wisecreator/blob/master/executables/wisecreator)
4. Finally run the below commands in a shell  
    Windows: `wisecreator.exe PATH_TO_YOUR_MOBI_BOOK`   
    Linux &nbsp; &nbsp; &nbsp;: `./wisecreator PATH_TO_YOUR_MOBI_BOOK`

*You can move standalone wisecreator file anywhere you like on your computer, but if you are using calibre portable, make sure you add  your calibre portable folder to the PATH environment variable*  

## script

1.  You need to have [calibre](https://calibre-ebook.com/) on your device.  
2.	To run the script you need to have [Python3](https://www.python.org/downloads/)  
3. 	Make sure you have these Python libs:  
	[NLTK](http://www.nltk.org/) - `pip install nltk` 
	cursor - `pip install cursor`
	sqlite3 - included in standard library, or if your python has been built from source, use `pip install pysqlite3`
4. 	Run wisecreator:  
    `./main.py PATH_TO_YOUR_MOBI_BOOK`

*calibre console utility "ebook-convert" is used inside the script*

---

## Kindle Android app

1. You need to have [root access](https://www.xda-developers.com/root/) to your android phone.
2. Follow the script or executable and get new .mobi and .kll files
3. Rename `LanguageLayer.en.ASIN.kll` to `WordWise.en.ASIN.db`
4. Push the .mobi book to `Android/data/com.amazon.kindle/files`
5. Push the WordWise.en.ASIN.db file to `/data/user/0/com.amazon.kindle/databases`. You need root access for this.
6. set the permissions for the wordwise file by running `chcon u:object_r:app_data_file:s0:c512,c768 [filename].db` from a terminal emulator app or via adb shell at the above path.

---

To develop:

You need pyinstaller to pack executables. You can install it with pip.
