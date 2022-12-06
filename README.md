# Jobly
Jobly is a web application that allows users to view and apply for different (fake) companies and jobs.

## Description
This is the back-end API for the Springboard Jobly project, created with Express, Node, and PostgreSQL. For the front-end application, [see here](https://github.com/kevban/jobly-frontend)

## Authentication
In the request header, include your json web token for your account to access and edit your account.
## Endpoints
### `POST https://papayas-jobly-api.up.railway.app/auth/token` 
fetch json web token using username and password

request format
```
{
  "username": "username",
  "password": "password"
}
```
response format
```
{
    "token": "jwt_token"
}
```
### `POST https://papayas-jobly-api.up.railway.app/auth/register` 
create a new account

request format
```
{
  "username": "username",
  "password": "password",
  "firstName": "First",
  "lastName": "Last",
  "email": "email@mail.com"
}
```
response format
```
{
    "token": "jwt_token"
}
```
### `GET https://papayas-jobly-api.up.railway.app/jobs` 
view all available jobs

response format
```
{
    "jobs": [arr of jobs]
}
```
### `GET https://papayas-jobly-api.up.railway.app/companies` 
view all available companies

response format
```
{
    "companies": [arr of companies]
}
```
### `PATCH https://papayas-jobly-api.up.railway.app/users/:username` 
edit account information

request format
```
{
  "password": "password",
  "firstName": "First",
  "lastName": "Last",
  "email": "email@mail.com"
}
```
response format
```
{
    "user": 
      {
        "username": "username"
        "firstName": "First",
        "lastName": "Last",
        "email": "email@mail.com"
      }
}
```
### `POST https://papayas-jobly-api.up.railway.app/users/:username/jobs/:jobId` 
apply for a job

response format
```
{
    "applied": jobId
}
```
