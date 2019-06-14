---
title: "Sed vs Awk"
date: 2019-06-14T16:45:35Z
categories: ["new_post"]
draft: false
---

#### sed command
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
Ref: https://www.tecmint.com/linux-sed-command-tips-tricks/

#### awk command
``` 
$ awk 'pattern {action}' input-file > output-file

-- print 5th column from lines those match the pattern
$ awk 'word {print $5}' input-file


-- seperate by field(-F) and print 2nd column
$ awk -F, '{print $2}'

```
Ref: https://likegeeks.com/awk-command/
https://www.lifewire.com/write-awk-commands-and-scripts-2200573
