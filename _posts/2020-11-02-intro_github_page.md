---
layout: post
title:  "Github Pages and Jekyll"
author: "Ashraf Ahmed"
---

At a first glance Github pages might seem a little magical. In order to fully understand how github pages work you need to know a little bit about the static site generator being used behind the scene. Under the hood, Github pages use a static site theme generated called Jekyll. At its core, Jekyll translates files written in either HTML or Markup languages into HTML Web Page which you can view from any web browser.  

Jekyll themes are templates which you can use to give your site a specific look and feel. There are a lot of Jekyll themes out there [https://jekyllthemes.io/](https://jekyllthemes.io/). Github only supports a fraction of those themes by default as outlined in the Supported Themes webpage. You can create your theme from scratch if you know enough about HTML, Cascading Style Sheets, and Ruby. However, you don't need to know any of that to use them.  

##Jekyll Fundamentals 
To fully become productive in github pages, there are a few Jekyll concepts that you should be familiar with. Mainly: 
- Configuration 
- Pages 
- Posts 
- Front Matter 

This post is to provide a lightweight treatment of those concepts. For more in depth information, take a look at the Jekyll walkthrough videos. 

When you first enable github pages on a given github repository, github adds a *_config.yml* file to the root of your repository. Here is an example of the config file in my portfolio: 
```
title: About Me 
description: Technology Entrepreneur, Software Architect Freelancer, Student of Statistics, Neuroscience, and Machine Learning. 
theme: jekyll-theme-minimal 
logo: [https://avatars3.githubusercontent.com/u/16357832?s=400&u=236b9145f6e5111e1c97495731168bf8117d535a&v=4]
```

Here, the title is the site's main title which would be displayed at different parts of your site based on which theme do you choose. Here, I've used the minimal theme which is one of the simplest themes out there. 
Every theme can have different configuration. Note that my configuration includes a logo field which tells the theme where to get my logo which is displayed on the left hand menu of the generated site. 

Pages are the simplest form of content you can have in a site. They can be either in HTML or Markup. Markup pages are a little more restricted because Markup languages are very inflexible. For instance, you can't include different colors words in the same paragraph if you are using a markup page but you sure can do that in HTML pages. The site theme you choose is the one in control in terms of how to layout the content within a page and which font or what text color to use. One of the advances of Jekyll is that you can include pages in either html or markup in the same site without problems. 

Jekyll was created to simplify creating blogs. In Jekyll, a Post is a special type of a page. It is exactly a blog post that includes things like a title, date, picture and body. A post page must follow certain rules in order for Jekyll to better understand your post and render it into an HTML page correctly.  
Finally, Front matter is used in order to provide metadata about your page. For instance, let's say you are using a theme that includes a top level navigation menu. You can tell Jekyll which pages to include in the navigation menu by including a block of text at the top of your page. The following is an example taken from my portfolio: 

```
--- 
layout: default 
title:  "About Me" 
--- 
```

This block tells Jekyll that the page that contain that text should be laid out in the default navigation menu and the link should be called "About Me". 
Jekyll is a very advanced, powerful, site generated with many out of the box themes to use. You don't need to be an expert in web technologies in order to create a site. The following tutorials cover Jekyll and github pages to a great length. 

- [Building static sites with Jekyll](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)
- [Building a portfolio site](https://medium.com/@jarednutt27/building-a-portfolio-site-or-github-and-jekyll-match-made-in-heaven-13139b768f54)
- [Jekyll for Portfolio Website](https://yannherklotz.com/blog/2018-07-08-jekyll-for-portfolio-website.html)

 
