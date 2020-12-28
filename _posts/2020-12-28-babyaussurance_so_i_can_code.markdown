---
layout: post
title:      "BabyAussurance So I Can Code!"
date:       2020-12-28 14:15:10 -0500
permalink:  babyaussurance_so_i_can_code
---


As a full time teacher, mom, wife and part-time software engineer student I have my hands full.  My 18 month old toddler is the size of a three year old. Literally! So while I try to divide my attention between him and the many other task on my plate, he constanly finds things to get into. Hence, every other day I log into Amazon.com to find the newest tool, gadget, or baby product that will help baby proof the house and reassure me that my little guy is safe while I work. Unfortunately alot of the reviews are more focused on how well a child likes the product or how pretty it is rather than how safe it is. This brought me to the idea behind my Rails project. Why not create a web application that specifically allows people to add and review the baby products that they own with a focus on what parents really care about safety. 

With the help of Rails generators I  created four models: users, baby products, brands, and reviews with a stretch goal of coming back to extend the brand model later. My primary focus was to meet the many requirements of the project before coming back to build the brand model out. I'm happy that I waited because I ran into many errors and had to do alot of debugging. What helped me the most was remembering that Rails is literally Sinatra on steriods. Everytime I was confused by an error, I thought back to my understanding of Sintara. 

Here are a couple of tips that helped me get back on track when I hit a bug:

* Ruby is a very easy to read and intuitive language so don't be afraid to use the documentation to try new things. 
* Build out the navi in your layouts view as you go to ensure that your web application is easy to navigate. 
* Pay attention the number of parameters that needed to be passed through with a method or you will run into errors.
* While adding your third-party authorization, if you run into errors make sure to check your validations to ensure they are not causing an issue.
* While adding your third-party authorization, you can use either the email or the third-parties uid. I found that using the email was easier. 
* There are a ton of video walkthroughs that can help you pinpoint unfamiliar errors.

Happy Coding!


