---
layout: post
title:      "An Issue I Can't Solve"
date:       2021-01-24 21:25:46 -0500
permalink:  an_bug_i_cant_solve
---


I made a *Twitter* clone for one of my projects and this week I went back to try and add to it. While looking at it, I found an issue that I fixed in a way that made it work, but it is definitely not the correct way to handle it. The issue lies in an event handler in a component that allows you to "like" another person's comment. 

I think that the cause of the issue has something to do with state, however I can't figure out how to make it work. I call a function that gets user information from the state and adds to it. The problem is that what I get back isn't the updated information, it is the original information. I solved it by running the function twice, but like I said before, that isn't the correct way to do it. 

This is what my event looks like. I know that this might not be enough information but maybe it is all you need to see to find out what I am doing wrong.

```
    handleLike = (event) => {
        event.preventDefault()
        let bleatLike = {bleat_id: event.target.value, user_id: this.props.userId}
        this.props.likeBleat(bleatLike)
        if(this.props.bleat.user_id !== this.props.userId){
            this.props.getSelectedUser(this.props.bleat.user_id)
            this.props.getSelectedUser(this.props.bleat.user_id)
        }
    }
```

I have made a post about it on stack overflow, but nobody has responded to it yet. I thought that I would post about it here and maybe someone would read this and know how to fix it. If you have an idea of what I am doing wrong, I would love to hear from you. Send me an email to g.rob92@outlook.com. 
