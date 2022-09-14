+++
title = "My very first post"
tags = ["hugo", "jekyll"]
date = "2014-03-10"
+++

## This is how I create page titles, don't forget the space `space`

then I can type more here



multiple spaces dont work work


    ▾ <root>/
        ▾ images/
            logo.png
        z

test - this indenting is done with tab

    asdf


```yaml makes things look a little cooler?
params:
  CopyrightHTML: "Copyright &#xA9; 2013 John Doe. All Rights Reserved."
  TwitterUser: "spf13"
  SidebarRecentLimit: 5
  testing: 2
  icanputanythinghere: duh
```

this is how insert an image 
![image alt text](/me.jpeg) 





or I can do this
{{<figure src="/me.jpeg" title="Steve Francia" height="50" >}}

here are some more options for that

### src:
URL of the image to be displayed.

### link:
If the image needs to be hyperlinked, URL of the destination.

### target:
Optional target attribute for the URL if link parameter is set.

### rel:
Optional rel attribute for the URL if link parameter is set.

### alt:
Alternate text for the image if the image cannot be displayed.

### title:
Image title.

### caption:
Image caption. Markdown within the value of caption will be rendered.

### class:
class attribute of the HTML figure tag.

### height:
height attribute of the image.
 
 
### width:
width attribute of the image.

### attr:
Image attribution text. Markdown within the value of attr will be rendered.

### attrlink:
If the attribution text needs to be hyperlinked, URL of the destination.

Can't do math yet, see https://hyperupcall.github.io/blog/posts/render-latex-with-katex-in-hugo-blog/
$$\int_{a}^{b} x^2 dx$$


