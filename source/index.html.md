---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the SimpleFundraiser API, and glad to have you on board!

SimpleFundraiser provides a simple and powerful REST API.

All product capabilites are supported through **six core resources**:

  1. **Account**
  2. **Fundraiser**
  3. **Prize**
  4. **Prize Program**
  5. **Seller**


This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Account


## Conceptual Overview

Account holders can fall into one of two account types, which affects the portal they use

* Account Type: **REPRESENTATIVE**
  * These are the people who initially provision the fundraiser.
  * These users work within the **fundraiser management portal**
* Account Type: **SPONSOR**
  * These are the people volunteer to oversee an individual fundraiser, they often are the parents of the sellers
  * These users work within the **participant manager portal**

## /account/login

```shell
curl "http://example.com/api/account/login"
  -H "Authorization: meowmeowmeow"
```

```javascript
const fundraiserApi = require('simple-fundraiser');

const account = await fundraiserApi.account.login('username','password')
```

> The above command returns JSON structured like this:

```json
{
  "api_token": "json web token",
  "account": {
    "id": "account id",
    "account_type": "account type",
  }
}
```

This endpoint logins in an account, and returns an authentication token

### HTTP Request

`GET http://simplefundraier.com/api/account/login`

### Body Parameters

Parameter | Description
--------- | ------- 
username | Account holder's username
password | Account holder's password

<aside class="warning">
  The returned JSON web token must be used in the authorization header of any authed requests
</aside>


## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "api_token": "json web token"
  "account": {
    "id": "account id",
    "account_type": "account type",
  }
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete


# Fundraiser

## GET    /fundraiser
## POST   /fundraiser
## GET    /fundraiser/:id
## PATCH  /fundraiser/:id
## DELETE /fundraiser/:id

# Prize

## GET    /prize
## POST   /prize
## GET    /prize/:id
## PATCH  /prize/:id
## DELETE /prize/:id

# Prize Program

## GET    /prize_program
## POST   /prize_program
## GET    /prize_program/:id
## PATCH  /prize_program/:id
## DELETE /prize_program/:id

# Seller

## GET    /seller
## POST   /seller
## GET    /seller/:id
## PATCH  /seller/:id
## DELETE /seller/:id
## POST   /seller/:id/payment
