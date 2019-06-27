---
layout: post
title:  "Chrome Runtime for Desktop App Development"
date:   2019-06-25 18:00:00 +0800
categories: default
# https://jekyllcodex.org/without-plugin/slider/
slider:
  text_color: white
  shadow_color: black
  a1: 
    - image: /assets/chrome-runtime-2.png
      label:
    - image: /assets/chrome-runtime-3.png
      label: 
---

From an abstract point of view, the browser is equivalent to a unified entry point for web applications, and people can access all public content on the Internet through a browser. This architecture is far superior to concentrating all resources and programs into the installation package. **But it is also not perfect, and the capabilities of the browser directly limit the capabilities of web applications**. In order to increase the expressiveness of the web application, people can only constantly improve the browser. In the IE era, people tried [Java Applet](https://en.wikipedia.org/wiki/Java_applet), [ActiveX](https://en.wikipedia.org/wiki/ActiveX), etc., but in the end, they were abandoned due to security issues. Now, people are counting on the [WebAssembly](https://webassembly.org/), which is trying to add more desktop content to the Web. People make difficult choices between ability and safety. This step is extremely slow, and we need to find another way.

As the running environment of the web application, the browser provides the necessary infrastructure for the web application. Since we can't build a versatile browser, why not attach this running environment to other applications?

We modified the build script and part of the code in the [Chromium open source project](https://www.chromium.org/Home) to compile the Chromium's executable program file into a dynamic link library file. This gives it the opportunity to hosted into another program. The host program will have the full capabilities of the browser. Now, the Chromium becomes a Web Runtime.

Including the [JRE](https://en.wikipedia.org/wiki/Java_virtual_machine) and [CLR](https://en.wikipedia.org/wiki/Common_Language_Runtime), any system called runtime has a language engine and graphics capabilities. Chromium happens to have it, it has an [HTML-based interface rendering mechanism](https://www.chromium.org/blink), and also provides a [JavaScript language engine](https://v8.dev/). Since Chromium is loaded into desktop applications, it should be able to build a more powerful graphical interface using HTML and desktop technologies, and the scope of JavaScript will be expanded. We call our work **Chrome Runtime**.

![assets/chrome-runtime-1.png](assets/chrome-runtime-1.png)

Of course, we are also aware of the security issue. Security is a double-edged sword. Excessive security restrictions can reduce the software's ability, and too low-security restrictions can pose a potential threat. Chromium has many security designs, including the [Multi-Process Architecture](https://www.chromium.org/developers/design-documents/multi-process-architecture), [Site Isolation](https://www.chromium.org/Home/chromium-security/site-isolation), and the [Sandbox](https://chromium.googlesource.com/chromium/src/+/master/docs/design/sandbox.md). We put the native code in a separate process and communicate using IPC, similar to the [Native Messaging](https://developer.chrome.com/extensions/nativeMessaging).

{% if page.slider %}
  {% include slider.html slides="a1" %}
{% endif %}

In order to better describe the layout between the native interface and the web page, we started to pay attention to HTML. In the Web philosophy, everything in the Web is part of an HTML document. You can write an ```<img />``` tag to represent an image, or you can write a ```<script />``` tag to represent a piece of program logic. That being the case, why not expand its scope and treat everything on the desktop as part of HTML? We have extended the HTML model to include our custom tags. By writing custom tags in HTML, you can mix native graphical interfaces into web pages. This is a bit like [Flash](https://en.wikipedia.org/wiki/Adobe_Flash_Player), but we adapt to a wider range of desktop technologies.

![assets/chrome-runtime-1.png](assets/chrome-runtime-4.png)

More importantly, we put the native and web elements in an equal position, and no one is absolutely dominant. Instead of sticking out a small piece of space from a web page to place native elements, you can more flexibly choose to place native elements side by side with the page or let the native elements lie outside the page. You can pop up a [WinForm](https://en.wikipedia.org/wiki/Windows_Forms) window for your app by writing a specific tag on the page.

![assets/chrome-runtime-1.png](assets/chrome-runtime-5.png)

Through the above effects, I believe that some readers have realized the great potential of it. However, due to space limitations, this article can only show a small part of our work. More content will be included in subsequent articles. We also welcome comments and suggestions on our work.

Our project: [https://github.com/TangramDev/Tangram](https://github.com/TangramDev/Tangram)