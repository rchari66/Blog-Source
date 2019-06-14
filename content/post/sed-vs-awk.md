---
title: "Sed vs Awk"
date: 2019-06-14T16:45:35Z
categories: ["new_post"]
draft: false
---

#### sed command
* Basics   
    ``` 
    -- Replace all 'foo' with 'bar' globally.
    $ sed -i 's/foo/bar/g' <filename>
    
    -- print line from 4 through 15
    $ sed -n '4,15p' <file name>
    
    -- exclude lines from 10 through 15
    $ sed '10,15d' <file-name>
    
    
    -- Display lines from different ranges
    $ sed -n -e '10,15p'-e '25,35p' <file-name>
    
    -- display content of a file after replacing a word
    $ sed 's/<word>/<new-word>/g' <file-name>
    
    -- replacing a word in a file
    $ sed -i 's/<word>/<new-word>/g' <file-name>
    
    
    -- replace a word and ignore case
    $ sed -i 's/<word>/<new-word>/gi' <file-name>
    ```
    
    ``` 
    -- Replace a word or characters in a range
    $ sed '30,50 s/<word>/<new-word/g'
    $ sed -i '30,50 s/<word>/<new-word/g'
    
    -- swiching multiple matches
    $ sed -i 's/ \(.*\):\(.*\)/\2, \1 /g'
    
    
    -- Replacing words only if seperate match is found.
    $ sed '/<pattern>/ s/<word>/<new-word>/g' msg.txt
    
    -- multiple replacements
    $ sed -i 's/that/this/gi;s/line/verse/gi' myfile.txt
    ```
* Ref: https://www.tecmint.com/linux-sed-command-tips-tricks/

#### AWK command
*  Awk basic usage
    ``` 
    Awk can take the following options:
    
    -F fs     To specify a file separator.
    -f file     To specify a file that contains awk script.
    -v var=value     To declare a variable.
    ```
    ``` 
    $ awk 'pattern {action}' input-file > output-file
    
    -- print 5th column from lines those match the pattern
    $ awk 'word {print $5}' input-file
    
    
    -- seperate by field(-F) and print 2nd column
    $ awk -F, '{print $2}'
    
    -- If fieds are numbers, aws can run commands on them
    $ awk '{ print ($2 * $3) + $7 }' input-file
    
    -- Replace second field
    $ echo "Hello Tom" | awk '{$2="Adam"; print $0}'
    Hello Adam
    $
    ```
---

* Awk Preprocessing
    
    ``` 
    -- Print first line "The File Contents" followed by content of the file.
    $ awk 'BEGIN {print "The File Contents:"}
    {print $0}' myfile
    
    -- prints first line and last line in between file's content
    $ awk 'BEGIN {print "The File Contents:"}
        {print $0}
        END {print "File footer"}' myfile
    ```
    ``` 
    -- Count number of lines in a file
     $ awk 'BEGIN {count=0;} {print $0; var++;} END {print count}' <filename>
     
    -- 
    ```
* Awk built-in variables
    ``` 
    FIELDWIDTHS     Specifies the field width.
    RS     Specifies the record separator.
    FS     Specifies the field separator.
    OFS  Specifies the Output separator.
    ORS  Specifies the Output separator.
    ```

* Awk Arrays
    ```
    $ awk 'BEGIN
            {
                array["key1"]="value1"; 
                array["key2"]["subkey1"]="subvalue1";
                
                print array["key1"];
                print array["key2"]["subkey1"];
            }'
            
    -- tp delete array element
    $ awk 'BEGIN
            {
                array["key"]="value"
                print array["key"]
                
                delete array["key"]
                
                # Below line prints nothing.
                print array["key"]
            
            }'
            
            
    -- Default value of array[key] is 0, when used in aithmatic operations
    $ awk 'BEGIN {array["key"]++; print array["key"]}'   
    1
    Ref here : https://www.gnu.org/software/gawk/manual/html_node/Uninitialized-Subscripts.html#Uninitialized-Subscripts
    ```
* Multidimentional Arrays in Awk
    ``` 
    $ awk 'BEGIN {vector["a", "aa"] = "Hello World!";  print vector["a", "aa"]}'
    
    ```
* Sorting Arrays
    ``` 
    Ref: https://www.gnu.org/software/gawk/manual/html_node/Controlling-Scanning.html#Controlling-Scanning
    ```
Note: 
    Semicolon(;) is not required if one line is standalone statement. 
    Semicolon is needed to sperate multiple statements in one line.


Ref: 

https://likegeeks.com/awk-command/

https://www.lifewire.com/write-awk-commands-and-scripts-2200573

https://www.gnu.org/software/gawk/manual/html_node/Arrays.html#Arrays
