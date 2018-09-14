# CRUD with Express

Hi Class,

Today we did a CRUD application using express, below is a summary of the lecture.

## Review

Q: What is a HTTP server?

* A software receive HTTP request and sends HTTP response
Q: What is a HTTP client?

* A software that sends HTTP request and receive HTTP response
* Browser
Q: What does the following code do?
```
app.get('/', (req, res) => {
  res.render('index');
});
```
* This is registering a routes, it is NOT sending a GET request
Q: What is a route?

* Verb + Path
## HTTP Method - Safe and Idempotency

* GET Safe, Idempotent
* POST Not Safe, Not Idempotent
* PUT Not Safe, Idempotent
* DELETE Not Safe, Idempotent
## Designing RESTful Routes - CRUD

As a user, I can see a list of drinks

* GET /drinks
As a user, I can create a new drink

* GET /drinks/new
* POST /drinks
As a user, I can update a existing drink

* GET /drinks/:id/edit
* PUT /drinks/:id (if PUT not available: POST /drinks/:id/update)
As a user, I can delete a existing drink

* DELETE /drinks/:id (if DELETE not available: POST /drinks/:id/delete)
## Lecture Code

https://github.com/rbao/w2d3-20180905

