---
title: "Proxy setting in Java to run in Terminal"
date: 2-Dec-2020
featureImage: "/images/blog/dukejava.png"
thumbnail: "/images/blog/dukejava.png"
shareImage: "/images/blog/dukejava.png"
description: "When you are working in yoru company where you have to make your standalope app to access internet, How your app need to reach the proxy ?"
categories:
  - Java
tags:
  - proxy
  - setting
---




 Many time I use to forget how to work inside a firewall/proxy enabled environment, particularly when you using Terminal/Commandline. I use to run apps outside of the IDE some time run java class in command prompt. The app may try to connect internet or call some url etc. And you get exception of Connection timeout or socket error etc. All we need to do is make Java aware of Proxy IP and port!

When you work under a proxy and like to run your app in you have to setup the proxy setting for your Java app.

Java provides following way to work in a Proxy environment:

Proxy setup in Java provides both HTTP and HTTPs.


* **http.proxyHost** – host name/ip of the proxy
* **http.proxyPort** – port of the proxy

For HTTPs: instead of http give https as prefix

System Property:
System class having property settings, through this you can enable proxy setting through programmatically

In your java code you may give inside a static block

```java
System.setProperty("http.proxyHost", "<HOST>");
System.setProperty("http.proxyPort", "<PORT>");
```

To clear the setting use

```java
System.clearProperty("http.proxyHost");
```

Command Line:
If you don’t like to hardcode in code you can use switch for your java command also as follows

```bash
$ java -Dhttp.proxyHost=<HOST> -Dhttp.proxyPort=<PORT> HelloWebWorld
```
