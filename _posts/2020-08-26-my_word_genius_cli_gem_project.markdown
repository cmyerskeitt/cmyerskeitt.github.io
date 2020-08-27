---
layout: post
title:      "My Word Genius CLI Gem Project"
date:       2020-08-26 21:13:43 -0400
permalink:  my_word_genius_cli_gem_project
---

Due to the COVID-19 pandemic, many students will lag behind this upcoming year. As a current 6th grade ELA teacher at a K-8 inner city school in Connecticut, I predict that grade level vocabulary will be very challenging for my incoming students. Hence, I set out to create a CLI that would pull from a Word API and streamline the process of defining and analyzing new vocabulary. My final goal being to create a quick way to access the definitions, pronunciation, syllables, and frequency of usage for English words. 

During the planning phase, I opted to use an API mostly because I didn't feel like we were given a sufficient amount of information on how to make an API call in the Learn lessons. Although I initially struggled to find an API that had both a working endpoint and would produce the desired outcome, I was luck enough to find a database of free API's on rapidapi.com. After hours of browsing, I found a Word API that when called would return a large dataset of information  based on the word passed through as a parameter. The website provided a Ruby code snippet which initially led me to believe that this project would be quick and easy. I was wrong. 

Here is where using the Learn video library, reading Slack faithfully, attending office hours, and pair programming with classmates comes in handy. I was lucky enough to be able to walk through the foundation of setting up my gem dependencies, files, and folders with my cohort lead in office hours. She showed me how to configure each file in order to make sure that they were aware of each other (here is where you will meet and struggle with require_relative). After setting up my bin file, my environment, a CLI class, a Word class, and an API class, I was ready to build out my code. However, I couldn't wrap my mind around how I was going to get from a set of blank files to a working CLI gem. To make matters worst, problems with the IDE caused me to move to a local environment right at the start of my project. Don't worry the story gets better. I promise. 

Initially the Word API required that I use Rest-Client to get the data from my API and then use JSON to parse. In order for the method to make use of the API call, I created variables to assign the necessary data to each attribute and called .new on the Word class with the attributes passed through as parameters upon instantiation. From there I used what I learned from the Music CLI and Student Scraper labs to build out my CLI class. Along the way while pair programming,  I worked through using while loops for error handling, adding comments to help leave myself little reminders, and brainstorming git commit messages every few minutes. As I got further into the project, my best friend literally became "binding.pry". Why? Because it's very important to pry into your code and to know exactly the value and location of data before you pass it around. 

My code finally seems to work.Yah! I'm done, right? No.
Refactoring and testing your code are the last major steps of building your project before wrapping up. Did you run the program all the way through? Did you test to see what happens when you put in the wrong response? Did you error handle for all nil responses? Is there any code that is redundant or unnecessary? Does each response do what you intended? Why or why not? 

Ok. I think we are finished. What do think about my first CLI project? 
Check it out [here.](https://github.com/cmyerskeitt/cmyerskeitt_cli_project)







