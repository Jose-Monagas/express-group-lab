
<body>
  <h2>Overview:</h2>
  <p>We created an instance of the app object, set up middleware, and set the view engine to jsx. Also, set the app to
    send
    mongoose to connect to our mongodb database and set up our server to listen on port 3000. We set up different
    controller functions such as getUser, createUser, deleteUser, updateUser and logUser. But for a user to be able to
    update or delete they must be authenticated and isloggedIn property being true.</p>

  <h2>Implementation:</h2>
  <p>Used mvc to structure our files. In the model directory we have a user model where we use mongoose to create a user
    schema and add validation of how our documents should be structured in mongodb. We have a routes folder in which the
    userroutes are (HTTP verbs). Each route has its own user controller functionality. routes: update, delete, and logout
    need Auth. functionality which verifies the credentials of the user against the info that exhists in the database.
    if the data matches, the user can make the request to update, delete and logout. We use tryCatch for error handling.
    Lastly, for storing our environment variables, we put them in the .env file and to make the token more secure, we
    put our 'secret' in the .env as well. Of which requires you to require the secret in models, controls and routes
    using ---require('dotenv').config()---. </p>

  <h2>Serving static files:</h2>
  <p>to serve our static file in views, we first set our app to use express.static middleware. Of which, references the
    public folder for items/pages/ etc that will be displayed on the browser. For ex: to diplay the css file found
    public folder for the css folder. ex:http://localhost:3000/css/app.css</p>

  <h2>Testing:</h2>
  <p>Used postman to manually test our routes and console more info about the made request -- like http verb, the ip, as
    well as the response time and size. Then used jest and supertest to write automated tests to ensure the
    functionality, correctness and reliability of our code. All six tests passed successfully.
  </p>
  <h2>Optimizations</h2>
  <p>when we generate a token in the middleware we set/assign token to true (which corrosponds to the id of the user).
    And then, when we make further requests we dont need to generate another token because its set to true in login.
    This is in lieu of setting the auth token to true every time. We followed DRY methodology that keeps the code
    readable and maintainable. we tested the optimization of our code by creating an artillery file and tested our
    server to handle enough throughput and it passed. Instead of hard storing the password in the code, we used bcrypt
    to hash the password making it more secure and unique.</p>
  <h2>Challenges:</h2>
  <ul>
    <li>Logout functinality</li>
    <li>Undestanding JWT</li>
    <li>Postman api calls</li>
    <li>Not knowing if delete route needed auth</li>
  </ul>
</body>

</html>
