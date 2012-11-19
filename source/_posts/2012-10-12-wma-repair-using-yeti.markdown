---
layout: post
title: "WMA repair using Yeti"
date: 2012-10-12 13:11
comments: true
categories:
- Yeti
- WMA
---

Figured I would put this up here, mostly for my own reference for some of the links down below.
Yeti can be grabbed from its [git repository](https://github.com/mtscout6/yeti).

{% gist 3881245 %}

As you can see this is a simple one liner. It takes in the filename and will repair it in place. 
Making a copy of the file before it's repaired might be a good idea. This method reconstructs the header information
on the WMA file so that it is in a valid state again.  This fixes issues like players not knowing the length of the file,
not being able to skip through the file, and more importantly not being able to convert the file to another format or 
splicing/combining. You can alternatively pass a stream into the method instead of a file name. The second parameter should
almost always be false. It signifies if the filepath/stream being passed in is from a broadcast.

Some notable classes would be the FileProperties
{% gist 3881775 %}

and DataProperties
{% gist 3881787 %}

These are the classes that read and write the header information for the file.
The header/section guid's from the ASF spec are in Yeti for the other areas 
but the classes that would read and write those values haven't been created.

If you want to know what those guids are for and what data they point to that information can be found in the ASF specification document found
[here](http://www.microsoft.com/en-us/download/details.aspx?id=14995).

Another tool that is incredibly helpful for figuring out what is wrong with your file is the 'Windows Media ASF Viewer'.
It can tell you any format errors that you have with the file and the structure of the data in your file. The download link
can be found [here](http://www.microsoft.com/en-us/download/details.aspx?id=12826).

I have some running examples of this here: [Yeti-Examples](https://github.com/JordanZaerr/Yeti-Examples). 
I will mention that the broken.wma file that I used is horrendous audio quality since I recorded it 
with earbuds held up to my laptop's microphone. It is just 40 seconds of the mp3 that is also in the examples.
The music is from djabacus who is a friend of mine and some of his music can be found [here on the audio tab](http://www.djabacus.net) for free.