
### General Info


#### The external IP of the service

Below is the external ip of the service:
`ab6db219ddfde4818b6cda0ff9e8caa1-790306849.us-east-2.elb.amazonaws.com`



### Endpoints


#### GET `/`

- a quick health check of the application
- returns 'Healthy' if it's working
- an example test: 
```
curl --request GET http://ab6db219ddfde4818b6cda0ff9e8caa1-790306849.us-east-2.elb.amazonaws.com/
```


#### POST `/auth`

- takes an email and password as json arguments
- returns a JWT based on a secret
- an example test: 
```
export TOKEN=`curl -d '{"email":"leyis_test@gmail.com","password":"test123"}' -H "Content-Type: application/json" -X POST ab6db219ddfde4818b6cda0ff9e8caa1-790306849.us-east-2.elb.amazonaws.com/auth  | jq -r '.token'`
```


#### GET `/contents`

- takes a valid JWT token
- returns the un-encrypted version of the token
- an example test:
```
curl --request GET 'ab6db219ddfde4818b6cda0ff9e8caa1-790306849.us-east-2.elb.amazonaws.com/contents' -H "Authorization: Bearer ${TOKEN}" | jq
```











