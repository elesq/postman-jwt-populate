# postman-jwt-populate

Get the {{jwt_token}} from auth and into global variable

-   from /auth endpoint of an API create a test
-   the test should have the folowing code:

```
var jsonData = JSON.parse(responseBody)
tests['Access Token not empty']   = jsonData.access_token !== undefined
postman.setEnvironmentVariable("jwt_token", jsonData.access_token)
```

-   run the /auth endpoint and it will be accessible from every other endpoint that has `Authorization / JWT {{jwt_token}}` set
