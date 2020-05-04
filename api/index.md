---
title: API Docs
color: '#d3badf'
layout: "layouts/api.pug"
---
<img src="/assets/cat.png" class="cat no-shadow"/>

This API is used to find, save, and update the spaces of signed up users. You can use it to make cool things too.

(*・_・)⊃══✫⌒*･ﾟ✲

[[toc for route types only, sticky, horizontal]]
[rate-limits](#rate-limits)

# Authentication

Kinopio uses simple token-based authentication using your user `apiKey`. The easiest way to get your apiKey is by entering `JSON.parse(localStorage.user).apiKey` in your browser console on [kinopio.club](http://kinopio.club).

Use your apiKey in the `Authorization` header of each request.

> 🙈 Your API key carries the same privileges as your user account, so be sure to keep it secret!

(For testing, you can also use a query string (`?apiKey=`) but this is less secure and not recommended)

<a name="rate-limits"></a>
[[ // TODO Make this a bubble button? special h1 class
[[ // TODO design goal = you know what section you are in , anywhere in middle of page
# Rate Limits

The API is limited to 5 requests per second. If you exceed this rate, you will receive a 429 status code and will need to wait 30 seconds before subsequent requests will succeed.

# Routes

## Base Route

[https://api.kinopio.club](https://api.kinopio.club) is the base path for all routes

Method | Name | Description | Auth
--- | --- | --- | ---
`GET` | / | tells you if the api is online | None

## User

Users are representations of any account on Kinopio. Users are created by the server when they sign up.

Method | Name | Description | Auth
--- | --- | --- | ---
`GET` | /user/public/:userId | Get public info on a user JSON.parse(localStorage.user).id | None
`GET` | /user | Get all info on the authenticating user | apiKey in authorization header
