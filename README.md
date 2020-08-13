# WR3 Faux Reddit Review
</br>

### MVP
-users can create an account
-users can login
-users can view posts
-users can upvote/downvote posts
-users can add post
-users can edit posts
-users can view their profile to see their posts and karma
</br>
*** ICE BOX ***
-users can comment on posts
-users can upvote/downvote posts
-user image
</br>

### DATABASE
-Schemas:

users
```SQL
  CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    first_name TEXT, 
    last_name TEXT,
    email VARCHAR(60),
    password TEXT, 
    users_karma_score INT
  );
```

post
```SQL
  CREATE TABLE posts (
    post_id SERIAL PRIMARY KEY,
    body text, 
    img text, 
    post_karma_score INT, 
    user_id INT REFERENCES users(user_id)
  );
```
comments
```SQL
CREATE TABLE comments (
  comment_id SERIAL PRIMARY KEY,
  body TEXT
  comment_karma_score INT,
  post_id INT REFERENCES post(post_id),
  user_id INT REFERENCES users(user_id)
);
```
#### SERVER
-Dependencies:
  -express - RESTful API
  -massive
  -dotenv
  -bcrypt
  -express-session

-File Structure:
  -Index.js
  -AuthController.js
  -PostController.js

### Front-end
-Dependencies:
  -axios
  -redux
  -react-redux
  -redux-promise-middleware
  -react-router-dom

-File Structure:
  -src/
  -App.js
  -App.css
  -reset.css
  -redux
    -store.js
    -reducer.js
-components/
  -Header.js
  -Login.js
  -Profile.js
  -FrontPage.js      
