---
layout: post
title:      "How to set up a polymorphic association"
date:       2020-12-28 05:37:51 +0000
permalink:  how_to_set_up_a_polymorphic_association
---


Polymorphic associations allow models to belong to more than one other model. They are useful in situations when your application has users of different types. I made an app where users could sign up as a maid or as a client and I used a polymorphic association to accomplish that. I am going to share some code snippets as I walk you through how I set it up.

First, I created an Account model. I needed the Account model to belong to the Maid and Client models so I set the Account model to 'belongs_to :accountable' and set polymorphic to true.
```
class Account < ApplicationRecord
    belongs_to :accountable, polymorphic: true, optional: true
end
```

From there, I created the Client and Maid models and gave them each a 'has_one :account' and set that as accountable.
```
class Client < ApplicationRecord
    has_one :account, as: :accountable
end

class Maid < ApplicationRecord
    has_one :account, as: :accountable
    has_many :schedules
    has_many :residences, through: :schedules
end
```

Setting my app up this way made it so I can give each account type different functions while also having a base set of functions available to both. I am still relatively new to polymorphic associations so if you see anything that is incorrect, feel free to reach out to me and let me know. I am also going to link the Ruby docs [here](https://guides.rubyonrails.org/association_basics.html) for more information.
