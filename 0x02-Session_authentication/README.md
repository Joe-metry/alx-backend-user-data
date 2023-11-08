#Overview of session authentication:

Session authentication is a method of verifying the identity of a user during a specific session or series of interactions with a system or application. It is used to ensure that only authorized users can access sensitive information or perform certain actions.

Here are some key points about session authentication:

1. Types of session authentication: There are two main types of session authentication:

a. Stateless session authentication: In this method, the server does not maintain any information about the user's session, and each request is treated as a new session. This type of authentication is typically used for simple applications where the user's identity does not need to be verified frequently.

b. Stateful session authentication: In this method, the server maintains information about the user's session, such as their username and any other relevant details. This type of authentication is typically used for more complex applications where the user's identity needs to be verified frequently.

2. Authentication protocols: There are several authentication protocols used in session authentication, including:

a. Basic Authentication: This protocol uses plain text passwords to authenticate users. It is not recommended for use over the internet because passwords can be easily intercepted.

b. Digest Authentication: This protocol uses a password and a nonce (a number used once) to authenticate users. It is more secure than Basic Authentication because it uses encryption to protect the password.

c. OAuth: This protocol allows users to grant applications limited access to their resources without sharing their passwords. It is commonly used for authorization rather than authentication.

3. Session authentication mechanisms: There are several mechanisms used in session authentication, including:

a. Cookies: These are small text files that are stored on the user's device and contain information about their session, such as their username and any other relevant details.

b. Tokens: These are unique strings of characters that are issued to users after they have successfully authenticated. They can be used to identify the user and their session.

c. HTTP Authentication: This method uses the HTTP protocol to authenticate users. It is not as secure as other methods because the password is sent in plain text over the internet.

4. Advantages and disadvantages:

Advantages:

* Session authentication provides an additional layer of security to protect sensitive information and systems.
* It can help prevent unauthorized access and data breaches.
* It can be used to track user activity and monitor for suspicious behavior.

Disadvantages:

* Session authentication can be complex to implement and manage.
* It can be vulnerable

#Simple API

Simple HTTP API for playing with `User` model.


## Files

### `models/`

- `base.py`: base of all models of the API - handle serialization to file
- `user.py`: user model

### `api/v1`

- `app.py`: entry point of the API
- `views/index.py`: basic endpoints of the API: `/status` and `/stats`
- `views/users.py`: all users endpoints


## Setup

```
$ pip3 install -r requirements.txt
```


## Run

```
$ API_HOST=0.0.0.0 API_PORT=5000 python3 -m api.v1.app
```


## Routes

- `GET /api/v1/status`: returns the status of the API
- `GET /api/v1/stats`: returns some stats of the API
- `GET /api/v1/users`: returns the list of users
- `GET /api/v1/users/:id`: returns an user based on the ID
- `DELETE /api/v1/users/:id`: deletes an user based on the ID
- `POST /api/v1/users`: creates a new user (JSON parameters: `email`, `password`, `last_name` (optional) and `first_name` (optional))
- `PUT /api/v1/users/:id`: updates an user based on the ID (JSON parameters: `last_name` and `first_name`)
