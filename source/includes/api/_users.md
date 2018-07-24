# Users

## Create a new user

> To create a new user, make a POST request with the following params:

```curl
curl "http://mathalicious.com/api/v1/users"
  -X POST
  -d "user[email]=user@example.com&user[first_name]=Jane&user[last_name]=Doe"
  -H "Authorization: abcdefghijklmnop123456789"
```

> The response will include the user's ID in the Mathalicious database and their API token:

```json
  {
    "user": {
      "id": "109",
      "email": "user@example.com",
      "api_token": "P5oPo1wMBRJYH-uEsBwS"
    }
  }
```

### HTTP Request:

`POST https://mathalicious.com/api/v1/users`

### Request Parameters:

Parameter | Description | Required
--------- | ----------- | --------
user[email] | User's email address | true
user[first_name] | User's first name | true
user[last_name] | User's last name | true
user[external_id] | User's external id, string | true
user[fake_email] | Boolean defining if user's email is fake |
user[zip_code] | User's zip code |
user[school_name] | User's school |
user[school_district] | User's school district |


## User Lookup

> To see if a user exists in the system, make a GET request to this endpoint.

```curl
curl "http://mathalicious.com/api/v1/users?email=user@example.com"
  -X GET
  -H "Authorization: abcdefghijklmnop123456789"
```

```curl
curl "http://mathalicious.com/api/v1/users?external_id=12345"
  -X GET
  -H "Authorization: abcdefghijklmnop123456789"
```

> If the user exists, we return the id and user_api_token

```json
  {
    "user": {
      "id": "109",
      "email": "user@example.com",
      "access_token": "P5oPo1wMBRJYH-uEsBwS"
    }
  }
```

### HTTP Request:

`GET https://mathalicious.com/api/v1/users?email=user@example.com`

### Request Parameters:

Parameter | Description | Required
--------- | ----------- | --------
email | User's email address 
external_id | User's external_id
