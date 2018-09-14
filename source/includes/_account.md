# Account


## Conceptual Overview

Account holders can fall into one of two account types, which affects the portal they use

* Account Type: **REPRESENTATIVE**
  * These are the people who initially provision the fundraiser.
  * These users work within the **fundraiser management portal**
* Account Type: **SPONSOR**
  * These are the people volunteer to oversee an individual fundraiser, they often are the parents of the sellers
  * These users work within the **participant manager portal**

## POST /account/login

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