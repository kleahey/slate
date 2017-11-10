# Standard Response Codes

The Common App API uses the following HTTP status codes:


HTTP Status Code | Scenario | Response Body
---------- | ------- | -------
200 | Response OK
201 | Record Created
400 | POST Call made without having any data
401 | Unauthorized (i.e. Username and Password) or token is not correct
403 | Forbidden (i.e. Forbidden to access specific methods)
404 | Record Not Found
409 | Record Already Exists
422 | Validation Error
500 | Server Error
501 | Method does not exist
