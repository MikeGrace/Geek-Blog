---
title: Determine if text in google spreadsheet cell exists in text in another column of cells
date: 2015-02-18T15:54:53+00:00
author: MikeGrace
layout: post
permalink: /2015/02/determine-if-text-in-google-spreadsheet-cell-exists-in-text-in-another-column-of-cells/
categories:
  - Google
  - How to
---
I had a email newsletter list with name and email addresses listed. I also had a different list of emails that needed to be removed from that list. I used this google spreadsheet cell formula to check to see if the current row&#8217;s email was in the list of emails in the next column. Once I had them marked I used [Delete a row in google spreadsheets based on value of cell](http://geek.michaelgrace.org/2015/02/delete-a-row-in-google-spreadsheets-based-on-value-of-cell/) to remove the row.

<pre><span class=" default-formula-text-color" dir="auto">=</span><span class=" default-formula-text-color" dir="auto">IF</span><span class=" default-formula-text-color" dir="auto">(</span> <span class=" default-formula-text-color" dir="auto">COUNTA</span><span class=" default-formula-text-color" dir="auto">(</span> <span class=" default-formula-text-color" dir="auto">IFERROR</span><span class=" default-formula-text-color" dir="auto">(</span> <span class=" default-formula-text-color" dir="auto">FILTER</span><span class=" default-formula-text-color" dir="auto">(</span><span dir="auto">$E$1:$E$97</span> <span class=" default-formula-text-color" dir="auto">,</span> <span dir="auto">$E$1:$E$97</span><span class="  default-formula-text-color" dir="auto">=</span><span dir="auto">C2</span> <span class=" default-formula-text-color" dir="auto">)</span> <span class=" default-formula-text-color" dir="auto">)</span> <span class=" default-formula-text-color" dir="auto">)</span> <span class=" default-formula-text-color" dir="auto">,</span> <span class=" string " dir="auto">"Yes"</span> <span class=" default-formula-text-color" dir="auto">,</span> <span class=" string " dir="auto">"No"</span> <span class=" default-formula-text-color" dir="auto">)

<a href="http://mikegrace.s3.amazonaws.com/geek-blog/text-in-cell-matches-text-in-column-google-spreadsheet.png"><img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/text-in-cell-matches-text-in-column-google-spreadsheet.png" alt="" width="804" height="350" /></a></span></pre>