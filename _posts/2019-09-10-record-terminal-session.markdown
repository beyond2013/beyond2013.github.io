---
layout: default
title:  "Recording Terminal Sessions in Ubuntu"
comments: true
categories: terminal recording 
---

I have struggled when student asked me to provided them all the commands I ran in terminal (mostly MySQL queries). 

I recently came across a very nice tool to record terminal sessions in ubuntu. The name of the tool is asciinema:

1. Install it using 

```bash 
apt install asciinema
```
2. Record session by issuing 

```bash
asciinema rec
```

3. When done press Ctrl+D, it will prompt you to save the file
4. To play the recorded file use

```bash 
asciinema play filename
```

5. plenty of [usage options](https://asciinema.org/docs/usage) i am yet to explore
