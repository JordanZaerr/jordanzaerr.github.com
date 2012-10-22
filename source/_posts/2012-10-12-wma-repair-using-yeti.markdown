---
layout: post
title: "WMA repair using Yeti"
date: 2012-10-12 13:11
comments: true
categories:
- Yeti
- WMA
---

Figured I would put this up here.

{% gist 3881245 %}

As you can see this is a simple one liner. It takes in the filename and will repair it in place. 
Making a copy of the file before it's repaired might be a good idea. This method reconstructs the header information
on the WMA file so that it is in a valid state again.  This fixes issues like players not knowing the length of a file,
not being able to skip through the file, and more importantly not being able to convert the file to another format or 
splicing/combining. You can alternatively pass a stream into the method instead of a file name. The second parameter should
almost always be false. It signifies if the file/stream being passed in is from a broadcast.

Some notible classes would be the FileProperties
{% gist 3881775 %}

and DataProperties
{% gist 3881787 %}

These are the classes that read and write the header information about your file.
The header/section guid's from the ASF spec are in Yeti for the other header/sections but the classes 
haven't been created that to read and write those values.

...not quite done with this, will add more later when I have time.