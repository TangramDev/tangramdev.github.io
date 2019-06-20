---
layout: post
title:  "A New Way to Define Desktop Software using Web!"
date:   2019-06-19 18:00:00 +0800
categories: jekyll update
# https://jekyllcodex.org/without-plugin/slider/
slider:
  text_color: white
  shadow_color: black
  a1: 
    - image: /assets/image4.png
      label:
    - image: /assets/image5.png
      label: 
    - image: /assets/image6.png
      label: 
    - image: /assets/image7.png
      label:
  a2: 
    - image: /assets/image9.png
      label:
    - image: /assets/image8.png
      label: 
  a3: 
    - image: /assets/image1.png
      label:
    - image: /assets/image3.png
      label: 
    - image: /assets/image2.png
      label: 
---

> **Quick Links:**  
> [Visit our website](https://www.tangram.dev)  
> [Visit our Open Source project](https://github.com/TangramDev)  
> [Download demo program (A demo program based on C#)](https://github.com/TangramDev/Tangram/releases)


Welcome to a wonderful Web-Desktop Hybrid Programming World, where you will experience an extended DOM environment for developing desktop software using web-desktop hybrid technology.

This is a new and dynamic desktop software world where you can combine most of the existing component frameworks, such as .NET, Java, COM, C++, Web, and Office, etc. …

> The screenshot below is from our first C# sample program. It is included in the [ChromeApp.zip](https://github.com/TangramDev/Tangram/releases) package.

*This package contains everything you need to develop .NET apps based on Tangram. It contains a sample program chromeapp.exe and the corresponding source chromeapp.zip. Before starting development work, you need to install the appropriate installation package, tangramsetupx64.msi or tangramsetupx86.msi, depending on your application architecture.*

Now, the range of web page would be expanded. The HTML will represent more elements. The desktop environments would become part of HTML. Developers can manipulate desktop components same as a div.

In the early period, We attempt to display interface use Microsoft.NET user control or form instead of standard HTML elements.

{% if page.slider %}
  {% include slider.html slides="a1" %}
{% endif %}

This is a hybrid interface. There are both the standard web page and desktop native components. In the HTML code, you will find a segment of special HTML be used to describe the layout.

[source code]

You maybe feel it is another form of web extension (or plugin). Similar NaCl or CEF. Emmm..., Let us go further.

{% if page.slider %}
  {% include slider.html slides="a2" %}
{% endif %}

This time, we completely abandoned the traditional web page. It almost is a Microsoft.NET Winform window except for the navigation bar and title bar. The interesting point is you can still manipulate this form use HTML. You can change the layout of the user area or add a new icon to the toolbar.

It all depends on how you write your extension HTML.

[source code]

If you are a corporate IT administrator, maybe you can found a new way to distribute software.

Of course, the tab bar and navigation bar is not required. You can completely hide all the browser parts.

![assets/image10.png](assets/image10.png)

Place the tab bar inside the desktop apps.

{% if page.slider %}
  {% include slider.html slides="a3" %}
{% endif %}

We use Tangram as our codename. Tangram is an ancient oriental art. Produce greater value through the division of labor and combination. In the software world, Tangram hopes to break down the barriers between various technologies and bring more flexibility and continuity to the software.

Moreover, the browser is not our only goal. We have greater ambitions.

Our technology is in Microsoft Office.
![assets/excel.png](assets/excel.png)

Our technology is in Java/Eclipse.
![assets/eclipse.png](assets/eclipse.png)

We don't think we can fully explain our products with just a few screenshots. It is recommended that you download and experience our [demo program](https://github.com/TangramDev/Tangram/releases).
