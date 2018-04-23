The fastest way to create user would be to send a HTTP POST request to the back-end server via Postman.

**Steps:**

1.	Use API Development environment, in my case I am using Postman to run API operations.
2.	Send a POST Request to http://dev.recruit.com:8080/api/signup along with the following body in JSON format:
```
{
    "name": "Your Name",
    "username": "unique username",
    "email": "abc@abc.com",
    "password": "P@SSW0rD"
}
```
3.	You should be able to login with the new credentials created.
