# Goal

Creating an Express server (don't auto-generate). Add routes based on the specs provided below. Some routes have additional requirements for features.

Test your server's routes with an application like [POSTMAN](https://www.getpostman.com/) or with the [curl](http://curl.haxx.se/docs/) command from the terminal.

## Server Specs
### Modules
- some JS server
- something to parse data that will be posted to the server
- something to handle sessions
- a templating engine

### Calulator Routes

- `/add/34/67` -> 34 + 67 = 101
  - displays the `results` template [X + Y = Z]
  - `/divide/81/9` -> 81 / 9 = 9
    - displays the `results` template [X / Y = Z]
  - same for subtract and multiply
    - `results` template is reused for each calculation route
  - Validation middleware
    - all routes must have 2 numbers. e.g. a `POST` to `/add/3/` should return a `422` status code with a message saying that another number is needed in order to run the operations.

### Root Route and Questionaire
- A generic welcome message, **"Welcome, Human"**
- Should have a form that asks for someone's name and favorite movie (or any other question you'd like)
  - form should `POST` to a route
    - this route will keep track of each person's name and their answer to the question.

  - The user's session should store the users name
    - when a user returns to the `/` route it will say 'Welcome Back, [name]'

  - There should be a route where you can find a user's answer to the question
    - For Example, **"Ray posted an answer to the question: 'what is your favorite movie' which is 'Elevator To The Gallows'"**, if you go to the route `/favorite-movie/ray/` it render a template that says, 'Ray's favorite movie is: Elevator To The Gallows'. The name after `/favorite-movie/:user/` help this route be dynamic.