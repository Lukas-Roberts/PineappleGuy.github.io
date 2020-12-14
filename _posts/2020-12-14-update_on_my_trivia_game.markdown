---
layout: post
title:      "Update on my trivia game"
date:       2020-12-14 06:03:30 +0000
permalink:  update_on_my_trivia_game
---


Since my last post I haven't done a lot of work on the game. I am doing a little work on it here and there, but I have been a little busy lately. I have some of the models made and I have 50 questions for the *Friends* trivia. I am going to share with you what I have done with the models, including some snippets of code.

The first model I made was the 'Question' model. A question belongs to a game, and a game has many questions. A 'question' is made up of a question, some possible answers and the correct answer. All questions will be multiple choice and have either 2 or 4 answers to choose from. Upon creation, I am validating to make sure a question is given along with the correct answer.
```
class Question < ApplicationRecord
    validates :question, presence: true
    validates :correct_answer, presence: true
    belongs_to :game
end
```

The next model I made was the 'User' model. A user will have many games and have many questions through games. Users will sign up with a username, an email address and a password. I validate the presence of all three.
```
class User < ApplicationRecord
    validates :username, presence: true
    validates :password, presence: true
    has_many :games
    has_many :questions, through :games
end
```

The last model I made was the 'Game' model. A game will belong to a user and have many questions. Games are created with a name, a topic and user id. I don't have any validations for this class but I will share the snippet so you can see the relationships.
```
class Game < ApplicationRecord
    belongs_to :user
    has_many :questions
end
```

I still want to add some sort of rating feature for the games. I also need to figure out how to make a friendship system but I think that is going to take a bit of time, so I don't think I am going do that part next. The next thing I am gonna work on is making some views and creating an account to see how it works. I will keep you posted.
