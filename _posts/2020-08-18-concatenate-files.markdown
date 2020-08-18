---
layout: default
title:  "Concatenating files on ubuntu terminal"
date:   2020-08-18 16:30 
comments: true
categories: concatenate files ubuntu terminal
---

I had scanned a book and ran OCR to obtain several text files with the following pattern:

`graph-1.txt, graph-2.txt, graph-3.txt, ....., graph-10.txt`

I wanted to concatenate the text of all files into one. Googled on how to do it and found several useful links:

- [Stack Overflow](https://stackoverflow.com/questions/5917413/concatenate-multiple-files-but-include-filename-as-section-headers)
- [How-To Geek](https://www.howtogeek.com/448446/how-to-use-the-ls-command-on-linux/)

One of the problems when concatenating file is to sort files and `ls graph* -r -t ` helped. The `-t` option sorts files in descending order according to the modification time i.e. most recently modified file first. To reverse the sorting order use `-r` option. This information is provided by the How-To Geek link above.

To concatenate the contents of the file I took help by modifying one of the answers provided in response to the Stack Overflow question (see the link above).

The snippet I used is as follows:

```bash
for file in `ls graph* -t -r`; do cat "$file" >> allgraph.txt;done;
```

Which results in `allgraph.txt` containing the contents of all files.
