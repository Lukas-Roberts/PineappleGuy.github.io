---
layout: post
title:      "Blather - A Twitter Clone"
date:       2020-09-09 22:05:44 +0000
permalink:  blather_-_a_twitter_clone
---


I decided to make a Twitter clone for my React project. Once I started working, I began to realize how much functionality Twitter has and that it would be quite an extensive project to completely replicate Twitter, so I decided to scope down the project. I got rid of features, like hastags, and I focused more on the core functionality. Users can make bleats(tweets) and comment/like other users' bleats. Users can also follow/unfollow other users.

There were two parts that took me a while to figure out. The first was how to set up following/followers. I accomplished this through 'aliasing' my User class as FollowingUser like this, forgive me if that is the wrong term.
```
class User < ApplicationRecord
    has_many :follower_users, class_name: "FollowingUser", foreign_key: "following_id", dependent: :destroy
    has_many :following_users, foreign_key: "follower_id", dependent: :destroy
    has_many :followers, class_name: "User", through: :follower_users, foreign_key: "follower_id"
    has_many :following, class_name: "User", through: :following_users, foreign_key: "following_id"
end
```

The second part was making my ProfileContainer, Profile, and Bio components be reusable for when the current user searches for other users, and differentiate between the two.. It was a simple solution, so I won't bore you with another snippet.

I had a good time setting up how a users feed worked. I made a couple methods and I had everything looking good and working just the way I wanted. Then I realized, by creating a new user, that I had made it all under the impression that Users would already have tweets because I was using accounts that I had seeded to test everything. That was about half-way through the project, so I spent the rest of that day editing the methods and renderings to account for if a user is new and doesn't have any content. I made sure, moving forward, that I kept that in mind.

I am happy with how it all turned out, but I plan on adding more features, like notifications. I also want to add hashtags, and I'm excited to find out how they work. For now, though, I need to work on my resume and sending out some applications. Wish me luck!
