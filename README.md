# Mailjs

A JavaScript wrapper around the [mail.tm](https://docs.mail.tm/) api.


If the request is sent correctly, `status` returns true. If it returns incorrect, the `status` will be false and the `message` in the data is also added.

# Account

## Create Account
```js
mailjs.register("user@example.com", "password")
  .then(console.log)
```

### Success result

```json
{
  "status": true,
  "data": {
    "address": "user@example.com",
    "quota": 0,
    "used": 0,
    "isDisabled": true,
    "isDeleted": true,
    "createdAt": "2021-05-18T20:19:49.630Z",
    "updatedAt": "2021-05-18T20:19:49.630Z"
  }
}
```

## Login

`mailjs.token` and `mailjs.id` can be used to access the user token and id later.

```js
mailjs.login("user@example.com", "password")
  .then(console.log)
```

### Success result

```json
{
  "status": true,
  "data": {
    "token": "[JWT TOKEN]",
    "id": "123456"
  }
}
```

## Get Account Data

```js
mailjs.me()
  .then(console.log)
```

### Success result

```json
{
  "status": true,
  "data": {
    "id": "123456",
    "address": "user@example.com",
    "quota": 0,
    "used": 0,
    "isDisabled": true,
    "isDeleted": true,
    "createdAt": "2021-05-18T20:26:11.597Z",
    "updatedAt": "2021-05-18T20:26:11.597Z"
  }
}
```

## Delete Account

```js
mailjs.deleteMe()
  .then(console.log)
```

### Success result

```json
{
  "status": true,
  "data": {}
}
```
