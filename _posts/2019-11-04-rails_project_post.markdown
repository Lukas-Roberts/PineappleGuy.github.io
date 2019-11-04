---
layout: post
title:      "Rails Project Post"
date:       2019-11-04 05:42:02 +0000
permalink:  rails_project_post
---

 For my project, I made an application for maids and clients. A user can sign up, either as a maid or as a client. If you sign up as a client, you can add residences to your account. Once you have a residence on your account, you can then submit a request to have it cleaned. 
 
 The request form allows you to select from a list of maids, choose a day of the week for the cleaning to take place and select how long you would like the maid to clean. The list of maids is limited to the maids that are in the same city as you. Once a clean request has been submitted, it will show a status of "Pending" until the maid you selected either denies or approves your request. 
 
 This project was pretty tough. My account model is polymorphic and that was a journey I had never been on before. I think I have  pretty good grasp on how it works now, but boy oh boy was it an adventure.
 
```
 class Account < ApplicationRecord
    belongs_to :accountable, polymorphic: true, optional: true
    validates :username, presence: true, uniqueness: true
    validates :password, presence: true, on: :creates
    validates :email, presence: true, uniqueness: true, format: { with: URI::MailTo::EMAIL_REGEXP }
    has_secure_password
	end
	
class Client < ApplicationRecord
    has_one :account, as: :accountable
    has_many :residences
    validates :first_name, :last_name, :city, :state, presence: true
end

class Maid < ApplicationRecord
    has_one :account, as: :accountable
    has_many :schedules
    has_many :residences, through: :schedules
    validates :first_name, :last_name, :city, :state, presence: true
end
``` 

Another rough part was OmniAuth. I still have a head ache from setting that up.

All in all, this was an incredible learning experience. I learned what polymorphism is, how it works, and how to set it up in a rails application. I learned how implement login and signup capabilities from other websites, using OmniAuth. I also learned about bootstrap, had no idea that was a thing. I am excited to add this project to my portfolio and move on to the next! 
