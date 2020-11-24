# Vagrant lab

## Timings

This lab should take 60 - 90 minutes to complete

## Summary

The development team are happy to use your vagrant machine to work on. But they all need to install it on their machines and to know how it works.


The node-sample-app is already in your starter code. It's inside the app folder, please read the readme for more instructions.

## Tasks

* Create a vagrant file that creates the machine as we did in the previous lesson.

* Add to the README.md instructions that explain the steps the developer will need to go through to use this environment i.e they'll need to install vagrant and virtual box, install all the plugins and know where to put their app code.

* Swap repos with another team memeber and test theirs to make sure the instructions are clear and all the files are included.

## Bonus Task

* The goal is that the developers should be able to simply clone your repo and run "vagrant up". Can you automate the installation of the required vagrant plugins?

> NOTE: At the moment we only expect our vagrant machine to display the nginx test page. We will move on to running the app in this environment in a following lesson

## Acceptance Criteria

* Uses vagrant file
* Create VM
* host set to development.local unless your expriencing lots of bugs, then keep that line commented - add this to your documentation 

* Documentation exists as README.md file
* Documentation includes: Intro, Pre Requisits  and Intructions

* repo exists on github


------------------------------------------------------------------

# Sparta Node Sample App

## Description

This app is intended for use with the Sparta Global Devops Stream as a sample app. You can clone the repo and use it as is but no changes will be accepted on this branch. 

To use the repo within your course you should fork it.

The app is a node app with three pages.

### Homepage

``localhost:3000``

Displays a simple homepage displaying a Sparta logo and message. This page should return a 200 response.

### Blog

``localhost:3000/posts``

This page displays a logo and 100 randomly generated blog posts. The posts are generated during the seeding step.

This page and the seeding is only accessible when a database is available and the DB_HOST environment variable has been set with it's location.

### A fibonacci number generator

``localhost:3000/fibonacci/{index}``

This page has be implemented poorly on purpose to produce a slow running function. This can be used for performance testing and crash recovery testing.

The higher the fibonacci number requested the longer the request will take. A very large number can crash or block the process.


### Hackable code

``localhost:3000/hack/{code}``

There is a commented route that opens a serious security vulnerability. This should only be enabled when looking at user security and then disabled immediately afterwards

## Usage

Clone the app

```
npm install
npm start
```

You can then access the app on port 3000 at one of the urls given above.

## Tests

There is a basic test framework available that uses the Mocha/Chai framework

```
npm test
```

The test for posts will fail ( as expected ) if the database has not been correctly setup.