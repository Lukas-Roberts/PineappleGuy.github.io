---
layout: post
title:      "Bootstrap is the Best!"
date:       2020-11-23 06:17:33 +0000
permalink:  bootstrap_is_the_best
---


Bootstrap is a CSS framework that allows you to format and style your webpage with ease. Bootstrap provides a lot of default styles as well as some pre-styled classes you can add to HTML elements to get a desired look.

Bootstrap is great for setting up a quick prototype and it is easy to get set up. My first experience with bootstrap was wonderful. I was used to creating my own styles, which I always found to be stressful, and it was nice not having to spend hours agonizing over basic formatting. I was able to decently style my application in what felt like a matter of minutes.

To get started, visit [www.getbootstrap.com](http://) and click on the ‘Get Started’ button. Once there, you will find instructions on how use the CDN links. Basically, all you have to is take this element:
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
```
and add it to your `<head>` tag in your html file. There are several ways to use Bootstrap, however this is the quickest way.

Once you have the link saved in your html file you can start using the pre-styled classes provided by Bootstrap. I will give you an example below of how easy it is to set up a basic navbar.
```
<nav class="navbar navbar-light bg-light">
     <a href="#" class="navbar-brand">Brand</a>
		 <ul class="navbar-nav mr-auto flex-row">
		      <li class="nav-item">
					     <a href="#" class="nav-link">Users</a>
					</li>
		 </ul>
</nav>
```
Using the code above will result in a light grey navbar at the top of the page with 'Brand' being in the top left corner in black font and 'Users' to the right of 'Brand' in dark grey font. I wanted to add an image to show you, but I can't figure out how to insert the image.

Anyway, if you haven't had a chance to use Bootstrap then I highly recommend giving it a go in your next project. Not only will it save you time styling, but it will also save you the headache of trying to figure out justify-content.

