---
layout: post
title: Ronin Roundup
---
A we enter the final stages of the Makers Academy Ronin Web Development Bootcamp. It seems appropriate to blog the process of our final project as a way for myself to document what I know will be a very fast moving process, providing a venue to analyse the day and a reflective source to come back to after the process.

These two weeks will be very important to me as the reason for joining the Ronin cohort was to develop the skills for fast prototyping of applications to keep providing our clients at work with innovative solutions to their problems. I am thoroughly looking forward to trialling this in the 'safe' environment of this learning environment.

##Amazong##

This week we have led into the final projects, starting the week with a 'Hackathon' style event whereby we selected a project as a team and then had approximatley 30 hours to turn this into a MVP. As this was the end of 'Rails' week most teams, ours included chose to use a Ruby-on-Rails stack to completed the project with.

Our app provided a facility to record a list of Amazon products and set the price you are willing to pay for them, then on returning products that have reached your budget are identified and you will be informed if the price has risen or dropped since you first added it to the list.

Introducing [Amazong!](https://github.com/RBGeomaticsRob/price-drop-app)
![Alt text](/images/amazong.png)

###High's###
- Quite simply the biggest high for me was actually realising we could take an idea from conception to a product!
- We worked well at really identifying our MVP requirments, which gave us a coherent and achieveable set of goals
- Team Dynamics, we had very little wasted time due to having a well defined Backlog of tasks to tackle.
- Agility of the process, we met back on a regular basis for code reviews reducing the risk of the app heading off the MVP course.
- Testing - Every aspect of the application was Test Driven and we are very proud to have achieved [100% Code Coverage] (https://coveralls.io/r/DanBlakeman/price-drop-app)

###Low's###
- Amazon Product API is complex and took a good few hours to understand and access data from in the end we used the very helpful Vacuum gem to assist this process.
- Selecting the technologies to use, I still feel very novice in this aspect of selecting why one technology should be selected over another.
- While our unit tests were, our feature tests were not mocked and hence were making live calls to the API.

##Makermix##

The rest of the week was spent in a challenge as all 8 members of the cohort. This presented the problem of engaging all 8 people in a remote environment which is tricky and the sprint planning meeting was drawn out but effective as we had a clear MVP by the end of it. The particular element to address in this challenge  was creating a public API and being a client of our own api to develop the front-end. This is the structure used by many companies, including Twitter, who have and intersting [blog post](https://blog.twitter.com/2010/tech-behind-new-twittercom). It is termed as [dogfooding](http://en.wikipedia.org/wiki/Eating_your_own_dog_food) as it drives companies to improve their public API's as they also consume them. 

Using this structure, it is key in the sprint planning that you have a clear definition of the routes you will be using and the objects that will be returned and received. Then it was off in front-end and back-end teams for lots of mocking and stubbing of the potential incoming / outgoing messages. We chose a MEAN stack as it was a weaker point than Rails for most of use. As part of the front-end angular team we had no problem with stubbing the unit tests as karma has access to injecting the $httpbackend service in to deal with this, however this option is not available in protractor and we tried various 'fake' servers to mock these however struggled finding one that we could get to return the correct object after a POST request, in the end we built our own mocking server using node.js for testing purposes, which was a worthwhile exercise.

###Learning Points to take into the Final Project###
- Clearly understand and define the MVP as the firsts steps in the project before any coding
- Use user stories, journeys and wireframing to drive feature testing.
- Communication is key, especially as team size expands
- Keep agile, review often and critically analyse against MVP
- Code Review often so all team members have a holistic overview of the codebase
- Have a very clear definition of the API of the app
- Use a kanban board to organise tasks to be achieved to give all on the project a good idea of what is currently happening
- Get user feedback, use a staging server a constant development version.

Bring on Monday to find out what our projects will be!

---
