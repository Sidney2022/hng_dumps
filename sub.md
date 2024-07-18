# Description
Develop a backend endpoint to handle requests for creating subscription_plan. The endpoint will accept a plan name, description, price, features. validate and sanitize the data, and then handle both successful and failed validations appropriately. If the data passes validation, they will be stored in the database and a 'success' response will be sent to the client. If validation fails, an error message will be returned.

# Acceptance Criteria
- Accepts and validates the plan name, description, price and features.
- Persist the data to the database.
- Return the appropriate response and status code
### Authentication
- The user must be signed in as a super admin to access the view endpoint.
- If a user is not authenticated as a super admin, the API should return a 401 Unauthorized error.
# Requirements
-  Implement API endpoint with data validation and sanitization
 - Set up database integration and secure storage
 - authentication as a super admin
# Expected Outcome
The user input data should be successfully sent to the backend, or the user will receive an error message. if unsuccessful,
Status code

- 201: data was successfully stored.
- 400: Invalid data.
- 401: plan name already exist.
- 500: A server error occurred.
- 
### Endpoint
[POST] /api/v1/admin/create-subscription-plan

Requests:

headers:

- content-type: application/json
```
{
    "name": "string",
    "price": "number",
    "description":" string",
    "features" : "list"
}
```

Responses:

Successful response: 
```
{
    "message": "string",
    "success": true,
    "status_code": int,
    "data" : dict
}
```
Validation Error response: 

```
{
    "message": "string",
    "success": false,
    "status_code": int,
    "data": dict
}

```
Server Error response: 
```
{
    "message": "string",
    "success": false,
    "status_code": int
}
```
Database design
schema

![Untitled](https://github.com/user-attachments/assets/9cdff051-4898-4951-ba4e-118c1de3d29c)


Testing
Unit Tests
The systems should have unit tests covering:

- [ ] Validate plan name and check for duplicate plan names.
- [ ]  Ensure every other data is in the right format/type
- [ ]  Ensure data is saved correctly to the database.
- [ ]  Test that the appropriate response and status code is returned
