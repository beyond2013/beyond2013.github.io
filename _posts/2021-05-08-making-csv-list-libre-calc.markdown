---
layout: default
title:  "How to create a csv list in libre Calc"
date:  2021-05-08 
comments: true
categories: csv list Libre Calc TEXTJOIN EXACT IF RIGHT
---

We were recording attendance of students on spreadsheets this way

![Spreadsheet used for recording attendance of students]({{ site.baseurl }}/assets/images/blog.png "Spread Sheet used to record attendance")

1. The R.No. column contained student's Roll Number like 2017-BS(CS)-E-01 
2. The column for date contained either P or A showing whether the student was present or absent.

Thanks to one of our faculty we now have CMS that would allow to store attendance. Now we have to populate all the data from spread sheets to the CMS.

The CMS requires a comma separated list of roll numbers, and following is how I obtained the information in the desired format.

1. In the first step I transformed all P's to the corresponding roll numbers using the following formula:

`=IF(EXACT(C3,"P"),RIGHT($B3,2),"")`
- 
  - which uses `exact()` function to check if the value in attendance column is equal to "P"
	- and the `right()` function returns the last two digits from the right of the roll number column, the dollar symbol is required so that when the formula is dragged the column remains fixed.
	- and `if()` functions which returns the roll number if the value is "P" otherwise it returns nothing
- The image below displays what I achieved 

![Roll numbers of students]({{ site.baseurl }}/assets/images/step1.png "Roll Numbers of present students")

2. The second and last step is to join the roll numbers with commas in between, which is achieved using TEXTJOIN  

`=TEXTJOIN(",", 1,C18:C31)` 

- The first argument to `TEXTJOIN` is delimiter, second argument 1 means I want to skip blank cells and the last argument is the range of values to convert

![Resulting csv list]({{ site.baseurl }}/assets/images/result.png "Resulting csv list")

- [Link to the attendance spreadsheet containing all working]({{ site.baseurl }}/assets/attendance.ods)
