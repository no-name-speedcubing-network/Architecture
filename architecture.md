# Project requirements

### Social network for speedcubers

###

## technical requirements 


- ##### This application must have a web interface. 

  - v1 it must be responsive on phones
  - v1 must have 2 color themes (light and )


- ##### authentication & authorization

  - v1 The user can register on the website by email.
  - v1 After basic registration, the user will receive a confirmation of the continuation of registration.
  - v1 The email must have a unique link.
  - v1 The user who goes by a link should be redirected to the profile page
  - v1 Unauthorized guests cannot view the profile and pictures of users.


- ##### profile

  - v2 The user can give or not give permission for watching his solves/solve to others
  - v1 In profile page the user can add his full name, bio, avatar, location (country & city).
  - v1 also in profile page the user can add time of solving different Rubik's cubes (pb (personal best),
  avg 5 (average of 5 solves), avg 100, avg 1000 (Only oficial WCA cubes)

- ##### posts

  - v1 The user can create posts
  - v1 Each post may have from 0 to 4 images
  - v1 Each post may have multiple tags.
  - v1 New tags may be added by authors.
  - v1 The just login user can look posts of other users via a feed of the latest posts.
  - v1 Users may like posts (and unlike as well)
  - v1 the user may share his results for one-solve/day/week by clicking button in timer section, after there will be a 
  nice card picture with users result/results
  - v1 Users can click this post with results and see all solves with scrambles for that time
  - v2 The user can simply translate every post and comment by pressing one button
  - v2 50% to 50% of posts that new user can see, is the most popular posts and the most popular posts from 
  people of your country
  - v2 The user can place link to YouTube video and another users can watch it in app

  

- ##### <p id="timer">Timer</p>

  - v1 time starts on space and stops on every key, on phones it's full touch screen
  - v1 The user may add unlimited sessions
  - v1 must include approved by community program for scrambles
  - v1 time on the timer may be shown or not shown along the solving
  - v1 solves must saving in system
  - v1/v2 session must be cached on users device 
  - v2 timer must include virtual cube
  - v2 The user can click on any solve with scramble (his or not) and watch solve (virtual cube requirement later)
  - v2/v3 Users can have virtual solving battles with another users in real time (mechanics later)
  - v2 The user may write reconstruction of his solves after he stops the timer


- ##### Also, some features for future release

  - v2 App must include page with tutorials from beginner to advanced
  - v2 App must have page with different algorithms were people can vote and add them
  - v2 Users can send request to connect, another user can accept or reject. 
  - v2 if one of users delete another from contact, connection disappears
  
#


### 1. Scalability (to 200 000 users)
  

### 2. Performance
- v2/v3 include system monitoring that will send message about low performance 
  

### 3. Fault Tolerance (99.9)
- v2/v3 include system monitoring that will send message about low performance


### 4. Availability + Partition Tolerance (AP over CP)


### 5. Security 
- common security practices 


### 6. Durability 

  

### 7. System Constraints

 - v1 must be released before 15 march
 - v1 only one developer can work on it
 - v1 before income cant use more than 15$ month
 - mustn't be scalable more to than 200 000 users (at all)
 - max. possible people at the same time 20 000 (if all traffic from timers will be on it) 

#


### API definition

###### rest api
  

### Entities and URIs

- Users ->  `/users/?user_id<user_id>`
- Profiles -> `/profiles/?user_id=<user_id>`
- Posts -> `/posts/?post_id<post_id>`
- Comments ->  `/posts/comments/?post_id<post_id>&comment_id=<comment_id>`
- Likes ->  `/posts/?post_id=<post_id>&likes` or `/posts/?comment_id=<comment_id>&likes`
- Sessions ->  `/timer/sessions/?session_id<session_id>`
- Solves -> `/time/solves/?user_id=<user_id>`


#### Resources Representation 

- user
  ```json
  {
    "id": 39523,
    "posts": 12,
    "comments_placed": 33,
    "likes_placed": 89,
    "profile_id": 43428,
    "connections": 34
  }
  ```


- profile 
  ```json
  {
    "Id": 43428,
    "user_id": 39523,
    "first_name": "Anton",
    "last_name": "Savytskyi",
    "bio": ".....",
    "location": "Ukraine, Kyiv",
    "results (also cubes models)": "table ->"
  }
  ```

- post  
  ```json
  {
    "id": 42194,
    "title": "how to become middle developer in one yer",
    "user_id": 3429,
    "topics": ["developer", "code", "money"],
    "likes": 9, 
    "body": "......"
  }
  ```

- comment 
  ```json
  {
    "id": 52, 
    "post_id": 342445, 
    "user_id": 64345,
    "body": "...."
  }
  ```

- like
  ```json
  {
    "id": 64,
    "post_id": 31213,
    "user_id": 5534,
    "comment_id": 4853256
  }
  ```
  
- Session 
  ```json
  {
    "id": 4393, 
    "user_id": 9743,
    "solve_id (many)": 3425325
  }
  ```
  

- Solve
  ```json
  {
    "id": 4342554,
    "user_id": 43252,
    "session_id": 85463,
    "scramble": "R2 F L' R' F2 B2 D2 ....",
    "time": "00:00:04:45,325",
    "reconstruction": "R L2 B' R' F B2 D' ...."
  }
  ```
  

## Technology stack

### backend
- Django REST framework
- Django ORM

### server side

### databases

### cloud providers

### testing
- pytest

### frontend
- react
- react-bootstrap