---
layout: post
title:      "Luminous Script & The Fast JSON API  Gem"
date:       2021-03-02 20:20:53 +0000
permalink:  luminous_script_and_the_fast_json_api_gem
---


I must admit that compared to our last three modules, Javascript was the hardest for me to wrap my mind around. First, I was challenged by the changes in syntax. Then, I had a hard time figuring out how to debug with breakpoints and the chrome dev tools. Finally, literally in the last week of the curiculum things started to click. For my Javascript project, I decided to build on the examples we had used in study group to create a very simple image portfolio to showcase what I have learned. 

Welcome to Luminous Script! When my web application loads you are asked for your name. This signs you up or logs you in as a user. Each user has the ability to submit an image_url and a caption to begin the process of storing and displaying their saved images. To satisfy the CRUD requirements, I made it so that a user can perform the create, read and delete actions on each image.

In order to continue to challenge myself to grow, I also utilized the Fast JSON API gem. According to the Flatiron (2020) , "The Fast JSON API is a JSON serializer for Rails APIs. It provides a way for us to generate serializer classes for each resource object in our API that is involved in customized JSON rendering. We can use these serializer classes to define the specific attributes we want objects to share or not share, along with things like related object attributes." In laymen's terms the Fast Json API indicates how resources are called and how associated links are shared. As a result, I received beautiful hashes that outlined all of the data for each user and image. 

However, I forgot to take that into account when I created my user constructor. Interestingly enough I didn't even notice the issue until I started to work on my image class. It wasn't until after I couldn't figure out how to acess both the user_id and the username at the same time that I realized that I had an major issue with the way my constructors were set up. Upon going back to debug I realized that I needed to acccount for the layered hashes coming thru the Fast JSON API in order to have access to all of my data. So instead of this.name = user.name in my constructor, I had to change my code to this.name = user.attributes.images. It seems simple enough but it took me 4 hours, help from my professor, and a headache to figure out. I may have learned Javascript the hard way but it all payed off in the end. 

If you get a chance, check out my project at  [https://github.com/cmyerskeitt/LuminousScript].




