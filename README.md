# jobsQueue

An application that allows users to retrieve any website's HTML

##Table of Contents
1. [Getting Set Up] (#Getting-Set-Up)
2. [Tech Stack Highlights] (#Tech-Stack)
3. [Tech Justification] (#Tech-Justification)
4. [High-Level Architecture] (#High-Level-Architecture)
5. [API Reference] (#API-Reference)


## Getting Set Up

### Application Installation

`git clone https://github.com/kmeraz/jobsQueue`

then

`npm install`

### Install the necessary npm packages globally

`npm install -g webpack`

`npm install -g nodemon`

`npm install -g mocha`

### Ensure that you have Redis and MongoDB installed

If you do not, then run:

`brew install redis`

`brew install mongodb`

### Then, run the Redis and MongoDB services

From your terminal, run:

`mongod`

`redis-server`

## Tech Stack Highlights

·[React](https://facebook.github.io/react/)
·[Node](https://nodejs.org/en/)
·[Express](http://expressjs.com/)
·[Redis](http://redis.io/)
·[MongoDB](https://www.mongodb.com/)

## Tech Justification

[React] - While the front-end is extremely lightweight, I opted to utilize React. Utilizing gZip on the server leaves the React library at only 43 kb in size. In comparison, jQuery comes in at 33 kb gZip'd. In this case, I saw the 10kb difference as being marginal and worth the scaffolding of the React application. If future requirements changed for a richer UX/UI, we would have the front-end ready to go.

[Node] - Node allowed me to quickly put together a server. As a developer, it also lessened the load by allowing me to utilize JavaScript across the stack. Furthermore, the NPM library provides an immense amount of libraries which allows for me to quickly find solutions to a problem that another developer may have already encountered and solved in the past. Essentially, we are able to leverage the power of the open-source community.

[Express] - Express is a great tool for managing everything and anything in the backend, including routes, requests, and middleware. Express allowed me quickly and effectively create a RESTful API, while keeping the MVC paradigm in mind. I am a big fan of the ease with which Express allows you to implement routing and utilize any of the vast array of npm module at our disposal.

[Redis] - Any time I am looking for speed in CRUD operations involving non-relational data, I evaluate if Redis is an appropriate solution. In this case, it most certainly was. I utilized Redis to store the key:value pairs of the jobCount (to keep a global counter of which jobID the application is at) and to hold the queue of jobs for the worker to grab and work on. Stringifying data and storing it as a value in Redis opens an endless amount of options for us as developers to incorporate optimization, speed and efficiency into our solutions.

[MongoDB] - While Redis has evolved into an option for permanent persistence of data, I decided that it would be best to keep seperation of concerns in mind. Thus, I decided to bring in MongoDB for the persistence of our long-term data (the HTML associated with a URL). MongoDB allows us to quickly spin up a non-relational database and it compliments architectures with non-relational data as its basis very well.

## High-Level Architecture
![Sorry, the schema image cannot be displayed. View it at http://i.imgur.com/LlUtAa8.jpg](http://i.imgur.com/LlUtAa8.jpg)







