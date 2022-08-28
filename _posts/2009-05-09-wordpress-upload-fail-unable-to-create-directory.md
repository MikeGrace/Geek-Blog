---
title: 'WordPress upload fail &#8211; unable to create directory&#8230;'
date: 2009-05-09T01:32:45+00:00
author: MikeGrace
layout: post
permalink: /2009/05/wordpress-upload-fail-unable-to-create-directory/
categories:
  - How to
  - Web Design -Dev
tags:
  - blog
  - Database
  - fail
  - fix
  - upload
  - WordPress
---
[<img class="aligncenter size-full wp-image-149" title="wordpress_bigger" src="/assets/2009/05/wordpress_bigger.jpg" alt="wordpress_bigger" width="150" height="150" />](/assets/2009/05/wordpress_bigger.jpg)

**Error Message:** Unable to create directory &#8230; {long directory path} &#8230; Is its parent directory writable by the server?

**Cause**: I recently changed hosting services so when I migrated my blog over to the new server everything worked great except for my WordPress uploads. Most things in WordPress are kept relative and ask the server where things are but the path to the upload files are kept in the database so if you change servers without changing the database string pointing to the correct directory you will get an error and probably frustrated also.

UPDATE 05/25/09

Thanks to a comment from [Matt Lindsay](http://mattlindsaydesign.com) I now realize that there is a much easier way to update the wordpress upload string in the database than digging into the actual database. A big thanks goes out to matt for making my blog better. ; )

**Quicker and easier fix**

  1. Login to your WordPress Admin
  2. Go to &#8220;Settings&#8221;
  3. Select &#8220;Miscellaneous&#8221;
  4. Put the correct path in the input field labeled &#8220;Full URL path to files&#8221;
  5. Save the changes and you should be done

<img class="aligncenter size-full wp-image-213" title="picture-11" src="/assets/2009/05/picture-11.png" alt="picture-11" width="600" height="231" srcset="/assets/2009/05/picture-11.png 600w, /assets/2009/05/picture-11-300x115.png 300w" sizes="(max-width: 600px) 100vw, 600px" />

The advantage I had in digging into the database is that when I switched hosting services only one of the folders in the path changed so I went in and just modified the one folder. This is nice if you don&#8217;t know the exact file path from the server root like me. ; )

**Older more complicated fix:**

  1. Login to your database for the WordPress blog.
  2. Browse/ view tables in the database created when setting up the blog
  3. Browse/ view table named &#8220;wp_options&#8221;
  4. In the &#8220;option\_name&#8221; column look for &#8220;upload\_path&#8221; (was #60 for me)
  5. Edit the row values and change to the correct path
  6. Save changes

[<img class="aligncenter size-full wp-image-148" title="picture-4" src="/assets/2009/05/picture-4.jpg" alt="picture-4" width="587" height="350" srcset="/assets/2009/05/picture-4.jpg 587w, /assets/2009/05/picture-4-300x178.jpg 300w" sizes="(max-width: 587px) 100vw, 587px" />](/assets/2009/05/picture-4.jpg)

After making that change the problem should be fixed and uploading will now work. If this helped be sure to give me a shout and leave a comment. Best of luck to you. ; )

Sources:
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
I figured this out all on my own. ; ) #HappyGeek