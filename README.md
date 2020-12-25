## Introduction
The Yatube API is created to enable interaction with the Yatube social network at the user level through the API.

## Features
1. Getting a complete list of all posts on Yatube
2. Getting a list of posts belonging to a specific group
3. Getting a complete list of comments to all posts
4. Getting a list of comments to a specific post
5. CRUD comments and posts
6. Following/unfollowing a user

## How to use
1. Fork and clone the repository
2. Set up a virtual environment and install dependencies from requirements.txt

## Authorization
To get access to the API, create a new user in Yatube and make a POST request to /api/v1/token/ with the *username* и *password*, after which you will receive a token. When making requests, pass this token in the header as **Authorization: Bearer <token>**

## Responses
Sample POST request to /api/v1/posts:
    `{
        "text":"Chandler and I are getting married!",
    }`
    
Sample response:
    `{
        "id": 3,
        "author": "monicageller",
        "text": "Chandler and I are getting married!",
        "pub_date": "2020-12-25T10:40:32.710136Z",
        "group": null
    }`
    
Sample POST request to add a comment to the post above (id=3):
    `{
        "post": 3,
        "text": "My best friend and my sister?!",
    }`

Sample response:
    `{
        "id": 1,
        "author": "rossgeller",
        "text": "My best friend and my sister?!",
        "created": "2020-12-25T10:49:56.272056Z",
        "post": 3
    }`

[Full API specificatioh (redoc.yaml)](https://github.com/cebanauskes/api_final_yatube/blob/master/static/redoc.yaml)