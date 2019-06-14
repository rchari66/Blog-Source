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
Ref: https://www.tecmint.com/linux-sed-command-tips-tricks/

#### awk command
``` 
$ awk 

```
Ref: https://likegeeks.com/awk-command/
https://www.lifewire.com/write-awk-commands-and-scripts-2200573

awk '{print $0}' file.name