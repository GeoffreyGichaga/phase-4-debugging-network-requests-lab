# Putting it All Together: Client-Server Communication

## Learning Goals

- Understand how to communicate between client and server using fetch, and how
  the server will process the request based on the URL, HTTP verb, and request
  body
- Debug common problems that occur as part of the request-response cycle

## Introduction

Just like the last lesson, we've got code for a React frontend and Rails API
backend set up. This time though, it's up to you to use your debugging skills to
find and fix the errors!

To get the backend set up, run:

```console
$ bundle install
$ rails db:migrate db:seed
$ rails s
```

Then, in a new terminal, run the frontend:

```console
$ npm install --prefix client
$ npm start --prefix client
```

Confirm both applications are up and running by visiting
[`localhost:4000`](http://localhost:4000) and viewing the list of toys in your
React application.

## Deliverables

In this application, we have the following features:

- Display a list of all the toys
- Add a new toy when the toy form is submitted
- Update the number of likes for a toy
- Donate a toy to Goodwill (and delete it from our database)

The code is in place for all these features on our frontend, but there are some
problems with our API! We're able to display all the toys, but the other three
features are broken.

Use your debugging tools to find and fix these issues.

There are no tests for this lesson, so you'll need to do your debugging in the
browser and using the Rails server logs and `byebug`.

**Note**: You shouldn't need to modify any of the React code to get the
application working. You should only need to change the code for the Rails API.

As you work on debugging these issues, use the space in this README file to take
notes about your debugging process. Being a strong debugger is all about
developing a process, and it's helpful to document your steps as part of
developing your own process.

## Your Notes Here

- Add a new toy when the toy form is submitted

  - How I debugged:
  - Tried to add a toy got and Got a 500 server error
  - On the rails backend there was a NameError stating uninitialized constant ToysController::Toys
  - Found the Model name was pluralized and changed it to singular

- Update the number of likes for a toy

  - How I debugged:
  - I clicked th like button to check what happens 
  - When the like button is clicked a 500 sever error stating that there is an unhandled json input popups
  - I checked what was to be returned after updating and there was nothing
  - I added a return value with a status code and the like process works perfectly

- Donate a toy to Goodwill (and delete it from our database)

  - How I debugged:
  - First I clicked the donate button to get a response and there was a 404 error 
  - On the backedn there was a notification of a missing route - DELETE
  - I added the route on the resources
  - The button was able to delete each and every toy clicked
