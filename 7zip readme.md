

zip a file.........

    7z a -tzip "C:\Users\Perfect\Desktop\chrone job\File Splitter\test.zip" "C:\Users\Perfect\Desktop\chrone job\File Splitter\sample.bak"



Split a large file into parts and zip.....(3mb size)
    // from 7zip directory
        7z a -v3m "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip" "C:\Users\Perfect\Desktop\chrone job\File Splitter\sample.bak"

    // path other than 7zip
        "C:\Program Files\7-Zip\7z.exe" a -v3m "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip" "C:\Users\Perfect\Desktop\chrone job\File Splitter\sample.bak"



Extract a zip........
    // from 7zip directory
        7z e "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip.001" -y -o"C:\Users\Perfect\Desktop\chrone job\File Splitter\merged file"

    // path other than 7zip
        "C:\Program Files\7-Zip\7z.exe" e "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip.001" -y -o"C:\Users\Perfect\Desktop\chrone job\File Splitter\merged file" 


Delete all files of a directory...........
    del /q destination\*



Task sheduler with arguments (split file)....
    1. MyComputer > Manage > Task Sheduler > Create Basic Task
    2. Give name to task and description(optional)
    3. Select when to execute task. > Next
    4. Action > Start a program > next
    5. In "program script" browse location of 7z.exe and select it. e.g "C:\Program Files\7-Zip\7z.exe"
    6. In "add arguments (optional)" enter argument for 7zip i.e.
         a -v3m "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip" "C:\Users\Perfect\Desktop\chrone job\File Splitter\sample.bak"

Task sheduler with .bat file (split file)....
    >> create a file with extension .bat and put following content in file 
        @ ehco off
        "C:\Program Files\7-Zip\7z.exe" a -v3m "destination\zipname.zip" "source\filename.ext"

        e.g @ ehco off 
            "C:\Program Files\7-Zip\7z.exe" a -v3m "C:\Users\Perfect\Desktop\chrone job\File Splitter\splits\part.zip" "C:\Users\Perfect\Desktop\chrone job\File Splitter\sample.bak"

    1. MyComputer > Manage > Task Sheduler > Create Basic Task
    2. Give name to task and description(optional)
    3. Select when to execute task. > Next
    4. Action > Start a program > next
    5. In "program script" browse location of your .bat file and select it. 
        e.g     "C:\Users\Perfect\Desktop\chrone job\File Splitter\FileSplit.bat"
    



Task sheduler with .bat file (send mail)....
    >> create a file with extension .bat and put following content in file 
       "D:\wamp64\bin\php\php5.6.25\php.exe" -f "D:\wamp64\www\split_and_mail\sendmail.php"

    1. MyComputer > Manage > Task Sheduler > Create Basic Task
    2. Give name to task and description(optional)
    3. Select when to execute task. > Next
    4. Action > Start a program > next
    5. In "program script" browse location of your .bat file and select it. 
        e.g     "C:\Users\Perfect\Desktop\chrone job\File Splitter\FileSplit.bat"