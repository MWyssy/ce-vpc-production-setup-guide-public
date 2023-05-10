# Cloud Network Engineer

This repository provides a scenario and task for you to go about setting up a full production ready AWS network setup.

## Scenario

It is time - you have got your first gig as a cloud engineer and the boss has tasked you with creating the production ready network for their new application.

They want you to focus on making sure the VPC, subnet, internet gateway, route tables and any NAT gateways are all ready to go!

You got this 🙌

## Requirements

These are the messages you got from the boss with some information around the type of setup they would like to see

> We need to create our production ready network setup and I need you to create it on AWS please. 

> In terms of requirements we'll need everything set in our own VPC and resillience wise it would be good to make sure that we can tolerate any of the data centres going down. Right now it doesn't have to span multiple geographic regions so something in the UK should be fine for now.

> We'll have some public services that can be accessed over the internet such as a webserver. We'll also have private services like our databases they must absolutely NOT be publicly accessible!!

> Thinking about it...the private services might still need to get out to the internet though, just to be updated or anything like that.

> Right now don't worry about making the databases or webservers etc its just the network setup for now please 🙏

> Oh and one more thing, can you write up the instructions on how you've done it - written as if you had to teach someone else how to do it.

> Oh sorry just remembered one more thing, we get audited in 2 days - if we don't get this right, we go out of business so #nopressure or anything like that


## Submission process

1. Fork this repository

2. Create a new file called INSTRUCTIONS.md

3. Document the steps you follow in order to implement the bosses requirements. Be as detailed as possible, try to pretend you are writing the instructions up for your future-self

4. Commit and push your instructions to your forked repository

5. Share your GitHub link to the repository


