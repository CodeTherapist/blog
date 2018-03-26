---
layout: post
title: "Running C# in the browser - the Blazor thing"
teaser: "description"
author: "Jürgen Gutsch"
comments: true
image: /img/cardlogo-dark.png
tags: 
- C#
- Web Assembly
- HTML5
---

One of the features of HTML5 is Web Assembly. Web Assembly offers the opportunity to run compiled code natively in the Browser. Usually Web Assemblies are written in C++. Web Assemblies should be uses, if you have high performant tasks on the client side. E. g. online games can use Web Assemblies to do 3D calculation in the background, graph libraries could use Web Assemblies to calculate the graphs to paint on Canvas elements. and so on.

Since more than a year, Steven Sanderson (Creator of Knockout.JS) played around with Web Assembly. He took the pretty small open source  .NET runtime "dotnet anywhere" and compiled it as a Web Assembly. Doing this he created a .NET runtime for the browser. Now he was able to run .NET Core assemblies in a Web Assembly in the browser. Isn't that amazing? This amazing new .NET platform was called **Blazor**.

In his demos, Steven loads an entire ASP.NET Core web application in the browser. He created something like a single page application, written in C# and Razor and ran it in the browser. This is quite cool, isn't it?

But this small runtime wasn't really complete. Especially with .NET Standard 2.0 the API grows a lot and the "dotnet anywhere" doesn't know anything about the .NET Standard. Actually is is pretty old and not really maintained and almost dead since six years.

Blazor was moved to the ASP.NET Organization on GitHub last summer and is now maintained by Microsoft, especially by the Mono team. Microsoft replaced "dotnet anywhere" by Mono. They found a way to make Mono a lot smaller for Web Assembly and to compile it as a Web Assembly. The works well.

The Mono team did a little more than just run a ASP.NET Core web app in the browser, because Xamarin Forms runs on top of mono and someone found a way to render Xamarin Forms as HTML, they got a Xamarin Forms app running in Web Assembly inside the browser. This is awesome. Xamarin Forms now has another platform to run, besides iOS, Android and MAC.

## Something feels wrong

But anyway, there is something about it that doesn't really feel good. Maybe this is, because my passion is web development, maybe there is something I don't get. I'm not sure. But it feels a little bit wrong to put a complete client application in a web assembly in the browser.

In every browser we have natively support for HTML, CSS and JavaScript. This is enough to create amazing rich browser applications, using Angular, React, Vue or whatever framework we want to use. Why should we  render ASP.NET Applications in the browser? Why should we build complete Applications using Xamarin Forms that gets rendered as HTML in the browser? I don't really get it. Sure we now can share client code between iOS, Android and Web Browser. This maybe makes sense in some special cases, but it also tastes a little bit like Silverlight.

Don't get me wrong. It is really, really cool to also use C# to write code for Web Assemblies. You can do a lot of cool things with it. You could write a API to connect to a special data source. You could move some high performant calculations in the background. If you write browser games, it could be an great way to run 3D calculations in an almost native performance. From my point of few, Web Assembly should be a possibility  to enrich browser based applications and not to render the whole client application in it.

I'm currently not sure how browsers handle Web Assemblies. Because it is a W3C standard they do it an almost similar way, but 

* Do they really handle high memory usages in the same way? 
* What about high CPU usage?
* How do they handle the life time of a Web Assembly?
* How does it work, if you close the browser?

Maybe this is specified by the W3C, but maybe it is, but the browsers will handle it differently anyway?

## What do you think?

Please tell me your opinion. Drop a comment for me and tell me what is wrong with my idea about Web Assemblies :-)

