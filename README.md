# Coffee Gif Browser

## Table of Contents
- [Install](#install)
- [Usage](#usage)
- [API](#api)
- [Authentication](#authentication)
- [Deployment](#deployment)
- [Known Bugs](#bugs)
- [Database Schema](#schema)

## Install

```
$ git clone https://github.com/derek1210/coffee-git-browser.git
$ cd coffee-git-browser
$ npm install
```

## Usage
To locally run the client and server, do:
```
$ npm start
```

To run just the server, do:

```
$ npm run server
```
Requests can now be sent to `localhost:8080/api`

To run just the client, do:
```
$ npm run client
```
The client will now run at `localhost:3000/`. Note that if the server is not running
users cannot log in, save gifs, etc. Fatal errors may occur as calls to `/api` cannot be made

Please see [Solutions.md](/Solutions.md) for detailed usage instructions.

## Authentication

Logins are facilitated by a `POST` request to the the `api/login` endpoint (see [docs/api.md](/docs/api.md)).
Passwords are hashed via `bcrypt` and checked against the password in the database.
Upon a successful login, two items are saved in localStorage. `isLoggedIn` is a boolean
which denotes whether or not a user is logged in. `uid` is a string which contains a logged in user's
unique identifier, which is used for facilitating saving and profile requests.

## Schema

```
{
  "_id": <ObjectId>,
  "name": <string>,
  "password" : <hashed string>,
  "email": <string>,
  "gifs": []
}
```

