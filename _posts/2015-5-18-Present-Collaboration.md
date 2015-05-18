---
layout: post
title: Present Collaboration
---

Project release this morning presented my group with the challenge to create an app to allow groups of people to collaboratively buy a present for a recipient, with the purchase being actioned on the last member of the group making the transaction.

##User Stories##
From the launch of the project we went straight into our first sprint planning meeting, initially our client was unavailable and hence we set about building user stories around what we knew about the project as a whole from it's initial launch at the Final Projects Jamboree.

##Client Meeting##

Mid Afternoon we were able to meet with Jordan, who is the client for the project and also happens to be the Marketing Director at [Makers Academy](www.makersacademy.com). Armed with a list of questions to further clarify the project requirements and extract and agree on an achieveable set for features, his initial overview of the project answered most of these and with a little extra conversation we walked away with a much firmer idea of the project as a whole.

##MVP##

Bouyant after the client meeting we returned to update our user stories to reflect our new knowledge of the problem. From this we were able to construct a firmer idea of the MVP roadmap that will be our nemesis challenge for the next 10 days.

##Wireframes##

Having spent a morning working as a team of 4 we realised it was time to refresh and split down into pairs, one taking a look at wireframing a user journey and the other looking at the 'Enough Design Up Front' minimal structure to shape the start of our BDD journey.

There had been a note on one of our slack boards about using [Balsamiq](https://balsamiq.com/) for wireframing, so we decided to try it out and are glad we did. It is an incredibly easy to pickup tool and actually allowed us to remotely "pair wireframe" in a driver navigator combo which was a very efficent and collaborative way to approach this. This is a process I am new too and had identified as a weak point from a previous project, I can see now how it gives you a very good picture of what you are trying to achieve and is a great step to take at the point you are unsure of the next direction to take. Some examples of our wireframing are below:

<img src="/images/WFhomepage.png" width="120px" /><img src="/images/WFsignUp.png" width="120px" /><img src="/images/WFsignedInUser.png" width="120px" /><img src="/images/WFaddGift.png" width="120px" /><img src="/images/WFgiftManagement.png" width="120px" />

##EDUF##

The other half of the team went off to look a the structure in genreal the app would require and more importantly the messages that the app would need to recieve and respond with, by default creating our API's routing structure.

At this point the two teams came back together to review each others process, a decision well made as using this process we moved forward quickly and produced a some solid decisions as both were revisited by another pair and the original pair had to explain their original reasoning which is always good for some rubber ducking of ideas.

##Technologies##

I'll talk further tomorrow of the technology stack we are going to use as we have tried to be relatively agnostic towards this until we have a really good understanding of the problem we face. However we did focus more on the technologies related to the practicalities of what we are trying to achieve essentially taking payments and recieving purchases.

The initial problem we came up against is the Amazon API's for a web app do not provide the ability to programmatically make purchases, severely restricting the ability to make automatic purchase of the gift. Speaking to our client this would be a nice to have, but it would be possible to go forward with a system that would collect money and then issue this money to one person in the group to make the purchase on the target being met.

Further research led us to a third party API [zinc.io](https://zinc.io), which after contact with them they have kindely granted us a client token to be able to work with the API for our project. This should allow us to make amazon purchases via the API from an 'escrow' account.

[Stripe](https://stripe.com/gb) will allow us to handle incoming card payments from contributors, it is a very mature and comprehensive API, which is exactly what we were looking for in handling sensitive data like card details. It also has a [PCI-level-1](https://www.pcisecuritystandards.org/) certification a data standard for purchase security.

##Backlog##

We finally moved into loading our backlog with tasks split down from our MVP Roadmap assisted by our user stories. We decided to use Trello as it gave us an easily useable solution for a kanban board, for teams working remotley from each other, like us! More to follow tomorrow on this as well. Signing off for tonight.


