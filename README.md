### Info

The app is not running anywhere currently, so it can only be accessed locally.



### Endpoints


#### GET `/`

- a quick health check of the application
- returns 'Healthy' if it's working
- an example test: 
```
curl --request GET http://localhost:8080/
```


#### POST `/auth`

- takes an email and password as json arguments
- returns a JWT based on a secret
- an example test: 
```
export TOKEN=`curl --data '{"email":"leyis_test@gmail.com","password":"test123"}' --header "Content-Type: application/json" -X POST localhost:8080/auth  | jq -r '.token'`
```
- to see the token: `echo $TOKEN`


#### GET `/contents`

- takes a valid JWT token
- returns the un-encrypted version of the token
- an example test:
```
curl --request GET 'http://localhost:8080/contents' -H "Authorization: Bearer ${TOKEN}" | jq .
```