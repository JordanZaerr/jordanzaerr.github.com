---
layout: post
title: "Service Watcher"
date: 2012-11-16 13:40
comments: true
categories:
- Service Watcher
---

<!--Yes I know this is bad...-->
<img src="/images/ServiceWatcher/ServiceWatcher.jpg" style="float: left; margin-right: 15px;">

You can grab the code from here: 
[Service Watcher](https://github.com/JordanZaerr/ServiceWatcher)

This is a simple application that allows you to monitor the status of services on any server that you have permissions to.

You can additionally start, stop, and kill processes for services by selecting the one you want and clicking the corresponding button.

<div style="clear:both; padding-top:25px;">
The config.xml file that generated the picture above looks like this.
Make sure you edit this file before you run the solution.
{% gist 4090873 %}
</div>

You can quickly find the service short name by looking it up in the task manager on the Services tab.

{% img /images/ServiceWatcher/TaskManager.jpg %}