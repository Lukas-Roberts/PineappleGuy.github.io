---
layout: post
title:      "Thoughts on creating a rating system?"
date:       2020-12-21 06:25:48 +0000
permalink:  thoughts_on_creating_a_rating_system
---


I am trying to create a rating system for my Maid Service project. My Maid Service project is not a live project but how it would work is that users can sign up as either a maid or a client. Once a client makes an account, they can add their home to their list of residences. From there, they can request a maid to come clean their home from a list of maids populated according to the home's city and state. 

I wanted to add a rating system because I feel like there would be a rating system for this kind of service. The only problem is that I haven't created a rating system before. I have only thought of one way to do it, but I am sure there must be a better way. 

For my system, I decided that the maids should start out with a rating of 0. Once they get their first request and finish the job the client should be able to rate them on how well they did on a scale of 1 to 5. I figured that I could keep track of the rating with 2 variables. I decided to call them: Overall Rating and Number of Ratings. Overall Rating is going to be a number that is incremented every time they get a new rating by the rated amount. Number of Ratings is being incremented by 1 with every rating. From there, I will divide Overall Rating by Number of Ratings to get the maids actual rating.

While this way is pretty simple, I feel like there has to be a better way to do it. If you're reading this and have a better idea, I would love to hear it. You can email me at garff247@gmail.com, send it with a subject of 'Better Rating System Idea.'  I look forward to hearing your ideas!
